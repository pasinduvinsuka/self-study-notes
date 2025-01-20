## GaRb (00)

##1
A is Green, B is red.. since A has more priority.
B don't have traffic, then amber timer enable is not running. So timer done is also 0. input is 00.

##2
A is Green, B is red.. 
B  have traffic, so timer enable is started. But timer done is still 0. and input should remain 01.
So A is Amber, B is red..

##3
A is Green, B is red..
B have traffic, so timer enable is started... and timer is done too.. so input is 11.. A will go to Red and B will go to green.. but this input is invalid since of the transition.

## AaRb (01)

##3
A is Amber, B is red...
There cannot be a input scenario where traffic_b is 0 and A is under Amber since A has more priority. So inputs 00 cannot exist.

##4
A is Amber, B is red...
B have traffic, so timer enable is started... But timer done is still 0. input remain as 01.
So A is Amber, B is red...

##5
A is Amber, B is red...
timer_done cannot be 1 without b having traffic. So input 10 cannot be exist.

##6
A is Amber, B is red...
Traffic in B and also timer is done.. So input is 11. 
Since timer done is also true A become Red , B becomes Green.

### RaGb (10)

##7
A is Red, B is green...
When the B don't have traffic, traffic in B is 0 , since A has more priority B will become Amber. So amber_timer_en is started. Input is 00.
A is Red, B is amber...

##8
A is Red, B is green...
When the B has traffic, traffic in B is 1. So B will keep Green.. And also in this state A is in red.. so the timer_done should be also 1. So there cannot be input exist as 01.
A is Red, B is green...

##9
A is Red, B is green...
When the B has traffic and its also in Green there  the input should be 11..Since A is Red timer_done should be 1 and traffic_b should be 1.

##10
A is Red, B is green...
Timer_done is 1 since still B is in Red.. So when B don't have traffic, traffic_b will become 0. Since A has more priority now B should become Amber. While B becomes Amber, amber_timer_en signal will become 1..so timer_done will reset to 0.. so there cannot be input as 10.

## RaAb(11)

##11
A is Red, B is Amber...
Timer_done is 0 and still B is in Amber.. B is in amber means B don't have traffic. So input will be 00.
A is Red, B is Amber..

##12
A is Red, B is Amber...
Since B was in Amber amber_timer_en is high.. and once it done the input will be 10.
A will become Green, B will become red..

##13
A is Red, B is Amber....
There cannot be traffic in B while its amber.. so input 11 cannot be exists.

##14
A is Red, B is Amber....
There cannot be traffic in B while its amber.. so input 01 cannot be exists.
