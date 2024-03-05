## Quantum Key Distribution
Quantum Key Distribution, as opposed to Public Key Cryptography, uses the components of Quantum Mechanics to enable a secure channel of communication between 2 parties. This is standardized by various protocols, that are:
listed as follows:
  - [BB84](https://arxiv.org/abs/2312.05609)
  - [E91](https://mpl.mpg.de/fileadmin/user_upload/Chekhova_Research_Group/Lecture_4_12.pdf)
  - DIKQKD
  - TFKQKD
(i will add more resources later)

## QKD has the ability to detect any attempts made by any third party to access/gain knowledge of the key, this is possible through the measurement paradox, because any measurement will introduce detectable anomalies on the key. 
The process of measuring any key will in general disturb the system.

Public Key Cryptography: :point_down:
![image](https://github.com/lakshya-chopra/quantum-computing/assets/77010972/141833ae-3053-46d8-bdaf-7c98a991f04e) 

Some important points:
  - It is a common misunderstanding that QKD is also used to encrypt & distribute data, which it doesn't. It is meant to produce and distribute a key which later on is used by an encryption algorithm such as AES256 to encrypt the data.
  - Thus, QKD can replace PKC, which requires 2 keys: Public & Private. PKC also poses a problem since it relies on computational tasks that are based on the unproven assumption of being hard to solve, such as factoring a really large integer into a product of its primes.
  - The security of QKD is proved by Information Theory, & forward secrecy.Thus, theoretically, QKD is unhackable since any attempts to access the information leaves behind evidence, and the key 🗝️🔐 only decodes a small amount of a secure information and the private key may be changed every second. Also, the measurement of any one quantum observable intrinsically creates an uncertainity in the other properties of the system, i.e. one cannot measure non commuting observales simultaneously, this is established from the **Uncertainity Principle** (which states that if you measure one aspect of a quantum system, like its position or momentum, with high precision, there will unavoidably be a degree of uncertainty in some other related property, such as its momentum or energy).
  - Another safety feature of QKD is highlighted from the *No Cloning Theorem*, which states that it is impossible to create an exact copy of a quantum state through general quantum gates (/operations). Thus, this prevents an eavesdropper to make copies of the state being transferred.
  - *Non Orthogonality Principle* states that the measurement outcome of two states that are not orthogonal to each other can be distinguished. This is again very useful as it guarantees that one can not determine which of the two non orthogonal states were measured.
  - [Useful PPT](https://www.slideserve.com/sun/the-adventures-of-alice-bob-eve-in-the-quantumland)
  - The successful transmission of secure information with a quantum channel has made QKD possible, and much more practical for the real world.
  - QKD involves 2 parties that wish to exchange keys through a classical and quantum channel. The Quantum channel is required to send quantum states, which doesn't need to be secure, and can be implemented over fiber optic, and even over free space. 
**Quantum Channel* is one which transmits qubits, where the states O and 1 are attached to photons by **Polarization**(incase of a fibre optic channel).

 - In Discrete Variable QKD, quantum info is encoded into DVs and binary data are measured by *single photon detectors* to extract the received quantum states. Here, the information is directly encoded into the polarization or phase state of the transmitted photon. (QM allows transfer of single photons).
- In Continuous Var QKD, the wave nature of light is utilised, and quantum info is encoded into the amplitude and phase of a *coherent* laser and is measured using **Homodyne detectors**.
- ![image](https://github.com/lakshya-chopra/quantum-computing/assets/77010972/d4bca1ac-3e49-459b-8bc1-bf4b730b3794)
- ![Source: Science Direct](https://github.com/lakshya-chopra/quantum-computing/assets/77010972/08a756bd-a1c9-40a7-8da9-8f6b7f38b03b) 


## Management of Secure keys:

 - Key Exchange
 - Key Sifting
 - Secret Key Distillation 


## Key Exchange :
  - The key exchange involves the encoding of information in qubits (usually photons).
  - In general, 2 main protocols are used to encode information:
      - Prepare and measure : In this, Alice encodes some classical information into quantum states, and sends it to Bob using an insecure channel of communication, later Bob performs some measurements on the received data to obtain the info (similar to **Quantum Teleportation**). Examples of protocols that use this: BB84, B92, & six-state protocols.
      - Quantum Entanglement: Here two qubits are entangled such that they become combined states which can not be individually separated, changes in any one of the state affects the another (note that this is not some sort of teleportation that takes place, but instead the two qubits are correlated upon their formation).<br>This is helpful in key distribution, as it immediately detects any forgery.
        <br>Alice prepares a *Maximally entangled Quantum state* (maximally entangled ensures complete correlation), of which one is sent to Bob and Alice keeps the other. Both of them perform measurement in two *[mutually unbiased system](https://en.wikipedia.org/wiki/Mutually_unbiased_bases)*, upon measurement, they both achieve a perfectly correlated states, which are RANDOM. An example of this includes the protocol: E91. <br>
Mutually Unbiased Bases can also be used for Quantum Error Connection, Quantum State Reconstruction and detection of Entanglement. (for ex: measurement of ket (+) results in 50-50 probability of both ket 0 and ket 1). Here, the main thing is: the measurement outcomes of a state prepared in a basis e<sub>i</sub> with respect to another basis state f<sub>i</sub> have the same probability. In slighlty easier words, this means the probability of measurement of outcomes in one basis are independent of the states prepared in other basis, with each outcome having an equal likelyhood. <br>
## Protocols:
<br>
(Note: Quantum Teleportation is a protocol for transmitting quantum states across distances, involves entanglement, while the BB84 quantum key distribution protocol is designed for secure communication by generating shared secret keys and involves the use of No Cloning Theorem.)<br>
<br>
- BB84: Alice and Bob use an insecure quantum channel and an authenticated classical channel.
  - Quantum Phase: First, Alice prepares a random quantum state encoding each bit (message bits) with the help of 4 basis states: horizontal, vertical, diagnol, & anti-diagnol (Photons as qubits). This is then sent to Bob, via a quantum channel, who then applies a quantum measurement to decode the bit values, effectively collapsing the state sent. Both Alice and Bob record their measurements & alice also notes the quantum system/state she sent and the relevant encoding. The transmission over the quantum channel introduces noise and effects of the eavesdropping attempts.
      
 - Classical Phase: 


### References:
  - [Helpful Link](https://medium.com/@qcgiitr/fundamentals-of-quantum-key-distribution-bb84-b92-e91-protocols-e1373b683ead)
  - [More on BB84](https://www.global.toshiba/ww/company/digitalsolution/articles/tsoul/38/004.html)
  - [Quantum Channel](https://www.sciencedirect.com/topics/engineering/quantum-channel)
  - [Quantum Indeterminacy](https://en.wikipedia.org/wiki/Quantum_indeterminacy)
  - [QKD/Wikipedia](https://en.wikipedia.org/wiki/Quantum_key_distribution)
  - [book](https://www.intechopen.com/chapters/59491)
