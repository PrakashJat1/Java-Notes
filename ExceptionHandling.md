

								

									

										#EXACEPTION HANDLING

Java.lang.Throwable -> It is the super class for all the exceptions and this class is used to decide what type of exception has occurred.
bg 

Throwable
├──  Error (Asynchronous)
│   ├── VirtualMachineError
│   │   ├── StackOverflowError
│   │   ├── OutOfMemoryError
│   │   ├── InternalError
│   ├── LinkageError
│   │   ├── NoClassDefFoundError
│   │   ├── UnsatisfiedLinkError
│   └── AssertionError
└── Exception (synchronous)
    ├── Checked Exceptions
    │   ├── IOException
    │   │   ├── FileNotFoundException
    │   │   ├── EOFException
    │   ├── SQLException
    │   ├── ClassNotFoundException
    │   ├── InterruptedException
    └── Unchecked Exceptions (RuntimeException)
        ├── NullPointerException
        ├── ArrayIndexOutOfBoundsException
        ├── StringIndexOutOfBoundsException
        ├── ArithmeticException
        ├── IllegalArgumentException
        │   └── NumberFormatException
        ├── ClassCastException
        ├── IllegalStateException
        ├── ConcurrentModificationException
        └── UnsupportedOperationException

->There are many types of error
                                                         1. syntax errors => are those that occur due to less knowledge of the language 

                                                         2. logical errors => arise due to wrong logic or formula 

                                                         3. runtime errors(Exception) => occur if users enter invalid input to the program. Because of invalid input, we get some unknown messages known as system-generated messages of error. 
                                                                           	      -> Languages like Java provide mechanisms to handle this type of error.
                                                                                      -> In the Java program, "runtime errors are known as exceptions". Exceptions always provide system error messages. 
                                                                                      -> If an exception occurs in Java then the program execution is abnormally terminated with the generation of a system error message.


Exception:- In Java, an exception is an event that occurs during the execution of a program, that disrupts the normal flow of instructions. 
            -> These exceptions can occur for various reasons, such as invalid user input, File not found, or division by zero. 
            -> When an exception occurs, it is typically represented by an object of a subclass of the java.lang.Exception class.

Exception Handling => Exception handling is the process of converting system error messages into user-friendly messages.
                   -> It is a mechanism to handle runtime errors such as ClassNotFoundException, IOException, SQLException, RemoteException, etc.
                  

**********Types of exceptions => There are two types of exceptions. 
1. predefined exceptions(built-in)=> These are those exceptions that are developed by the sun microsystem and supplied as a part of JDK to deal with universal problems. 
                                  -> Ex-  ArrayIndexOutOfBoudException, ArithmeticExceptions etc.

         Types of predefined exceptions => There are two types of predefined exceptions.
                 (i) Asynchronous exceptions(Error) => These are those exceptions that deal with h/w problems and external problems like power failure, motherboard failure, memory problems, etc

                                       *Note => These are not used because Sun Microsystem has not released any API for asynchronous exceptions. They have given one base class for java.lang.error; 

 
                 (ii) Synchronous exceptions(Exception) => those that deal with programmatic runtime errors these are again classified into two types.
 
	 1. Checked exception => These are subclasses of java.lang.Exception; 
			      - These are called checked because the compiler can check these exceptions at compile time only. 
                              - Ex- IOException, ClassNotFoundException, etc. 	   
			      - We can say that checked exceptions are those that can be predictable, and hence their handling mechanism is necessary.	
                              - It is compulsory to handle the Checked Exceptions.

	2. Unchecked exceptions => are those which are subclasses of java.lang.RuntimeException 
				 - These are not checked by the compiler because they occurred during runtime.
                                 - It is not mandatory to handle the Unchecked Exceptions. 
 

2. User-defined exceptions => These are those exceptions that are developed by Java programmers and supplied as a part of their projects to deal with their problems. 
                                - Ex- trying to enter salary as char for an employee, entering a human age as 500 or less than 0.
				- With the help of throw keyword we can generate user-defined exceptions also.
				- Whenever we want to throw a defined exception then the corresponding class must be the child of RuntimeException.
                                - While making user-defined exceptions our class should be the child of RuntimeException class. 
				- We are making our class as a child of RuntimException because it is a pure unchecked exception. here we need not perform Ducking because the process of auto ducking is available in the case of uncheckedExceptions.

