
[[Thread Life Cycle.canvas|Thread Life Cycle]]

- In java we can send signals from one thread to another thread. 
- In java all the classes are extended from the Object Class. Object class has below 3 methods which we can use to signal between the threads.
		1. wait ( )
		2. notify ( )
		3. notifyAll ( )


### Locks in Java

In java lock will be used to control the access to the shared resources. By doing that we can avoid the occur of race conditions which can happen when 2 threads are trying to write into the same resource at the same time. 

*Let's take a room with a door for an example and there will be few people in front of the door and door has a lock. So in order to enter the room, they need the key to acquire the lock. So one person will acquire the lock and go inside the room with the key. So no one else can enter to the room until he comes out and gives the key and release the lock. The same sort of mechanism is happening in the java too.*

- 'lock' is a part of the every object in the java.
- If there is a critical section which is inside of the 'synchronized' block, then the thread must acquire the lock to enter inside it and execute the things remaining inside the synchronized block. And once this lock is acquired by a thread, no other thread will be allowed to enter the critical section until the lock has been released.
- The lock is a part of the java object model and every object will have a lock. (We also call it as **monitor** )
- Lock is something tied to the object we created. Any number of synchronized methods of the same object will share the same lock which was tied to the object.

### Locks and Thread Communications

Sometimes threads will be needed to communicate. As an example, one thread might needs to wait until a signal from another thread. Java will use object locks for such scenarios.

 - **wait ( )** - once we call wait method on a object inside of the synchronized block, then it will release the lock of the object and thread will go into the waiting state.

		[Running State] ----calls wait()--------> [Waiting State]

- **notify ( )** - once we call the notify on the object, then it will wakes up a thread which was in the waiting state and will go to the ready state.

		[waiting State] ----calls notify()-------> [Ready State]

- **notifyAll ( )** - once we call notifyAll on the object, then all the threads which was in waiting state will get awaken and compete to acquire the lock tied to the object. But only one thread can acquire the lock and so the thread that acquired the lock will be moved into the 'ready' state and other threads will keep remain on the 'waiting' state.

```java
public class MonitorObject{
}

public class MyWaitNotify{

  MonitorObject myMonitorObject = new MonitorObject();

  public void doWait(){
    synchronized(myMonitorObject){
      try{
	    System.out.println(Thread.currentThread().getName() + " is waiting.");
        myMonitorObject.wait();
        System.out.println(Thread.currentThread().getName() + " finish waiting.");
      } catch(InterruptedException e){...}
    }
  }

  public void doNotify(){
    synchronized(myMonitorObject){
	    System.out.println(Thread.currentThread().getName() + " is notifying.");
	    myMonitorObject.notify();
	    System.out.println(Thread.currentThread().getName() + " finish notify.");
    }
  }
}
```

The above process can be shown as below.

![[Pasted image 20241125155335.png]]

[[Thread Signaling Process.canvas|Thread Signaling Process]]

### IllegalMonitorStateException

A thread cannot call any of the method from wait ( ), notify ( ), notifyAll ( ) without holding the lock related the object which the method was called. Otherwise it will throw an error 'illegalMonitorStateException'.



### Missed Signals

```java
package threadsignaling;  
  
public class SignalCarrier {  
  
    public void doWait(){  
        synchronized (this) {  
            try {  
            System.out.println("Waiting for signal");  
            this.wait();  
            System.out.println("Finished waiting for signal");  
            }catch (InterruptedException e){  
                System.out.println(e.getMessage());  
            }  
        }  
    }  
  
    public void doNotify() {  
        synchronized (this) {  
                System.out.println("Notifying signal");  
                this.notify();  
                System.out.println("Finished notifying signal");  
  
        }  
    }  
  
    public void doNotifyAll() throws InterruptedException {  
        synchronized (this) {  
            System.out.println("Notifying signal");  
            this.notifyAll();  
            System.out.println("Finished notifying signal");  
        }  
    }  
}
```

