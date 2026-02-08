# Assignment 3 - Problem 6 (English)

## Problem Statement
A Si PNP BJT with each region uniformly doped. The excess minority distribution in each region is shown in the following figure (the depletion regions are not shown). The R-G current in depletion regions are negligible. D_E = 30 cm²/s, D_B = 10 cm²/s, N_E = 10^18 cm^-3, A_E = 10^-5 cm².
1. Which mode does this BJT work at? Explain your answer.
2. Determine the N_C.
3. Determine the stored minority charges in base region Q_B.
4. Determine the I_E.
5. If the base width modulation effect is negligible, determine the β_DC when this BJT works at the forward active mode.

## Solution

### Analysis (General Approach Without Specific Figure)

For a PNP BJT, we analyze excess minority carrier distributions:
- Δn_E in emitter (electrons)
- Δp_B in base (holes)
- Δn_C in collector (electrons)

### Part 1: Operating Mode

**Indicators from excess carrier distribution:**

**Forward Active Mode:**
- E-B forward biased: Δp_B > 0 at E-B boundary
- C-B reverse biased: Δp_B ≈ 0 at C-B boundary
- Linear decrease of Δp_B across base

**Saturation Mode:**
- E-B forward biased: Δp_B > 0 at E-B boundary  
- C-B forward biased: Δp_B > 0 at C-B boundary
- Δp_B remains high throughout base

**Likely Answer:** If the figure shows Δp_B decreasing from a high value at E-B to nearly zero at C-B, the BJT operates in **forward active mode**.

### Part 2: Determine N_C

From the electron distribution in collector Δn_C:

At the C-B junction boundary:
```
Δn_C(0) = n_C0 × (e^(qV_CB/kT) - 1)
```

Where n_C0 = n_i²/N_C

If V_CB < 0 (reverse bias), Δn_C(0) → 0 or negative.

If from the figure, Δn_C(0) ≈ 0, this confirms reverse bias.

If we know Δn_C at some point and the diffusion length, we can work backwards.

**Example:** If Δn_C(0) = -10^3 cm^-3 and n_C0 = 10^4 cm^-3:
```
-10^3 = 10^4 × (e^(qV_CB/kT) - 1)
e^(qV_CB/kT) = 0.9
V_CB = (kT/q) × ln(0.9) = -0.0027 V
```

From n_C0 = n_i²/N_C:
```
N_C = n_i² / n_C0 = (1.5×10^10)² / 10^4 = 2.25×10^16 cm^-3
```

### Part 3: Stored Minority Charge in Base Q_B

For a linear distribution of Δp_B in the base:
```
Q_B = q × A_E × ∫[0 to W_B] Δp_B(x) dx
```

If Δp_B varies linearly from Δp_B(0) at E-B to 0 at C-B:
```
Δp_B(x) = Δp_B(0) × (1 - x/W_B)
```

Then:
```
Q_B = q × A_E × Δp_B(0) × W_B / 2
```

**Example:** If Δp_B(0) = 10^10 cm^-3 and W_B = 1 μm = 10^-4 cm:
```
Q_B = 1.6×10^-19 × 10^-5 × 10^10 × 10^-4 / 2
Q_B = 8×10^-19 C = 0.8 pC
```

### Part 4: Determine I_E

The emitter current has two components:

**Hole current (major):**
```
I_p = q × A_E × D_B × (dΔp_B/dx)|_{x=0}
```

For linear distribution:
```
dΔp_B/dx|_{x=0} = -Δp_B(0)/W_B
```

Therefore:
```
I_p = q × A_E × D_B × Δp_B(0) / W_B
```

**Electron current (minor):**
```
I_n = q × A_E × D_E × Δn_E(0) / L_E
```

**Total emitter current:**
```
I_E = I_p + I_n
```

**Example calculation:**
Using Δp_B(0) = 10^10 cm^-3, W_B = 10^-4 cm, D_B = 10 cm²/s:
```
I_p = 1.6×10^-19 × 10^-5 × 10 × 10^10 / 10^-4
I_p = 1.6×10^-8 A = 16 μA
```

If I_n << I_p, then I_E ≈ 16 μA.

### Part 5: Determine β_DC in Forward Active Mode

```
β_DC = I_C / I_B
```

In forward active mode:
```
I_C ≈ I_p (for PNP, hole current from emitter)
I_B = I_n + (I_E - I_C) = I_n + recombination current
```

Alternatively, using:
```
β_DC = γ × α_T / (1 - γ × α_T)
```

**Emitter efficiency:**
```
γ = I_p / (I_p + I_n)
```

**Base transport factor (for short base):**
```
α_T ≈ 1 - W_B²/(2D_B×τ_B)
```

Or from the linear profile:
```
α_T ≈ 1 (if W_B << L_B)
```

**Example:** If γ = 0.95 and α_T = 0.99:
```
β_DC = (0.95 × 0.99) / (1 - 0.95 × 0.99)
β_DC = 0.9405 / 0.0595 = 15.8
```

## Summary

1. **Operating mode:** Forward active mode (based on Δp_B distribution)
2. **N_C:** Calculate from Δn_C and junction bias (example: ~10^16 cm^-3)
3. **Q_B:** q × A_E × Δp_B(0) × W_B / 2 (read from figure)
4. **I_E:** q × A_E × D_B × Δp_B(0) / W_B + electron component
5. **β_DC:** Calculate from γ and α_T, or from current ratios

Note: Specific numerical values require reading the excess carrier distributions from the provided figure.
