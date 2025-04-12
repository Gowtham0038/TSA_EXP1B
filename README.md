# Ex.No: 1B                     CONVERSION OF NON STATIONARY TO STATIONARY DATA
# Date: 31/03/2025
# Name: Gowtham C
# Reg.No: 212224240046

### AIM:
To perform regular differncing,seasonal adjustment and log transformatio on international airline passenger data
### ALGORITHM:
1. Import the required packages like pandas and numpy
2. Read the data using the pandas
3. Perform the data preprocessing if needed and apply regular differncing,seasonal adjustment,log transformation.
4. Plot the data according to need, before and after regular differncing,seasonal adjustment,log transformation.
5. Display the overall results.
### PROGRAM:
~~~
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from statsmodels.tsa.seasonal import seasonal_decompose

# Load the data
data = pd.read_csv("AirPassengers.csv")
# Create DataFrame
df = pd.DataFrame(data)

# Regular differencing
df['Regular Difference'] = df['#Passengers'].diff()

# Seasonal adjustment
result = seasonal_decompose(df['#Passengers'], model='additive', period=12)
df['Seasonal Adjustment'] = result.resid

# Log transformation
df['Log Transformation'] = np.log(df['#Passengers'])

# Plotting
plt.figure(figsize=(14, 10))

plt.subplot(4, 1, 1)
plt.plot(df['#Passengers'], label='Original')
plt.legend(loc='best')
plt.title('Original Data')

plt.subplot(4, 1, 2)
plt.plot(df['Regular Difference'], label='Regular Difference')
plt.legend(loc='best')
plt.title('Regular Differencing')

plt.subplot(4, 1, 3)
plt.plot(df['Seasonal Adjustment'], label='Seasonal Adjustment')
plt.legend(loc='best')
plt.title('Seasonal Adjustment')

plt.subplot(4, 1, 4)
plt.plot(df['Log Transformation'], label='Log Transformation')
plt.legend(loc='best')
plt.title('Log Transformation')

plt.tight_layout()
plt.show()

~~~

### OUTPUT:
ORIGINAL DATA
![428664840-1c9ebd2f-973a-41b4-ac1f-5778eec1f7d5](https://github.com/user-attachments/assets/4af4d787-311e-48ed-bd1b-bad26626009c)


REGULAR DIFFERENCING:
![428664882-40f55383-44c9-4667-8a78-59b611870b4b](https://github.com/user-attachments/assets/df1aad03-0b7a-4043-88e0-a3e310f7d206)


SEASONAL ADJUSTMENT:
![428664946-33f896d7-bc18-4e0f-854c-9beaf76d3816](https://github.com/user-attachments/assets/c6ebea98-f053-45b8-a28e-da76ade72ada)

### RESULT:
Thus we have created the python code for the conversion of non stationary to stationary data on international airline passenger data.

### Interpretation:
This is a Non stationary time series with Multiplicative Seasonality and Additive Trend
