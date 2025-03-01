# Math class (1 Feb)

Created: February 3, 2025 12:13 PM

### Math Class Overview

- **Package**: `java.lang.Math`
- **All methods are static**: You don't need to create an instance of the `Math` class to use its methods.
- **Commonly used for mathematical operations**: It includes methods for basic arithmetic, trigonometry, exponents, rounding, and more.

---

### Common Methods in the `Math` Class

### 1. **Basic Arithmetic**

- `Math.abs(x)`
    
    Returns the absolute value of `x`.
    
    Example: `Math.abs(-5)` returns `5`.
    
- `Math.max(x, y)`
    
    Returns the greater of two values.
    
    Example: `Math.max(10, 20)` returns `20`.
    
- `Math.min(x, y)`
    
    Returns the smaller of two values.
    
    Example: `Math.min(10, 20)` returns `10`.
    

---

### 2. **Exponents and Logarithms**

- `Math.pow(x, y)`

Returns `x` raised to the power of `y`.

Example: `Math.pow(2, 3)` returns `8` (2³).

- `Math.sqrt(x)`
- It gives NaN in -ive values.
    
    Returns the square root of `x`.
    
    Example: `Math.sqrt(16)` returns `4`.
    
- `Math.exp(x)`
    
    Returns Euler's number (e) raised to the power of `x`.
    
    Example: `Math.exp(1)` returns `2.71828`.
    
- `Math.log(x)`
- It gives NaN in -ive values.
    
    Returns the natural logarithm (base `e`) of `x`.
    
    Example: `Math.log(Math.E)` returns `1`.
    
- `Math.log10(x)`
- It gives NaN in -ive values.

Returns the base-10 logarithm of `x`.

Example: `Math.log10(100)` returns `2`.

---

### 3. **Trigonometric Functions**

- `Math.sin(x)`
    
    Returns the sine of `x` (in radians).
    
    Example: `Math.sin(Math.PI / 2)` returns `1`.
    
- `Math.cos(x)`
    
    Returns the cosine of `x` (in radians).
    
    Example: `Math.cos(0)` returns `1`.
    
- `Math.tan(x)`
    
    Returns the tangent of `x` (in radians).
    
    Example: `Math.tan(0)` returns `0`.
    
- `Math.toRadians(x)`
    
    Converts degrees to radians.
    
    Example: `Math.toRadians(180)` returns `3.14159` (π).
    
- `Math.toDegrees(x)`
    
    Converts radians to degrees.
    
    Example: `Math.toDegrees(Math.PI)` returns `180`.
    

---

### 4. **Rounding Methods**

- `Math.round(x)`
    
    Rounds `x` to the nearest integer.
    
    Example: `Math.round(3.2)` returns 3.
    
    Example: `Math.round(3.6)` returns `4`.
    
    Example: `Math.round(3.5)` returns `4`.
    
- `Math.ceil(x)`

Returns the smallest integer greater than or equal to `x`.

Example: `Math.ceil(3.2)` returns `4`.

Example: `Math.ceil(-3.2)` returns -3.0.

- `Math.floor(x)`
    
    Returns the largest integer less than or equal to `x`.
    
    Example: `Math.floor(3.8)` returns `3`.
    

---

### 5. **Random Numbers**

- `Math.random()`
Returns a random double value between `0.0` (inclusive) and `1.0` (exclusive).
Example: `Math.random()` might return `0.12345`.

---

### 6. **Constants**

- `Math.PI`
    
    Represents the mathematical constant π (pi), approximately `3.14159`.
    
- `Math.E`
    
    Represents the mathematical constant `e`, approximately `2.71828`.
    

---

### Example Code

```java
public class MathExample {
    public static void main(String[] args) {
        // Basic Arithmetic
        System.out.println("Absolute value of -5: " + Math.abs(-5));
        System.out.println("Max of 10 and 20: " + Math.max(10, 20));
        System.out.println("Min of 10 and 20: " + Math.min(10, 20));

        // Exponents and Logarithms
        System.out.println("2^3: " + Math.pow(2, 3));
        System.out.println("Square root of 16: " + Math.sqrt(16));
        System.out.println("Log of 100 (base 10): " + Math.log10(100));

        // Trigonometric Functions
        System.out.println("Sine of π/2: " + Math.sin(Math.PI / 2));
        System.out.println("180 degrees in radians: " + Math.toRadians(180));

        // Rounding
        System.out.println("Round 3.6: " + Math.round(3.6));
        System.out.println("Ceil of 3.2: " + Math.ceil(3.2));
        System.out.println("Floor of 3.8: " + Math.floor(3.8));

        // Random Number
        System.out.println("Random number: " + Math.random());
    }
}

```

---

### Notes

1. **Static Methods**: All methods in the `Math` class are static, so you call them using `Math.methodName()`.
2. **Precision**: The `Math` class uses double-precision floating-point arithmetic, so results may have slight rounding errors.
3. **Random Numbers**: For better control over random numbers, consider using the `Random` class in `java.util`.
4. **Constants**: Use `Math.PI` and `Math.E` for precise values of π and `e`.