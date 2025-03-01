#Inheritance

-> Inheritance is The mechanism of getting the data members and methods of the Base class and adding some new things in the Derived class is called Inheritance.
-> In Java one class can extend only one other class, which means it does not support Multiple Inheritance using class.
-> If we do not want to give the features of the base class to the derived class then the definition of the base class must be made as final, which means the final class can't be inheritable.
-> If we do not want to give some of the features of the base class to the child class we then make those features private.
-> Types:- 
         1) Single Inheritance - When a class is derived from a single base class then it is called single inheritance.
         2) Multilevel Inheritance  - If a class is derived from another derived class then it is called multilevel inheritance.
         3) Hierarchical Inheritance - If two classes are derived from a single class it is called Hierarchical Inheritance.
         4) Hybrid inheritance - Combination of two inheritance (Ex - Single and Hierarchical)



										


								                   #POLYMORPHISM

-> Poly means many & morphism means forms, defining one thing in many forms is called Polymorphism. 
-> There are two types of Polymorphism 1)Compile Time Polymorphism (Ex: Method Overloading)
				       2)Run Time Polymorphism (Ex: Method Overriding)

                                          1)Method Overloading

-> Writing methods with the same name by changing the signature is called Method Overloading.
-> Signature means either :
                          1. The number of parameters should be different
                          2. Types of parameters should be different
                          3. The order of parameters should be different






									**************# 2) METHOD OVERRIDING ( 4 January )***************

-> The process of redefining the base class method in the child class is called method overriding.
-> In the method overriding, the name and signature of the base and child class methods should be the same.
-> For non-static methods: The method call depends on the object, not on the reference type. This is known as runtime polymorphism or dynamic method dispatch. It means that the overridden method that gets called is determined by the actual object type at runtime.
-> For static methods: The method call depends on the reference type, not on the object. This is known as method hiding. In this case, the static method in the subclass hides the static method in the superclass, and the version of the method that gets called is determined by the reference type at compile time.

->*** Overriding Rules for return type- 
		1) In method overriding, the superclass method return type and subclass method return type must be the same if it is primitive.
		2) If the return type is derived/referenced in overriding, then the subclass overriding method can have the same class return type or the subclass return type but not the superclass name return type.
		3) Covariant Return Types:- Since Java 5, the return type of the overriding method can be a subclass of the return type declared in the superclass method. This is known as covariant return types.

-> ***  Overriding Rules for Access specifiers - 
    1 private -- within the class 
    2 default -- within the package
    3 Protected -- within the package and child class
    4 public -- entire project ( anywhere)

->*** Overriding Rules related to static keyword - In the case of the static method if the base class has a static keyword then it is compulsory to give static in the child class also.

-> If we write a static method, there will be no dynamic binding. In that case, only the base class method will be called.

-> *** In a subclass overriding method the access level should be same as the superclass or lower, but it can not be higher in security.

-> In the case of attributes there is not the concept of dynamic binding.
            
-> Dynamic Binding /Late Binding / Runtime Binding - Which method will be called if this decision is taken at run time then it is called run-time binding.







                                                                                                #ABSTRACTION (Abstract class + interface)

												#ABSTRACT CLASS (5 January )

-> In Java programming we have two types of classes - 1) Concrete class -
									-> It is a class that contains fully defined methods. 
									-> Define methods of a class are also known as implemented or concrete methods.
									-> Once the class is concrete we can create objects directly.
						      
