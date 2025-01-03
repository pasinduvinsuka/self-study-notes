![[Pasted image 20241228191847.png]]

Let's consider only the integral part from the above example . And also let's imagine we are holding the drone tight using our hands without letting it go at the biggening using our hands.
![[Pasted image 20241228192059.png]]
`So in here initially the error will be 50. So our integral will have that value.So because of that our propllers will start to speed up more. But still we are holding the drone, so the error will remain the same and because of this our controller will increase the propellers speed more and more. But there is a limit of the maximum speed the propeller can have. So once that's reached our propeller won't speeed up more than that. But our integral error is still there. So our actuating signal will keep growing, but motors are already saturated.`

--- 

So now we have noticed our integral part has exceeded the saturation level of the motor. The issue is arise when we are trying to remove back this exceeded amount from our integral. 

`Let's consider our motor's maximum speed is 1000 rpm.But since we kept holding our drone, the output of our integral is requesting now 2000 rpm.But motors are only spinning at 1000 rpm since its the maximum speed of the motors.`

`So now let's give a change for the drone to go up, let's release it from our hand. Remember that now our drone propellers are spinning at 1000 rpm and also our integral part is requesting 2000 rpm. Since we released the drone at 1000 rpm, our drone will start to go up pretty much faster, and also our error begins to decrease very fast too.`
![[Pasted image 20241228193055.png]]

And what's because of the speed it had it's gonna past our target altitude and rise up more. So our error will start to reach a negative value.

![[Pasted image 20241228193228.png]]
`So now since our error term is negative, our integral output will start to get decreased. But there is an issue. Think that our integral output reduced to 1900 from 2000, still motors are spinning at 1000 rpm.`

- 2000 rpm --> 1900 rpm  - still motors spinning at 1000 rpm
- 1900 rpm --> 1500 rpm  - still motors spinning at 1000 rpm
- 1500 rpm --> 1100 rpm  - still motors spinning at 1000 rpm

`So our motors will keep spinning at 1000 rpm until the integral output reach to the level 1000 from the 2000 and goes below.So until that point our motors are spinning at 1000 rpm and because of this our drone will be sky rocketting and go so high and lose from our area.

![[Pasted image 20241228195237.png]]

So this is called as the integral windup and we need to protect our PID controller from this. Because we don't know when our actuators will get saturated.

**So if something has saturated, then we need to minimize the time that takes to reverse the command when error change the sign.**

So we need to implement some sort of anti-windup method.

## Anti-windup methods

1. Clamping  - [[Clamping]]
2. Back-Calculation - [[Back-calculation]]
3. Observer approach - [[Observer approach]]
