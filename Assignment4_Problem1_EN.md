# Assignment 4 - Problem 1 (English)

## Problem Statement
An ideal MOS structure is maintained at T = 300 K, t_ox = 0.1 μm, and the p-Si substrate doping concentration is N_A = 10^15 cm^-3. Determine:
1. Fermi potential φ_F
2. W_dep when semiconductor's surface potential φ_s = 2φ_F
3. E_s (surface electric field) when semiconductor's surface potential φ_s = 2φ_F
4. Threshold voltage V_T

## Solution

### Given Data
- T = 300 K
- t_ox = 0.1 μm = 10^-5 cm
- N_A = 10^15 cm^-3
- n_i = 1.5×10^10 cm^-3
- ε_ox = 3.9ε_0 = 3.45×10^-13 F/cm
- ε_s = 11.7ε_0 = 1.04×10^-12 F/cm

### Part 1: Fermi Potential φ_F

The Fermi potential is:
```
φ_F = (kT/q) × ln(N_A/n_i)
φ_F = 0.0259 × ln(10^15 / 1.5×10^10)
φ_F = 0.0259 × ln(6.67×10^4)
φ_F = 0.0259 × 11.11
φ_F = 0.288 V ≈ 0.29 V
```

### Part 2: Depletion Width W_dep at φ_s = 2φ_F

At strong inversion (φ_s = 2φ_F), the depletion width reaches its maximum:
```
W_dep,max = sqrt(4ε_s × φ_F / (qN_A))
W_dep,max = sqrt(4 × 1.04×10^-12 × 0.288 / (1.6×10^-19 × 10^15))
W_dep,max = sqrt(1.20×10^-12 / 1.6×10^-4)
W_dep,max = sqrt(7.5×10^-9)
W_dep,max = 8.66×10^-5 cm = 0.866 μm
```

### Part 3: Surface Electric Field E_s at φ_s = 2φ_F

The surface electric field is:
```
E_s = -sqrt(4qN_A × φ_F / ε_s)
E_s = -sqrt(4 × 1.6×10^-19 × 10^15 × 0.288 / 1.04×10^-12)
E_s = -sqrt(1.84×10^-4 / 1.04×10^-12)
E_s = -sqrt(1.77×10^8)
E_s = -1.33×10^4 V/cm
```

The magnitude is |E_s| = 1.33×10^4 V/cm.

### Part 4: Threshold Voltage V_T

For an ideal MOS structure (assuming n+ poly-Si gate or metal gate with appropriate work function):

```
V_T = V_FB + 2φ_F + (sqrt(4qε_s × N_A × φ_F)) / C_ox
```

For ideal MOS with n+ poly-Si gate on p-substrate:
```
V_FB ≈ 0 (ideal case)
```

Oxide capacitance per unit area:
```
C_ox = ε_ox / t_ox = 3.45×10^-13 / 10^-5 = 3.45×10^-8 F/cm²
```

Maximum depletion charge:
```
Q_dep,max = -qN_A × W_dep,max = -1.6×10^-19 × 10^15 × 8.66×10^-5
Q_dep,max = -1.39×10^-8 C/cm²
```

Threshold voltage:
```
V_T = 2φ_F + |Q_dep,max| / C_ox
V_T = 2 × 0.288 + 1.39×10^-8 / 3.45×10^-8
V_T = 0.576 + 0.403
V_T = 0.979 V ≈ 0.98 V
```

Alternatively:
```
V_T = 2φ_F + (2/C_ox) × sqrt(qε_s × N_A × φ_F)
V_T = 0.576 + (2 × 1.33×10^4 × 1.04×10^-12) / 3.45×10^-8
V_T = 0.576 + 0.402
V_T ≈ 0.98 V
```

## Summary

1. φ_F = 0.29 V
2. W_dep,max = 0.866 μm (at φ_s = 2φ_F)
3. |E_s| = 1.33×10^4 V/cm (at φ_s = 2φ_F)
4. V_T = 0.98 V
