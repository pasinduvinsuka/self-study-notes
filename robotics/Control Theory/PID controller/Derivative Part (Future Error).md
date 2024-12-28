![[Pasted image 20241228134722.png]]
`Right before we get into our 50 meters, there will be an interesting situation. The propotioanl part is 0 but the depending on how we get to the current point (where now only have a really small error) our integral part may have a value more than 100.`
`So this will cause our drone to rise more than the 50 m. So because of the extra propeller speed we had when we were closer to 50m, our drone will have to go bit higher in order to reduce its speed by creating a negative error.`
## So this over shooting is not something we have expected !

So how can we solve this ? 

**That's by adding a part where we can calculated the future error. So we do that with a derivative.**

![[Pasted image 20241228135459.png]]

![[Pasted image 20241228135601.png]]
`In here the d erivative will produce a measure of the rate of change of error, which give us about how fast our error is growing or shriking.`
`So if our drone is rising quickly (fast approaching the goal), then our will start to decrease quickly. So that decreasing will have a negative rate which will produce a negative value.`
`So this value is added to our controller. So this will reduce our propeller speed.`

[[PID Controller Finally]]]