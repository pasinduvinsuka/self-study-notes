![[Pasted image 20241228190159.png]]
Above was the theoretical PID controller we had before. But in practical life this is not the good solution.

![[Pasted image 20241228190603.png]]
In our theoretical  linear actuator, we don't have any sort of limit (saturation.). If our integral part is gonna increase with the error then our actuator signal also gonna get increased according to that no matter whether its 1000 rpm or 10000000000 rpm.
**But in real life things are not like that**

![[Pasted image 20241228190342.png]]
`In real life, the actuators are not linear.`
