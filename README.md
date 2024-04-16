# assignment2
# Build 99% Confidence Interval Using Sample Standard Deviation
Using Sample Standard Deviation
import numpy as np
from scipy.stats import t
data = [1.13, 1.55, 1.43, 0.92, 1.25, 1.36, 1.32, 0.85, 1.07, 1.48, 1.20, 1.33, 1.18, 1.22, 1.29]
sample_mean = np.mean(data)
sample_std = np.std(data, ddof=1) 
n = len(data)
t_value = t.ppf(0.995, df=n-1)
margin_of_error = t_value * (sample_std / np.sqrt(n))
lower_bound = sample_mean - margin_of_error
upper_bound = sample_mean + margin_of_error
print("99% Confidence Interval for the Mean Number of Characters Printed:")
print(f"({lower_bound:.4f}, {upper_bound:.4f})")

# Build 99% Confidence Interval Using Known Population Standard Deviation

import numpy as np
data = [1.13, 1.55, 1.43, 0.92, 1.25, 1.36, 1.32, 0.85, 1.07, 1.48, 1.20, 1.33, 1.18, 1.22, 1.29]
population_std = 0.2 
sample_mean = np.mean(data)
n = len(data)
z_value = 2.576
margin_of_error = z_value * (population_std / np.sqrt(n))
lower_bound = sample_mean - margin_of_error
upper_bound = sample_mean + margin_of_error
print("99% Confidence Interval for the Mean Number of Characters Printed (with known population standard deviation):")
print(f"({lower_bound:.4f}, {upper_bound:.4f}) million characters")