```java
package org.example;  
  
import threadsignaling.SignalCarrier;  
  
public class Main {  
    public static void main(String[] args) {  
        SignalCarrier signalCarrier = new SignalCarrier();  
        Thread waiterThread = new Thread(signalCarrier::doWait);  
        Thread notifyThread = new Thread(signalCarrier::doNotify);  
        waiterThread.start();  
        notifyThread.start();  
    }  
}
```

Threads are scheduled by the JVM. So the order of thread scheduling is **Unpredictable**.
Due to this unpredictable thing, there is two possible thread execution orders we can get.

1. waiterThread.start( ) runs first, notiyThread.start( ) runs second :
		![[Pasted image 20241126231115.png]]
		*in this scenario there won't be any issues*



2. notiyThread.start( ) runs first, waiterThread.start( ) runs second :
	![[Pasted image 20241126231655.png]]
		*in here we can see that the waiter thread has stucked in it's wait state because the notify signal has already finished calling. So there will be a 'signal lose' .* 

So we should find a proper approach to avoid those missed signals.
So as a solution for this we can introduce a state to keep the track of whether the signal was notified before it calls the wait method. 

```java
package threadsignaling;  
  
public class SignalCarrier {  
  
    //a variable to keep the track whether the thread was signaled or not  
    boolean wasSignaled = false;  
  
    public void doWait() {  
        synchronized (this) {  
            try {  
                if (!wasSignaled) {//call the wait method only if the lock object hasn't been notified yet.  
                    System.out.println("Waiting for signal");  
                    this.wait();  
                    System.out.println("Finished waiting for signal");  
                }else {  
                    wasSignaled = false;  
                }  
            } catch (InterruptedException e) {  
                System.out.println(e.getMessage());  
            }  
        }  
    }  
  
    public void doNotify() {  
        synchronized (this) {  
            wasSignaled = true; // make the state of wasSignaled true once the doNotify method has been called  
            System.out.println("Notifying signal");  
            this.notify();  
            System.out.println("Finished notifying signal");  
  
        }  
    }  
  
    public void doNotifyAll() throws InterruptedException {  
        synchronized (this) {  
            wasSignaled = true; // make the state of wasSignaled true once the doNotify method has been called  
            System.out.println("Notifying signal");  
            this.notifyAll();  
            System.out.println("Finished notifying signal");  
        }  
    }  
}
```

![[Pasted image 20241201123538.png]]

Now in here we can see that the thread is not indefinitely waiting if it has missed the signal.

### Spurious Wakeups

For some inexplicable reasons , sometime the threads can get wakeup even if the notify( ) or notifyAll( ) methods haven't even called yet. If this happen there can be serious problems in our application. So in order to fix this what we gonna do is keep the track whether the thread was signaled inside of the notify method and keep checking it in the wait method with a loop. So even if the thread tries to get wakeup automatically, because of the loop checking it won't happen. 

```java
package threadsignaling;  
  
public class SignalCarrier {  
  
    //a variable to keep the track whether the thread was signaled or not  
    boolean wasSignaled = false;  
  
    public void doWait() {  
        synchronized (this) {  
            try {  
                //call the wait method only while the lock object hasn't been notified yet via the notify methods.  
                while (!wasSignaled) {  
                    System.out.println("Waiting for signal");  
                    this.wait();  
                    System.out.println("Finished waiting for signal");  
                }  
                wasSignaled = false;  
  
            } catch (InterruptedException e) {  
                System.out.println(e.getMessage());  
            }  
        }  
    }  
  
    public void doNotify() {  
        synchronized (this) {  
            wasSignaled = true; // make the state of wasSignaled true once the doNotify method has been called  
            System.out.println("Notifying signal");  
            this.notify();  
            System.out.println("Finished notifying signal");  
  
        }  
    }  
  
    public void doNotifyAll() throws InterruptedException {  
        synchronized (this) {  
            wasSignaled = true; // make the state of wasSignaled true once the doNotify method has been called  
            System.out.println("Notifying signal");  
            this.notifyAll();  
            System.out.println("Finished notifying signal");  
        }  
    }  
}
```