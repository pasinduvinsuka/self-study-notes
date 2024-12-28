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
`So let's increase our gain to 5. Then our drone will start to lift up then our error rate will slowly go down. So when our eror rate is going down our propeller speed will also go down. Then once our error rate reach to 20 from 50 then our propeller speed will again be `