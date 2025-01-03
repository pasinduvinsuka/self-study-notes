Noise is a random disturbance on our signal. Those noises are something unavoidable when we are working with sensors.

![[Pasted image 20241228232350.png]]

![[Pasted image 20241228232458.png]]
Temperature captured without and with noises are shown here. Because of the noises we can see there are sort of tiny fluctuations.

Low amplitude signals won't affect for some controllers. **But that's not true for an ideal PID controller.**
**![[Pasted image 20241228234959.png]]

In here the derivative part will amplify the high frequency signals, so those tiny barely noticeable noises may get amplify to a values that can be an affect to our systems. Below is an explanation how that's gonna happen.

![[Pasted image 20241228235222.png]]
`In here the slope will give the derivative of this signal. What's gonna happne if we increase the frequency of this signal ?`
![[Pasted image 20241228235319.png]]
`Now here we can see that the increased frequency has caused to the increase the slope of our frequency which means it has increased the value of derivative.`

So how can we reduce the slope (value of the derivative) while keeping our frequency ? We can do it simply by reducing the amplitude of our frequency like in below.
![[Pasted image 20241228235611.png]]

 ![[Pasted image 20241229000907.png]]
 `We can represent any noise with the infinite number of the sin waves.`This is what we are doing with the Fourier transform ([[Fourier Series]]).`For this example let's assume that we are able to represent our noise only with an one sin wave.`
`So we can take the slope of this sin wave by taking the derivative of it.`

`So by examine the derivative we can see we have got a sin wa ve with the same frequency. But if our omega is greater than 1 rad/s then our amplitude will get larger and vise versa if our omega is lesser than 1 rad/s our amplitude will get low.so what we can notice is :

- higher frequencies will give higher amplitude signals 
- lower frequencies will give lower amplitude signals

So based on this the value of our derivative get changed.`
 ![[Pasted image 20250103102620.png]]

 So in here we can notice that the higher the frequency, the higher the amplitude will be  and vice versa.

So now what we gonna do as the designer is to block the frequencies which are above a certain level from entering into our system.
![[Pasted image 20250103102858.png]]


![[Pasted image 20250103103502.png]]
So in here we can add our filter into the derivative like this. Ideally we might need our filter to remove all the noised but this is something that cannot be achieved in the real world.

But luckily for the many signals we consider, the noise across the spectrum is pretty low power , low amplitude. And the signal we are interested in keeping has a large power and low frequency compared to that noise.
![[Pasted image 20250103103846.png]]

so what we can do here is removing the bothersome noise with high frequency which are affecting our current signal. We can remove this noise simply by a first order low pass filter. So what this filter does is allow the signals which has low frequency below the cut off frequency without doing any change and also lower the amplitude of the signal which are above the cutoff frequency. So by doing this our high frequency signal's will get low amplitude and that will reduce the affect we had on the value of our derivative.

So the key aspect of this filter is to determine 