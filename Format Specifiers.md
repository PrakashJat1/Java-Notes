# Format Specifiers

Created: February 6, 2025 7:52 PM

# Format Specifiers in Java

## Introduction

Format specifiers in Java are used with `System.out.printf()` and `String.format()` methods to format output. They allow precise control over how values are displayed, including width, precision, alignment, and data type.

## Syntax

The general syntax for format specifiers is:

```
%[flags][width][.precision]conversion-character

System.out.printf("All combined: %-+10.2f%n", value);
```

- **%** - Indicates the beginning of a format specifier.
- **flags** - Optional modifiers to control alignment, sign, etc.
- **width** - Specifies the minimum number of characters to be printed.
- **.precision** - Defines the number of decimal places for floating-point numbers.
- **conversion-character** - Determines the data type of the argument.

## List of Format Specifiers with Examples

### 1. Integer Format Specifiers

| Specifier | Description | Example |
| --- | --- | --- |
| `%d` | Decimal integer (base 10) | `System.out.printf("%d", 100);` → 100 |
| `%x` | Hexadecimal integer (lowercase) | `System.out.printf("%x", 255);` → ff |
| `%X` | Hexadecimal integer (uppercase) | `System.out.printf("%X", 255);` → FF |
| `%o` | Octal integer | `System.out.printf("%o", 255);` → 377 |

### 2. Floating-Point Format Specifiers

| Specifier | Description | Example |
| --- | --- | --- |
| `%f` | Decimal floating-point | `System.out.printf("%.2f", 3.14159);` → 3.14 |
| `%e` | Scientific notation (lowercase) | `System.out.printf("%e", 1234.56);` → 1.234560e+03 |
| `%E` | Scientific notation (uppercase) | `System.out.printf("%E", 1234.56);` → 1.234560E+03 |
| `%g` | Uses `%f` or `%e` depending on value | `System.out.printf("%g", 0.00001234);` → 1.234e-05 |
| `%G` | Uses `%f` or `%E` depending on value | `System.out.printf("%G", 12345.67);` → 12345.7 |

### 3. Character Format Specifier

| Specifier | Description | Example |
| --- | --- | --- |
| `%c` | Character | `System.out.printf("%c", 'A');` → A |

### 4. String Format Specifier

| Specifier | Description | Example |
| --- | --- | --- |
| `%s` | String | `System.out.printf("%s", "Hello");` → Hello |

### 5. Boolean Format Specifier

| Specifier | Description | Example |
| --- | --- | --- |
| `%b` | Boolean | `System.out.printf("%b", true);` → true |

### 6. Hashcode Format Specifier

| Specifier | Description | Example |
| --- | --- | --- |
| `%h` | Hash code of an object | `System.out.printf("%h", "Java".hashCode());` → varies |

## Flags in Format Specifiers

| Flag | Description | Example |
| --- | --- | --- |
| `-` | Left-align the output | `System.out.printf("%-10d", 50);` → "50        " |
| `+` | Show sign for numbers | `System.out.printf("%+d", 50);` → "+50" |
| `0` | Pad with zeros | `System.out.printf("%05d", 50);` → "00050" |

## Width and Precision

### Width and Precision

- **Width**: Specifies the minimum number of characters to be written to the output.
- **Precision**: Used with floating-point specifiers to define the number of digits after the decimal point.

Examples:

```java
public class WidthPrecisionExample {
    public static void main(String[] args) {
        double value = 123.456;

        System.out.printf("Default: %f%n", value);         // Default: 123.456000
        System.out.printf("Width 10: %10.2f%n", value);    // Width 10:     123.46
        System.out.printf("Precision 2: %.2f%n", value);   // Precision 2: 123.46
    }
}
```

### Practical Example: Printing a Table

java

```java
public class TableExample {
    public static void main(String[] args) {
        String[] headers = {"ID", "Name", "Age", "City"};
        String[][] data = {
            {"1", "John", "28", "New York"},
            {"2", "Jane", "32", "London"},
            {"3", "Tom", "25", "Tokyo"},
            {"4", "Lucy", "29", "Mumbai"}
        };

        // Print headers
        System.out.printf("%-5s %-10s %-5s %-10s%n", headers[0], headers[1], headers[2], headers[3]);
        // Print a separator line
        System.out.println("------------------------------------");

        // Print rows
        for (String[] row : data) {
            System.out.printf("%-5s %-10s %-5s %-10s%n", row[0], row[1], row[2], row[3]);
        }
    }
}
```

This code will output:

`ID    Name       Age   City      
------------------------------------
1     John       28    New York 
2     Jane       32    London   
3     Tom        25    Tokyo    
4     Lucy       29    Mumbai`

## Conclusion

Format specifiers are powerful tools in Java that allow developers to format numbers, strings, and other data types with precision. Understanding them is crucial for producing well-structured output in applications.