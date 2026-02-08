# Assignment 3 - Problem 2 (English)

## Problem Statement
Given a NPN BJT where I_En = 100 μA, I_Ep = 1 μA, I_Cn = 99 μA, and I_Cp = 0.1 μA, calculate:
1. α_T
2. γ
3. I_E, I_C, I_B
4. α_DC and β_DC
5. I_CB0 and I_CE0
6. If I_Cn is increased to a value closer to 100 μA while all other current components remain fixed. What effect does the I_Cn increase have on β_DC? Explain your answer.
7. If I_Ep is increased while all other current components remain fixed. What effect does the I_Ep increase have on β_DC? Explain your answer.

## Solution

### Given Data
- I_En = 100 μA (electron current injected from emitter)
- I_Ep = 1 μA (hole current injected into emitter)
- I_Cn = 99 μA (electron current reaching collector)
- I_Cp = 0.1 μA (hole current in collector)

### Part 1: Base Transport Factor α_T

α_T is the fraction of electrons injected from emitter that reach the collector:
```
α_T = I_Cn / I_En = 99 / 100 = 0.99
```

### Part 2: Emitter Efficiency γ

γ is the fraction of emitter current that is due to electrons:
```
γ = I_En / (I_En + I_Ep) = 100 / (100 + 1) = 100/101 ≈ 0.9901
```

### Part 3: Total Currents I_E, I_C, I_B

**Emitter current:**
```
I_E = I_En + I_Ep = 100 + 1 = 101 μA
```

**Collector current:**
```
I_C = I_Cn + I_Cp = 99 + 0.1 = 99.1 μA
```

**Base current (from current conservation):**
```
I_B = I_E - I_C = 101 - 99.1 = 1.9 μA
```

### Part 4: DC Current Gains α_DC and β_DC

**α_DC (common-base current gain):**
```
α_DC = I_C / I_E = 99.1 / 101 ≈ 0.9812
```

Or alternatively:
```
α_DC = γ × α_T = 0.9901 × 0.99 = 0.9802 ≈ 0.98
```

**β_DC (common-emitter current gain):**
```
β_DC = I_C / I_B = 99.1 / 1.9 ≈ 52.2
```

Or alternatively:
```
β_DC = α_DC / (1 - α_DC) = 0.9812 / (1 - 0.9812) = 0.9812 / 0.0188 ≈ 52.2
```

### Part 5: Reverse Saturation Currents I_CB0 and I_CE0

**I_CB0** is the collector-base reverse saturation current:
In ideal approximation, I_CB0 represents the minority carrier generation current:
```
I_CB0 = I_Cp (approximately) = 0.1 μA
```

**I_CE0** is the collector-emitter reverse saturation current:
```
I_CE0 = I_CB0 / (1 - α_DC) = 0.1 / (1 - 0.9812)
I_CE0 = 0.1 / 0.0188 ≈ 5.3 μA
```

Or using the relation:
```
I_CE0 = (1 + β_DC) × I_CB0 = (1 + 52.2) × 0.1 = 5.32 μA
```

### Part 6: Effect of Increasing I_Cn

If I_Cn increases toward 100 μA:

**New α_T:**
```
α_T,new = 100 / 100 = 1.0
```

**New α_DC:**
```
α_DC,new = γ × α_T,new = 0.9901 × 1.0 = 0.9901
```

**New β_DC:**
```
β_DC,new = α_DC,new / (1 - α_DC,new) = 0.9901 / 0.0099 = 100
```

**Effect:** β_DC **increases** from 52.2 to 100.

**Explanation:** Increasing I_Cn improves the base transport factor α_T (fewer electrons recombine in the base), which increases α_DC. Since β_DC = α_DC/(1-α_DC), even small increases in α_DC near 1 cause large increases in β_DC.

### Part 7: Effect of Increasing I_Ep

If I_Ep increases while other components remain fixed:

**New γ:**
```
γ_new = I_En / (I_En + I_Ep,new) = 100 / (100 + I_Ep,new)
```

This decreases γ (emitter efficiency decreases).

**New α_DC:**
```
α_DC,new = γ_new × α_T = [100/(100 + I_Ep,new)] × 0.99
```

This decreases α_DC.

**New β_DC:**
```
β_DC,new = α_DC,new / (1 - α_DC,new)
```

Since α_DC decreases, β_DC **decreases**.

**Explanation:** Increasing I_Ep means more holes are injected from base into emitter, reducing emitter efficiency γ. This reduces α_DC, which in turn reduces β_DC. The transistor becomes less efficient as more of the emitter current is "wasted" on hole injection rather than useful electron injection.

## Summary

1. α_T = 0.99
2. γ = 0.9901
3. I_E = 101 μA, I_C = 99.1 μA, I_B = 1.9 μA
4. α_DC = 0.98, β_DC = 52.2
5. I_CB0 = 0.1 μA, I_CE0 = 5.3 μA
6. Increasing I_Cn **increases** β_DC (better base transport)
7. Increasing I_Ep **decreases** β_DC (worse emitter efficiency)
