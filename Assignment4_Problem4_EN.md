# Assignment 4 - Problem 4 (English)

## Problem Statement
For a NMOSFET, W/L = 5, t_ox = 20 nm, μ_n = 600 cm²/(V·s), and the square law theory is utilized.
1. When the device is working at the deep linear region (V_DS is very small but non-zero), the on-resistance is 500 Ω, determine the Q_inv
2. Determine the required V_GS - V_T for making on-resistance 500 Ω

## Solution

### Given Data
- W/L = 5
- t_ox = 20 nm = 20×10^-7 cm
- μ_n = 600 cm²/(V·s)
- R_on = 500 Ω
- ε_ox = 3.45×10^-13 F/cm

### Part 1: Determine Q_inv

In the deep linear region (V_DS → 0), the MOSFET acts as a resistor.

The on-resistance is:
```
R_on = 1 / (μ_n × (W/L) × |Q_inv|)
```

Solving for |Q_inv|:
```
|Q_inv| = 1 / (μ_n × (W/L) × R_on)
|Q_inv| = 1 / (600 × 5 × 500)
|Q_inv| = 1 / (1.5×10^6)
|Q_inv| = 6.67×10^-7 C/cm²
```

### Part 2: Determine V_GS - V_T

The inversion charge is related to gate voltage by:
```
Q_inv = -C_ox × (V_GS - V_T)
```

Therefore:
```
V_GS - V_T = |Q_inv| / C_ox
```

Calculate C_ox:
```
C_ox = ε_ox / t_ox
C_ox = 3.45×10^-13 / (20×10^-7)
C_ox = 1.725×10^-7 F/cm²
```

Now:
```
V_GS - V_T = 6.67×10^-7 / 1.725×10^-7
V_GS - V_T = 3.87 V ≈ 3.9 V
```

### Verification

Using the linear region equation with V_DS → 0:
```
g_ds = ∂I_D/∂V_DS = μ_n × C_ox × (W/L) × (V_GS - V_T)
```

The on-resistance:
```
R_on = 1/g_ds = 1 / [μ_n × C_ox × (W/L) × (V_GS - V_T)]
R_on = 1 / [600 × 1.725×10^-7 × 5 × 3.87]
R_on = 1 / (2.00×10^-3)
R_on = 500 Ω ✓
```

## Summary

1. |Q_inv| = 6.67×10^-7 C/cm² = 0.667 μC/cm²
2. V_GS - V_T = 3.9 V
