![[Pasted image 20241228190159.png]]
Above was the theoretical PID controller we had before. But in practical life this is not the good solution.

![[Pasted image 20241228190815.png]]
In our theoretical  linear actuator, we don't have any sort of limit (saturation.). If our integral part is gonna increase with the error then our actuator signal also gonna get increased according to that no matter whether its 1000 rpm or 10000000000 rpm.
**But in real life things are not like that**

![[Pasted image 20241228190342.png]]
`In real life, the actuators are not linear.`

---

![[Pasted image 20241228191107.png]]
let's consider that  a system is responsible for a constant error. So when that error goes through the integral the integral will cause our output to rise over time. So in this case let's imagine our actuator is a motor. But in real life our motors will have a maximum rpm. So the motor is not gonna increase its speed after it hits it's maximum rpm.

![[Pasted image 20241228191116.png]]
