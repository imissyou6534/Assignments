# Assignment 3 - Problem 1 (English)

## Problem Statement
A Si NPN BJT with N_E = 10^18 cm^-3, N_B = 10^16 cm^-3, N_C = 10^15 cm^-3, and W_B = 2 μm is maintained under equilibrium conditions at room temperature.
1. Sketch the energy band diagram for the device, properly positioning the Fermi level in the three regions.
2. Sketch the electrostatic potential (setting V=0 in the emitter region), the electric field, and the charge density as a function of position inside the BJT.
3. Calculate the net potential difference between the collector and emitter V_CE.
4. Determine the quasi-neutral width of the base.
5. Calculate the maximum magnitude of the electric fields in the E-B and C-B depletion regions.

## Solution

### Given Data
- T = 300 K, n_i = 1.5×10^10 cm^-3
- N_E = 10^18 cm^-3 (emitter doping)
- N_B = 10^16 cm^-3 (base doping)
- N_C = 10^15 cm^-3 (collector doping)
- W_B = 2 μm (base width)
- ε_s = 1.04×10^-12 F/cm

### Part 1: Energy Band Diagram

For NPN BJT at equilibrium, the Fermi level E_F is constant throughout the device.

**Fermi level positions:**
- Emitter (n-type): E_F close to E_C (heavily doped n+)
- Base (p-type): E_F close to E_V (p-doped)
- Collector (n-type): E_F between E_C and E_i (lightly doped n)

Energy band diagram (text representation):
```
Emitter      Base       Collector
(n+)         (p)        (n)

E_C ___      ____       ___
       \    /    \     /
        \  /      \   /
         \/qV_BE   \ /qV_BC
    E_F _ _ _ _ _ _ _ _ _ _  (constant)
         /\        / \
        /  \      /   \
       /    \____/     \___
E_V __/                    
```

### Part 2: Electrostatic Potential, Electric Field, and Charge Density

**Setting V=0 in emitter:**

Electrostatic Potential V(x):
```
V   |       ___________
    |      /           \___
VBE |_____/                 
    |                      \___
    |                          \___
0   |___________________________VCE
    E    EB    B    BC    C
```

Electric Field E(x):
```
E   |    ^          ^
    |   /|\        /|\
    |    |          |
0   |____.__________.__________
    E   EB    B   BC    C
    |
```

Charge Density ρ(x):
```
ρ   | +  |    -    |  +
    |____|_________|_______
    E   EB    B   BC    C
```

### Part 3: Net Potential Difference V_CE

**E-B junction built-in potential:**
```
V_BE = (kT/q) × ln(N_E × N_B / n_i^2)
V_BE = 0.0259 × ln(10^18 × 10^16 / (1.5×10^10)^2)
V_BE = 0.0259 × ln(10^34 / 2.25×10^20)
V_BE = 0.0259 × ln(4.44×10^13)
V_BE = 0.0259 × 31.43 = 0.814 V
```

**B-C junction built-in potential:**
```
V_BC = (kT/q) × ln(N_B × N_C / n_i^2)
V_BC = 0.0259 × ln(10^16 × 10^15 / (1.5×10^10)^2)
V_BC = 0.0259 × ln(10^31 / 2.25×10^20)
V_BC = 0.0259 × ln(4.44×10^10)
V_BC = 0.0259 × 24.52 = 0.635 V
```

**Net potential difference:**
```
V_CE = V_BE + V_BC = 0.814 + 0.635 = 1.449 V ≈ 1.45 V
```

### Part 4: Quasi-Neutral Base Width

**E-B depletion width:**
```
W_EB = sqrt(2ε_s × V_BE / q × (N_E + N_B)/(N_E × N_B))
W_EB ≈ sqrt(2ε_s × V_BE / q × 1/N_B)  (since N_E >> N_B)
W_EB = sqrt(2 × 1.04×10^-12 × 0.814 / (1.6×10^-19 × 10^16))
W_EB = sqrt(1.06×10^-9)
W_EB ≈ 3.26×10^-5 cm = 0.326 μm
```

Most of W_EB extends into the base (x_B,EB).

**B-C depletion width:**
```
W_BC = sqrt(2ε_s × V_BC / q × (N_B + N_C)/(N_B × N_C))
W_BC = sqrt(2 × 1.04×10^-12 × 0.635 / 1.6×10^-19 × 1.1×10^16/10^31)
```

For the base side:
```
x_B,BC = W_BC × N_C/(N_B + N_C) ≈ W_BC/11 ≈ 0.087 μm
```

**Quasi-neutral base width:**
```
W_B' = W_B - x_B,EB - x_B,BC
W_B' ≈ 2.0 - 0.30 - 0.09 ≈ 1.61 μm
```

### Part 5: Maximum Electric Fields

**E-B junction:**
```
E_max,EB = -qN_B × x_B,EB / ε_s
E_max,EB ≈ 1.6×10^-19 × 10^16 × 3×10^-5 / 1.04×10^-12
E_max,EB ≈ 4.6×10^4 V/cm
```

**B-C junction:**
```
E_max,BC = -qN_C × x_C,BC / ε_s
E_max,BC ≈ 1.33×10^4 V/cm
```

## Summary
1. Energy band diagram shows constant E_F with band bending at junctions
2. V_CE = 1.45 V
3. W_B' ≈ 1.61 μm
4. E_max,EB ≈ 4.6×10^4 V/cm, E_max,BC ≈ 1.33×10^4 V/cm
