![[Pasted image 20241014073050.png]]
### 1. **A Door (1 DoF)**:

- A door can only **swing open and closed** on its hinges. It can't move up, down, or sideways.
- **1 degree of freedom** – It has only one way it can move: rotating on its hinges.

### 2. **A Car (3 DoF)**:

- A car can **move forward and backward**, **side to side** (though usually not much unless you slide it), and it can also **rotate** or turn (change direction).
- **3 degrees of freedom** – It can move in three ways: front/back, left/right, and turn (rotate) on the road.

### 3. **A Drone (6 DoF)**:

- A drone can move **up and down** in the air, go **forward and backward**, and **left and right**. It can also **tilt forward and backward**, **tilt side to side**, and **rotate** (yaw) while flying.
- **6 degrees of freedom** – It can move in six different ways, which makes it very flexible!

### 4. **Human Arm (7 DoF)**:

- Your arm can **move up and down** (like lifting your arm or dropping it). It can also **move side to side** (swinging your arm across your body) and **rotate at the shoulder**.
- Your elbow bends (one movement), and your wrist can **rotate and bend** in two different ways.
- **7 degrees of freedom** – The human arm is very flexible and can move in a lot of different ways!

### 5. **A Ball (Spherical Joint) (3 DoF)**:

- A ball can rotate in **any direction** when held in a socket (like in your shoulder or hip joint).
- It can rotate **up/down**, **left/right**, and also **spin around**.
- **3 degrees of freedom** – It can rotate in three different directions.

### 6. **A Table on Wheels (4 DoF)**:

- A table on wheels can **move forward/backward** and **left/right** (rolling around).
- If the wheels allow it, the table can also **rotate** (turn in place).
- **4 degrees of freedom** – It can roll in two directions and rotate.

### Movements of the Table:

1. **Forward/Backward movement** – This is along one axis (let's call it the X-axis). The table can roll forward and backward.
    
    - **1 DoF**
2. **Left/Right movement** – This is movement along a different axis (let's call it the Y-axis). The table can roll sideways.
    
    - **1 DoF**
3. **Rotation** – The table can also rotate (spin) around a point without changing its location (like when turning in place). This is a rotation around a vertical axis (Z-axis).
    
    - **1 DoF**

### Why 4 DoF?

Now, normally, this would describe 3 degrees of freedom: two translational (X, Y) and one rotational (Z). However, if the wheels on the table are designed to rotate or swivel (like on a shopping cart), **each wheel can rotate independently**, adding **another rotational degree of freedom**. This extra movement allows the table to turn more smoothly in multiple directions.

- **2 translational movements** (forward/backward and left/right)
- **2 rotational movements** (rotation of the whole table + rotation or swiveling of the wheels)

That gives the table a total of **4 degrees of freedom**!

If the table only moved in two directions and rotated around itself, it would have 3 DoF. But since the wheels provide more rotational flexibility, we count it as 4 DoF.
### Summary:

Each "degree of freedom" is a different way that something can move, and the more ways something can move, the more flexible or mobile it is. A simple hinge or slide has fewer degrees of freedom than a robot arm or a drone!

![[Pasted image 20241030223026.png]]
