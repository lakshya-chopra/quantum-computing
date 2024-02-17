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
- Toffoli gate with empty control bits (activated by 0).
- Identities like, H^2 = I, H ⊗ H = (H ⊗ I)(I ⊗ H), HZH = X, and HXH = Z.
- ![image](https://github.com/lakshya-chopra/quantum-computing/assets/77010972/111387ba-fbb1-41be-9c6b-079d8da697c1)
  
- <br>[source](https://quantumcomputing.stackexchange.com/questions/13782/cnot-expressed-with-cz-and-h-gates-by-taking-into-account-hzh-x)
- [also check this out](https://quantumcomputing.stackexchange.com/questions/12458/show-that-a-cz-gate-can-be-implemented-using-a-cnot-gate-and-hadamard-gates?)


Let's look at some common Quantum algorithms :

- ### Deutsch-Josza:
 - This algorithm determines whether a function is balanced or constant with 100% accuracy in just a single shot, unlike classical computers which might need upto 2^(n-1) + 1 possible shots.

 - It uses Hadamard gates to make use of quantum parallelism, this allows it to test all the possible input combinations in just a single shot.

 - There are n+1 input qubits, with the first n being the actual inputs and the last one an auxiliary.

 - An oracle is used which implements a function f(x), which is obtained using the (n+1)th Qubit that is set to |0⟩.
 - Here's how the oracle is implemented for a single qubit function:
   ![image](https://github.com/lakshya-chopra/quantum-computing/assets/77010972/1c0ce24a-1975-4bee-b9d8-65c2027037cc)
 - Circuit Diagram: <br>
   ![image](https://github.com/lakshya-chopra/quantum-computing/assets/77010972/9117f696-3239-420e-b0c3-ef4520abfda6)
 
 - The computation behind the algorithm is big and can be read at the above mentioned source itself. The main crux of the computation is the phase inversion applied by the oracle which allows us to determine the nature of the function in just one attempt.
 - The cricuit has Hadamard Gates on both sides of the oracle which utilises the symmetry. The Hadamards after the oracle work to amplify the probability of the correct outputs and minimize those which are incorrect.
 - The final result for 0...0 bitstring is always 0...0 in the case of constant functions and something else for balanced functions.
 - For multi qubit functions, we use Toffoli gates to implement a balanced oracle.<br>
- ### Bernstein-Vazirani: This is another algorithm based on the above mentioned Deutsch Josza algo. It is concerned with finding a hidden bit string "s" which is utilised by a function f(x) = s.x, where (.) -> indicates the inner product of the two bitstrings.
   - The classical approach to find s involves N tries, where N = number of bits in the bitstring, and is implemented by passing to the function 0...01, 0...10, until 1...00, where the last bit becomes 1 and rest all are zero.
   - The quantum approach utilises the power of Quantum Parallelism (using Hadamard Gates) and takes only 1 try, thus provides a tremendous speedup over the classical approach.
   - The quantum approach utilises the concept of an Oracle,<br>![image](https://github.com/lakshya-chopra/quantum-computing/assets/77010972/146eb547-e02e-42fc-bfeb-dceb19784877)<br>Here, x is a n-bit bitstring and y is the output bit. ⊕ represents the XOR Gate or sum (mod 2).

   - Phase Inversion (or Kickback) is the amazing trick utilised here.
   - This algorithm too doesn't have any sort of entanglement, the only operator which can create entanglement is U<sub>f</sub>, which too requires a state which is either fully entangled or partially, however, the state |ψ2> is fully unentangled as it can be factorised completely in the following way: <br>
   ![image](https://github.com/lakshya-chopra/quantum-computing/assets/77010972/9b510d6d-c92f-4f86-8273-d0447f50bb99)

  - Here's how a sample oracle with s = 1011 can be implemented. Notice how we use a CNOT for each bit '1' in s. We can generalize this as follows: (CNOT<sub>ij</sub>)^i, i can either be 0 or 1 and j is the output Qubit (the target)
  ![image](https://github.com/lakshya-chopra/quantum-computing/assets/77010972/557d527f-ae47-4a7a-922b-b89e238e13ea)



 #### ALL the picture credits to this really good & informative research pdf: [Basic Quantum Algorithms](https://arxiv.org/pdf/2201.10574.pdf)
