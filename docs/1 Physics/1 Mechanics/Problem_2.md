# Problem 2
# **Projectile Motion: Theory, Formulas, and Examples**

## **1. Introduction**
Projectile motion refers to the motion of an object under the influence of gravity, assuming no air resistance. It consists of two independent components:
- **Horizontal Motion**: Constant velocity motion.
- **Vertical Motion**: Uniformly accelerated motion due to gravity.

## **2. Useful Definitions**
- **Initial velocity** ($v_0$): The speed at which the object is launched.
- **Angle of projection** ($\theta$): The angle at which the object is launched with respect to the horizontal.
- **Acceleration due to gravity** ($g$): The constant acceleration experienced due to Earth's gravity. Typically, $g = 9.81 \, m/s^2$.
- **Time of flight** ($t_f$): The total time the projectile remains in the air.
- **Maximum height** ($H$): The highest vertical position the projectile reaches.
- **Range** ($R$): The horizontal distance covered by the projectile.

---

## **3. Governing Equations of Motion**
### **(a) Horizontal Motion**
Since there is no acceleration in the horizontal direction:
$$ x = v_0 \cos\theta \cdot t $$

### **(b) Vertical Motion**
Using kinematic equations for motion under gravity:
$$ y = v_0 \sin\theta \cdot t - \frac{1}{2} g t^2 $$

---

## **4. Key Formulas**
### **(a) Time of Flight**
The projectile reaches the ground when $y = 0$. Solving for $t$:
$$ t_f = \frac{2 v_0 \sin\theta}{g} $$

### **(b) Maximum Height**
The maximum height occurs when vertical velocity becomes zero:
$$ H = \frac{v_0^2 \sin^2\theta}{2g} $$

### **(c) Range of the Projectile**
The horizontal distance traveled before returning to the ground:
$$ R = \frac{v_0^2 \sin 2\theta}{g} $$

### **(d) Velocity Components at Any Time**
- Horizontal velocity: $ v_x = v_0 \cos\theta $
- Vertical velocity: $ v_y = v_0 \sin\theta - g t $

---

## **5. Examples**
### **Example 1: Finding Time of Flight and Range**
A projectile is launched with an initial velocity of $v_0 = 20$ m/s at an angle of $45^\circ$. Find:
1. The time of flight.
2. The range of the projectile.

#### **Solution:**
Given:
- $v_0 = 20$ m/s
- $\theta = 45^\circ$
- $g = 9.81$ m/s²

**Step 1: Compute Time of Flight**
$$
t_f = \frac{2 v_0 \sin\theta}{g} = \frac{2 \times 20 \times \sin 45^\circ}{9.81}
$$
$$
t_f \approx 2.87 \text{ s}
$$

**Step 2: Compute Range**
$$
R = \frac{v_0^2 \sin 2\theta}{g} = \frac{20^2 \sin 90^\circ}{9.81}
$$
$$
R \approx 40.8 \text{ m}
$$

---

### **Example 2: Maximum Height**
A ball is thrown with an initial velocity of $15$ m/s at an angle of $30^\circ$. Find the maximum height.

**Solution:**
$$
H = \frac{v_0^2 \sin^2\theta}{2g}
$$
$$
H = \frac{15^2 \sin^2 30^\circ}{2 \times 9.81}
$$
$$
H \approx 2.86 \text{ m}
$$

---

## **6. Python Simulation**
You can simulate projectile motion using Python:

```python
import numpy as np
import matplotlib.pyplot as plt

def projectile_trajectory(v0, theta, g=9.81):
    theta_rad = np.radians(theta)
    t_flight = 2 * v0 * np.sin(theta_rad) / g
    t = np.linspace(0, t_flight, num=100)
    
    x = v0 * np.cos(theta_rad) * t
    y = v0 * np.sin(theta_rad) * t - 0.5 * g * t**2

    return x, y

# Example: Projectile with v0 = 20 m/s and θ = 45°
x_vals, y_vals = projectile_trajectory(20, 45)

plt.plot(x_vals, y_vals)
plt.xlabel("Horizontal Distance (m)")
plt.ylabel("Vertical Distance (m)")
plt.title("Projectile Motion")
plt.show()

