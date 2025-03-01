									#CONSTRUCTOR

 -> Constructor is a special method used to initialize data members of a class.
 -> Constructor name is the same as class name.
 -> Constructors are called automatically when the object is created.
 -> Constructor may or may not be private.
 -> We can not use abstract keywords with the constructor.
 -> There are 2 types of constructors (Default and Parameterized)  

1) Default constructors (DC): If the constructor has no parameter, it is called a default constructor. 
                 Types:- 
 		         1. (SDDC) System Define Default Constructor—If the class does not have a constructor, the system will generate a constructor called System Define Default Constructor.             Constructor.
                         2. (UDDC) User Define Default Constructor—If the user creates a constructor without any parameters, it is called a User Define Default Constructor.            

2) Parameterized Constructor (PC): A constructor with a parameter is called a parameterized constructor. This constructor receives values while creating objects.

2.1) Object Parameterized Constructor(Copy Constructor) -> An object parameterized constructor receives an object as a parameter and is used to copy the values of one object to another object (points Different Memory Address).
				




										#CONSTRUCTOR CHAINING AND INITIALIZATION BLOCK

-> ****Whenever we return from the superclass for the first time, all the Instance Initialization Blocks of the child class will be executed.
