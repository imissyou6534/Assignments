# Assignment 4 - Problem 7 (English)

## Problem Statement
For a NMOSFET, W = 50 μm, L = 5 μm, t_ox = 50 nm, N_A = 3×10^15 cm^-3, μ_n = 800 cm²/(V·s), heavily doped n+ poly-Si is utilized as gate electrode, Q_ox = 0.
Determine: 
1. V_T
2. I_Dsat when V_GS = 2 V
3. g_ds when V_GS = 2 V and V_DS = 0 V
4. g_m when V_GS = 2 V and V_DS = 2 V

## Solution

### Given Data
- W = 50 μm = 50×10^-4 cm
- L = 5 μm = 5×10^-4 cm
- t_ox = 50 nm = 50×10^-7 cm
- N_A = 3×10^15 cm^-3
- μ_n = 800 cm²/(V·s)
- n+ poly-Si gate, Q_ox = 0
- T = 300 K, n_i = 1.5×10^10 cm^-3
- ε_ox = 3.45×10^-13 F/cm
- ε_s = 1.04×10^-12 F/cm

### Preliminary Calculations

**Oxide capacitance:**
```
C_ox = ε_ox / t_ox = 3.45×10^-13 / (50×10^-7) = 6.9×10^-8 F/cm²
```

**Fermi potential:**
```
φ_F = (kT/q) × ln(N_A/n_i)
φ_F = 0.0259 × ln(3×10^15 / 1.5×10^10)
φ_F = 0.0259 × ln(2×10^5)
φ_F = 0.0259 × 12.21
φ_F = 0.316 V
```

### Part 1: Threshold Voltage V_T

For n+ poly-Si gate on p-substrate, V_FB ≈ 0 (ideal case with Q_ox = 0).

```
V_T = 2φ_F + (1/C_ox) × sqrt(4qε_s × N_A × φ_F)
```

Calculate the depletion charge term:
```
Q_dep,max = -sqrt(4qε_s × N_A × φ_F)
Q_dep,max = -sqrt(4 × 1.6×10^-19 × 1.04×10^-12 × 3×10^15 × 0.316)
Q_dep,max = -sqrt(6.32×10^-16)
Q_dep,max = -2.51×10^-8 C/cm²
```

Therefore:
```
V_T = 2 × 0.316 + 2.51×10^-8 / 6.9×10^-8
V_T = 0.632 + 0.364
V_T = 0.996 V ≈ 1.0 V
```

### Part 2: I_Dsat when V_GS = 2 V

Check: V_GS - V_T = 2 - 1 = 1 V

Saturation current:
```
I_Dsat = (μ_n × C_ox × W / (2L)) × (V_GS - V_T)²
I_Dsat = (800 × 6.9×10^-8 × 50×10^-4 / (2 × 5×10^-4)) × 1²
I_Dsat = (800 × 6.9×10^-8 × 5) × 1
I_Dsat = 2.76×10^-4 A = 0.276 mA
```

### Part 3: g_ds when V_GS = 2 V and V_DS = 0 V

At V_DS = 0 V, the device is in the linear region (deep triode).

The drain-source conductance is:
```
g_ds = ∂I_D/∂V_DS |V_DS=0 = μ_n × C_ox × (W/L) × (V_GS - V_T)
```

```
g_ds = 800 × 6.9×10^-8 × (50×10^-4 / 5×10^-4) × (2 - 1)
g_ds = 800 × 6.9×10^-8 × 10 × 1
g_ds = 5.52×10^-4 S = 0.552 mS
```

### Part 4: g_m when V_GS = 2 V and V_DS = 2 V

Check operating region: V_GS - V_T = 1 V, V_DS = 2 V
Since V_DS (2 V) > V_GS - V_T (1 V), the device is in saturation.

Transconductance in saturation:
```
g_m = ∂I_Dsat/∂V_GS = μ_n × C_ox × (W/L) × (V_GS - V_T)
```

```
g_m = 800 × 6.9×10^-8 × (50×10^-4 / 5×10^-4) × 1
g_m = 800 × 6.9×10^-8 × 10
g_m = 5.52×10^-4 S = 0.552 mS
```

## Summary

1. V_T = 1.0 V
2. I_Dsat = 0.276 mA (at V_GS = 2 V)
3. g_ds = 0.552 mS (at V_GS = 2 V, V_DS = 0 V)
4. g_m = 0.552 mS (at V_GS = 2 V, V_DS = 2 V, in saturation)
