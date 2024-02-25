# quantum-computing

[NOTE: this is just a small text intended to provide you some gist of Quantum Computing]

**Quantum Computers** utilise the principles of quantum mechanics to perform computations as opposed to classical computers which are limited to classical physics phenomena.Thus, they require special materials (like *superconductors, diamond nv centers, trapped ions*) to work as required (unlike classical comps which use electrical pulses).

They follow 4 main quantum principles, stated as follows:
  - Quantum Entanglement: [Quantum entanglement is the phenomenon that occurs when a group of particles are generated, interact, or share spatial proximity in such a way that the quantum state of each particle of the group cannot be described independently of the state of the others, including when the particles are separated by a large distance.](https://en.wikipedia.org/wiki/Quantum_entanglement). Thus, the particles are correlated with each other, also the interesting thing is, the states aren't decided until one of the particles is measured. They don't involve any transfer of information as well (for eg: if you measure the spin of one particle to be negative, then the particle entagled with it must have the opposite spin).
    
  - Superposition: Every Quantum state can be thought of as a linear combinatin of some other quantum states (for eg: a linear combination of vectors with some vectors being the basis). Similar to the superposition of waves/electric fields.
A Qubit in quantum computers is thus a superposition of |0⟩ and |1⟩ (the basis).
Qubits are neutral atoms and the gates are implemented by shining lasers of a certain frequency or colour. The frequency is calculated from the energy band gap between the |0⟩ and |1⟩.

For superconducting qubits, current is applied.



    
  - Inteference: Quantum Interference is the essentially the interference of the probability amplitudes of various quantum paths which lead to observable patterns (like constructive interference or destructive)
    
  - Measurement

## Resources:
  - [Problems Quantum Computers solve and a brief intro on them](https://learn.microsoft.com/en-us/azure/quantum/overview-understanding-quantum-computing#how-does-quantum-computing-solve-problems)
  - [Quantum Computing Book](https://github.com/JackHidary/quantumcomputingbook)
  - [NPTEL Course](https://www.youtube.com/playlist?list=PLuBwWyD3M82x9PfxeF7oxb0E122mQAWh6)
  - [Basics of Quantum Info](https://learning.quantum.ibm.com/course/basics-of-quantum-information)
  - [Quantum Inspire](https://www.quantum-inspire.com/kbase/superposition-and-entanglement/)
  
  
## Quantum Computer's components: 
  - a shell which stores the qubits in a safe environment where the temperature is just above absolute zero to minimize vibrations of the qubits.
  - Quantum Gates
  - A classical computer which runs the program, handles I/O, performs computation and addressing tasks.
    Thus, this is a hybrid model of Quantum Computers, wherein we have a classical computer in control of a quantum processor.

## Correlations (part of entanglement):
  - Classical
  - Quantum
    <br>
    [More on this topic](https://learn.microsoft.com/en-us/azure/quantum/concepts-multiple-qubits#understanding-classical-correlations)
    
## Qubits:
  [Inspo taken from](https://learn.microsoft.com/en-us/azure/quantum/concepts-the-qubit)

## Quantum systems:
  ### By IBM:
    - Eagle (127 Qubits)
    - Hummingbird(65 qubits)
    - Condor ( 1121 qubits)
    Others include Osprey, & Falcon.

## Quantum SDK(s):
  - Qiskit, [Qiskit - github](https://github.com/Qiskit/qiskit)
  - Intel Quantum SDK
    ![Intel Q SDK](https://www.intel.com/content/dam/www/public/us/en/newsroom/posts/newsroom-02-quantum-sdk-fulls-stacks.jpg.rendition.intel.web.1648.927.jpg)
  - Q# (Programming Language)

[Qiskit textbook](https://github.com/qiskit-community/qiskit-textbook)

## Some helpful links:
- [Bloch Sphere](https://medium.com/quantum-untangled/quantum-states-and-the-bloch-sphere-9f3c0c445ea3)

- [Postulates](https://www.sydney.edu.au/science/chemistry/~mjtj/CHEM3117/Resources/postulates.pdf)

- [Hermitian Matrix and it’s association with the observables](https://physics.stackexchange.com/questions/560673/equivalence-of-hermitian-operator-and-hermitian-matrix-in-quantum-mechanics)
    
- [forgot the title](https://ocw.mit.edu/courses/5-61-physical-chemistry-fall-2007/3b1fb40c61e7f939861b190bedbc57a7_lecture24.pdf)

- [Multi Qubit states](https://cse.iitkgp.ac.in/~goutam/quantumComputing/lect2.pdf)

- [Quantum Algorithms](https://github.com/Qiskit/textbook/blob/main/notebooks/ch-algorithms)

- [Global and Relative Phase](https://pavanjayasinha.medium.com/but-what-is-a-quantum-phase-factor-d05c15c321fe)
  (Note that global of a qubit doesn't really matter, relative phases are more important)

