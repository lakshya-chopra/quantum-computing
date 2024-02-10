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
 
