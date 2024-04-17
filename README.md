# PHYS360_BungeeJumping

# Simulation and Animation of Bungee Jumping
Physics 360 Final Project <br>

**Summary** <br>
This project aims to simulate and animate the act of bungee jumping while highlighting the physics/kinematics behind the process. This is executed using Python and its relevant packages such as NumPy, MatPlotLib, and more. 

**Background** <br> 
Bungee jumping is an oscillary motion and serves as a great application of methods covered in class such as using ordinary differential equations to solve and simulate oscillations such as the double pendulum. It also incorporates methods of animation covered in class as well. This is an interesting project as we are able to understand the physics behind thrilling activities such as bungee jumping. 

To begin with, we can establish some variables such as: <br>

$h$ = the height of the jumper above the ground, in meters <br>
$t$ = the time, in seconds, elapsed since the jump <br>
$s$ = the distance travelled by the jumper, in meters <br>

We can also use *Hooke's Law* to understand how the bungee cord behaves when it stretches during the jump. <br>

<p align="center">$F_c = -kx$</p>

```python
import numpy as np
from scipy.integrate import odeint

m = 70  # mass of the jumper
g = 9.81  # gravitational acceleration 
k = 50  # spring constant of the bungee cord
L = 20  # length the jumper falls below the platform before the cord starts to stretch 

def bungee_motion(y, t):
    x, v = y  # displacement x and velocity v
    dxdt = v  # derivative of displacement is velocity
    dvdt = (m*g - k*(x - L))/m  # acceleration equation
    return [dxdt, dvdt]

x0 = 0  # initial displacement
v0 = 0  # initial velocity
y0 = [x0, v0]  # initial state vector

t = np.linspace(0, 10, 1000)  # time from 0 to 10 seconds
sol = odeint(bungee_motion, y0, t)
```

This Python code simulates the motion of a bungee jumper, considering the effects of gravity and the elasticity of the bungee cord. It defines a second-order ordinary differential equation describing the jumper's motion and solves it numerically using the odeint function from scipy.integrate.

**Resources** <br>
[Physics of Bungee Jumping](https://www.real-world-physics-problems.com/physics-of-bungee-jumping.html)

[Graphs and Formulas](https://staff.fnwi.uva.nl/a.j.p.heck/Guide_on_modelling/Documents/Understanding_the_physics_of_bungee_jumping.pdf)

[Mathematics of Bungee Jumping](https://www.math.cuhk.edu.hk/~mathcal/mathproj/unit2/)

**Objectives** <br>
1. Outline the kinematics and math behind bungee jumping using computational physics methods.
2. Be able to gather data through pandas and use the data to animate the motion of bungee jumping using matplotlibs 

*Questions that could be addressed* <br>
1. What is the velocity of the jumper when the cord begins to stretch?
2. At what time does the jumper reach its minimum height?
3. What is the maximum acceleration experienced by the jumper during the entire bungee jump?
4. How do variations in the jumper's initial velocity or height affect the dynamics of the bungee jump?

   


