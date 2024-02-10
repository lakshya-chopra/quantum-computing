# Quantum Algorithms

Quantum Algorithms are specifically curated for quantum computers to showcase how useful they can be in certain cases, for ex: running classically exponential time programs in polynomial time.

Before you learn this, please revise some common Qubit gates like:
 - Pauli X,Y and Z
 - Hadamard
 - CNOT
 - Toffoli
 - Modified CNOT (which is activated when control Qubit is |0⟩)
 - U gate (which can be used to generate an arbitrary qubit), alongside Rx, Ry and Rz operators

Let's look at some common Quantum algorithms :

- Deutsch-Josza:
 - This algorithm determines whether a function is balanced or constant with 100% accuracy in just a single shot, unlike classical computers which might need upto 2^(n-1) + 1 possible shots.

 - It uses Hadamard gates to make use of quantum parallelism, this allows it to test all the possible input combinations in just a single shot.

 - There are n+1 input qubits, with the first n being the actual inputs and the last one an auxiliary.

 - An oracle is used which implements a function f(x), which is obtained using the (n+1)th Qubit that is set to |0⟩.
 - Here's how the oracle is implemented for a single qubit function:
   ![image](https://github.com/lakshya-chopra/quantum-computing/assets/77010972/1c0ce24a-1975-4bee-b9d8-65c2027037cc)
   [Source](https://arxiv.org/pdf/2201.10574.pdf)
 - Circuit Diagram:
   ![image](https://github.com/lakshya-chopra/quantum-computing/assets/77010972/9117f696-3239-420e-b0c3-ef4520abfda6)

 - The computation behind the algorithm is big and can be read at the above mentioned source itself.
 - The final result for 0...0 bitstring is always 0...0 in the case of constant functions and something else for balanced functions.


 
