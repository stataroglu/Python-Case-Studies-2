```python

import numpy as np
import matplotlib.pyplot as plt


# Assigning the x, y and z values
x = np.linspace(0, 6*np.pi, 100)
y = (10*((x-1)**4))*(np.exp(-x))
ξ = np.random.uniform(0,1,1)[0]
z = ξ*((np.sin(x))**2)


# Plot Settings
fig, axis1 = plt.subplots()
plt.title("y(x) and z(x) values", fontsize=18)

# X Axis Settings
plt.xlim(left=0)
plt.xlim(right=max(x))
axis1.set_xticks(np.linspace(0,20,9))

# Primary Axis Settings
color = "C0"
axis1.plot(x, y, color, label="y(x)")
axis1.set_xlabel("x ", fontsize= 14)
axis1.set_ylabel("y(x)", color=color, fontsize= 14)
axis1.tick_params(axis="y", labelcolor=color)
axis1.set_yticks(np.linspace(0,20,9))
plt.ylim(0,20)
plt.grid(True)

# Secondary Axis Settings
color = "C1"
axis2 = axis1.twinx()
axis2.plot(x, z, color, label="z(x)")
axis2.set_ylabel("z(x)", color=color, fontsize= 14)
axis2.tick_params(axis="y", labelcolor=color)
axis2.set_yticks(np.linspace(0,1,9))
plt.ylim(0,1)

# Adding Legend
lines, labels = axis1.get_legend_handles_labels()
lines2, labels2 = axis2.get_legend_handles_labels()
axis2.legend(lines + lines2, labels + labels2, loc="best")

# Plotting All
plt.show()
```

![Image](https://raw.githubusercontent.com/SeckinTataroglu/Python-Case-Studies-2/master/answers_task_1_img.png)
