# Quantum Algorithms

Quantum Algorithms are specifically curated for quantum computers to showcase how useful they can be in certain cases, for ex: running classically exponential time programs in polynomial time.

Before you learn this, please revise some common Qubit gates like:
 - Pauli X,Y and Z
 - Hadamard
 - CNOT (also learn that CNOT creates entanglement only if the control qubit is in a superposition state)
 - Toffoli
 - Modified CNOT (which is activated when control Qubit is |0⟩)
 - U gate (which can be used to generate an arbitrary qubit), alongside Rx, Ry and Rz operators
 - An interesting modification of CNOT gate which works only when the control qubit is |0⟩.
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
 - The circuit has Hadamard Gates on both sides of the oracle which utilises the symmetry. The Hadamards after the oracle work to amplify the probability of the correct outputs and minimize those which are incorrect.
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

### Simon’s Problem: This is another particular case of the Deutsch Josza Algorithm. It is exponentially faster than the best known classical algorithms. This algorithm exploits **Quantum Parallelism** and **Maximal Entanglement** (like in Bell States). It is basically used to determine whether a function is one to one or two to one. 
 - The classical approach to determine this involves 2<sup>n/2</sup> in the best case and 2<sup>n</sup> in the worst, Simon's algo can do the same in n try.
 - Here, we are given a function f : {0,1}<sup>n</sup> -> {0,1}<sup>n</sup>, we have a secret string s (which has the same number of bits as the domain) such that f(x) = f(y) where y = x ⊕ s.
 - Here, we have 2n bits going through/out of the oracle, first n are the inputs, and the next n are used to store the outputs after applying the oracle U<sub>f</sub>.
 - All the 2n qubits are initialized to 0.....0 initially.
   <br>![image](https://github.com/lakshya-chopra/quantum-computing/assets/77010972/29af3584-eea3-4c7b-a622-43a203ee5259)
 - The algorithm is implemented in the almost entirely same way as the above 2 algos, where first we apply the Hadamard gates and then U<sub>f</sub> acts on the state
   ![image](https://github.com/lakshya-chopra/quantum-computing/assets/77010972/3729e462-cd34-428c-b41b-afa912e6b6cb)
 <br> to produce
   ![image](https://github.com/lakshya-chopra/quantum-computing/assets/77010972/272bea8a-f895-4922-91cc-5ef502428b3f)
 - After application of the oracle function, we measure the last n qubits, if we get f(x) = z<sub>0</sub>z<sub>1</sub>....z<sub>n</sub>, the first n qubits collapse to  a superposition of the points in the domain that will give us this f(x).
 - ![image](https://github.com/lakshya-chopra/quantum-computing/assets/77010972/61bb73f1-5c6d-40b6-8d1a-c97e37fbbd06)
 - After application of the second set of Hadamard gates on the first n qubits, we get: <br>![image](https://github.com/lakshya-chopra/quantum-computing/assets/77010972/80a30154-048a-4894-9828-a81b89333eeb)
 - This can further be simplified to this, ![image](https://github.com/lakshya-chopra/quantum-computing/assets/77010972/e4edc07a-cbf6-451c-bf76-9b4090c619d9) <br> after writing (x' + s) as: ![image](https://github.com/lakshya-chopra/quantum-computing/assets/77010972/076b1b78-1efd-490d-b786-04ce2dc334d7)
 - 




#### The above mentioned algorithms work on a similar principle that is Quantum Parallelism where the Hadamard gates generate all the possible combinations at the same time.The Oracle function applies the function for all possible qubit combinations and computes the output. The Oracle does a trick by applying a *Phase Inversion* on the input bits which encodes the result of the computation onto the input bits.

#### The final set of Hadamard gates lead to constructive interference of the desired outputs (amplification of probability amplitudes) and destructive for the undesired ones, giving us a very high probability to get the correct result in just 1 try.





 #### References: 
   - [Basic Quantum Algorithms](https://arxiv.org/pdf/2201.10574.pdf)
   - [Bernstein-Vazirani](https://www.ryanlarose.com/uploads/1/1/5/8/115879647/bv-algorithm.pdf)
