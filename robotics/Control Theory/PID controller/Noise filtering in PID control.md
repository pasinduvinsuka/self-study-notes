Noise is a random disturbance on our signal. Those noises are something unavoidable when we are working with sensors.

![[Pasted image 20241228232350.png]]

![[Pasted image 20241228232458.png]]
Temperature captured without and with noises are shown here. Because of the noises we can see there are sort of tiny fluctuations.

Low amplitude signals won't affect for some controllers. **But that's not true for an ideal PID controller.**
**![[Pasted image 20241228234959.png]]

In here the derivative part will amplify the high frequency signals, so those tiny barely noticeable noises may get amplify to a values that can be an affect to our systems. Below is an explanation how that's gonna happen.

![[Pasted image 20241228235222.png]]
`In here the sloap will give the derivative of this signal. What's gonna happne if we increase the frequency of this signal ?`

![[Pasted image 20241228235319.png]]