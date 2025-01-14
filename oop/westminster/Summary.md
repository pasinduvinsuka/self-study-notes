- Object keeps references. (pointers)
![[Pasted image 20250114145716.png]]

- All instance variables and methods we create are **dynamic** (things created at the runtime) by default unless we use the keyword "static".

### **Static  vs non static

- static means pertaining to the class in general and not only to an object.
- we can access static variables without creating an instance of the class since they are available at the class loading time.
- if a method or a variable is not static, then we need to create an instance first in order to access them.

### Java Packages
![[Pasted image 20250114150644.png]]

### 01. Inheritance

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

### 02. Polymorphism (Introduce the substitution principle)

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
- by default all the methods which are inside in the interface are public  and abstract.
- by default all the variable inside of an interface are public static final. So we have to initialize an value too when we define an variable inside of an instance.

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
In an interface we use an dotted arriw