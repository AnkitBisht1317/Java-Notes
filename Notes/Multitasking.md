# MULTITASKING - 
- Excuting servral task at a time is a concept of multitasking there are 2 type of multitasking.
## 1. Process Based - 
- Ecxuting servral task at a time where each task is a seprate independent program (process) is called process baseed multitasking.
     - Example- java program at editor,listen audio song from same system and download a file from same system.
- All these task will excuted at a time and indepandent of each other hence it is process based multitasking.
- process based multitasking best suitable at OS level.

## 2. Thread Based Multitasking - 
- Excuting sevral task at a time where each task is sperate independent part of same program is called thread based multitasking, and each indepandent part is called thread.
- Whether is process based or thread based the objective of multitasking is to reduced respnes time of system and improve performance.
- The main improtant application area of multithreading are -
     - To develop multimedia graphics
     - To develop video games
     - To develop animation
     - To develop web and application server etc.
- Compared to older programming languages, developing multithreaded applications in Java is easier because Java provides built-in support for multithreading with a rich API (Thread, Runnable).

# DEFINING A THREAD - 
- Define a thread using two ways.

## 1. By Extending Thread Class - 

```java
class MyThread extends Thread {
    public void run() {
        for (int i = 1; i <= 5; i++) {
            System.out.println("Thread running: " + i);
        }
    }
    public static void main(String[] args) {
        MyThread t1 = new MyThread();
        t1.start(); 
        // Main thread continues
        for (int i = 1; i <= 5; i++) {
            System.out.println("Main thread: " + i);
        }
    }
}
```

### cases - 
#### i) Thread Scheduler - 
- It is a part of JVM
- It is resposible to scheduler thread that is, if multiple thread are waking to get chance of exution when which order thread will excuted will be decided by thread scheduler.
- We can not accept which algorithm follow by thread scheduler is vaild from JVM to JVM

#### ii) Diffrence between t.start() v/s t.run()-
- In the t.start() a new thread will be created which is responsible for excution of run method.
- But in the case of t.run() a new thread not will be created and run() method will be excuted just like a normal method call by main thread.

#### iii) Importance of thread class start() - 
- Thread class start method is responsible to register thread with thread scheduler and all other mandatory activity hence with excuted thread class start method there is no chance of start a new thread in java.

#### iv) Overloading Run Method Possible - 
- Overloading of run method is possiable but thread class start method invoked no argument run method the overoading method we call explict like a normal method class.

```java
class MyThread extends Thread {
    public void run() {
        System.out.println("Default run method (no-arg) is running...");
    }
    public void run(String message) {
        System.out.println("Overloaded run method says: " + message);
    }
    public static void main(String[] args) {
        MyThread t = new MyThread();

        t.start();
        t.run("Hello Thread!");
    }
}
```
- If you not overriding run method then thread class run method will excuted with has empty implementation hence we not any output.

#### vi) Overriding Of Start() Method() 
- If we override start method our start method will excuted just like normal method call and new thread wan't be create.

```java
class MyThread extends Thread {
    public void start() {
        System.out.println("start() method overridden - running like a normal method.");
    }
    public void run() {
        System.out.println("run() method is running in a new thread.");
    }
    public static void main(String[] args) {
        MyThread t = new MyThread();
        t.start(); // This will NOT start a new thread
    }
}
```

## 2. By Implimenting Runnable Interface - 
- We can define a thread by implementing Runnable Interface.
- Runnable interface present in java.lang package and it contain only one method (that is run() method).

```java
class MyRunnable implements Runnable {
    public void run() {
        for (int i = 1; i <= 5; i++) {
            System.out.println("Runnable thread: " + i);
        }
    }
    public static void main(String[] args) {
        MyRunnable runnable = new MyRunnable();    // Create Runnable object
        Thread t1 = new Thread(runnable);          // Wrap it in a Thread object
        t1.start();                                // Start the thread
        for (int i = 1; i <= 5; i++) {
            System.out.println("Main thread: " + i);
        }
    }
}
```

## Question -  Which is best by thread and by runnable ?
- Among to way define a thread implement runnable approach is recommanded.
In the first approach, our class must extend the Thread class, so we cannot extend any other class — which means we lose the benefit of inheritance. However, in the second approach, by implementing the Runnable interface, our class can still extend another class, so we retain the advantage of inheritance.

# Thread Name : 
- Every thread in java has same name it may default name generated by JVM or custmized name provied by programmer.
- we can gert and set Name of a thred by using following two method of thread class.
                                      public final string getName();
                                      public final void setName(String name);
```java
class MyThread extends Thread {
    public void run() {
        System.out.println("Running thread: " + Thread.currentThread().getName());
    }
}
public class ThreadNameDemo {
    public static void main(String[] args) {
        MyThread t1 = new MyThread(); // default name will be Thread-0
        MyThread t2 = new MyThread(); // default name will be Thread-1

        // Print default names
        System.out.println("Default name of t1: " + t1.getName());
        System.out.println("Default name of t2: " + t2.getName());

        // Set custom names
        t1.setName("Alpha");
        t2.setName("Beta");

        // Print custom names
        System.out.println("Custom name of t1: " + t1.getName());
        System.out.println("Custom name of t2: " + t2.getName());

        // Start threads
        t1.start();
        t2.start();
    }
}
```

# Thread Priorities :
- Every thread in java has same priorotie it may be default prioritie gentrated by JVM or custmize prioritie by programmer the vaild range of thread prioritie is 1 to 10.
- Where 1 is min priorite and 10 is max prioritie

# Prevent A Thread Exceution :