Example - Age checker (Exception generator)

		import java.util.*
		import java.io.*;
		
		public class InvalidAge extends RuntimeException{

                        InvalidAge(String str)
			{
                          super(str);
			}

                      
                        public static void main(String [] args)
			{
			  Scanner sc = new Scanner(System.in);
			  System.out.println("Enter your age : ");
                          int age  = sc.nextInt();
                          if(age < 10)
                             throw new InvalidAge("wrong age");
			  else
			     System.out.println("Valid Age");
			     
			}

			}



Example 1.1 (Exception handling) : 

		import java.util.*
		
		public class InvalidAge extends RuntimeException{

                        InvalidAge(String str)
			{
                          super(str);
			}

                      
                        public static void main(String [] args)
			{
			  Scanner sc = new Scanner(System.in);
			  System.out.println("Enter your age : ");
                          int age  = sc.nextInt();

                          if(age < 10)
                           try{
                             throw new InvalidAge("wrong age");
			      }
			   catch(InvalidAge ia)
			      {
                             System.out.println("handling Done");
			      }
			  else
			     System.out.println("Valid Age");
			
                   System.out.println("Done");     
			}
                     

			}


Example 2 -  Password Checker only one @ must be present (Exception Generate)
               
                import java.util.*
		import java.io.*;
		
		public class Atrate extends RuntimeException{

                        Atrate(String str)
			{
                          super(str);
			}

                      
                        public static void main(String [] args)
			{
			  Scanner sc = new Scanner(System.in);
			  System.out.println("Enter your age : ");
                          String pass = sc.nextLine();

                          for(int i  = 0 ; i < pass.length(); i++)
                               if( s.charAt(i) == '@')
                                  count++;

                          if(count != 1)
                             throw new Atrate("invalid password");
			  else
			     System.out.println("Valid password");
			     
			}

			}


             (Handling) :-

                import java.util.*
		import java.io.*;
		
		public class Atrate extends RuntimeException{

                        Atrate(String str)
			{
                          super(str);
			}

                      
                        public static void main(String [] args)
			{
			  Scanner sc = new Scanner(System.in);
			  System.out.println("Enter your age : ");
                          String pass = sc.nextLine();

                          for(int i  = 0 ; i < pass.length(); i++)
                               if( s.charAt(i) == '@')
                                  count++;

                          if(count != 1)
                           {
                            try{
                             throw new Atrate("invalid password");
                               }
                               catch(Atrate a)
				{
                                  System.out.println("handling done");
				}   
                            }
			  else
			     System.out.println("Valid password");
			     
			}

			}


           
                    

