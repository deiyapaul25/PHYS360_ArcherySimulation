# PHYS360_ArcherySimulation

# Comparing the Trajectory of a Recurve Bow and Barebow using Computational Physics
Physics 360 Final Project <br>

**Summary** <br>
This project aims to simulate and animate difference in trajectory of an arrow from a recurve bow and a barebow in archery. This is executed using Python and its relevant packages such as NumPy, MatPlotLib, and more. By employing computational physics principles, I aim to investigate how the distinct design characteristics of these two types of bows influence the trajectory of the arrow and hope offer practical implications for archers to optimize their performance. I will be comparing the projectile motion of a recurve bow and a barebow which each have the following initial conditions: <br>
- Draw Weight: 15 kilograms
- Launch Angle: 30 $\degree$
- Mass of Arrow: 25 grams
- Distance of Target: 50 meters

**Motivation/Background** <br> 
Archery consists of many different types of bows which each have its own characteristics. In this simulation, I will be comparing recurve bows and barebows. Recurve bows have a stabilizer, which helps stabilize the bow, and a sight, which helps with precision. Barebow, on the other hand, does not have any additional gadgets and is, as the name implies, a bare bow. <br>

Archery is a personal hobby of mine and I even shot for the university's team! I shoot barebow and so I have much less accuracy compared to my friends who shoot recurve or compound (another type of bow). Because of this, I would like to explore how much of a difference in overall accuracy the recurve is to a barebow through computational physics!

This project requires a computational approach to it because there are many factors (such as the sight and stabilizer) which increase the precision of the recurve. This requires me to account for the deviation in launch angle (which will reflect on precision), represented by $\sigma$. Then, with that accounted for, I can use Numpy to calculate the proejctile motion of the arrow along with its trajectory to compare how much more accurate the recurve is to the barebow. <br>

Using computational physics, I can also explore which factors can help increase the precision of barebow, such as changing the draw weight, launch angle, or other factors. 

**Results** <br>
In this section, I will outline the computations involved in comparing the trajectory of arrows shot from a recurve bow and a barebow. I start by adjusting the standard deviation of the launch angle to reflect the influence of additional accessories such as stabilizers and sights on the recurve bow's precision.

To calculate the adjusted standard deviation for launch angle, I'll consider the reduction factors for stabilizers and sights. Assuming a typical standard deviation of 2 degrees for launch angle without any additional gadgets, I applied a reduction of 20% for stabilizers and 30% for sights. We can use Python to reflect this calculation: <br>

```python
# Standard deviation of launch angle for barebow (without the additional gadgets)
std_regular = 2.0

# Reduction factor for stabilizer (20% reduction)
reduction_stabilizer = 0.8

# Reduction factor for sights (30% reduction)
reduction_sights = 0.7

# Calculate adjusted standard deviation with stabilizer
std_stabilizer = std_regular * reduction_stabilizer
print("Standard deviation with stabilizer:", std_stabilizer, "degrees")

# Calculate adjusted standard deviation with sights
std_sights = std_regular * reduction_sights
print("Adjusted standard deviation with sights:", std_sights, "degrees")

```
This returns: <br>

```
Adjusted standard deviation with stabilizer: 1.6 degrees
Adjusted standard deviation with sights: 1.4 degrees
```
This adjustment allows us to better represent the expected variability in launch angle for each type of bow, which is crucial for accurate trajectory simulations. <br>

Moving forward, I plan to calculate the projectile motion of the arrow for both the recurve bow and barebow using Python. This involves determining the initial velocity based on draw weight, draw distance, and arrow mass, and then calculating the trajectory using the equations of motion for projectile motion.

```python
import numpy as np
import matplotlib.pyplot as plt

def calculate_initial_velocity(draw_weight, draw_distance, arrow_mass):
    # Calculate initial velocity based on draw weight, draw distance, and arrow mass

def calculate_trajectory(initial_velocity, launch_angle, std_adjusted):
    # Calculate the trajectory of the arrow
    # Use the equations of motion for projectile motion

def main():
    # initial conditions
    draw_weight_recurve = 15  # Draw weight of recurve bow (kg)
    draw_weight_barebow = 15  # Draw weight of barebow (kg)
    draw_distance = 0.7112  # Draw distance (m)
    arrow_mass = 0.03  # Mass of arrow (kg)
    target_distance = 50  # Distance to target (m)

    # Calculate initial velocity
    initial_velocity_recurve = calculate_initial_velocity(draw_weight_recurve, draw_distance, arrow_mass)
    initial_velocity_barebow = calculate_initial_velocity(draw_weight_barebow, draw_distance, arrow_mass)

    # Calculate trajectory for recurve bow
    # Use adjusted standard deviation for launch angle based on the presence of stabilizers/sights

    # Calculate trajectory for barebow
    # Use adjusted standard deviation for launch angle based on the absence of stabilizers/sights

main()
# Plot trajectories
_fig, ax = plt.subplots()
# Compare the trajectories of the recurve bow and barebow
# Visualize the arrow paths and target position

```
This approach will enable us to compare the trajectories of arrows shot from the two types of bows accurately, considering the effects of different initial conditions and variability in launch angle.

**Questions to Address** <br>
1. How much more accurate is the recurve than the barebow
2. Which factor (ie draw weights, launch angle, etc) makes more of an impact in precision for a barebow
3. How does wind affect the performance of both bows
4. How do forces, including gravitational force, air resistance, and the force exerted by the bowstring, influence the arrow's trajectory and velocity

These questions are important to address because it will understand the overall physics of archery, which will help in terms of making the necessary adjustments to an archer's form and technique to optimize their performance. 
   


