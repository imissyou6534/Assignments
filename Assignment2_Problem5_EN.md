# Assignment 2 - Problem 5 (English)

## Problem Statement
For a Si pn abrupt junction at RT, the distribution of carrier concentrations is shown in the figure (not provided, but we can infer from typical problem).
1. Is this junction forward or reverse biased? Explain your reason.
2. Does low-level injection prevail in the quasi-neutral regions? Explain your reason.
3. Determine N_A and N_D.
4. Determine the applied bias V_A.

## Solution

### Assumptions
Since the figure is not provided, I'll provide a general approach for solving such problems.

### Part 1: Bias Direction

To determine if the junction is forward or reverse biased, examine:
- **Forward bias**: Minority carrier concentration at the junction boundary increases above equilibrium (Δn_p > 0, Δp_n > 0)
- **Reverse bias**: Minority carrier concentration at the junction boundary decreases below equilibrium (approaches zero)

**If Δp_n(x_n) > 0 and Δn_p(-x_p) > 0**: The junction is **forward biased**
**If p_n(x_n) << p_n0 or n_p(-x_p) << n_p0**: The junction is **reverse biased**

### Part 2: Low-Level Injection

Low-level injection means:
- Δn_p << p_p0 (in p-region)
- Δp_n << n_n0 (in n-region)

Where:
- p_p0 ≈ N_A (majority carriers in p-region)
- n_n0 ≈ N_D (majority carriers in n-region)

**Check**: If Δp_n << N_D and Δn_p << N_A, then low-level injection prevails.

Typically, for forward bias with V_A < 0.6V, low-level injection is maintained.

### Part 3: Determining N_A and N_D

From the carrier concentration diagram:
- **N_D** ≈ majority electron concentration in n-region (plateau level)
- **N_A** ≈ majority hole concentration in p-region (plateau level)

The minority carrier concentrations at equilibrium:
- p_n0 = n_i^2/N_D
- n_p0 = n_i^2/N_A

### Part 4: Determining Applied Bias V_A

From the minority carrier concentration at the junction boundary:

For holes in n-region:
```
p_n(x_n) = p_n0 × e^(qV_A/kT)
```

Therefore:
```
V_A = (kT/q) × ln(p_n(x_n)/p_n0)
V_A = (kT/q) × ln((p_n0 + Δp_n(x_n))/p_n0)
```

Similarly for electrons in p-region:
```
V_A = (kT/q) × ln(n_p(-x_p)/n_p0)
```

## Example Solution
Assuming typical values from a figure:
- N_D = 10^16 cm^-3 (from n-region plateau)
- N_A = 10^17 cm^-3 (from p-region plateau)
- p_n0 = (1.5×10^10)^2/10^16 = 2.25×10^4 cm^-3
- p_n(x_n) = 10^10 cm^-3 (from figure at junction boundary)

Then:
```
V_A = 0.0259 × ln(10^10/2.25×10^4)
V_A = 0.0259 × ln(4.44×10^5)
V_A = 0.0259 × 13.0
V_A ≈ 0.337 V (forward bias)
```

Low-level injection check:
```
Δp_n = 10^10 - 2.25×10^4 ≈ 10^10 cm^-3
N_D = 10^16 cm^-3
Δp_n << N_D ✓ (Low-level injection holds)
```

## Summary
The solution methodology depends on reading the carrier concentration diagram accurately to extract N_A, N_D, and minority carrier concentrations at the junction boundaries.
