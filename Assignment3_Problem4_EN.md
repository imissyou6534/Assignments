# Assignment 3 - Problem 4 (English)

## Problem Statement
The ΔnE/nE0, ΔpB/pB0, and ΔnC/nC0 distributions in the quasi-neutral regions of a PNP BJT are as sketched in the following figure. Determine:
1. The polarity of V_EB
2. The polarity of V_CB
3. The magnitude of V_CB
4. The working mode of this PNP BJT

## Solution

### Analysis Approach

For a PNP BJT, we analyze the normalized excess carrier distributions to determine bias conditions.

### Part 1: Polarity of V_EB

**In PNP BJT:**
- Emitter is p-type, Base is n-type

**Forward bias (V_EB > 0):**
- Holes injected from emitter to base
- ΔpB/pB0 > 0 at the E-B junction boundary

**Reverse bias (V_EB < 0):**
- Hole concentration depleted
- ΔpB/pB0 < 0 at the E-B junction boundary

**From typical figure:**
If ΔpB/pB0 shows a positive value at the E-B boundary and decreases into the base, this indicates **V_EB > 0** (forward bias).

**Answer:** V_EB is **positive** (forward biased E-B junction)

### Part 2: Polarity of V_CB

**In PNP BJT:**
- Collector is p-type, Base is n-type

**Forward bias (V_CB > 0):**
- ΔpB/pB0 > 0 at the C-B junction boundary

**Reverse bias (V_CB < 0):**
- ΔpB/pB0 < 0 or ≈ 0 at the C-B junction boundary

**From typical figure:**
If ΔpB/pB0 at the C-B boundary is negative or zero, this indicates **V_CB < 0** (reverse bias).

**Answer:** V_CB is **negative** (reverse biased C-B junction)

### Part 3: Magnitude of V_CB

At the C-B junction in the base side:
```
ΔpB/pB0 = e^(qV_CB/kT) - 1
```

If from the figure, ΔpB/pB0 ≈ -1 at the C-B boundary:
```
-1 = e^(qV_CB/kT) - 1
e^(qV_CB/kT) = 0 (approximately)
```

This indicates strong reverse bias, V_CB → large negative value.

If ΔpB/pB0 = -0.5 at C-B boundary:
```
-0.5 = e^(qV_CB/kT) - 1
e^(qV_CB/kT) = 0.5
qV_CB/kT = ln(0.5) = -0.693
V_CB = -0.693 × kT/q = -0.693 × 0.0259 = -0.018 V
```

**More realistic example:**
If ΔpB/pB0 = -0.9:
```
e^(qV_CB/kT) = 0.1
qV_CB/kT = ln(0.1) = -2.303
V_CB = -2.303 × 0.0259 = -0.060 V
```

**Answer:** |V_CB| depends on the exact value from the figure, typically ranging from 0.02 V to several volts for reverse bias.

### Part 4: Working Mode

BJT operating modes are determined by junction biases:

| Mode | E-B Junction | C-B Junction |
|------|-------------|-------------|
| Forward Active | Forward | Reverse |
| Saturation | Forward | Forward |
| Reverse Active | Reverse | Forward |
| Cutoff | Reverse | Reverse |

**From our analysis:**
- V_EB > 0 (E-B forward biased)
- V_CB < 0 (C-B reverse biased)

**Answer:** The PNP BJT is operating in **forward active mode**.

### Additional Verification

In forward active mode for PNP:
- Holes injected from emitter (p) to base (n)
- Most holes sweep across base to collector
- ΔpB/pB0 is highest at E-B boundary, decreases across base
- ΔpB/pB0 is low/negative at C-B boundary (reverse biased)
- This matches the typical carrier distribution pattern

## Summary

1. **V_EB polarity:** Positive (forward bias)
2. **V_CB polarity:** Negative (reverse bias)
3. **|V_CB| magnitude:** Read from ΔpB/pB0 value at C-B using V_CB = (kT/q)×ln(1 + ΔpB/pB0)
4. **Operating mode:** Forward active mode

Note: Specific numerical values require reading normalized excess carrier concentrations from the provided figure.
