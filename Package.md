											#PACKAGE (January 13)

-> The limitation of inheritance is that the features of the base class get inherited in the child class but within the same file.
-> But if we want to give properties of a class present in one file into a class present in another file then we use packages.
-> A package is a collection of classes, interfaces, and sub-packages.
-> If we want to give any class or interface to any number of Java programmers then such class and interfaces must be placed in a package. Hence classes and interfaces of the package will be common for any Java programmers.
-> Types of packages - there are two types of packages
							1. Predefine Packages - Predefine Packages are those that are developed by Son microsystem and supplied as Java software to deal with universal requirements.
										- Predefine packages are:
													1) java.lang.*; - this package is used to achieve language functionality. This is one of the packages that is imported to every Java program hence it is called the default package.
													2) java.io.*;   - this package is used for I/O operations(File Related).
													3) java.util.*; - this package is also known as the collection package all the collection-related classes are available inside this package.



							2. UserDefine Packages - User-defined packages are those that are developed by Java programmer and supplied as a part of their project to deal with common requirements.
                                       						- Syntax: package package_name; Example - package com.infobeans.genai; (javac -d . Project.java) here package is a keyword used to define UserDefine Package.

***Rules for creating packages -1. The access specifier of the class and interface must be public. 
				2. The specifier of the constructor of the class which is present in the package must be public.
				3. The specifier of the method present in the class must be public.

***Number of ways to refer to package - 1. Using import keyword.(ex- import p1.Test;)
				        2. By using a fully qualified name - canonical form ( ex - p1.Test t = new Test() )
				
**static import(jan 16 ) - 
		    Static import is a feature introduced in JAVA version 5 (JDK 5) that allows public static members of one package to be transferred directly into another package. (Ex- import static java.lang.System.*; )

