![[Pasted image 20241228114009.png]]
The drone will have 4 propellors and they will help the drone to up into the air.
![[Pasted image 20241228114100.png]]
So let's imagine that our system needs the altitude of 50m and hover over there.

So our plant will be the drone and our actuating signal will be the propellor speed and output will be the altitude.

- - - 
**So can we  just use a proportional controller like before ?** 

![[Pasted image 20241228114309.png]]
![[Pasted image 20241228114437.png]]
`So when our drone is in the ground the error rate will be 50 and that will generate a larger propellor speed. So the drone will lift up and the error will get reduced.`



![[Pasted image 20241228114908.png]]
![[Pasted image 20241228114918.png]]
`So now let's imagine that our drone has reached the desired height. So what's gonna happen next ? The error will drop to 0 since the output and command variable both are 50m.So this will cause to turn off the propellor and if it happened then our drone is gonna fall off.`

So when that's happening the propellor speed will again begin to increase since the error rate is increasing now.

![[Pasted image 20241228115017.png]]
`Note : There will be specific speed where the propellor lift force will get equal to the drone weight. So in that speed, the drone will start hovering.So let's assume that our propellors need to rotate at 100 rpm in order to hover the drone.So this speed will depened on our propotional gain now`

![[Pasted image 20241228122354.png]]
`So let's assume that our initial propotional gain is 2. So then our propeller speed will be 100 rpm (error rate x gain = 50 x 2 = 100 ).So our drone will be hover at the ground level. 

`So let's increase our gain to 5. Then our drone will start to lift up then our error rate will slowly go down. So when our eror rate is going down our propeller speed will also go down. Then once our error rate reach to 20 from 50 then our propeller speed will again be 20 x 5 = 100 rpm. So our drone will start to hover again when the error rate is 20.`

`So now let's increase our gain again to 10 from 5. Now our drone will start to lift up again and our error rate will start to go down. So what will happend once our error rate reached the value 10. then again our propeller speed will be 10 x 10 = 100 and then the drone will start to hover again.`

`So now let's increase our gain again to 100 and then our drone will again start to lift up until it reach the error rate 1 and once it reached the error rate 1, then again our propller speed will be 100 and our drone will start to hover.`

So we can notice that this gonna continue happening.

**No matter how much we increase the gain, our error won't go away.** 
The error is only getting smaller and smaller with our proportional controller system.

# So we  can see that a simple proportional controller will not work in every situation : (

So what's the solution we got for this ? 

![[Pasted image 20241228123442.png]]

In here we have noticed that our proportional control system kept having a error no matter how much we have increased our gain.