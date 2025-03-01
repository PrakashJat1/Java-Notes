# Multithreading

Created: February 28, 2025 11:12 AM

# Multithreading

- In Java programming, developing multithreading is very easy because API does maximum work.
- Java provides inbuilt support for multithreading.

```java
public class First  extends Thread{

    public void run(){
         for(int i = 0 ; i < 60 ;i++)
        System.out.println("t");
    }

    public static void main(String[] args) {
        
        First t = new First();
        t.start();

        for(int i = 0 ; i < 60;i++)
        System.out.println("Main");

    }
}
```

- In this example, the main thread start t thread.
- When we write t.start(), it first checks it in our class; if not found, it will check in the Thread class.
- The thread class start() method is internally called our run() method.

### Way of Creating Thread

1. extends Thread class (Disadvantage - We can’t inherit the features of another class by inheriting thread class)
2. implements Runnable interface.
- It is a functional interface present in java.lang package, it contains only one method called run() method.

### Start()

- Register the thread with the thread scheduler.
- Perform all activities.
- Call run() of our class if present; otherwise, call run() of Thread class.
- If we create a start() method in our class, then there will not be any Multithreading.

### run()

- If we are not overriding run() in our class, then thread class run() will be called, which has empty implementation, and hence, we will not get any result.

### How to stop or pause a thread execution

Different methods are used to stop or interrupt the thread execution.

1. yield() 
2. join() 
3. sleep()  

### yield()

- It is a static method in the  Thread class.
- It is used to pause a thread.
- Suppose many threads are taking more time, but the second thread wants less time to complete.
- Whenever the yield() method is executed, the current thread execution will be paused to give the chance to another thread.

### join()

- In the case of interdependency, the join() method is used.
- If a thread wants to wait until the completion of some other thread, then we use join.

### Sleep()

- sleep() is used to pause a thread for a particular time.
- If a thread doesn’t want to go for any operation, then we apply the sleep method.