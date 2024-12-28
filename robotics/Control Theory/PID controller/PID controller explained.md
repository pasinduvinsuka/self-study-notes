![[Pasted image 20241228123956.png]]

So how can we get rid of the previously discussed steady state error ? we can do it by letting our controller to use the past information. We are doing it by adding an integrator path.
![[Pasted image 20241228124038.png]]

![[Pasted image 20241228130836.png]]
`So our integral part will keep the track of our error rate. So it will keeps running the sum of error over time. So whenever there is an error the integral part is gonna increase.
`So while in the steady state error our integral part will keep to growing.`

![[Pasted image 20241228131058.png]]
`So now in here our both propotional and intergral controllers will work together to bring our error down to the 0.

![[Pasted image 20241228131312.png]]
`
![[Pasted image 20241228131342.png]]

- **Error vs Time (Top Graph):**
    
    - The error starts at **1 meter** (steady-state error) and gradually decreases as the drone approaches the setpoint of 50 meters.
- **Integral of Error vs Time (Middle Graph):**
    
    - The integral of the error grows steadily when the error is high and slows down as the error decreases.
    - It stops increasing once the error becomes zero, reflecting the accumulated correction needed over time.
- **Actuating Signal vs Time (Bottom Graph):**
    
    - The actuating signal (motor RPM) starts at **100 RPM** and increases due to the integral term.
    - It stabilizes at a higher RPM once the error is corrected and the drone reaches the target altitude.