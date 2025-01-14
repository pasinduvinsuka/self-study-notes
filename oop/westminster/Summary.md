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

`An instance of a subclass can take place of an instance of its any of superclasses.`
![[Pasted image 20250114152331.png]]
![[Pasted image 20250114152348.png]]

**Dynamic vs Static Binding**

- Dynamic binding (mostly method overriding) : which method to call is resolved at the runtime
- Static binding (method overloading) : which method to call is resolved at the compile time
![[Pasted image 20250114153730.png]]

### Final keyword

## Final Classes
- If we declare a class as final then we cant use that class to extend an anotehr class. So we can prevent inheritance by making a class as 'final'.
