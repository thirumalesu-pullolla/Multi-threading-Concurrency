
## ✅ Ways to Create a Thread

```java
1. Extending Thread Class

class MyThread extends Thread {
    public void run() {
        System.out.println("Thread is running");
    }
}

public class Main {
    public static void main(String[] args) {
        MyThread t = new MyThread();
        t.start(); // starts a new thread
    }
}

2. Implementing Runnable Interface
 
class MyRunnable implements Runnable {
    public void run() {
        System.out.println("Thread is running");
    }
}

public class Main {
    public static void main(String[] args) {
        Thread t = new Thread(new MyRunnable());
        t.start(); // starts a new thread
    }
}

✅ Thread vs Runnable

Feature	           Thread	                        Runnable
Inheritance	       Not flexible (extends Thread)	Flexible (can extend another class)
Usage              Less used in real-world	      Preferred in real-world
Structure	         extends  Thread	              implements Runnable

✅ start() vs run()

Method	Behavior
start()	Starts a new thread and executes the run() method inside it
run()	  Executes like a normal method in the current thread

✅ Real-World Analogy: IRCTC Booking Example
 
class Booking extends Thread {
    private String user;

    Booking(String user) {
        this.user = user;
    }

    public void run() {
        System.out.println(user + " booking started");
        try {
            Thread.sleep(2000); // simulating booking delay
        } catch (Exception e) {}
        System.out.println(user + " booking done");
    }

    public static void main(String[] args) {
        new Booking("Rahul").start();
        new Booking("Priya").start();
    }
}


🧠 MCQs & Answers
Which method starts a thread? → start()

Interface for multithreading? → Runnable

run() method is in? → Runnable

run() called directly? → Runs in main thread (not separate)

Production usage preferred? → Runnable

Which allows behavioral inheritance? → Runnable

What does Thread.sleep(2000) do? → Pauses for 2 seconds

Thread class implements? → Runnable

If you override run() and call it directly? → No new thread is created

Which is preferred: Runnable or Thread? → Runnable

✅ Summary
Use Runnable in real-world applications for flexibility and cleaner design.

Always use .start() to begin a new thread; do not call run() directly.

Thread class is used when you want to override thread-specific behavior directly.

Multithreading helps improve responsiveness in real apps like IRCTC, Zomato, and Paytm.

