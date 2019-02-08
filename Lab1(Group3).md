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
![lab1](https://github.com/allisontran/Lab-1/blob/master/Lab1Figure(Group3).png)
Figure 1: Linear Regression

slope = 0.04793591266894401
intercept = 0.6213770978761325
$$y=0.04793591266894401x+0.6213770978761325$$

2) "Does absorbance increase linearly with concentration of the red dye?"

Yes, absorbance increases linearly with concentration until a certain threshold where the solution has become opaque. After removing the last two data points (that are past the mentioned threshold), our experimental data roughly fits a linear regression model as shown in figure 1; its lack of accuracy is due to experimental error, but a general linear shape can be seen from the figure generated from the data.

3) What is the value of the extinction coefficient, ε?

The extinction coefficient is calculated by A = εbc. Since the data is meant to model a linear trend, ε = A/bc can be calculated using any data point on the line. Using the second data point:

$$\epsilon=\frac{(0.437)}{(19mm)*(1mg/L)} = 0.023L/(mm)(mg)$$

4) Did you use interpolation or extrapolation to get the concentration of the unknown?

We used interpolation to get the concentration of the unknown because the adsorption value of the unknown solution was within the values that we had collected data for.

5) What measurement controls the accuracy of the density measurement for the NaCl solution?

The accuracy of the density measurement for the NaCl solution is controlled by the mass of 100mL of 1 M NaCl solution, which was measured by calculating the difference between the measured mass of the empty 100mL flask and the measured mass of the flask and the 1M solution mixed in the flask.

6) What density did you expect (see prelab 2)?

The density that we calculated in the prelab is 997.6985kg/m^3
$$density=(0.6985*1M)+\frac{997kg}{m^3}=\frac{997.6985kg}{m^3}$$

7) Approximately what should the accuracy be for the density measurement?

Constants:
Mass_Flask_Empty= 21.093g;
Mass_Flask_Solution= 124.688g

$$Mass\,Solution= Mass\,Flask\,Solution - Mass\,Flask\,Empty$$

Density_Calculated= Mass_Solution/(0.1L);
Density_Actual= 997.7kg/m^3

$$percent\,error=\frac{(Density\,Calculated - Density\,Actual)*100}{Density\,Actual}=0.038$$

The percent error for the density measurement is around 3.8%

8) Don’t forget to write a brief paragraph on conclusions and on suggestions using Markdown (make sure you connect your conclusions to your objectives for doing the research)

Due to accuracy errors during data collection, we were unable to get the desired result of a linear trend between the absorbance and concentration of the solution. Though the data was initially linear for the first few concentrations, the trend became overall exponential when the last few points were factored in. We believe that the experimental errors were due to inconsistencies with the equipment that was used to measure the absorbance of the solution samples, as we got different readings when testing the same sample multiple times. To verify our data, we remade several of our solution samples and tested them again, and used the best data from each trial. In the end, we were able to conclude that our data roughly fits a linear regression model when using smaller concentrations of the red dye. If we were to repeat the experiment, it would be helpful to have clearer instructions for setting up and using the photometer, especially in terms of pulling the sample up through the tube using the syringe and checking for air bubbles. The ProCoDA software was relatively easy to understand for data collection, so most of the changes to the procedure would be in terms of using and operating the physical lab equipment. Regardless, we completed our experimental objectives in the sense that we learned how to calibrate and use various lab equipment, gained proficiency in regard to pipetting and preparing dillusions, and learned how to measure concentrations using a photometer.

```
