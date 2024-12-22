Let's imagine a real life example similar to a deadlock.
Let's imagine there is 2 toys a ball and a car. There is 2 kids called Jim and Tom. 
- Jim will grab the car first and say that he needs the ball too.
- Tom will grab the ball first and he says that he needs the car too.

Now both of the kids are stucked waiting for a toy which is already under the other kids hand.

Similarly these sort of scenario can be happened in computing too.
- Thread 1 locks Resource 1 and needs Resource 2.
- Thread 2 locks Resource 2 and needs Resource 1.

Both thread will be waiting to release each others lock causes for a deadlock.

Deadlock can also include more than two threads. This makes it harder to detect. Here is an example in which four threads have deadlocked:

- Thread 1  locks A, waits for B
- Thread 2  locks B, waits for C
- Thread 3  locks C, waits for D
- Thread 4  locks D, waits for A