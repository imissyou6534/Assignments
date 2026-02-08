# Assignment 4 - Problem 3 (English)

## Problem Statement
For a NMOSFET, assume that its channel width W is a function of y-coordinate, i.e., W(y) = W_0 + y, where y = 0 and y = L represent the source and drain terminals separately. Using the square law theory, determine the equations for I_D and I_Dsat.

## Solution

### Square Law Theory for Variable Width Channel

For a MOSFET with variable channel width W(y), the current equation must account for the geometry variation.

### Derivation

The basic current equation in the gradual channel approximation:
```
I_D = -μ_n × W(y) × Q_inv(y) × dV/dy
```

Where the inversion charge density is:
```
Q_inv(y) = -C_ox × [V_GS - V(y) - V_T]
```

Substituting:
```
I_D = μ_n × W(y) × C_ox × [V_GS - V(y) - V_T] × dV/dy
```

Since I_D is constant along the channel:
```
I_D × dy = μ_n × W(y) × C_ox × [V_GS - V(y) - V_T] × dV
```

With W(y) = W_0 + y:
```
I_D × dy = μ_n × (W_0 + y) × C_ox × [V_GS - V(y) - V_T] × dV
```

### Part 1: Linear/Triode Region Equation I_D

Integrating from source (y=0, V=0) to drain (y=L, V=V_DS):

Left side:
```
∫[0 to L] I_D dy = I_D × L
```

Right side:
```
∫[0 to L] μ_n × (W_0 + y) × C_ox × [V_GS - V(y) - V_T] dV/dy × dy
```

Change variable from y to V(y). Using V(L) = V_DS and V(0) = 0:

For a linear approximation where y ≈ L×V/V_DS in first order:
```
I_D × L ≈ μ_n × C_ox × ∫[0 to V_DS] (W_0 + L×V/V_DS) × [V_GS - V - V_T] dV
```

Evaluating the integral:
```
∫[0 to V_DS] (W_0 + L×V/V_DS) × [V_GS - V - V_T] dV
= W_0 × [(V_GS - V_T)×V - V²/2]|[0 to V_DS] + (L/V_DS) × ∫[0 to V_DS] V×[V_GS - V - V_T] dV
```

First term:
```
W_0 × [(V_GS - V_T)×V_DS - V_DS²/2]
```

Second term:
```
(L/V_DS) × [(V_GS - V_T)×V²/2 - V³/3]|[0 to V_DS]
= (L/V_DS) × [(V_GS - V_T)×V_DS²/2 - V_DS³/3]
= L × [(V_GS - V_T)×V_DS/2 - V_DS²/3]
```

Combined:
```
I_D = (μ_n × C_ox / L) × {W_0×[(V_GS - V_T)×V_DS - V_DS²/2] + L×[(V_GS - V_T)×V_DS/2 - V_DS²/3]}
```

Simplifying:
```
I_D = (μ_n × C_ox / L) × [(W_0 + L/2)×(V_GS - V_T)×V_DS - (W_0/2 + L/3)×V_DS²]
```

Or using effective width W_eff = W_0 + L/2:
```
I_D ≈ (μ_n × C_ox × W_eff / L) × [(V_GS - V_T)×V_DS - V_DS²/2]
```

### Part 2: Saturation Current I_Dsat

Saturation occurs when V_DS = V_DSsat = V_GS - V_T

Substituting into the I_D equation:
```
I_Dsat = (μ_n × C_ox / L) × [(W_0 + L/2)×(V_GS - V_T)² - (W_0/2 + L/3)×(V_GS - V_T)²]
```

Factoring:
```
I_Dsat = (μ_n × C_ox × (V_GS - V_T)² / L) × [(W_0 + L/2) - (W_0/2 + L/3)]
```

Simplifying the bracket:
```
(W_0 + L/2) - (W_0/2 + L/3) = W_0/2 + L/2 - L/3 = W_0/2 + L/6
```

Therefore:
```
I_Dsat = (μ_n × C_ox / (2L)) × (W_0 + L/3) × (V_GS - V_T)²
```

Or:
```
I_Dsat = (μ_n × C_ox × W_avg / 2L) × (V_GS - V_T)²
```

Where W_avg = W_0 + L/3 is a weighted average channel width.

## Summary

**Linear region:**
```
I_D = (μ_n × C_ox / L) × [(W_0 + L/2)×(V_GS - V_T)×V_DS - (W_0/2 + L/3)×V_DS²]
```

**Saturation region:**
```
I_Dsat = (μ_n × C_ox / (2L)) × (W_0 + L/3) × (V_GS - V_T)²
```

The variable width causes the effective width to be an average value weighted by the current distribution along the channel.
