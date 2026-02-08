# Assignment 4 - Problem 5 (English)

## Problem Statement
For a NMOSFET, its I_D-V_DS plot is shown in the following figure. W = 2.5 μm, L = 0.5 μm, t_ox = 10 nm. The square law theory is utilized.
1. If V_T = 0.5 V, determine the V_GS
2. When the device is biased to work at point A in the figure, determine the Q_inv at the drain terminal point
3. If the V_GS is changed to V_GS - V_T = 3 V, and V_DS = 4 V, determine the I_D

## Solution

### Given Data
- W = 2.5 μm = 2.5×10^-4 cm
- L = 0.5 μm = 0.5×10^-4 cm
- t_ox = 10 nm = 10×10^-7 cm
- V_T = 0.5 V
- ε_ox = 3.45×10^-13 F/cm

### Calculations

**Oxide capacitance:**
```
C_ox = ε_ox / t_ox = 3.45×10^-13 / (10×10^-7) = 3.45×10^-7 F/cm²
```

### Part 1: Determine V_GS

**From the figure** (assuming typical I_D-V_DS characteristics):
- If the figure shows saturation current I_Dsat at a specific V_GS
- Read I_Dsat from the curve

**Example:** If I_Dsat = 1 mA from the figure:

Using saturation current equation:
```
I_Dsat = (μ_n × C_ox × W / (2L)) × (V_GS - V_T)²
```

We need μ_n, which can be determined if one curve is fully specified, or assume typical value:
μ_n ≈ 500 cm²/(V·s) for Si

```
1×10^-3 = (500 × 3.45×10^-7 × 2.5×10^-4 / (2 × 0.5×10^-4)) × (V_GS - 0.5)²
1×10^-3 = (500 × 3.45×10^-7 × 2.5) × (V_GS - 0.5)²
1×10^-3 = 4.31×10^-4 × (V_GS - 0.5)²
(V_GS - 0.5)² = 2.32
V_GS - 0.5 = 1.52
V_GS = 2.02 V
```

### Part 2: Q_inv at Drain Terminal (Point A)

At point A, assume the device is in saturation region.

At the drain end in saturation:
```
Q_inv(L) = 0 (pinch-off condition)
```

If point A is in linear region with V_DS < V_GS - V_T:
```
Q_inv(L) = -C_ox × [V_GS - V(L) - V_T]
Q_inv(L) = -C_ox × [V_GS - V_DS - V_T]
```

**Example:** If V_GS = 2 V, V_DS = 1 V at point A:
```
Q_inv(L) = -3.45×10^-7 × (2 - 1 - 0.5)
Q_inv(L) = -3.45×10^-7 × 0.5
|Q_inv(L)| = 1.725×10^-7 C/cm²
```

### Part 3: I_D with V_GS - V_T = 3 V and V_DS = 4 V

Check if in saturation: V_DS (4 V) > V_GS - V_T (3 V) → Yes, saturation

Use saturation current equation:
```
I_D = (μ_n × C_ox × W / (2L)) × (V_GS - V_T)²
```

With V_GS - V_T = 3 V and μ_n = 500 cm²/(V·s):
```
I_D = (500 × 3.45×10^-7 × 2.5×10^-4 / (2 × 0.5×10^-4)) × 3²
I_D = (500 × 3.45×10^-7 × 2.5) × 9
I_D = 4.31×10^-4 × 9
I_D = 3.88×10^-3 A = 3.88 mA
```

## Summary (Example Values)

1. V_GS ≈ 2.0 V (determined from saturation current in figure)
2. |Q_inv| at drain ≈ 1.73×10^-7 C/cm² (if in linear region at point A)
3. I_D = 3.88 mA (with V_GS - V_T = 3 V, V_DS = 4 V)

Note: Actual values depend on reading the I_D-V_DS curves from the provided figure.
