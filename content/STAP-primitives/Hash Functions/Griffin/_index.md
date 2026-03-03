---
title: "Griffin"
linkTitle: "Griffin"
type: docs
math: true
categories: [Hash-Function, SPZ]
tags: [Horst]
---


> **Designers**: Lorenzo Grassi, Yonglin Hao, Christian Rechberger, Markus Schofnegger, Roman Walch, Qingju Wang.
>
> **Article**: Horst Meets Fluid-SPN: Griffin for Zero-Knowledge Applications, CRYPTO 2023


Griffin is a family of sponge hash and compression functions designed for Zero-Knowledge applications, using the internal permutation Griffin-\(\pi\), which is defined over the finite field \(F_t\) where \(t = 3\) or \(t\) is a multiple of four.

Griffin is claimed to offer efficient verifiability, high degrees of security in both forward and backward directions, minimal multiplicative complexity, and robust security against algebraic attacks on top of simple arguments against statistical attacks.

Each round function of Griffin-\(\pi\) consists of a nonlinear layer, the addition of a round constant, and a linear layer defined by multiplication by an MDS matrix ensuring full diffusion. The nonlinear layer of Griffin-\(\pi\) consists of two nonlinear sublayers defined by three different nonlinear functions. Two of these functions are invertible power maps, \(x \mapsto x^d\) and \(x \mapsto x^{(1/d)}\). The third function is based on the proposed Horst strategy, which uses the map \((x,y) \mapsto (x, y \cdot G(x))\) for a quadratic function G such that \(G(z)\) is different from 0 for each z.


## Cryptanalysis


1. **Authors:** Augustin Bariant, Aurélien Boeuf, Axel Lemoine, Irati Manterola Ayala, Morten Øygarden, Léo Perrin, Håvard Raddum

    **Title:** The Algebraic Freelunch: Efficient Gröbner Basis Attacks Against Arithmetization-Oriented Primitives, CRYPTO 2024

    Recovery of a CICO solution for 7 out of 10 rounds of Griffin in less than four hours with attack complexities as low as 2^64 for its weakest variants

    
## Implementation

Details on implementation

## References
1. Some reference
2. Other reference