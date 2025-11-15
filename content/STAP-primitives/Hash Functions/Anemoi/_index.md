---
title: "Anemoi"
linkTitle: "Anemoi"
type: docs
math: true
categories: [Hash-Function, SPZ]
tags: [Flystel, CCZ-equivalence]
---


> **Designers**: Clémence Bouvier, Pierre Briaud, Pyrros Chaidos, Léo Perrin, Robin Salen, Vesselin Velichkov, Danny Willems.
>
> **Article**: New Design Techniques for Efficient Arithmetization-Oriented Hash Functions: Anemoi Permutations and Jive Compression Mode, CRYPTO 2023

Anemoi is a family of ZK-friendly permutations, that can be used to construct efficient hash functions and compression functions. Anemoi relies on two new components: a new S-box called Flystel, exploiting a previously unknown relationship with CCZ-equivalence, and a new mode of operation called Jive.

The Flystel is a pair of functions (the open and closed Flystel) relying on two quadratic functions \(Q_\gamma\), \(Q_\delta\) and a permutation \(E\). While the open Flystel is a high degree permutation of \((F_q)^2\) the closed Flystel is a low degree function of \((F_q)^2\). The two variants are CCZ-equivalent, meaning that it is possible to encode the verification of the evaluation of the open Flystel \(H\) using the polynomial representation of the closed Flystel \(V\).

The internal state of Anemoi is represented as a matrix with \(l\) columns and \(2\) rows. A round function is then a permutation of \((F_q)^{2l}\), where \(q\) is either a prime number or a power of \(2\). The function applied at each round has a classical **Substitution-Permutation Network (SPN)** structure: first the constant addition, then the linear layer, and finally the S-box layer (i.e. the Flystel).


## Cryptanalysis

The FreeLunch attack and 6 worlds of GB are two recent algebraic cryptanalysis on Anemoi. Both papers slightly reduce the security margin of Anemoi for the instance with l=1

1. **Authors:** Jung Hee Cheon, Wonhee Cho, Jeong Han Kim, Jiseung Kim

    **Title:** Augustin Bariant, Aurélien Boeuf, Axel Lemoine, Irati Manterola Ayala, Morten Øygarden, Léo Perrin, Håvard Raddum

2. **Authors:** Thomas Johansson, Willi Meier, Vu Nguyen
    
    **Title:** Katharina Koschatko, Reinhard Lüftenegger, Christian Rechberger
    
## Implementation

Details on implementation

## References
1. Some reference
2. Other reference