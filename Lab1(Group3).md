# Lab-1
``` python
from aguaclara.core.units import unit_registry as u
import numpy as np
import matplotlib.pyplot as plt
import pandas as pd
from scipy import stats
data_file_path="https://raw.githubusercontent.com/allisontran/Lab-1/master/lab1data.tsv"
df = pd.read_csv(data_file_path,delimiter='\t')
print(df)
list(df)
columns=df.columns
print(columns)
x = df.iloc[:,0].values
x
y = df.iloc[:,1].values
y
slope, intercept, r_value, p_value, std_err = stats.linregress(x,y)
fig, ax = plt.subplots()
ax.plot(x, y, 'ro', )
ax.plot(x, slope * x + intercept, 'k-', )
ax.set(xlabel=list(df)[0])
ax.set(ylabel=list(df)[1])
ax.legend(['Measured', 'Linear regression'])
ax.grid(True)
plt.show()

```
slope = 0.04793591266894401
intercept = 0.6213770978761325
$$y=0.04793591266894401x+0.6213770978761325$$

2) "Does absorbance increase linearly with concentration of the red dye?"
Yes, absorbance increases linearly with concentration until a certain threshold where the solution has become opaque. After removing the last two data points (that are past the mentioned threshold), our experimental data roughly fits a linear regression model; its lack of accuracy is due to experimental error, but a general linear shape can be seen from the graph generated from the data.

3) What is the value of the extinction coefficient, ε?

4) Did you use interpolation or extrapolation to get the concentration of the unknown?
We used interpolation to get the concentration of the unknown because the adsorption value of the unknown solution was within the valuess that we had colleceted data for.

5) What measurement controls the accuracy of the density measurement for the NaCl solution?

6) What density did you expect (see prelab 2)?
The density that we calculated in the prelab is 997.6985kg/m^3

7) Approximately what should the accuracy be for the density measurement?
The percent error for the density measurement is around 3.8%

8) Don’t forget to write a brief paragraph on conclusions and on suggestions using Markdown (make sure you connect your conclusions to your objectives for doing the research)
suggestions on:
improving the data acquisition software
modifying the experimental apparatus
making the experiment easier to understand
modifying the experiment to include some new experimental aspect related to the main topic
alternate ways to analyze the data

```
