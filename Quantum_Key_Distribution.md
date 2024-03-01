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

Some important points:
  - It is a common misunderstanding that QKD is also used to encrypt & distribute data, which it doesn't. It is meant to produce and distribute a key which later on is used by an encryption algorithm such as AES256 to encrypt the data.
  - Thus, QKD can replace PKC, which requires 2 keys: Public & Private.
  - The security of QKD is proved by Information Theory, & forward secrecy.
## Key Exchange :
  - The key exchange involves the encoding of information in qubits (usually photons).
  - In general, 2 main protocols are used to encode information:
      - Prepare and measure
      - Quantum Entanglement: Here two qubits are entangled such that they become combined states which can not be individually separated, changes in any one of the state affects the another (note that this is not some sort of teleportation that takes place, but instead the two qubits are correlated upon their formation. This is helpful in key distribution, as it immediately detects any forgery.
      - 
