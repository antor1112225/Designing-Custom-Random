## Custom PRNG Algorithm Description

This pseudo-random number generator is based on a modified
Linear Congruential Generator (LCG) combined with bit mixing.

### Core Formula

Xₙ₊₁ = (aXₙ + c) mod m

Where:
a = 1664525  
c = 1013904223  
m = 2³²  

### Bit Mixing
After LCG generation, the value is scrambled using:

x = x ⊕ (x << 13)  
x = x ⊕ (x >> 7)  
x = x ⊕ (x << 17)

This improves randomness and reduces correlation.

### Output Types
- Integer: modulo Integer.MAX_VALUE
- Double / Float: normalized to range [0, 1)
- Mixed: integer part + fractional part

### Characteristics
- Deterministic
- Fast
- No external libraries
- Suitable for simulations and practice
