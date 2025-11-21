### Adding Grid Lines To A Figure 
---

## **1. Importing Required Libraries**

```python
import matplotlib.pyplot as plt
import pandas as pd
```

* **pandas** is used to create and manage structured data (tables).
* **matplotlib.pyplot** is used for creating graphs and plots.

---

## **2. Creating the Data**

```python
data ={
    "Cricket_bat": ["SG", "CA","SS"],
    "MRP": [1000, 2000, 3000],
    "WEIGHT": [1100, 1300, 1250]
}
```

A dictionary is created with:

* **Cricket_bat** → names of bat brands
* **MRP** → their prices
* **WEIGHT** → their weights

---

## **3. Creating a DataFrame**

```python
dataFrame = pd.DataFrame(data)
```

This converts the dictionary into a **table-like structure** called a DataFrame:

| Cricket_bat | MRP  | WEIGHT |
| ----------- | ---- | ------ |
| SG          | 1000 | 1100   |
| CA          | 2000 | 1300   |
| SS          | 3000 | 1250   |

---

## **4. Plotting the Line Graph**

```python
plt.plot(dataFrame["Cricket_bat"], dataFrame["MRP"], dataFrame["WEIGHT"])
```

### ⚠ **Problem in your code:**

`plt.plot()` expects **x values** and **one y-value series**, but you passed **two y-value series**.
This will cause an error.

Correct usages include:

* Plot one line:
  `plt.plot(x, y1)`
* Plot multiple lines:
  `plt.plot(x, y1); plt.plot(x, y2)`

---

## **5. Adding a Grid**

```python
plt.grid()
```

This displays grid lines on the graph for better readability.

---

## **6. Show the Plot**

```python
plt.show()
```

Displays the graph window.

---

# ✔ Corrected Version of Your Code

If you want to plot **MRP** and **WEIGHT** on the same graph:

```python
import matplotlib.pyplot as plt
import pandas as pd

data = {
    "Cricket_bat": ["SG", "CA", "SS"],
    "MRP": [1000, 2000, 3000],
    "WEIGHT": [1100, 1300, 1250]
}

dataFrame = pd.DataFrame(data)

plt.plot(dataFrame["Cricket_bat"], dataFrame["MRP"], label="MRP")
plt.plot(dataFrame["Cricket_bat"], dataFrame["WEIGHT"], label="Weight")
plt.grid()
plt.legend()
plt.show()
```

---

