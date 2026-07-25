# Ex.No: 1B                     CONVERSION OF NON STATIONARY TO STATIONARY DATA
# Date:  25-07-2026

### AIM:
To perform regular differncing,seasonal adjustment and log transformatio on international airline passenger data
### ALGORITHM:
1. Import the required packages like pandas and numpy
2. Read the data using the pandas
3. Perform the data preprocessing if needed and apply regular differncing,seasonal adjustment,log transformation.
4. Plot the data according to need, before and after regular differncing,seasonal adjustment,log transformation.
5. Display the overall results.
### PROGRAM:
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt


data = pd.read_csv(r"C:\Users\admin\Downloads\bmw (1).csv")

# Sort by year
data = data.sort_values("year").reset_index(drop=True)

# First-order differencing
data['price_diff'] = data['price'].diff()

# Log transformation
data['price_log'] = np.log(data['price'])

# Log differencing
data['price_log_diff'] = data['price_log'].diff()

plt.figure(figsize=(14,12))

plt.subplot(4,1,1)
plt.plot(data['price'])
plt.title("Original Price")
plt.ylabel("Price")

plt.subplot(4,1,2)
plt.plot(data['price_diff'])
plt.title("First Order Differencing")
plt.ylabel("Differenced Price")

plt.subplot(4,1,3)
plt.plot(data['price_log'])
plt.title("Log Transformation")
plt.ylabel("Log Price")

plt.subplot(4,1,4)
plt.plot(data['price_log_diff'])
plt.title("Log Transformation + Differencing")
plt.ylabel("Log Difference")

plt.tight_layout()
plt.show()

# Display transformed data
print(data[['year','price','price_diff','price_log','price_log_diff']].head())
```

### OUTPUT:


REGULAR DIFFERENCING:

<img width="1152" height="236" alt="image" src="https://github.com/user-attachments/assets/afdeeed9-f731-4d6d-b61e-279e3791af41" />

<img width="1142" height="242" alt="image" src="https://github.com/user-attachments/assets/1038c93a-4b4f-47f1-9319-ce6c5feda29d" />

SEASONAL ADJUSTMENT:

<img width="1082" height="233" alt="image" src="https://github.com/user-attachments/assets/a0c3766f-8bd0-42ed-90b6-ba287eb116bf" />


LOG TRANSFORMATION:

<img width="1191" height="358" alt="image" src="https://github.com/user-attachments/assets/39509b45-099d-440a-aabf-2c50cb5ccb3d" />


### RESULT:
Thus we have created the python code for the conversion of non stationary to stationary data on international airline passenger
data.
