[[fundamentals_of_control_r1_6.pdf]]



> [!NOTE] What is a system ?
>
> System is a collection of interconnected parts which will form a larger and more complex whole

Let's consider a car as an example. Car as a whole is a complex system. And the breaking system in the car is a sub part of that. We can consider the breaking system also as a set of collection of small sub parts.

![[Pasted image 20241225110619.png]]
This is the part that is actually converting the car’s kinetic energy into heat energy and reducing the vehicle’s speed. Yet the disc brakes are small systems on their own because they are made up of rotors, calipers, brackets, shielding, fasteners, and hoses which allow the disc brakes to function correctly

![[Pasted image 20241225110806.png]]

Typically we will define the system in the box via mathematical model that will represent the its equations of behavior.

- System can be simple as a single disc disk brake which takes the force of the hydraulic fluid and the output being the temperature of the rotor which slows down the car by converting it's kinematic energy into the heat.
- Or else a system can be complex like a entire car which have hundreds of inputs and outputs.
![[Pasted image 20241225111226.png]]

##  3 Problems we will face 

In a give plant there will be 3 things. 
	- Inputs
	- Outputs
	- A box which representing the system 

So the 3 problem we will face are 
[[#01.System Identification]] - Black box method , White box method
[[#02.Simulation Problem]]
[[#03.Control Problem]]
# 01.System Identification

# 01.**Black Box Method**
![[Pasted image 20241225111922.png]]
We have given with various known inputs and expected outputs. We have to infer what's inside the box by based on the relationship between both inputs and outputs.

---

02.**White Box Method**
![[Pasted image 20241225112057.png]]
We can open the box and see what's inside. So we can see all the underlying electronics, software and all . Then we have to figure out the mathematical equations.
![[Pasted image 20241225112427.png]]
![[Pasted image 20241225112541.png]]

# 02.Simulation Problem
[[fundamentals_of_control_r1_6.pdf#page=18&selection=21,0,21,22|fundamentals_of_control_r1_6, page 18]]

Inputs and the mathematical model is given, we have to predict the output changes against to those.

![[Pasted image 20241225113523.png]]

# 03.Control Problem
[[fundamentals_of_control_r1_6.pdf#page=20&selection=8,1,9,19|fundamentals_of_control_r1_6, page 20]]

System and the outputs are given, we have to determine the appropriate inputs through various control methods.
![[Pasted image 20241225113827.png]]

# Types Of Control Systems

1. [[Open Loop Control Systems]]
2. [[Closed Loop Control Systems]]

[[Transfer Functions]]
[[Time Domain and Frequency Domain]]
[[PID Control]]