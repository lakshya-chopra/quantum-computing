## lattice based cryptography:

Lattice based cryptography involves constructions of crypto primitives(one which forms the basis for any cryptographic protocol/algorithms) using the mathematical structures, Lattice.
This type of constructions are widely used in Quantum safe cryptographic protocols, for ex: CRYSTALS Kyber/Dilithium, Falcon, FrodoKEM(not standardized due to low performance), NTRUEncrypt & SWIFFT.

Though not all, still a lot of lattice based constructions are safe from both quantum & classical computers, unlike Diffie-Hellman Key Exchange, ECC & RSA.

## A bit about Lattices:
Technically, Lattices are discrete subgroups of R<sup>n</sup>, i.e. it can be thought of as a regularly spaced grid of elements/points stretching up to infinity. In cryptography, we only consider integer lattices, which are those belonging to Z<sup>n</sup>.
The basis of a lattice, L can be written as:
![image](https://github.com/lakshya-chopra/quantum-computing/assets/77010972/67bccb63-0847-4f77-88c2-a8e6ca7351c2)