**Keywords related to exception handling - 
					   -> their are different keywords used in Exception Handling(try, catch, finally, throw, throws)
						1) try - it is a block in which we write the statements that can cause Run time errors during execution, whenever any exception occurs in the try block then program flow is abnormally terminated and controls come out of the try block and execute appropriate catch block.
						       - We can't write try block without catch or finally.
						       - We can write a try block without a catch block if finally is there in case of an unchecked exception.
					               - We can't write a try block without a catch block if it contains a checked exception.
						       - If there is a catch with a checked exception then at least one exception-raising statement is compulsory in the try block. (not compulsory in the case of unchecked exception)
                                                       - Automatic Resource Management (ARM) with try-with-resources Introduced in Java SE 7, the try-with-resources statement enables automatic resource management. Any resource that implements AutoCloseable can be used within this statement, ensuring that resources are closed automatically.

                                                       java
                                                       try (BufferedReader br = new BufferedReader(new FileReader("file.txt"))) {
                                                           // Use the resource
                                                       } catch (IOException e) {
                                                           // Handle exceptions
                                                       }

						2) catch - It is one of the blocks in which we write the statements that provide user-friendly error messages.
							 - catch block will be executed if an exception occurs in the try block. If at any point in time, only one catch block will be executed.
							 - A catch with a super class exception can handle sub-class exceptions also.
                                                         - Generic catch - If we give a single catch with parent class "Exception" called Generic catch.

						3)finally - this block always contains the block of statement/close the resources like- files and database.
							  - It is the last executable block in exception handling.
							  - finally block is 100% executed.
							  - Writing the finally block is optional.
							  - If an exception occurs and control jumps from try block to catch block. If we write System.exit(0); (exit() of System or Runtime class) then the code will be terminated hence this is the only case when finally block will not be executed.
			
						4)throws - It is a keyword that indicates the specific method to place the common exception method with try and catch.
							 - The process of propagation of an object from called method to calling method is called Ducking.
							 - Unchecked exceptions have Auto-Ducking.
							 - *For checked exception, there is no Auto-Ducking we need to perform the process of ducking for this purpose we will use the keyword "throws" to perform ducking.
							 - The advantage of this process is that rather than performing exception handling on a specific place we can perform the process of ducking and we can bring the exception object from the called method to the calling place. It means don't need to provide try and catch in a different method.  
							 - As we go from called place to calling place the exception of hierarchy of exception should increase but it should not decrease in order.
                                                                                Ex- FileNotFound -> IOException -> Exception

							-Related to overriding - In method overriding if both the methods from the child class and base class contain throws then as we go from the base class to the child class the child class overriding method can throw as same exception or sub-class exception but can't throw the super-class exception in the case of checked exception not for unchecked exception.
                                                                               - In the case of unchecked exceptions, the exception can be different from both overriding methods.

						5) throw - throw is a keyword used to generate or create an exception object explicitly(Custom Exception).
							- The throw keyword must be used as a part of the method body or a block.
							- With the help of throw keyword we can generate user-defined exceptions also.
				 			- Whenever we want to throw a user-defined exception then the corresponding class must be the child of RuntimeException.
                                 			- While making user-defined exceptions our class should be the child of RuntimeException class. We are making our class as a child of RuntimException because it is pure unchecked exception. here we need not to perform Ducking because the process of auto ducking is available in the case of uncheckedExceptions.





*********Number of ways to find details about unknown exceptions - 1)By using an object of java.lang.Exception  (Direct Object printing)
								   2)By using printStackTrace() - It is one of the pre-defined methods that is present in java.lang.Throwable class and it is inherited in java.lang.Exception class.
												- It displays the following details:- (i) name of the unknown exception.
																     (ii) nature of the massage.
																     (iii)line number where the exception has occurred.
												Ex - e.printStackTrace();
	
								  3)By using getMassage() - It is a pre-defined method that displays the nature of the exception.
											  - e.getMassage();


*****Rules - once control is transferred to the catch block it will never come back toward the try block.
          - We can not have any statement between try and catch block.
          - We can not have any statement between two catch blocks.
          - We can not have any statement between catch and finally block.
          - If we give a single catch with parent class "Exception" then we will not be able to give different messages. (called Generic Catch)
	  - We can have multiple catch blocks for the same try block, but those multiple catch blocks should be in ascending/increasing order of their inheritance hierarchy.
          - Multiple Exceptions in One Catch Block
Since Java SE 7, you can catch multiple exceptions in a single catch block using the pipe (|) symbol.

java
try {
    // Code that may throw exceptions
} catch (IOException | SQLException e) {
    // Handle both IO and SQL exceptions
}


****Rules related to return type - If we have a return statement in the try block as well as all the catches then we can't write any statement after that.
				 - If we have a return statement in try or catch then the return value will be from try or catch. But statements in the finally block will be executed before returning.
				 - If we have a return statement in try block as well as all the catches and in finally then always return statement of finally will be executed.
				 - If we have a return statement in the finally block then we can't write even a single statement after finally.

 

***********Common Practices
-> Don't Catch Top-Level Exceptions: Avoid catching Exception and Throwable directly.
-> Catch Specific Exceptions: Always try to catch specific exceptions.
-> Log Exceptions: Ensure that exceptions are logged and understood.
-> Resource Management: Use try-with-resources statements for managing resources.

Example
java
try {
    // Code that may throw an exception
    if (someCondition) {
        throw new MyException("Custom error message");
    }
} catch (MyException e) {
    // Handle custom exception
    System.out.println("Caught MyException: " + e.getMessage());
} catch (Exception e) {
    // Handle other exceptions
    System.out.println("Caught Exception: " + e.getMessage());
} finally {
    // Run code whether exception occurs or not
    System.out.println("Finally block executed");
}