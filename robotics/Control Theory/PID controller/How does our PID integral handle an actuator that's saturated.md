![[Pasted image 20241228191847.png]]

Let's consider only the integral part from the above example . And also let's imagine we are holding the drone tight using our hands without letting it go at the biggening using our hands.
![[Pasted image 20241228192059.png]]
`So in here initially the error will be 50. So our integral will have that value.So because of that our propllers will start to speed up more. But still we are holding the drone, so the error will remain the same and because of this our controller will increase the propellers speed more and more. But there is a limit of the maximum speed the propeller can have. So once that's reached our propeller won't speeed up more than that. But our integral error is still there. So our actuating signal will keep growing, but motors are already saturated.`

--- 

So now we have noticed our integral part has exceeded the saturation level of the motor. The issue is arise when we are trying to remove back this exceeded amount from our integral. 

`Let's consider our motor's maximum speed is 1000 rpm.But since we kept holding our drone, the output of our integral is requesting now 2000 rpm.`