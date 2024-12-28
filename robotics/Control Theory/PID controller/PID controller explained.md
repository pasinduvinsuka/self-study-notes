![[Pasted image 20241228123956.png]]

So how can we get rid of the previously discussed steady state error ? we can do it by letting our controller to use the past information. We are doing it by adding an integrator path.
![[Pasted image 20241228124038.png]]

![[Pasted image 20241228130836.png]]
`So our integral part will keep the track of our error rate. So it will keeps running the sum of error over time. So whenever there is an error the integral part is gonna increase.
`So while in the steady state error our integral part will keep to growing.`

![[Pasted image 20241228131058.png]]
`So now in here our both propotional and intergral controllers will work together to bring our error down to the 0.`