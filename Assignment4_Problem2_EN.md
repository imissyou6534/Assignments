# Assignment 4 - Problem 2 (English)

## Problem Statement
The following figure shows the energy band diagram for an ideal MOS structure operated at T = 300 K with V_G ≠ 0. Note that E_F = E_i at the Si-SiO2 interface.
1. Does the equilibrium condition prevail inside the semiconductor?
Determine: 2. Fermi potential φ_F; 3. semiconductor's surface potential φ_s; 4. applied gate voltage V_G; 5. oxide layer's thickness t_ox.

## Solution

### Analysis (Without Specific Figure)

For a general MOS energy band diagram analysis where E_F = E_i at the surface:

### Part 1: Equilibrium Condition

**No, equilibrium does not prevail** inside the semiconductor when V_G ≠ 0.

**Explanation:**
- In thermal equilibrium, the Fermi level E_F is constant throughout the material
- When a gate voltage is applied, the semiconductor is driven into non-equilibrium
- However, we can use quasi-Fermi levels or analyze using the band bending
- The condition E_F = E_i at the surface indicates the surface is at intrinsic condition

### Part 2: Fermi Potential φ_F

The Fermi potential is determined by the bulk doping.

If the bulk is p-type with N_A:
```
φ_F = (kT/q) × ln(N_A/n_i)
```

**From the figure:** Read the energy difference between E_F and E_i in the bulk.
```
E_F - E_i = -qφ_F (for p-type)
```

**Example:** If E_F is 0.3 eV below E_i in the bulk:
```
φ_F = 0.3 V
```

This corresponds to:
```
N_A = n_i × e^(φ_F×q/kT) = 1.5×10^10 × e^(0.3/0.0259) ≈ 1.55×10^15 cm^-3
```

### Part 3: Surface Potential φ_s

The surface potential is the band bending from bulk to surface.

Given E_F = E_i at the surface:
```
At surface: E_F - E_i = 0
At bulk: E_F - E_i = -qφ_F (for p-type)
```

The surface potential is:
```
φ_s = (E_i,bulk - E_i,surface)/q
```

Since E_F = E_i at surface, and the bulk Fermi level is constant in quasi-static analysis:
```
φ_s = φ_F
```

Wait, more accurately:
- Surface potential φ_s is the change in electrostatic potential from bulk to surface
- At surface: E_F = E_i means the surface is at midgap (intrinsic condition)
- In bulk: E_F is φ_F below E_i (for p-type)

Therefore:
```
φ_s = φ_F
```

Actually, if E_F = E_i at the surface and this is a p-type substrate:
```
φ_s = φ_F (midgap condition at surface)
```

This is the flatband condition transitioning to weak inversion.

### Part 4: Applied Gate Voltage V_G

```
V_G = V_FB + φ_s + V_ox
```

Where V_ox is the voltage drop across the oxide:
```
V_ox = Q_s / C_ox
```

At φ_s = φ_F (surface at midgap):
```
Q_s ≈ -qN_A × W_dep = -qN_A × sqrt(2ε_s × φ_F / (qN_A))
Q_s = -sqrt(2qε_s × N_A × φ_F)
```

For ideal MOS, V_FB = 0.

**Example calculation:**
If φ_F = 0.3 V, N_A = 1.55×10^15 cm^-3:
```
Q_s = -sqrt(2 × 1.6×10^-19 × 1.04×10^-12 × 1.55×10^15 × 0.3)
Q_s = -sqrt(9.73×10^-17)
Q_s = -9.87×10^-9 C/cm²
```

If from figure, t_ox is given or C_ox can be calculated:
```
V_G = φ_F + |Q_s|/C_ox
```

### Part 5: Oxide Thickness t_ox

From the energy band diagram, read:
- The width of the oxide region (scaled appropriately)
- Or calculate from given parameters

If V_G and other parameters are known:
```
V_ox = V_G - V_FB - φ_s
C_ox = Q_s / V_ox
t_ox = ε_ox / C_ox
```

**From figure:** Measure the physical oxide thickness (if scale is provided).

## Example Solution

**Assuming from a typical figure:**
- E_F in bulk is 0.3 eV below E_i → φ_F = 0.3 V → N_A ≈ 1.55×10^15 cm^-3
- E_F = E_i at surface → φ_s = φ_F = 0.3 V
- Given V_G = 0.5 V from figure
- Then V_ox = 0.5 - 0.3 = 0.2 V

If Q_s = 9.87×10^-9 C/cm²:
```
C_ox = 9.87×10^-9 / 0.2 = 4.94×10^-8 F/cm²
t_ox = 3.45×10^-13 / 4.94×10^-8 = 6.98×10^-6 cm ≈ 70 nm
```

## Summary

1. **Equilibrium:** No, non-equilibrium under gate bias
2. **φ_F:** Read from E_F - E_i in bulk (example: 0.3 V)
3. **φ_s:** Equal to φ_F when E_F = E_i at surface (example: 0.3 V)
4. **V_G:** Calculate from V_G = φ_s + V_ox (example: 0.5 V)
5. **t_ox:** Calculate from C_ox or read from figure (example: 70 nm)

Note: Exact values require reading the energy band diagram from the provided figure.
