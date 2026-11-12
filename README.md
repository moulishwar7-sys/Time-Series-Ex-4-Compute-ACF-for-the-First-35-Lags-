# Time-Series-Ex-4-Compute-ACF-for-the-First-35-Lags-

# AIM:
To compute and plot the AutoCorrelation Function (ACF) of a time-series dataset for the first 35 lags and use the ACF pattern to identify a suitable time-series model.

# PROGRAM:
```
import pandas as pd
import matplotlib.pyplot as plt
from statsmodels.tsa.stattools import acf
from statsmodels.graphics.tsaplots import plot_acf

# Step 1: Create time-series data (Monthly website visitors in thousands)
data = [
 50, 55, 60, 58, 62, 70, 75, 72, 68, 60, 52, 58,
 62, 68, 74, 71, 78, 85, 90, 88, 82, 75, 65, 72,
 76, 82, 88, 85, 92, 100, 108, 105, 98, 90, 80, 88,
 92, 98, 105, 102, 110, 120
]
series = pd.Series(data)

# Step 2: Plot time series
plt.figure(figsize=(10, 4))
plt.plot(series, marker='o')
plt.title("Monthly Website Traffic")
plt.xlabel("Time (Months)")
plt.ylabel("Visitors (in thousands)")
plt.show()

# Step 3: Calculate ACF for first 35 lags
acf_values = acf(series, nlags=35)

# Step 4: Display ACF values
print("ACF Values:")
for lag, value in enumerate(acf_values):
 print("Lag", lag, ":", round(value, 4))

# Step 5: Plot ACF
plt.figure(figsize=(12, 5))
plot_acf(series, lags=35)
plt.title("ACF for First 35 Lags - Website Traffic")
plt.xlabel("Lag")
plt.ylabel("Autocorrelation")
plt.show()

```

# OUTPUT:

<img width="871" height="431" alt="image" src="https://github.com/user-attachments/assets/4598f490-c061-4aa8-9c20-438b7aba3c79" />

<img width="547" height="730" alt="image" src="https://github.com/user-attachments/assets/ad477426-3242-489d-8f5d-d21cd44be63c" />





