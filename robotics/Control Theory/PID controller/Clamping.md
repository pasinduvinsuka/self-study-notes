So in here our clamping method has 2 separate checks that it's doing.

1. Check the PID controller output with the clamping saturation limit - `If the values are equal then there is no saturation has been taken. If the values are not equal then there is a saturation happened.`
1. 