2)Abstract class  - An abstract class is a class that contains some defined methods and some undefined methods.
                  - undefined methods of Java are also known as abstract methods.
                  - An abstract method is a method that contains only the declaration but not the body.
                  - We can not use the final keyword with the abstract class.
                  - We can not make abstract methods as a final.
                  - We can have a constructor in the abstract class.
                  - We can have instance variables in the abstract class.
                  - We can not use abstract keyword with constructors.
		  - We can extends an Abstract class in an abstract class or can implements interfaces in an abstract class but can't normal class.
                  - We can not use abstract keyword with attributes.
                  - We can not use abstract keyword with defined methods.
		  - Define the abstract method in the child class is called implementation, The implementation rule will be similar to overriding, for implementation the name and signature should be the same in both base and child.
                  - We can also write the main method in an Abstract class, which is called by JVM, and execute the inner code of the main method.

   - Drawbacks of abstract class 

		1. With the help of an abstract class we can not achieve 100% abstraction because it contains defined methods and constructors.
                2. With the help of class concept we can not achieve multiple inheritance.



                                                   

 #FINAL

 * Static final attribute=> We can initialize static final at the time of declaration or static initialization block.

* final=> is a keyword that is applicable for class attributes and methods.

* final for class => final class cannot be inherited.

* final for attribute => final attribute does not have a default value.

* we cannot change the value of the final attribute

* The final attribute can be initialized at the time of declaration, constructor, or instance initialization block.

* if we initialize the final attribute in the constructor then it is compulsory to initialize it in every constructor.
 
* final for method => final method cannot be redefined  in the child class, which means we cannot override the final method
 
* Q. Can we overload the abstract method?
* ans. Yes, we can overload the abstract methods.

 * Q. Can we overload the final method?
 * and yes
  
 * Q. Can we override the abstract method?
 * and yes
  
 * Q. Can we override the final method?
 * Ans No 
 
 * Q Can we override the static method?
 * Ans No
  
 * Q. Can we overload the static method?
 * ans. yes
  
 * Q can we use static keywords with class?
 * Ans No
 
 * Q can we define the abstract method as the final method?
 * Ans No
  
 * Q can we use abstract keywords with static keywords?
 * Ans No
  
 * Q can we use an abstract keyword with a private keyword?
 * Ans No











											#INTERFACE

-> An interface is a collection of "public static final data members and public abstract methods".
-> Interface participates in multiple inheritance.
-> We can't give the body of methods in the interface.
-> till JDK 1.7 interface contains abstract method but after 
								- JAVA 1.8 we can add default(with default keyword)  and static, methods with body in the interface.
								- JAVA 1.9 we can add a private method or private static methods with the body inside the interface.
-> Data members of the interface must only be initialized at the time of declaration.
-> We can't create the object of the interface.
-> Interfaces cannot have constructors because they cannot be instantiated directly.
-> Inheritance Sequence - The extends keyword must come before the implements keyword.
-> If we want to inherit a class in an interface it is not possible.
-> We can extends interfaces in an interface but can't implements abstract classes or an Abstract class or a normal class in an interface. 

-> Use interface - 1. Using Anonymous Classes
		   2. Using Lambda Expressions (for Functional Interfaces)
		   3. Using Concrete Implementations in other class

****** Default methods in the interface 
					- After JAVA 1.8 we can give the body of the method inside the interface with the help of the default keyword.
					- Default Method - The method by which we can write the method with the body in the interface.
					- Access specifier of a method in the interface is public.
					- We can access by implemented class object (not compulsory to override).
					- Ambiguity - If two interfaces have same method then, it is compulsory for the implemented class to override that method and call a specific parent imteface method.
					- It is not mandatory to give the body of the default method of the interface in the implements class.
					- The interface is lightweight compared to the class.
					- We can't use default and static keyword together.
 					- Object level method.


****** static methods in the interface 
					- After JAVA 1.8 we can give static methods inside the interface.
					- We can only call the static method by the help of interface name.
					- We can't override the static method of a interface if we do then it is called Method Hiding.
                                        - This static method will have the body.
					- We can also write the main method in the interface(after JDK 8), which is called by JVM, and execute the inner code of the main method.
					- We can't use default and static keyword together.
					- Class level method.
                                                                                    
****** Private methods in the interface
					- After JAVA 1.9 we can have private methods inside the interface.
					- We can give the body of this private method inside the interface.
					- This method can only be used within the interface itself.
					- We can access the content of the private method in the interface in its static and default methods.