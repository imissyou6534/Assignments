# Assignment 2 - Problem 4 (English)

## Problem Statement
For a Si p+n long diode at RT, both sides are uniformly doped. Given that N_D = 10^16 cm^-3, τ_p = 10^-8 s, D_p = 10 cm^2/s, and V_A = 23kT/q. Determine:
1. Minority distribution in n-Si, i.e. Δp_n(x)~x
2. The x-coordinate at which majority induced current equals to the minority induced current, i.e. J_n = J_p

## Solution

### Given Data
- T = 300 K (RT)
- N_D = 10^16 cm^-3
- τ_p = 10^-8 s (minority carrier lifetime)
- D_p = 10 cm^2/s (hole diffusion coefficient)
- V_A = 23kT/q = 23 × 0.0259 = 0.596 V
- For Si: n_i = 1.5 × 10^10 cm^-3

### Part 1: Minority Distribution Δp_n(x)

For a long diode under forward bias, the excess minority carrier concentration follows:

```
Δp_n(x) = p_n(x) - p_n0 = p_n0(e^(qV_A/kT) - 1) × e^(-x/L_p)
```

Where:
- p_n0 = n_i^2/N_D = (1.5×10^10)^2/10^16 = 2.25×10^4 cm^-3
- L_p = sqrt(D_p × τ_p) = sqrt(10 × 10^-8) = sqrt(10^-7) = 3.16 × 10^-4 cm = 3.16 μm
- e^(qV_A/kT) = e^23 ≈ 9.74 × 10^9

Therefore:
```
Δp_n(x) = 2.25×10^4 × (9.74×10^9 - 1) × e^(-x/3.16×10^-4)
Δp_n(x) ≈ 2.19×10^14 × e^(-x/3.16×10^-4) cm^-3
```

Or more precisely:
```
Δp_n(x) = 2.19×10^14 × exp(-x/L_p)  where L_p = 3.16 μm
```

### Part 2: Position where J_n = J_p

The minority carrier current (hole current) is:
```
J_p(x) = -qD_p × dΔp_n/dx = qD_p × Δp_n(0)/L_p × e^(-x/L_p)
```

At x = 0:
```
J_p(0) = qD_p × Δp_n(0)/L_p
      = 1.6×10^-19 × 10 × 2.19×10^14 / 3.16×10^-4
      = 1.11×10^4 A/cm^2
```

The majority carrier current (electron current) in the quasi-neutral n-region:
```
J_n(x) = J_total - J_p(x)
```

Since total current is constant:
```
J_total = J_p(0) = 1.11×10^4 A/cm^2
```

At equilibrium, J_n = J_p when:
```
J_n(x) = J_p(x)
J_total/2 = J_p(0) × e^(-x/L_p)
1/2 = e^(-x/L_p)
-x/L_p = ln(0.5) = -0.693
x = 0.693 × L_p = 0.693 × 3.16 μm
x ≈ 2.19 μm
```

## Summary
1. Δp_n(x) = 2.19×10^14 × exp(-x/3.16μm) cm^-3
2. J_n = J_p at x ≈ 2.19 μm from the junction
