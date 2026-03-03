---
title: "Multi Party Computation"
type: docs
tags: [STAP-use-cases]
math: true
---


{{% pageinfo %}}
Multi Party Computation (MPC) is a cryptographic protocol dividing a computation among multiple parties where no single party can see the data of the other parties.
{{% /pageinfo %}}


## MPC-friendly Encryption
As opposed to traditional ciphers built from linear and non-linear building blocks for applications where these two have roughly similar costs in hardware and software implementations, the situation is radically different for ciphers implemented in an MPC protocol. Linear operations come almost for free since they only incur local computation, whereas the bottleneck is non-linear operations that involve symmetric cryptographic operations and communication between parties.

This cost metric suggests that ciphers that find a use-case in MPC protocols should desirably minimize their use of non-linear operations while most cryptographically relevant work is performed as linear operations. This design philosophy is related to the fundamental theoretical question of the minimal multiplicative complexity (MC) of certain tasks, which is simply the number of multiplications (AND gates) in a circuit. A lower MC allows for a positive impact on latency and throughput of the MPC evaluation of the cipher, making it an essential feature of the circuit.

## MPC for Boolean circuits
There are two classes of practically efficient secure MPC protocols for securely evaluating Boolean circuits where XOR gates are considerably cheaper (no communication and less computation) than AND gates. The first has a constant number of rounds, and their total amount of communication depends on the MC of the circuit since each AND gate requires communication. The second has a round complexity that is linear in the multiplicative depth of the evaluated circuit since each AND gate requires interaction, and hence the performance depends on both the MC and multiplicative depth of the circuit.

## Arithmetic Masking-friendly Block Ciphers
Masking is a counter-measure against side-channel attacks that ultimately relies on MPC techniques. Indeed, the core idea is to perform the computation to protect using multiple statistically independent shares that need to be recombined to obtain the output. An attacker trying to gather information about the internal properties of the device running the encryption algorithm then needs to place probes in multiple positions, greatly increasing the cost of their attack.

In recent years, masking over prime fields has been argued to be inherently more efficient than masking operating on Boolean variables. This insight has lead to the design of masking-friendly block ciphers operating over a finite field of size p, p a small prime (e.g. 127). The efficiency metric is then, like above, closely related to the multiplicative complexity of the primitive (and in turn to the degree of the round function).

## Correlated PRFs
During initialization, several MPC protocols require the users to be provided with correlated random bits. These are the output of a correlated pseudo-random function (cPRF), a dedicated primitive with unusual cost metrics and security model. As always with STAPs, the cost metric is dictated by the specifics of the higher level protocol; for example, the function may need to be quadratic. The security model is more relaxed than usual for PRFs: indeed, the attacker is not allowed to choose the input of the queries. While they can see plaintext/output pairs, they do not get to chose the plaintext; instead, these are obtained by sampling a uniform distribution.

