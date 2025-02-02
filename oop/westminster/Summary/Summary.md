- Object keeps references. (pointers)
![[Pasted image 20250114145716.png]]

- All instance variables and methods we create are **dynamic** (things created at the runtime) by default unless we use the keyword "static".

# **Static  vs non static

- static means pertaining to the class in general and not only to an object.
- we can access static variables without creating an instance of the class since they are available at the class loading time.
- if a method or a variable is not static, then we need to create an instance first in order to access them.

# **Java Packages**
![[Pasted image 20250114150644.png]]

# 01. Inheritance

use keyword  'extend'.
![[Pasted image 20250114151032.png]]![[Pasted image 20250114151107.png]]

 - reuse
 - less redundancy
 - increased maintainability are the advantages of inheritance.

**Importance of super keyword

- Subclass won't inherit the constructor from the superclass.
- So in the subclass we need to initialize both of the instance variables that belongs to the subclass and superclass. 
- In order to initialize the instance variable belongs to the superclass we will use the  "super" keyword inside in the subclass
![[Pasted image 20250114151605.png]]

- super must come first before the other statement in the body of the subclass constructor.
- If subclass don't have any constructor, then java will create a non-argument constructor that contains only super();

`Note: Declaring variables as protected inside the superclass will expose them to the subclass. But it's a good practise to declare them as private and use getters and setters to access them.`

- we can override the methods that existed in the superclass inside of the subclass. 

# 02. Polymorphism (Introduce the substitution principle)

`An instance of a subclass can take place of an instance of its any of Asuperclasses.`
![[Pasted image 20250114152331.png]]
![[Pasted image 20250114152348.png]]

**Dynamic vs Static Binding**

- Dynamic binding (mostly method overriding) : which method to call is resolved at the runtime
- Static binding (method overloading) : which method to call is resolved at the compile time
![[Pasted image 20250114153730.png]]

### Final keyword

## Final Classes

- If we declare a class as final then we cant use that class to extend an another class. So we can prevent inheritance by making a class as 'final'.

**Final Methods**

- The methods marked as final cannot be overridden.
- A constructor cannot be final.

### Abstract classes

- if there is an any abstract method inside a class, then that class also should be abstract. (there can be methods without marked as abstract too inside of an abstract class.)
- Abstract classes cannot be instantiated (cannot create an instance from an abstract class).

- we can extend our subclasses from an abstract class.
		- if we define all the inherited methods from the abstract class inside of our subclass then it is complete.
		- if we are not defining all the methods that are inherited from the abstract class, then we have to mark our subclass also as an abstract class.

**Abstract method vs Concrete method**

- Abstract class cannot have a method body and a concrete method should have a method body.

## **Interfaces**

- interfaces will define the method but cannot have the method body.
- by default all the **methods which are inside in the interface are public and abstract**.
- by default all the **variable inside of an interface are public static final**. So we have to initialize an value too when we define an variable inside of an instance.

 - We can implement a class from an interface
		- if we define all the methods inside the class which we implemented from the     interface then its complete.
		- if we don't define all the methods which were in the interface, then our class should also defined as abstract.

- And also we can extend interface from another interface.
![[Pasted image 20250114172852.png]]

 - And also unlike the classes, an interface will support to extend from multiple other interfaces.
 
```java
interface A {
    void methodA();
}

interface B {
    void methodB();
}

interface C extends A, B {
    void methodC();
}

```

| Interface                                                | Abstract Class                                                                                                                                                             |
| -------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| methods inside of an interface cannot have a method body | methods inside of an abstract class can have concrete methods too. But if any method inside of an abstract class is marked as abstract, then it cannot have a method body. |
| A class can have many interfaces                         | A class can only have one superclass regardless of its abstract or not                                                                                                     |
|                                                          |                                                                                                                                                                            |
![[Pasted image 20250114173820.png]]
In an interface we use an dotted arrow in class diagram and normal arrow for classes.

### File handling

- All input and output in Java is accomplished by a classes called streams.
	- byte streams : stores data in binary format (InputStream, OutputStream to deal with those )
	- character streams : stores data as a sequence of characters (Reader, Writer to deal with those)

- InputStream, OutputStream, Reader, Writer all these are abstract classes.

![[Pasted image 20250114195505.png]]

### File Class

- This is used to retrieve the information about the files and directories from disk.
- Object of File class **doesn't open the actual files/ directories.** It only provide methods to operate on the given file/directories named.

![[Pasted image 20250114195845.png]]
![[Pasted image 20250114195859.png]]

## Reading/Writing files using character streams

![[Pasted image 20250114200013.png]]
![[Pasted image 20250114200054.png]]
![[Pasted image 20250114200543.png]]

## Reading and writing files using byte streams

![[Pasted image 20250114200713.png]]

## BufferedReader and BufferedWriter Class
![[Pasted image 20250114200806.png]]
![[Pasted image 20250114200942.png]]

### Exception handling

## Throwable Class

![[Pasted image 20250114203309.png]]


```java
public class CustomRuntimeException extends RuntimeException { 
	public CustomRuntimeException(String message) {
		super(message); 
	} 
}
```

![[Pasted image 20250114203634.png]]


# **Multithreading**

![[Pasted image 20250114215502.png]]


# **Thread Life cycle**

Once we instantiate the thread object , it's in the "New" or "Born" State.
![[Pasted image 20241119100150.png]]
Once we call the start( ) method on the created thread, then it will be in the "Ready" state.
![[Pasted image 20241119100255.png]]

And then once a processor is allocated to the thread which was in "Ready" state, then the thread will be go to the "Running" state. So the job we have written under the run( ) method will be completed in this state.

Once the job which was under the run( ) method is completed, then our thread will goes to the "Dead" state. Dead state is the last state that a thread will have.

If the "Running" state in a busy wait , we can swap it to the "Ready" state with the help of the scheduler. (We can do this by calling the ==*yield( )*== method . )

And also by calling ==*sleep( )*== method, we can move the thread which is in running state into the "Sleep" state. Once the time we have given under the ==*sleep (seconds t)*== method has exceeded by the thread, then the thread will be moved to the "Ready" state.

Once we called ==*suspend( )*== method in a thread which is in the "Running" state, then the thread will be moved to the "Blocked" state. Once we call the ==*resume( )*== method on a thread, which is under the "Blocked" state, then it will be moved into the "Ready" state.

If we called the ==*wait ( )*== on a  * **Thread Object**  which is under the "Running" state, then it will be moved into the "Waiting" state. Once we called the ==*notify( )*== on the * **Thread Object**, then it will be moved into the "Ready" state.

![[Pasted image 20250114220033.png]]

# Thread priorities
- Thread.MIN_PRIORITY  - minimum priority
- Thread.NORM_PRIORITY - default priority
- Thread.MAX_PRIORITY - maximum priority

![[Pasted image 20250114220704.png]]
![[Pasted image 20250114221153.png]]
![[Pasted image 20250114221200.png]]
