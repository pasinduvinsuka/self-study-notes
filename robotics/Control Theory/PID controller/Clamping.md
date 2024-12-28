So in here our clamping method has 2 separate checks that it's doing.

1. **Check the PID controller output with the clamping saturation limit** - `If the values are equal then there is no saturation has been taken. If the values are not equal then there is a saturation happened.`

2.  **Check the sign of the PID controller output with the sign of the error** - `Check whether the both error and the output signs are equal

![[Pasted image 20241228210645.png]]
`So in here if our signs are same and also there is a saturation then the value of our AND gate will be 1 and we will clamp the integral part.(think as disconnecting the integral part)`

`If the sign got changed, or else there is no saturation then we will restore our integral part again.`
![[Pasted image 20241228211124.png]]