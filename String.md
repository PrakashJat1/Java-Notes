*************************************************************************#String class**************************************************

->Here are the most commonly used constructors of the String class in Java: (total-9)

1. String s = new String(): Creates an empty string.

2. String s = new String(String original): Creates a new string that is a copy of the original string.

3. String s = new String(char[] value): Constructs a new string from a character array.

4. String s = new String(byte[] bytes): Constructs a new string from a byte array.

-> String class is available in Java.lang package.
-> String contains a collection of characters.
-> All the Strings will be stored in a specific region called String Pool, which has two partitions.

	1) Constant Pool - All the String literals will be stored or created in a constant pool.
				- In constant pool, first JVM will check whether is an existing object with the same content, then in that case the new object will not be created it will point to the same object.

	2) Non-Constant Pool -  If a String object is created dynamically then they are stored in Non-Constant Pool.
				- In the Non-Constant pool, when we create an object, a new object is created every time (in modification also).

-> In Java, a String is an immutable object. If we can change the content of the object, then it is called mutable.
											
-> String Creation - We can create a String in different ways.
			1)We can create a String just by assigning a group of characters to a string. It is called String Literal.
				ex - String str = "hello";

			2)We can create an Object to a String class by allocating memory using a new keyword.
				ex - String s  = new String("hello");
			

			3)Another way of creating a String is by converting the character array into a String.
				Ex - char c[] = {'A', 'B', 'C'};
					String s = new String(c);


**String Class Methods - 

1. public java.lang.String concat(java.lang.String); - this method is used to append one string to another.

2. public int length(); - this method is used to find the number of characters in the String.

3. public char charAt(int); - this method is used to get the character from a specific index.

4. public int compareTo(java.lang.Object); - This method will compare two strings and return the Unicode difference of the first mismatched character.

5. public int compareToIgnoreCase(java.lang.String);  - This will compare two Strings where the case will be ignored.

6. public boolean equals(java.lang.Object);- It is used to compare two strings by their content and return Boolean.

7. public boolean equalsIgnoreCase(java.lang.String); - It is used to compare two strings where the case will be ignored by return Boolean.

8.  public boolean startsWith(java.lang.String); - It will return true if our string starts with a given String.

9.  public boolean startsWith(java.lang.String, int); - The startsWith(String prefix, int toffset) method in Java is used to check if the specified substring (prefix) occurs at the specified index (toffset) of the given string. It returns a boolean value: true if the substring starts at the specified index, and false otherwise.

10.  public boolean endsWith(java.lang.String); - Test the ending of the String.

11. public int indexOf(java.lang.String); -  Provide index of particular string or character.
   
         public int indexOf(int);
         public int indexOf(int, int);
         public int indexOf(int, int, int);
	 public int indexOf(java.lang.String, int from);
         public int indexOf(java.lang.String, int from , int to);

**********NOTE - If not present then give -1.

12.  public int lastIndexOf(java.lang.String); - this method will provide the last occurrence of a String or character.

	public int lastIndexOf(int);
  	public int lastIndexOf(int, int);
	public int lastIndexOf(java.lang.String, int);
  	static int lastIndexOf(byte[], byte, int, java.lang.String, int);

13. public java.lang.String toUpperCase(); - convert String to Uppercase.

	public java.lang.String toUpperCase(java.util.Locale);


14. public java.lang.String toLowerCase(); - convert String to lowercase.

	public java.lang.String toLowerCase(java.util.Locale);


