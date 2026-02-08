# Assignment 4 - Problem 8 (English)

## Problem Statement
Assume that n+ poly-Si gate electrode is adopted for NMOSFET, t_ox = 1.1 nm, N_A = 10^18 cm^-3, Q_ox = 0. Determine:
1. V_T
2. Subthreshold swing S
3. I_off when W = 1 μm, L = 18 nm, considering that I_D = 100W/L (nA) when V_GS = V_T

## Solution

### Given Data
- n+ poly-Si gate
- t_ox = 1.1 nm = 1.1×10^-7 cm
- N_A = 10^18 cm^-3
- Q_ox = 0
- T = 300 K, n_i = 1.5×10^10 cm^-3
- ε_ox = 3.45×10^-13 F/cm
- ε_s = 1.04×10^-12 F/cm

### Preliminary Calculations

**Oxide capacitance:**
```
C_ox = ε_ox / t_ox = 3.45×10^-13 / (1.1×10^-7) = 3.136×10^-6 F/cm²
```

**Fermi potential:**
```
φ_F = (kT/q) × ln(N_A/n_i)
φ_F = 0.0259 × ln(10^18 / 1.5×10^10)
φ_F = 0.0259 × ln(6.67×10^7)
φ_F = 0.0259 × 18.02
φ_F = 0.467 V
```

### Part 1: Threshold Voltage V_T

For n+ poly-Si gate on p-substrate with Q_ox = 0:

```
V_T = 2φ_F + (1/C_ox) × sqrt(4qε_s × N_A × φ_F)
```

Calculate depletion charge:
```
Q_dep,max = -sqrt(4 × 1.6×10^-19 × 1.04×10^-12 × 10^18 × 0.467)
Q_dep,max = -sqrt(3.10×10^-13)
Q_dep,max = -5.57×10^-7 C/cm²
```

Threshold voltage:
```
V_T = 2 × 0.467 + 5.57×10^-7 / 3.136×10^-6
V_T = 0.934 + 0.178
V_T = 1.112 V ≈ 1.11 V
```

### Part 2: Subthreshold Swing S

The subthreshold swing is:
```
S = (kT/q) × ln(10) × (1 + C_d/C_ox)
```

Where C_d is the depletion capacitance:
```
C_d = ε_s / W_dep,max
```

Maximum depletion width:
```
W_dep,max = sqrt(4ε_s × φ_F / (qN_A))
W_dep,max = sqrt(4 × 1.04×10^-12 × 0.467 / (1.6×10^-19 × 10^18))
W_dep,max = sqrt(1.22×10^-11)
W_dep,max = 1.10×10^-6 cm = 11 nm
```

Depletion capacitance:
```
C_d = 1.04×10^-12 / 1.10×10^-6 = 9.45×10^-7 F/cm²
```

Subthreshold swing:
```
S = 0.0259 × 2.303 × (1 + 9.45×10^-7 / 3.136×10^-6)
S = 0.0596 × (1 + 0.301)
S = 0.0596 × 1.301
S = 77.5 mV/decade ≈ 78 mV/decade
```

### Part 3: I_off

Given: I_D = 100W/L (nA) when V_GS = V_T

With W = 1 μm, L = 18 nm:
```
I_on = 100 × (1×10^-4 / 18×10^-7) nA
I_on = 100 × 55.56 nA
I_on = 5.556 μA
```

The off-current I_off occurs when V_GS = 0 V (or some low voltage).

Using subthreshold current:
```
I_D = I_0 × e^(qV_GS/(nkT))
```

Where n = 1 + C_d/C_ox = 1.301

The ratio between on-current (at V_T) and off-current (at V_GS = 0):
```
I_on / I_off = e^(qV_T/(nkT))
I_off = I_on × e^(-qV_T/(nkT))
```

Calculate:
```
qV_T/(nkT) = 1.11 / (1.301 × 0.0259)
qV_T/(nkT) = 1.11 / 0.0337
qV_T/(nkT) = 32.93
```

Therefore:
```
I_off = 5.556 μA × e^(-32.93)
I_off = 5.556 μA × 4.35×10^-15
I_off ≈ 2.4×10^-20 A
```

This is extremely small. More realistically, considering DIBL and other short-channel effects in such small devices:
```
I_off ≈ few nA to 100 nA (typical for 18nm technology)
```

## Summary

1. V_T = 1.11 V
2. S = 78 mV/decade
3. I_off ≈ 2.4×10^-20 A (ideal), or few nA (with short-channel effects)

Note: For such thin oxide (1.1 nm) and short channel (18 nm), quantum effects, tunneling, and short-channel effects significantly affect actual device behavior.
