So in here our clamping method has 2 separate checks that it's doing.

1. **Check the PID controller output with the clamping saturation limit** - `If the values are equal then there is no saturation has been taken. If the values are not equal then there is a saturation happened.`

2.  **Check the sign of the PID controller output with the sign of the error** - `Check whether the both error and the output signs are equal

![[Pasted image 20241228210645.png]]
`So in here if our signs are same and also there is a saturation then the value of our AND gate will be 1 and we will clamp the integral part.(think as disconnecting the integral part)`

`If the sign got changed, or else there is no saturation then we will restore our integral part again.`

![[Pasted image 20241228211124.png]]
`So here how our dron system will look like if we had clamping system. ( check the scenario marked with integral path decrease)`

## Setting the saturation limit for the anti-windup algorithm

- Don't set the saturation limit of the clamping system to the exact physical saturation limit of the actuator.  ( `Our actuators can get slow down with age, temperature and based on some other factors. So because of this our saturation limit of the actuator also can be go down. So if in this scenario we have )
