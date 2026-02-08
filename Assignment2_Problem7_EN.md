# Assignment 2 - Problem 7 (English)

## Problem Statement
For a Si n+p junction at RT. N_A = 10^17 cm^-3, D_n = 19 cm^2/s and A_E = 10^-5 cm^2. The width between the boundary of SCR in p-Si and Ohmic contact metal electrode of p-Si is 3 μm. All the carriers recombine at the Ohmic contact metal electrode of p-Si. Assuming that the current flowing in this junction is 0.5 mA, determine the total number of stored charges in the quasi-neutral region of p-Si.

## Solution

### Given Data
- T = 300 K
- N_A = 10^17 cm^-3
- D_n = 19 cm^2/s
- A_E = 10^-5 cm^2
- W_B = 3 μm = 3×10^-4 cm (base width)
- I = 0.5 mA = 5×10^-4 A
- n_i = 1.5×10^10 cm^-3

### Analysis

This is a short diode problem because all carriers recombine at the back contact, meaning the quasi-neutral region width is finite (W_B = 3 μm).

For a short diode, the minority carrier distribution is approximately linear rather than exponential.

### Minority Carrier Distribution

For a short base with boundary conditions:
- At x = 0: Δn_p(0) = n_p0(e^(qV_A/kT) - 1)
- At x = W_B: Δn_p(W_B) = 0 (all carriers recombine at contact)

The distribution is linear:
```
Δn_p(x) = Δn_p(0) × (1 - x/W_B)
```

### Current Equation

For a short diode, the current density is:
```
J_n = qD_n × Δn_p(0)/W_B
```

Therefore:
```
I = A_E × J_n = qD_n × A_E × Δn_p(0)/W_B
```

Solving for Δn_p(0):
```
Δn_p(0) = I × W_B / (qD_n × A_E)
Δn_p(0) = 5×10^-4 × 3×10^-4 / (1.6×10^-19 × 19 × 10^-5)
Δn_p(0) = 1.5×10^-7 / (3.04×10^-23)
Δn_p(0) = 4.93×10^15 cm^-3
```

### Stored Charge Calculation

The total stored minority carrier charge is:
```
Q = q × A_E × ∫[0 to W_B] Δn_p(x) dx
```

For linear distribution:
```
Q = q × A_E × ∫[0 to W_B] Δn_p(0) × (1 - x/W_B) dx
Q = q × A_E × Δn_p(0) × [x - x^2/(2W_B)]|[0 to W_B]
Q = q × A_E × Δn_p(0) × [W_B - W_B/2]
Q = q × A_E × Δn_p(0) × W_B/2
```

Substituting values:
```
Q = 1.6×10^-19 × 10^-5 × 4.93×10^15 × 3×10^-4 / 2
Q = 1.6×10^-19 × 10^-5 × 4.93×10^15 × 1.5×10^-4
Q = 1.18×10^-12 C
```

Alternatively, using the transit time relationship:
```
Q = I × τ_t
```

Where the transit time for a short diode is:
```
τ_t = W_B^2 / (2D_n) = (3×10^-4)^2 / (2 × 19)
τ_t = 9×10^-8 / 38 = 2.37×10^-9 s
```

Therefore:
```
Q = 5×10^-4 × 2.37×10^-9 = 1.18×10^-12 C
```

### Total Number of Stored Charges

```
N = Q/q = 1.18×10^-12 / 1.6×10^-19
N = 7.4×10^6 electrons
```

## Summary
The total number of stored charges in the quasi-neutral region of p-Si is approximately **7.4 × 10^6 electrons** or the stored charge is **1.18 pC**.
