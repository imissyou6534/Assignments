# Assignment 2 - Problem 1 (English)

## Problem Statement
Use the depletion region assumption to analyze and discuss the linearly graded junction. For a pn junction with dopants linearly distributed in the depletion region N_D - N_A = αx and applied bias V_A. Determine the formulas for:
1. Electric field
2. Electric potential
3. Built-in potential
4. Depletion region width

## Solution

### 1. Electric Field

For a linearly graded junction with N_D - N_A = αx, where α is the gradient constant.

Using Poisson's equation:
```
dE/dx = -ρ/ε_s = -q(N_D - N_A)/ε_s = -qαx/ε_s
```

Integrating from 0 to x:
```
E(x) = -qαx²/(2ε_s) + C
```

At x = 0, by symmetry in a linearly graded junction, E(0) = 0, so C = 0.

Maximum electric field occurs at x = 0:
```
E_max = E(0) = 0 (by symmetry consideration)
```

Actually, for proper boundary conditions, let's consider x_p (p-side extent) and x_n (n-side extent).

The charge density is:
```
ρ(x) = qαx  (for -x_p < x < x_n)
```

Using Poisson's equation and proper boundary conditions:
```
E(x) = -qα/(2ε_s) * (x² - x_n²)  for 0 < x < x_n
E(x) = -qα/(2ε_s) * (x² - x_p²)  for -x_p < x < 0
```

At x = 0 (junction), the maximum field is:
```
E_max = qα/(2ε_s) * (x_n² + x_p²)/2
```

By charge neutrality: x_p = x_n for linearly graded junction, so:
```
E_max = qαx_n²/ε_s
```

### 2. Electric Potential

Integrating the electric field:
```
V(x) = -∫E(x)dx
```

For the n-side (0 < x < x_n):
```
V(x) = qα/(2ε_s) * [x³/3 - x_n²x] + C
```

For the p-side (-x_p < x < 0):
```
V(x) = qα/(2ε_s) * [x³/3 + x_p²x] + C'
```

### 3. Built-in Potential

The built-in potential V_bi is the total potential drop across the junction:
```
V_bi = V(x_n) - V(-x_p)
```

For a linearly graded junction with x_p = x_n = W/2:
```
V_bi = qα/(12ε_s) * W³
```

Or in terms of x_n:
```
V_bi = qα/(3ε_s) * x_n³
```

### 4. Depletion Region Width

With applied bias V_A, the total voltage is V_bi - V_A.

From the relation:
```
V_bi - V_A = qα/(3ε_s) * W³
```

Solving for W:
```
W = [3ε_s(V_bi - V_A)/(qα)]^(1/3)
```

This is the total depletion width for a linearly graded junction under applied bias.

For thermal equilibrium (V_A = 0):
```
W₀ = [3ε_sV_bi/(qα)]^(1/3)
```

## Summary

The linearly graded junction differs from the abrupt junction in that:
- The depletion width varies as (V_bi - V_A)^(1/3) instead of (V_bi - V_A)^(1/2)
- The electric field profile is parabolic rather than linear
- The built-in potential has a cubic dependence on depletion width
