
                                                                                      #Object class

-> It is a class in java.lang package.
-> It is the super most class for all the classes in Java.
-> Each method in the Object class has a default behavior. If we want to change that behavior, we need to override the Object class method in our class.
-> Object class is important because of its methods there are different methods in Object class.

***Methods- 

1. equals(Object obj) – Compares two objects for equality based on their memory address (should be overridden).
2. hashCode() – Returns a hash code for the object, used in hashing-based collections (override with equals()).  [ return Objects.hash(id,name);]
3. toString() – Returns a string representation of the object (usually overridden for readability).
4. getClass() – Returns the runtime class of the object for reflection.
5. clone() – Creates and returns a copy of the object (requires implementing Cloneable).
6. finalize() – Called by the garbage collector before object destruction (deprecated in Java 9+).
7. wait() – Makes the calling thread wait until notify() or notifyAll() is called.
8. notify() – Wakes up a single thread waiting on the object's monitor.
9. notifyAll() – Wakes up all threads waiting on the object's monitor.
	
1. toString();  -> public java.lang.String toString();
                -> When we try to append an object to a String or if we try to print an object, then the toString() method will be called.
                -> If toString() method is not present in our class then the Object class toString() method will be called.
   
Default implementation - 
                         public String toString() {

                                   return getClass().getName() + "@" + Integer.toHexString(hashCode());
				}

MCQ -> Hashcode -  it is a unique identifier for the object. The hash code is an integer representation of the memory address where the object is stored.
    -> Any class that requires a custom string representation can override toString() method.
    -> It Returns the object's class name and hashcode. (Ex- Student@1fee6fc)
    -> Using String.format() or StringBuilder for better performance is the recommended way to generate a string representation of an object in a custom toString() method.

Advantage - By overriding the toString() method of the Object class, we can return values (0822CS221130 Prakash Indore) of the object, so we don't need to write much code.






2.equals(); -> public boolean equals(java.lang.Object);
            -> The object class equals() method has a default behavior that compares addresses.
Example1 -
  
 public class Person{
   int id;
   String name;
   Person(int id  ,String name) 
   {
     this.id = id;
     this.name = name;
   }
   public static void main(String[]args)
    {
      Person p1 = new person(101,"rashmika");
      Person p2 = new person(101,"rashmika");
      int i = 10;
      int j = 10;
      System.out.printl( i == j); //true
      System.out.println( p1.equals(p2) );  //false  (in this equals() of object class will be called which compare with address)
      System.out.println(p1 == p2 ); //false
    }

                       }


Example 2 - 
    public class Person{
   int id;
   String name;
   Person(int id  ,String name) 
   {
     this.id = id;
     this.name = name;
   }
   @Override
    public boolean equals(Person p)
     {
       return this.id == p.id && this.name.equals( p.name); //String class equals() method called
     }
   public static void main(String[]args)
    {
      Person p1 = new person(101,"rashmika");
      Person p2 = new person(101,"rashmika");
      System.out.println(p1.equals(p2));          //person class equals() method called
    }
                        }





3.hashCode(); ->   public native int hashCode();
              -> Hashcode -  it is a unique identifier for the object. The hash code is an "integer representation of the memory address" where the object is stored.
              -> For every object JVM generates one unique number, this number is called hashcode.
              -> In hashing-related data structure while saving the object JVM uses this hashcode.
	      -> If we want to add any object in the hash table first JVM will ask for the hashcode and then store the object.    
              -> System.out.println( p1.hashCode() );  here hashcode of object class is called.
Example - 
  public class Person{
   int id;
   String name;
   Person(int id  ,String name) 
   {
     this.id = id;
     this.name = name;
   }
    public int hasCode()
     {
       return Objects.hash(id,name); //return a unique hashCode according to id and name
     }
   public static void main(String[]args)
    {
      Person p1 = new person(101,"rashmika");
      System.out.println(p1.hashcode());          //person class hashCode() method called
    }
                        }



4.clone();  -> protected native java.lang.Object clone() throws java.lang.CloneNotSupportedException;
            -> clone() method return Object so it is compulsory to perform type casting from the Object class type to the corresponding Class type.
	    -> Suppose we have some object on which we can not perform direct action in this case we will use the concept of cloning, the main purpose here is to maintain a back-up copy.
	    -> Clone() method is a protected method in the Object class, and it is required to preserve the state of object cloning.
	    -> If we want to perform cloning of our object, then our class must be a child of the cloneable interface.
            -> Cloneable Interface 
				  - It is a marker Interface.
				  - If an interface does not contain any method then it is called a Marker Interface.
				  - Cloneable is a licensed mechanism that provides permission for cloning(shallow cloning).
  
Example  -  

    public class Cloning implements Cloneable{
        int i = 10;
        int j = 20;
   public static void main(String [] args) throws CloneNotSupportedException{
    Cloning c1 = new Cloning();
    Cloning c2  = (Cloning) c1.clone();
    c2.i = 100;
    c2.j = 200;
System.out.println("c1 data members ");
System.out.println(c1.i);//10
System.out.println(c1.j);//20
System.out.println("c2 data members ");
System.out.println(c2.i);//100
System.out.println(c2.j);//200
System.out.println("c1 data members ");
System.out.println(c1.i);//10
System.out.println(c1.j);//20
     }
                         }
