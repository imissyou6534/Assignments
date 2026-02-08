# Assignment 4 - Problem 10 (English)

## Problem Statement
A MOSFET has the following parameters: n+ poly-Si as gate electrode, t_ox = 8 nm, N_A = 10^17 cm^-3, and Q_ox = 5×10^10 cm^-2.
1. What is the V_T of this MOSFET?
2. Is this MOSFET enhancement mode or depletion mode?
3. What type of dopants and dose are required such that V_T = 0?

## Solution

### Given Data
- n+ poly-Si gate
- t_ox = 8 nm = 8×10^-7 cm
- N_A = 10^17 cm^-3
- Q_ox = 5×10^10 cm^-2 = 5×10^10 × 1.6×10^-19 = 8×10^-9 C/cm²
- T = 300 K, n_i = 1.5×10^10 cm^-3
- ε_ox = 3.45×10^-13 F/cm
- ε_s = 1.04×10^-12 F/cm

### Preliminary Calculations

**Oxide capacitance:**
```
C_ox = ε_ox / t_ox = 3.45×10^-13 / (8×10^-7) = 4.31×10^-7 F/cm²
```

**Fermi potential:**
```
φ_F = (kT/q) × ln(N_A/n_i)
φ_F = 0.0259 × ln(10^17 / 1.5×10^10)
φ_F = 0.0259 × ln(6.67×10^6)
φ_F = 0.0259 × 15.71
φ_F = 0.407 V
```

**Flat-band voltage:**

Work function difference for n+ poly-Si on p-Si:
```
φ_ms = -(φ_F + E_g/(2q))
φ_ms = -(0.407 + 0.56)
φ_ms = -0.967 V
```

With oxide charge:
```
V_FB = φ_ms - Q_ox/C_ox
V_FB = -0.967 - 8×10^-9 / 4.31×10^-7
V_FB = -0.967 - 0.0186
V_FB = -0.986 V
```

### Part 1: Threshold Voltage V_T

Maximum depletion charge:
```
Q_dep,max = -sqrt(4qε_s × N_A × φ_F)
Q_dep,max = -sqrt(4 × 1.6×10^-19 × 1.04×10^-12 × 10^17 × 0.407)
Q_dep,max = -sqrt(2.71×10^-14)
Q_dep,max = -5.21×10^-7 C/cm²
```

Threshold voltage:
```
V_T = V_FB + 2φ_F + |Q_dep,max|/C_ox
V_T = -0.986 + 2(0.407) + 5.21×10^-7 / 4.31×10^-7
V_T = -0.986 + 0.814 + 1.209
V_T = 1.037 V ≈ 1.04 V
```

### Part 2: Enhancement or Depletion Mode?

Since V_T = 1.04 V > 0:

**Answer: Enhancement mode**

**Explanation:** An enhancement-mode NMOSFET requires a positive gate voltage (V_GS > V_T > 0) to create the inversion channel and turn on the device. With V_GS = 0, the device is off, which is characteristic of enhancement-mode operation.

### Part 3: Dopant Type and Dose for V_T = 0

Current V_T = 1.04 V
Desired V_T = 0 V
ΔV_T = 0 - 1.04 = -1.04 V

To decrease V_T, we need to add **donor dopants (n-type, e.g., Phosphorus or Arsenic)** near the surface by ion implantation.

The threshold voltage shift:
```
ΔV_T = -qN_impl / C_ox
```

For n-type implant (negative ΔV_T):
```
-1.04 = -qN_impl / C_ox
N_impl = 1.04 × C_ox / q
N_impl = 1.04 × 4.31×10^-7 / 1.6×10^-19
N_impl = 2.80×10^12 cm^-2
```

**Answer:**
- **Dopant type:** n-type (Phosphorus, P or Arsenic, As)
- **Dose:** 2.8×10^12 cm^-2

### Verification

New threshold voltage:
```
V_T,new = V_T,old - qN_impl/C_ox
V_T,new = 1.04 - 1.6×10^-19 × 2.80×10^12 / 4.31×10^-7
V_T,new = 1.04 - 1.04
V_T,new = 0 V ✓
```

With V_T = 0, the device becomes a **zero-threshold** or **native** NMOSFET, which is at the boundary between enhancement and depletion modes.

## Summary

1. V_T = 1.04 V
2. **Enhancement mode** (V_T > 0)
3. Add **n-type dopants (Phosphorus or Arsenic)** with dose **2.8×10^12 cm^-2** to achieve V_T = 0
