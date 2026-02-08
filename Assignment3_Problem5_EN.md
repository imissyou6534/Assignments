# Assignment 3 - Problem 5 (English)

## Problem Statement
Two Si NPN BJTs, #1 and #2, are identical except W_B1 > W_B2. Besides, N_E >> N_B > N_C, and W << L_B in both transistors. Under the same forward active mode, which BJT will exhibit:
1. the larger emitter efficiency γ? Explain your answer.
2. the larger base transport factor α_T? Explain your answer.
3. the larger β_DC? Explain your answer.
4. the greater sensitivity to base width modulation effect? Explain your answer.
5. the larger punch-through voltage? Explain your answer.

If the maximum output current is assumed to be limited by carrier multiplication and avalanching, which BJT will exhibit:
6. the larger V_CB0? Explain your answer.
7. the larger V_CE0? Explain your answer.

## Solution

### Part 1: Emitter Efficiency γ

Emitter efficiency is:
```
γ = I_En / (I_En + I_Ep) = 1 / (1 + I_Ep/I_En)
```

For NPN BJT:
```
I_Ep/I_En ≈ (D_p × p_n0 × L_n) / (D_n × n_p0 × L_p)
           ≈ (D_p × N_E × L_n) / (D_n × N_B × L_p)
```

Since W << L_B, the short base approximation applies:
```
I_Ep/I_En ∝ W_B
```

**Therefore:** BJT #2 (with smaller W_B2) has **larger γ** because less hole current flows back into the emitter.

### Part 2: Base Transport Factor α_T

For short base (W << L_B):
```
α_T = 1 - W_B²/(2L_n²)
```

**Therefore:** BJT #2 (with smaller W_B2) has **larger α_T** because:
- Less recombination in the thinner base
- α_T ≈ 1 - W_B²/(2D_n×τ_n)
- Smaller W_B → larger α_T

### Part 3: DC Current Gain β_DC

```
β_DC = (γ × α_T) / (1 - γ × α_T)
```

Since BJT #2 has both larger γ and larger α_T:

**Therefore:** BJT #2 (with smaller W_B2) has **larger β_DC**.

**Explanation:** Both emitter efficiency and base transport factor improve with thinner base, resulting in higher current gain.

### Part 4: Sensitivity to Base Width Modulation (Early Effect)

Base width modulation causes:
```
ΔW_B / W_B
```

The relative change in base width affects α_T and hence I_C:
```
Δα_T / α_T ∝ 2W_B × ΔW_B / L_n²
```

The output conductance is:
```
g_o = ∂I_C/∂V_CE ∝ I_C / V_A
```

Where V_A (Early voltage) is inversely proportional to sensitivity.

For the same ΔW_B, the relative change ΔW_B/W_B is larger for smaller W_B.

**Therefore:** BJT #2 (with smaller W_B2) has **greater sensitivity** to base width modulation.

**Explanation:** A given change in depletion width represents a larger fractional change in the total base width when the base is thinner, making the Early effect more pronounced.

### Part 5: Punch-Through Voltage

Punch-through occurs when the C-B depletion region reaches the E-B depletion region, i.e., when:
```
x_C,CB = W_B
```

The punch-through voltage V_PT is when:
```
W_CB ≈ W_B
```

Since W_B1 > W_B2:

**Therefore:** BJT #1 (with larger W_B1) has **larger punch-through voltage**.

**Explanation:** A wider base requires higher reverse bias on the C-B junction for the depletion region to span the entire base width.

### Part 6: Breakdown Voltage V_CB0

V_CB0 is the collector-base breakdown voltage with emitter open.

Breakdown voltage is primarily determined by:
- Collector doping N_C
- Base doping N_B  
- Electric field in the C-B depletion region

Since both transistors have identical doping profiles:

**Therefore:** **Both BJTs have the same V_CB0**.

**Explanation:** Breakdown voltage depends on the junction doping concentrations, not on the base width. Since N_C and N_B are identical for both devices, V_CB0 is the same.

### Part 7: Breakdown Voltage V_CE0

V_CE0 is the collector-emitter breakdown voltage with base open.

The relationship is:
```
V_CE0 ≈ BV_CBO / √(β_DC)
```

Or more accurately:
```
V_CE0 ≈ BV_CBO / (1 + β_DC)^(1/n)
```

Since BJT #2 has larger β_DC:

**Therefore:** BJT #1 (with smaller β_DC due to larger W_B1) has **larger V_CE0**.

**Explanation:** Higher β_DC leads to more effective multiplication of carriers through the transistor action, reaching avalanche breakdown at lower V_CE. The transistor with lower β_DC can sustain higher V_CE before breakdown.

## Summary

| Parameter | Larger in BJT #1 or #2 | Reason |
|-----------|----------------------|---------|
| γ | #2 (smaller W_B) | Less hole injection to emitter |
| α_T | #2 (smaller W_B) | Less recombination in base |
| β_DC | #2 (smaller W_B) | Higher γ and α_T |
| Early Effect Sensitivity | #2 (smaller W_B) | Larger ΔW_B/W_B ratio |
| V_PT | #1 (larger W_B) | Wider base to punch through |
| V_CB0 | Same | Same doping profile |
| V_CE0 | #1 (larger W_B) | Lower β_DC |
