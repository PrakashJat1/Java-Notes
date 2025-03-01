



                                                                               #WRAPPER CLASSES


-> Wrapper classes in Java are used to convert primitive data types into objects. 
-> They belong to the java.lang package and provide utility methods for operations such as parsing, comparison, and conversion.
-> Unlike ==, which compares object references, equals() compares actual values present in all the Wrapper Classes.

-> List of Wrapper Classes in Java
Primitive Type	              Wrapper Class
byte	       	              Byte
short		              Short
int		              Integer
long		              Long
float		              Float
double		              Double
char		              Character
boolean		              Boolean

->Each wrapper class provides methods for converting values, comparing values, and performing various utility functions.

1. Common Utility Methods in All Wrapper Classes
Most wrapper classes (Byte, Short, Integer, Long, Float, Double) share these methods:

Method - 
valueOf(String s)		Converts a String to an object of the wrapper class.
valueOf(primitiveType)		Converts a primitive value to its wrapper object.
parseXxx(String s)		Converts a String to a primitive value (byte, short, int, etc.).
toString()	        	Converts an object to a String.
compare(x, y)	       		Compares two values of the same type by their content and returns -1, 0, and 1 according to comparison.
compareTo(WrapperClass obj)	Compares two wrapper objects by their content and returns -1, 0, and 1 according to comparison.
xxxValue()	        	Converts a wrapper object to its primitive type (byteValue(), intValue(), etc.).


-> Methods in Each Wrapper Class

1. Byte Class


Methods:
	byteValue(): Returns the value as a byte.
	compare(byte x, byte y): Compares two byte values.
	compareTo(Byte b): Compares this object with another Byte.
	equals(Object obj): Checks if this object equals another by their content.
	parseByte(String s): Converts a String to byte.
	parseByte(String s, int radix): Converts a String to byte with specified radix.
	toString(): Returns a string representation.
	valueOf(byte b): Returns an instance of Byte.
	valueOf(String s): Converts a String to a Byte.
	valueOf(String s, int radix): Converts a String to a Byte in a specified radix.

2. Short Class

Methods:
Similar to Byte, but works with short values.


3. Integer Class

Methods:
bitCount(int i): Returns the number of 1 bits in the binary representation.
compare(int x, int y): Compares two int values.
compareTo(Integer i): Compares this Integer with another.
decode(String nm): Converts a String to an Integer using radix detection.
getInteger(String nm): Returns an Integer for the system property.
parseInt(String s): Converts a String to int.
parseInt(String s, int radix): Converts String to int using the given radix.
toBinaryString(int i): Returns binary representation.
toHexString(int i): Returns hexadecimal representation.
toOctalString(int i): Returns octal representation.
valueOf(int i): Returns an Integer object.
valueOf(String s): Converts a String to an Integer.
valueOf(String s, int radix): Converts String to Integer with radix.


4. Long Class

Methods:
Similar to an Integer, but works with long values.


5. Float Class

Methods:
compare(float f1, float f2): Compares two float values.
compareTo(Float f): Compares this Float with another.
floatValue(): Returns the float value.
isNaN(): Checks if the value is NaN.
isInfinite(): Checks if the value is infinite.
parseFloat(String s): Converts a String to float.
toString(): Returns a String representation.
valueOf(float f): Returns a Float object.
valueOf(String s): Converts a String to Float.


6. Double Class
 
Methods:
Similar to Float, but works with double values.



7. Character Class
 
Methods:
charValue(): Returns the char value.
compare(char x, char y): Compares two char values.
compareTo(Character c): Compares this Character with another.
isDigit(char ch): Checks if the character is a digit.
isLetter(char ch): Checks if the character is a letter.
isLetterOrDigit(char ch): Checks if the character is a letter or a digit.
isLowerCase(char ch): Checks if the character is lowercase.
isUpperCase(char ch): Checks if the character is uppercase.
toLowerCase(char ch): Converts to lowercase.
toUpperCase(char ch): Converts to uppercase.
toString(): Returns a string representation.



8. Boolean Class
 
Methods:
booleanValue(): Returns the boolean value.
compare(boolean x, boolean y): Compares two boolean values.
compareTo(Boolean b): Compares this Boolean with another.
equals(Object obj): Checks equality.
parseBoolean(String s): Parses a String to boolean.
toString(): Returns a String representation.
valueOf(boolean b): Returns a Boolean object.
valueOf(String s): Converts a String to Boolean.



Example - 

public class WrapperClass {
    public static void main(String[] args) {
        
        int a  = 10;
        int a1 = 20;
        System.out.println("Reverse of "+a+" : "+(int)Integer.reverse(a));
        System.out.println("Sum : "+Integer.sum(a, a1));
        System.out.println("Max : "+Integer.max(a, a1));
        System.out.println("Min : "+Integer.min(a, a1));

        System.out.println("\nNumber System");
        System.out.println("to Binary : "+Integer.toBinaryString(a));
        System.out.println("to Octal : "+Integer.toOctalString(a));
        System.out.println("to Hexa : "+Integer.toHexString(a));

        Integer b = Integer.valueOf(a);
        Integer c = Integer.valueOf(a);
        Integer d = Integer.valueOf(a-5);
        Integer e = Integer.valueOf(a+5);
        int f = c.intValue();
        int g = d.intValue();
        int h = e.intValue();

        String s = b.toString();
        System.out.println("Object to String : "+s);
        
        int n = Integer.parseInt(s);
        System.out.println("String to primitive : "+n);

        Integer n1 = Integer.valueOf(s);
        System.out.println("String to Object  : "+n1);

        System.out.println(Integer.compare(a, f)); //0
        System.out.println(Integer.compare(a, g)); //1
        System.out.println(Integer.compare(a, h)); //-1

        System.out.println(b.compareTo(c)); // 0
        System.out.println(b.compareTo(d)); //1
        System.out.println(b.compareTo(e)); //-1
        System.out.println("Primitive : "+a);
        System.out.println("WrapperClass Object : "+a);
    }
}
