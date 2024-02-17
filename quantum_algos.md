# Quantum Algorithms

Quantum Algorithms are specifically curated for quantum computers to showcase how useful they can be in certain cases, for ex: running classically exponential time programs in polynomial time.

Before you learn this, please revise some common Qubit gates like:
 - Pauli X,Y and Z
 - Hadamard
 - CNOT (also learn that CNOT creates entanglement only if the control qubit is in a superposition state)
 - Toffoli
 - Modified CNOT (which is activated when control Qubit is |0⟩)
 - U gate (which can be used to generate an arbitrary qubit), alongside Rx, Ry and Rz operators
 - An interesting modification of CNOT gate which works only when the control qubit is |0>.
    ![image](https://github.com/lakshya-chopra/quantum-computing/assets/77010972/c2e31bfd-0d82-4e61-aa81-0d0206be2de3)
 - more:
   ![image](https://github.com/lakshya-chopra/quantum-computing/assets/77010972/606041af-15dc-4f5b-98d2-1f2a13fb0e4e)
- Toffoli gate:
  ![image](https://github.com/lakshya-chopra/quantum-computing/assets/77010972/68e5ad8d-c1e2-44d5-9022-25c46c3f9901)
- Decomposition of multiqubit (n) Toffoli gates  with the help of (n - 2) ancilla bits and CNOT gates.
- Toffoli gate with empty control bits (activated by 0)


Let's look at some common Quantum algorithms :

- Deutsch-Josza:
 - This algorithm determines whether a function is balanced or constant with 100% accuracy in just a single shot, unlike classical computers which might need upto 2^(n-1) + 1 possible shots.

 - It uses Hadamard gates to make use of quantum parallelism, this allows it to test all the possible input combinations in just a single shot.

 - There are n+1 input qubits, with the first n being the actual inputs and the last one an auxiliary.

 - An oracle is used which implements a function f(x), which is obtained using the (n+1)th Qubit that is set to |0⟩.
 - Here's how the oracle is implemented for a single qubit function:
   ![image](https://github.com/lakshya-chopra/quantum-computing/assets/77010972/1c0ce24a-1975-4bee-b9d8-65c2027037cc)
 - Circuit Diagram:
   ![image](https://github.com/lakshya-chopra/quantum-computing/assets/77010972/9117f696-3239-420e-b0c3-ef4520abfda6)
 
 - The computation behind the algorithm is big and can be read at the above mentioned source itself.
 - The final result for 0...0 bitstring is always 0...0 in the case of constant functions and something else for balanced functions.
 - For multi qubit functions, we use Toffoli gates to implement a balanced oracle.
- Bernstein-Vazirani: This is another algorithm based on the above mentioned Deutsch Josza algo. It is concerned with finding a hidden bit string "s" which is utilised by a function f(x) = s.x, where (.) -> indicates the inner product of the two bitstrings.
   - The classical approach to find s involves N tries, where N = number of bits in the bitstring, and is implemented by passing to the function 0...01, 0...10, until 1...00, where the last bit becomes 1 and rest all are zero.
   - The quantum approach utilises the power of Quantum Parallelism (using Hadamard Gates) and takes only 1 try, thus provides a tremendous speedup over the classical approach.


 #### ALL the picture credits to this really good & informative research pdf: [Basic Quantum Algorithms](https://arxiv.org/pdf/2201.10574.pdf)
