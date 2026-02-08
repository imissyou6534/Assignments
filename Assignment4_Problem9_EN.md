# Assignment 4 - Problem 9 (English)

## Problem Statement
For a NMOSFET, heavily doped n+ poly-Si is utilized as gate electrode, Q_ox = q×8×10^10 cm^-2, L = 2 μm, W = 50 μm, t_ox = 5 nm, N_A = 10^15 cm^-3.
Determine:
1. V_FB
2. V_T
3. If the V_T is desired to be modulated to 0.5 V, which type of dopants should be added? What is the dose?

## Solution

### Given Data
- n+ poly-Si gate
- Q_ox = q×8×10^10 cm^-2 = 1.6×10^-19 × 8×10^10 = 1.28×10^-8 C/cm²
- L = 2 μm, W = 50 μm
- t_ox = 5 nm = 5×10^-7 cm
- N_A = 10^15 cm^-3
- T = 300 K, n_i = 1.5×10^10 cm^-3
- ε_ox = 3.45×10^-13 F/cm
- ε_s = 1.04×10^-12 F/cm

### Preliminary Calculations

**Oxide capacitance:**
```
C_ox = ε_ox / t_ox = 3.45×10^-13 / (5×10^-7) = 6.9×10^-7 F/cm²
```

**Fermi potential:**
```
φ_F = (kT/q) × ln(N_A/n_i)
φ_F = 0.0259 × ln(10^15 / 1.5×10^10)
φ_F = 0.0259 × 11.11
φ_F = 0.288 V
```

### Part 1: Flat-Band Voltage V_FB

For n+ poly-Si gate on p-substrate:

Work function difference (ideally):
```
φ_ms = φ_m - φ_s
```

For n+ poly-Si on p-Si:
```
φ_ms ≈ -(φ_F + E_g/(2q))
φ_ms ≈ -(0.288 + 1.12/2)
φ_ms ≈ -0.848 V
```

Flat-band voltage with oxide charge:
```
V_FB = φ_ms - Q_ox/C_ox
V_FB = -0.848 - 1.28×10^-8 / 6.9×10^-7
V_FB = -0.848 - 0.0186
V_FB = -0.867 V ≈ -0.87 V
```

### Part 2: Threshold Voltage V_T

```
V_T = V_FB + 2φ_F + Q_dep,max/C_ox
```

Maximum depletion charge:
```
Q_dep,max = -sqrt(4qε_s × N_A × φ_F)
Q_dep,max = -sqrt(4 × 1.6×10^-19 × 1.04×10^-12 × 10^15 × 0.288)
Q_dep,max = -sqrt(1.92×10^-16)
Q_dep,max = -1.39×10^-8 C/cm²
```

Threshold voltage:
```
V_T = -0.867 + 2(0.288) + 1.39×10^-8 / 6.9×10^-7
V_T = -0.867 + 0.576 + 0.020
V_T = -0.271 V
```

This is a depletion-mode device (negative V_T).

### Part 3: Threshold Voltage Adjustment to 0.5 V

Current V_T = -0.271 V
Desired V_T = 0.5 V
ΔV_T = 0.5 - (-0.271) = 0.771 V

To increase V_T, we need to add **acceptor dopants (p-type, e.g., Boron)** by ion implantation near the surface.

The threshold voltage shift due to implanted dose N_impl:
```
ΔV_T = -qN_impl / C_ox
```

For positive ΔV_T with p-type implant:
```
0.771 = qN_impl / C_ox
N_impl = 0.771 × C_ox / q
N_impl = 0.771 × 6.9×10^-7 / 1.6×10^-19
N_impl = 3.32×10^12 cm^-2
```

**Answer:**
- **Dopant type:** p-type (Boron, B)
- **Dose:** 3.32×10^12 cm^-2 ≈ 3.3×10^12 cm^-2

### Verification

New threshold voltage:
```
V_T,new = V_T,old + qN_impl/C_ox
V_T,new = -0.271 + 1.6×10^-19 × 3.32×10^12 / 6.9×10^-7
V_T,new = -0.271 + 0.771
V_T,new = 0.5 V ✓
```

## Summary

1. V_FB = -0.87 V
2. V_T = -0.27 V (depletion mode)
3. Add **p-type dopants (Boron)** with dose **3.3×10^12 cm^-2** to achieve V_T = 0.5 V
