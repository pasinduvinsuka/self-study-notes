![[Pasted image 20241228111356.png]]
![[Pasted image 20241228111522.png]]
In here the difference between the command and the feedback is called as the 'error term'. So what we wanna do is to make this error term to 0.

So how can we take this error term and convert a better suitable actuating signal ?So with the time the error will be driven into the 0.So we are using the controller to accomplish this.

![[Pasted image 20241228111734.png]]
## Example : A person standing in a Soccer Field

![[Pasted image 20241228112925.png]]

![[Pasted image 20241228113019.png]]
So in this scenario the 'walking speed ' will be the actuating signal and the our current location will be the output. And where we wanna go is the commanded variable which is 50m at the biggening.  And also the output is 0 at the biggening. So the error term will be 50 - 0 = 50 .  

So in this scenario our brain will be the controller and tells our legs how fast to walk.
Let's take a way that our brain will get the error rate and then it will multiplied by 0.1 to get the walking speed.

```
Walking speed  = error rate x 0.1
```

![[Pasted image 20241228113435.png]]

So initially the speed will be 5ms-1 and with the time since the error rate gets down our walking speed will get down too as in above graphs.

 So if we wanna go to our desired location in a less time what we have to do is increase our current gain value 01. to something higher.

![[Pasted image 20241228113650.png]]

So in this current example our human gonna stop at the exact right location once he reached their since there regardless of the gain amount since the error term will become 0.

## Will this sort of controller works for the all scenarios ?

[[Altitude Controller for a quadcopter drone]]
[[Anti-windup for PID control]]
[[Noise filtering in PID control]]