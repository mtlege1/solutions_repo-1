# Problem 1
# **Investigating the Range as a Function of the Angle of Projection**

## **1. Theoretical Foundation**

Projectile motion describes the motion of an object launched into the air, moving under the influence of gravity alone. The motion consists of two independent components: horizontal motion at constant velocity and vertical motion under uniform acceleration due to gravity.

### **1.1 Equations of Motion**

Using Newton’s Second Law, the fundamental equations for projectile motion can be derived. These assume negligible air resistance and uniform gravitational acceleration.

#### **Horizontal Motion:**

The horizontal displacement as a function of time:

$$
x(t) = v_0 \cos(\theta) t
$$

where:
- \( x(t) \) is the horizontal position,
- \( v_0 \) is the initial velocity,
- \( \theta \) is the launch angle,
- \( t \) is time.

Since no horizontal force acts on the projectile, the velocity remains constant:

$$
v_x = v_0 \cos(\theta)
$$

#### **Vertical Motion:**

The vertical displacement as a function of time:

$$
y(t) = v_0 \sin(\theta) t - \frac{1}{2} g t^2
$$

The vertical velocity at any time \( t \):

$$
v_y = v_0 \sin(\theta) - g t
$$

where \( g = 9.81 \text{ m/s}^2 \) is the acceleration due to gravity.

### **1.2 Time of Flight**

The total time the projectile remains in the air is found by solving for \( t \) when \( y(t) = 0 \):

$$
t_f = \frac{2 v_0 \sin(\theta)}{g}
$$

This indicates that flight time increases with higher initial velocity and greater launch angles.

### **1.3 Range of the Projectile**

The horizontal range \( R \) is obtained by substituting \( t_f \) into the horizontal displacement equation:

$$
R = \frac{v_0^2 \sin(2\theta)}{g}
$$

This equation reveals that the range depends on the square of the initial velocity, the gravitational acceleration, and the sine of twice the launch angle.

## **2. Analysis of Range vs. Launch Angle**

### **2.1 Maximum Range Condition**

Since \( \sin(2\theta) \) reaches its maximum value of 1 at \( 2\theta = 90^\circ \), the optimal launch angle is:

$$
\theta_{\max} = 45^\circ
$$

At this angle, the projectile achieves the greatest horizontal displacement.

### **2.2 Dependence on Initial Velocity and Gravity**

#### **Effect of \( v_0 \):**
- The range is proportional to \( v_0^2 \): doubling the velocity quadruples the range.

#### **Effect of \( g \):**
- The range is inversely proportional to gravity: weaker gravity results in greater range.

#### **Effect of Initial Height (\( h \))**
- If launched from a height \( h \), the flight time increases, leading to an extended range. The modified range equation is:

$$
R = \frac{v_0 \cos(\theta)}{g} \left( v_0 \sin(\theta) + \sqrt{(v_0 \sin(\theta))^2 + 2gh} \right)
$$

## **3. Practical Applications**

### **3.1 Ballistics and Engineering**
- Used in artillery, missile trajectories, and aerospace design.
- Essential for optimizing launch parameters in rocket science.

### **3.2 Sports and Mechanics**
- Determining optimal angles in sports such as javelin, golf, and basketball.
- Improving accuracy and performance in long-range shooting.

### **3.3 Air Resistance and Real-World Effects**
- In real conditions, drag force reduces the horizontal range.
- The Magnus effect in spinning projectiles influences trajectory.

## **4. Newton’s Contributions to Projectile Motion**

### **4.1 Newton’s Laws**

1. **First Law:** A projectile continues in motion unless acted upon by an external force.
2. **Second Law:** The force acting on the projectile causes acceleration:
   
   $$
   F = ma
   $$
   
3. **Third Law:** The force exerted on a projectile has an equal and opposite reaction on the launcher.

### **4.2 Universal Gravitation**

Newton’s Law of Universal Gravitation explains why projectiles follow a curved path:

$$
F = G \frac{m_1 m_2}{r^2}
$$

where \( G \) is the gravitational constant.

## **5. Python Implementation**

import numpy as np
import matplotlib.pyplot as plt

def projectile_range(v0, theta, g=9.81):
    return (v0**2 * np.sin(2 * np.radians(theta))) / g

angles = np.linspace(0, 90, 100)
v0 = 20  # Initial velocity in m/s
ranges = projectile_range(v0, angles)

plt.figure(figsize=(8,6))
plt.plot(angles, ranges, label=f'Initial Velocity = {v0} m/s')
plt.axvline(45, color='r', linestyle='--', label='Optimal Angle')
plt.xlabel("Launch Angle (degrees)")
plt.ylabel("Range (m)")
plt.title("Effect of Launch Angle on Projectile Range")
plt.legend()
plt.grid(True)
plt.show()
import matplotlib.pyplot as plt

def projectile_range(v0, theta, g=9.81):
    return (v0**2 * np.sin(2 * np.radians(theta))) / g

angles = np.linspace(0, 90, 100)
v0 = 20  # Initial velocity in m/s
ranges = projectile_range(v0, angles)

plt.figure(figsize=(8,6))
plt.plot(angles, ranges, label=f'Initial Velocity = {v0} m/s')
plt.axvline(45, color='r', linestyle='--', label='Optimal Angle')
plt.xlabel("Launch Angle (degrees)")
plt.ylabel("Range (m)")
plt.title("Effect of Launch Angle on Projectile Range")
plt.legend()
plt.grid()
plt.show()
![image](https://github.com/user-attachments/assets/fdffd1cb-55d7-4aa1-95c7-1d4f00f15666)


