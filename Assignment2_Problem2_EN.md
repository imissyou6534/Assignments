# Assignment 2 - Problem 2 (English)

## Problem Statement
A Si pn abrupt junction maintained at RT is doped such that E_F = E_V - 2kT for the p-Si side and E_F = E_C - E_G/4 for the n-Si side.
1. Draw the equilibrium energy band diagram for this pn junction
2. Determine the built-in potential V_bi and mark it in the energy band diagram

## Solution

### Part 1: Energy Band Diagram

For the p-Si side:
- E_F = E_V - 2kT
- This means the Fermi level is 2kT below the valence band edge
- The hole concentration can be found from: p = N_V * exp(-(E_F - E_V)/kT) = N_V * exp(2)

For the n-Si side:
- E_F = E_C - E_G/4
- This means the Fermi level is E_G/4 below the conduction band edge
- The electron concentration can be found from: n = N_C * exp(-(E_C - E_F)/kT) = N_C * exp(-E_G/(4kT))

At room temperature (T = 300K):
- kT ≈ 0.0259 eV
- For Si: E_G ≈ 1.12 eV

Energy Band Diagram (text representation):
```
p-side                Junction                n-side
                         
E_C  ----                                    ---- E_C
         \                                  /
          \                                /
           \                              /
            \                            /
  E_V - 2kT  \_ _ _ _ E_F _ _ _ _ _ _ _/  E_C - E_G/4
              \                          /
               \                        /
E_V  -----------\______________________/----------- E_V

         |<---- qV_bi ---->|
```

### Part 2: Built-in Potential Calculation

The built-in potential is determined by the Fermi level alignment at equilibrium.

On the p-side, the distance from E_F to E_i (intrinsic Fermi level):
```
E_F - E_i = -E_G/2 + 2kT (on p-side)
φ_p = (E_i - E_F)/q = E_G/(2q) - 2kT/q
```

On the n-side, the distance from E_i to E_F:
```
E_F - E_i = E_C - E_G/4 - (E_C - E_G/2) = E_G/4 (on n-side)
φ_n = (E_F - E_i)/q = E_G/(4q)
```

The built-in potential is:
```
V_bi = φ_p + φ_n = E_G/(2q) - 2kT/q + E_G/(4q)
V_bi = 3E_G/(4q) - 2kT/q
```

Substituting values at RT (T = 300K):
```
V_bi = 3(1.12)/(4) - 2(0.0259)
V_bi = 0.84 - 0.0518
V_bi ≈ 0.788 V ≈ 0.79 V
```

Alternative calculation method:
The Fermi level position from the band edges gives:
- On p-side: E_V,p - E_F = 2kT
- On n-side: E_F - E_C,n = -E_G/4

At equilibrium, E_F is constant throughout the device.
The built-in potential is the difference in band edge positions:
```
qV_bi = (E_C,n - E_V,n) - (E_C,p - E_V,p) + (E_F,p - E_V,p) + (E_C,n - E_F,n)
qV_bi = 2kT + E_G/4
V_bi = 2kT/q + E_G/(4q) = 0.0518 + 0.28 = 0.3318 V
```

Actually, let me recalculate more carefully:

On p-side: E_F is at E_V - 2kT, so it's 2kT above E_V (deeper in the gap)
On n-side: E_F is at E_C - E_G/4

The band bending is:
```
qV_bi = (E_C,n - E_V,p) - E_G
     = E_G + qV_bi - E_G = qV_bi
```

More correctly, from the Fermi level positions:
```
qV_bi = (E_C,n - E_F) - (E_F - E_V,p)
     = E_G/4 - (-2kT)
     = E_G/4 + 2kT
V_bi = E_G/(4q) + 2kT/q
V_bi = 1.12/4 + 2(0.0259) = 0.28 + 0.0518 = 0.332 V
```

## Answer
The built-in potential V_bi ≈ 0.33 V
