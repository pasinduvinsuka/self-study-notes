![[Pasted image 20241206130530.png]]
There will be 4 classes. Consumer class (Customer), Producer Class (Vendor) and a Ticket pool. We are also considering this system as a real time system.

There will be a maximum capacity of the pool and the number of total tickets available to buy at a given time cannot exceed this. The number of total tickets available to buy for the user at a given time should be visible to the consumer. 

*let's imagine there is total number of tickets are 10. And then there is 5 customers A,B,C,D,E trying to buy. So if A buys 1 ticket, then B should be only able to see 9 tickets.*
*But let's think that while A is buying a vendor has added a new ticket. So B should see total number of tickets as 10*

The above scenario will be the happy path. But there can be a scenario like

		A and B both access the ticket pool at the same time. The total available tickets they had at that moment is 10. So now A buys 1 ticket. If 