# Ex.No: 01A PLOT A TIME SERIES DATA
###  Date: 25-04-2026
### Reg no: 212224240130
### Name: Ramitha Chowdary S
# AIM:
To Develop a python program to Plot a time series data (population/ market price of a commodity
/temperature.
# ALGORITHM:
1. Import the required packages like pandas and matplot
2. Read the dataset using the pandas
3. Calculate the mean for the respective column.
4. Plot the data according to need and can be altered monthly, or yearly.
5. Display the graph.
# PROGRAM:
```python
from matplotlib import pyplot as plt
import pandas as pd

# Load the dataset
df = pd.read_csv("test.csv")

# Display first few rows
print(df.head())

# Convert 'Month' column to datetime
df['Month'] = pd.to_datetime(df['Month'])

# Check data types
print(df.dtypes)

# Set 'Month' as the index
df.set_index('Month', inplace=True)

# Resample to daily frequency and interpolate
df_resampled = df['#Passengers'].resample('D').interpolate()

# Plot the time series
df_resampled.plot(kind='line', label='Total Passengers', color='black')
plt.title('Time Series Plot of Number of Passengers Each Day')
plt.xlabel('Day')
plt.ylabel('Number of Passengers')
plt.legend()
plt.grid(True)
plt.tight_layout()
plt.show()
```
# OUTPUT:
<img width="932" height="910" alt="image" src="https://github.com/user-attachments/assets/699d0eab-edba-48ee-821f-b81ad491bbe4" />

# RESULT:
Thus we have created the python code for plotting the time series of given data.
