# Assignment 2 - Problem 3 (English)

## Problem Statement
A Si pn abrupt junction at RT under thermal equilibrium condition has doping of N_A = 10^16 cm^-3 and N_D = 10^15 cm^-3. Determine:
1. V_bi
2. x_p, x_n and W_dep
3. E_max
4. Draw the figures for charge density, electric field and electric potential as a function of coordinate

## Solution

### Given Data
- T = 300 K (Room Temperature)
- N_A = 10^16 cm^-3
- N_D = 10^15 cm^-3
- For Si at 300K: n_i = 1.5 × 10^10 cm^-3, ε_s = 11.7ε_0 = 1.04 × 10^-12 F/cm

### Part 1: Built-in Potential V_bi

```
V_bi = (kT/q) * ln(N_A * N_D / n_i^2)
V_bi = 0.0259 * ln(10^16 × 10^15 / (1.5 × 10^10)^2)
V_bi = 0.0259 * ln(10^31 / 2.25 × 10^20)
V_bi = 0.0259 * ln(4.44 × 10^10)
V_bi = 0.0259 * 24.52
V_bi ≈ 0.635 V
```

### Part 2: Depletion Region Widths

Using charge neutrality: N_A * x_p = N_D * x_n

Total depletion width:
```
W_dep = x_p + x_n = sqrt(2ε_s * V_bi / q * (N_A + N_D)/(N_A * N_D))
W_dep = sqrt(2 × 1.04×10^-12 × 0.635 / 1.6×10^-19 × (10^16 + 10^15)/(10^16 × 10^15))
W_dep = sqrt(2 × 1.04×10^-12 × 0.635 / 1.6×10^-19 × 1.1×10^16/10^31)
W_dep = sqrt(1.32×10^-12 × 0.635 × 1.1×10^-15)
W_dep = sqrt(9.22×10^-28)
W_dep ≈ 3.04 × 10^-14 m
```

Let me recalculate more carefully:
```
W_dep = sqrt(2ε_s/q × V_bi × (N_A + N_D)/(N_A × N_D))
W_dep = sqrt(2 × 1.04×10^-12 / 1.6×10^-19 × 0.635 × 1.1×10^16/10^31)
W_dep = sqrt(1.3×10^7 × 0.635 × 1.1×10^-15)
W_dep = sqrt(9.07×10^-9)
W_dep ≈ 9.52 × 10^-5 cm = 0.952 μm
```

From charge neutrality:
```
x_n = W_dep × N_A/(N_A + N_D) = 0.952 × 10^16/(1.1×10^16) = 0.866 μm
x_p = W_dep × N_D/(N_A + N_D) = 0.952 × 10^15/(1.1×10^16) = 0.0866 μm
```

### Part 3: Maximum Electric Field

```
E_max = -qN_D*x_n/ε_s = -qN_A*x_p/ε_s
E_max = 1.6×10^-19 × 10^15 × 0.866×10^-4 / 1.04×10^-12
E_max = 1.33 × 10^4 V/cm
```

### Part 4: Figures

**Charge Density ρ(x):**
```
         |
   qN_D  |________________
         |                |
    0    |________________|________________
         |        -x_p    0    x_n
  -qN_A  |                |
         |________________|
         
ρ(x) = -qN_A  for -x_p < x < 0
ρ(x) = qN_D   for 0 < x < x_n
ρ(x) = 0      elsewhere
```

**Electric Field E(x):**
```
    E    |
    0    |     /\
         |    /  \
         |   /    \
  E_max  |  /______\______
         | -x_p    0    x_n
         
E(x) increases linearly from 0 to E_max (p-side)
E(x) decreases linearly from E_max to 0 (n-side)
Peak at junction (x=0)
```

**Electric Potential V(x):**
```
    V    |           _____
  V_bi   |          /
         |         /
         |        /
    0    |_______/________
         |-x_p   0    x_n
         
V(x) is parabolic in depletion region
Total drop = V_bi
```

## Summary
- V_bi = 0.635 V
- x_p = 0.087 μm
- x_n = 0.865 μm  
- W_dep = 0.952 μm
- E_max = 1.33 × 10^4 V/cm