*********Java String Enhancements (Short Summary)
Java 8–11 introduced utility methods like join() for joining strings, isBlank() for checking empty or whitespace-only strings, strip() for Unicode-aware trimming, and repeat() for repeating a string multiple times.
Java 13–15 introduced Text Blocks ("""), allowing multi-line strings without needing escape sequences or \n.
Java 17+ added formatted(), a shorthand for String.format(), and String Templates (STR."Hello, {name}!") in Java 21, making string interpolation cleaner and safer.


HW - 	1) 20 methods of String
	2) Array of String
	3) WAP to check whether our string contains uppercase letters or not
	4) WAP to check whether our string contains lowercase letters or not
	5) WAP to check whether our string contains special characters or not







***************************************3:00 PM 1/22/2025 String Buffer****************************************************** 

there are total 4 constructors available in the StringBuffer class in Java, along with their parameter types:

1. StringBuffer s =  new StringBuffer(): Constructs a StringBuffer with an initial capacity of 16 characters.

2. StringBuffer s = new StringBuffer(int capacity): Constructs a StringBuffer with the specified initial capacity.

3. StringBuffer s = new StringBuffer(String str): Constructs a StringBuffer initialized to the contents of the specified string.

4. StringBuffer s = new StringBuffer(CharSequence seq): Constructs a StringBuffer that contains the same characters as the specified CharSequence.

-> To overcome the problem of string class string buffer class is introduced, which represents strings in such a way that their data can be modified. 
-> It is mutable. 
-> The methods that directly manipulate the data of the object are not available in the string class but such methods are available in the string buffer class.
-> The default capacity of a StringBuffer in Java is 16 characters.

StringBuffer str = new StringBuffer("abc");

methods of StringBuffer Class =>
1. append()
The append() method is used to add text to the end of the current StringBuffer object. This method can append a variety of data types, such as strings, characters, numbers, and even objects.

2. insert()
The insert() method inserts a string or other data type into the StringBuffer at the specified index. The index is 0-based.

3. replace()
The replace() method replaces a sequence of characters in the StringBuffer with the specified string. The replacement starts at the start index and ends before the end index.

4. delete()
The delete() method removes characters from the StringBuffer starting from the start index up to, but not including, the end index

5. reverse()
The reverse() method reverses the characters in the StringBuffer.

6. capacity()
The capacity() method returns the current capacity of the StringBuffer. The capacity is the amount of storage available for new characters before internal reallocation is needed.

7. length()
The length() method returns the number of characters in the StringBuffer.

8. setCharAt()
The setCharAt() method sets the character at the specified index. The index must be valid (within the range of the current string length).

Additional Methods:-   substring(): Extracts a part of the string.
			indexOf(): Returns the index of the first occurrence of the specified substring.
			charAt(): Returns the character at the specified index.
			ensureCapacity(): Ensures that the capacity is at least equal to the specified minimum.



append(String str) - returns StringBuffer

append(char c) - returns StringBuffer

append(char[] str) - returns StringBuffer

append(int i) - returns StringBuffer

append(Object obj) - returns StringBuffer

capacity() - returns int

charAt(int index) - returns char

delete(int start, int end) - returns StringBuffer

deleteCharAt(int index) - returns StringBuffer

ensureCapacity(int minimumCapacity) - returns void

equals(Object obj) - returns boolean

getChars(int srcBegin, int srcEnd, char[] dst, int dstBegin) - returns void

indexOf(String str) - returns int

insert(int offset, char c) - returns StringBuffer

insert(int offset, boolean b) - returns StringBuffer

insert(int offset, char[] str) - returns StringBuffer

lastIndexOf(String str) - returns int

length() - returns int

replace(int start, int end, String str) - returns StringBuffer

reverse() - returns StringBuffer

setCharAt(int index, char ch) - returns void

setLength(int newLength) - returns void

substring(int start) - returns String

substring(int start, int end) - returns String

toString() - returns String

trimToSize() - returns void






*****************************************2:59 PM 1/22/2025  StringBuilder  ****************************************

there are total 4 constructors:- 

1. StringBuilder sb = new StringBuilder(): Constructs a StringBuilder with an initial capacity of 16 characters.

1. StringBuilder sb = new StringBuilder(int capacity): Constructs a StringBuilder with the specified capacity.

1. StringBuilder sb = new StringBuilder(String str): Constructs a StringBuilder initialized to the contents of the specified string.

1. StringBuilder sb = new StringBuilder(CharSequence seq): Constructs a StringBuilder that contains the same characters as the specified CharSequence.

 => It is similar to the string buffer class its object is also mutable. The StringBuffer class is synchronized but the StringBuilder class is not synchronized.

-> Methods - Same as Stringbuffer

					


