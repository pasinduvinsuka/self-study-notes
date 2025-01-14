- Object keeps references. (pointers)
![[Pasted image 20250114145716.png]]

- All instance variables and methods we create are **dynamic** (things created at the runtime) by default unless we use the keyword "static".

### **Static  vs non static

- static means pertaining to the class in general and not only to an object.
- we can access static variables without creating an instance of the class since they are available at the class loading time.
- if a method or a variable is not static, then we need to create an instance first in order to access them.

### Java Packages
![[Pasted image 20250114150644.png]]

### Inheritance

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

`Declaring variables as protected inside the superclass will expose them to the subclass. But it's a good practise to declare them as private and use getters and setters to access them.`