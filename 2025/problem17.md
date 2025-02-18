## Solution: IIT JAM MS 2025 Problem 17 (MCQ2)
#### Answer: (D) by [Cheenta School of Statistics and Data Science](https://www.cheenta.com/cheenta-statistics-coaching-msc/)

-----
* [2025 IIT JAM MS Paper](https://drive.google.com/file/d/1lI9Dwthnycrx31mcVLDZoi3ERYe3jm4m/view?usp=sharing)
-----

* Observe that $Z_1, Z_2 \sim N(0, 2\sigma^2)$ because $V(Z_1) = V(Z_2) = V(X_1) + V(X_2) = 2\sigma^2$, since $X_1, X_2$ are identically distributed.
* Since $Cov(Z_1, Z_2) = 0$, and $Z_1, Z_2$ are normally distributed, $Z_1, Z_2$ are independent, and hence iid.
* Since $Z_1, Z_2$ are iid, $\frac{Z_1}{Z_2} \sim \frac{Z_2}{Z_1}$.
* Therefore, $P(\frac{Z_1}{Z_2} < 1) = P(\frac{Z_2}{Z_1} < 1) = \frac{1}{2}$, because $\{\frac{Z_1}{Z_2} < 1\} \cup \{\frac{Z_2}{Z_1} < 1\} \cup \{\frac{Z_1}{Z_2} = 1\} = \mathbb{R}$, and $P(\frac{Z_1}{Z_2} = 1) = 0$, since $\frac{Z_1}{Z_2}$ is continuous random variable.
* Take $A = Z_1^2 + Z_2^2 < 1$, $B = \frac{Z_2}{Z_1} < 1$, and $B^{c} = \frac{Z_2}{Z_1} \geq 1$. Then, show that $P(A \mid B) = P(A \mid B^{c})$ due to the fact $\frac{Z_1}{Z_2} \sim \frac{Z_2}{Z_1}$. Thus, $P(A \mid B) = \frac{P(A)}{P(B)} \neq P(A)$ (why? do some conditional probability calculations). Hence, $Z_1^2 + Z_2^2$ is not independent of $\frac{Z_2}{Z_1}$.

#### Python code for computing conditional probability

```
import numpy as np

# Number of samples for Monte Carlo simulation
n_samples = 10**7

# Define different standard deviations
sigma = 5.0

# Generate iid standard normal samples
Z1 = np.random.normal(10, sigma, n_samples)
Z2 = np.random.normal(10, sigma, n_samples)

# Compute conditions
condition1 = Z1**2 + Z2**2 < 200 # P(Z1^2 + Z2^2 < 1)
condition2 = Z1 / Z2 > 5      # P(Z1/Z2 < 1)

# Compute probabilities
P_A = np.mean(condition1)
print(P_A)

P_B = np.mean(condition2)
print(P_B)

# Compute joint probability P(A ∩ B)
P_A_intersect_B = np.mean(condition1 & condition2)
print(P_A_intersect_B)

# Compute conditional probability P(A | B) directly
P_A_given_B = P_A_intersect_B / P_B
print(P_A_given_B)
```
