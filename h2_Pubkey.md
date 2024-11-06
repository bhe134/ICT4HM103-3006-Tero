## Introduction:
* Cryptography attemps to solve a problems involving secrecy, authentication, integrity, and dishonest people or actors.
* Protocols  are steps between two or more parties to accomplish a task.
* Protocols, parties involved must know the protocol, must agree to follow the protocol, protocol must be clear to all parties, and the protocol must be complete.
* Cryptographic protocol: a protocol that uses cryptography. It invoves some cryptographic algorithm
## 2.5 COMMUNICATIONS USING PUBLIC-KEY CRYPTOGRAPHY
* Whitfield Diffie and Martin Hellman described public-key cryptography in 1976.
*	There consists of a public key and a private key. The public key is used to encrypt, while the private key is used for decrypting. The private key is secret.
*	How does it work:
    1). Alice and Bob agree on a public-key cryptosystem.
    2). Bob sends his public key to Alice.
    3). Alice encrypts the message with Bobs public key
    4). Bob decrypts the message with his private key.
*In a network users store their public keys in a database
	  1). Alice gets Bobs public key from the DB. Encrypts the message and sends to Bob.
    2). Bob decrypts the received message with his own private key.
*	Public key alogirithms are used to encrypt keys and not messages because: they are slow and are vulnerable to plain text attacks.
*	Infact, public-key cryptography is used to secure and distribute the session keys. These session keys are used to secure the message and this is called hybrid cryptosystem.
## 2.6 DIGITAL SIGNATURES
*	Possible to sign documents with a symmetric cryptosystem and an arbitrator.
*	The aribtrator shares different and unique secret keys to party A and B.
*	A encrypts a message with secret A, arbitrator gets the message and descrypts it with secret A, he encrypts the message with secret B and sends to B. Finally B, decrypts the message with secret B. This is time consuming, the arbitrator can be compromised thus revealing all secrets and this would result in chaos.
*	RSA Public key algorithms can be used for digital signatures where either the public key or private key is used for encryption.
*	Signing refers to encrypting with a private key, verification refers to decrypting with a public key.
## 2.7 DIGITAL SIGNATURES WITH ENCRYPTION
*	There is a combination of the security of encryption and authenticity of digital signature. It is analogous to having a letter from Mom. The signature proofs the authorship is Mom and the envelope further provides an added layer of privacy.
*	Thus, the act of signing before encrypting the message.
## 2.8 RANDOM AND PSEUDO-RANDOM-SEQUENCE GENERATION
*	Random number generators are not very random and don’t have to be. They are not secure enough for cryptography.
*	Cryptography is extremely sensitive to the properties of random-number generators.
*	A sequence generator can be termed pseudo-random if the randomness we can find passes statistical tests that is it looks random.
*	All of these pseudo-random generators are periodic with a potential of 2 to the power of 256 bits or higher.
*	One of the problem is wierd correlations and strange results. A cryptanalyst can use this as an attach basis. 
*	A cryptographically secure pseudo-random must be, unpredictable i.e. computationally impossible to predict the next random bit. Finally, it cannot be reliably reproduced, for example running the sequence generator two times with the same input results in completely unrelated random sequences.

## Reference: 
Bruce Schneier. March 2015. Applied Cryptography: Protocols, Algorithms and Source Code in C, 20th Anniversary Edition. Wiley. E-book. Accessed: 3 November 2024.

Pubkey today. Explain how you have used public key cryptography today or yesterday, outside of this homework. In addition to naming the system, identify how different parties use keys in different steps of the system. (Answering this question likely requries finding sources on your own. This subtask does not require tests with a computer.)

Usecase: SSH access to an internal log collection server.
For the secure connection to this internal log collection server, I generated a key pair. The public key I uploaded to the server and configured it such that while connecting to this server, it encrypts a challenge message with the uploaded public key. My client PC has the private key and thus interns decrypt this challenge message with the private key satisfying the ownership of the private key. This setup allows the login to the server without numerous uses of username and passwords.

Messaging. Send an encrypted and signed message using PGP, then verify and decrypt it. (You can use folders to simulate users or use two computers or two different OS users. Don't use Tero as a name of any party, unless that's your given name.)
The process below shows messaging between Alice (user1) and Martin (user2). The messaging is encrypted and signed using PGP. First, PGP is installed and then starts the process to generate key pairs, sign, encrypt and send the message. At user2s end, the message is finally decrypted.
## Generate Martins Keypair
![image](https://github.com/user-attachments/assets/d33d369b-2801-4b71-a9c7-c072bfe2693e)
![image](https://github.com/user-attachments/assets/03ce4e1a-768f-46d7-95bb-c463052503ba)
![image](https://github.com/user-attachments/assets/ae219456-3620-48a0-a487-63a4e0e6a0e2)
## Export My Public Key
![image](https://github.com/user-attachments/assets/a1eaeece-5ac5-49c9-a10e-8ebd0517c04c)
## Alice, Simulated
![image](https://github.com/user-attachments/assets/b1b5ace1-02c0-45be-bebf-d4fc6b8e8e9f)
![image](https://github.com/user-attachments/assets/62a144ab-3056-47a6-9e18-31dd589480c5)
## Alice Imports and Verifies Martins key
![image](https://github.com/user-attachments/assets/ffa9e2d1-e33f-4ed0-95a1-870f5d106071)
![image](https://github.com/user-attachments/assets/90e1761d-d271-4c10-90f3-7b970c10ee95)
![image](https://github.com/user-attachments/assets/b1a80733-55c8-4dde-9562-d330926b824c)
![image](https://github.com/user-attachments/assets/ebb77562-025f-4990-8c85-c0ddba38960b)
## Martin needs Alices Public Key to Know It's Her
![image](https://github.com/user-attachments/assets/48a01605-08a5-407b-94fe-54250b3830d9)
![image](https://github.com/user-attachments/assets/d62d295d-8a3d-467e-962f-b032f19bf17f)
![image](https://github.com/user-attachments/assets/b223385f-7695-4c56-bda1-4a1e2ee15dec)
![image](https://github.com/user-attachments/assets/07874564-bd4f-4290-9acb-66124fe3e0b1)
## Alice Sends a Secret Message
![image](https://github.com/user-attachments/assets/9e5a5ab7-cbce-4c11-8d08-a56a326116b5)
## Martin Decrypts and Verifies the Message
![image](https://github.com/user-attachments/assets/4cb81a4f-768b-450d-97d0-c63ac3f1fcaf)
## Reference: Tero, K. 2024. PGP - Send Encrypted and Signed Message - gpg URL: https://terokarvinen.com/2023/pgp-encrypt-sign-verify/. Accessed: 5 November 2024.
Eve and Mallory. In many crypto stories, Eve is a passive eavesdropper, listening on the wire. Mallory malliciously modifies the messages. Explain how PGP protects against Mallory and Eve. Be specific what features, which use of keys and which flags in the command are related to this protection. (This subtasks does not require tests with a computer).
Focusing on the example of communications with symmetric cryptography. We have Alice and Bob communicating.
  1.	Both parties agree on a cryptosystem
  2.	Next, both agree on a key.
  3.	Alice takes her plaintext message, encrypts it using the encryption algorithm and the key. The results in a ciphertext message.
  4.	Alice sends her ciphertext message to Bob.
  5.	Bob using the same algorithm and key decrypts the message and reads it.
### Case1: Eve is a passive eavesdropper.
Eve is an eavesdropper and sits between Alice and Bobs communication. Her intention is to intercept and read the messages between Alice and Bob. She sees the ciphertext message. She attempts to cryptanalyse the ciphertext however, a key feature in the algorithm its resistance to cryptanalysis with whichever computing power. However, if Eve listened on steps 1 and 2, she would learn the algorithm and key and would use that to decrypt the cipertext. Through key management, the key must be kept secret before, during and after the protocol. Hence, by encrypting messages we ensure protection against eavesdropping and that only the intended recipient reads the message.
### Case 2: Mallory malicious modifier of the message
Mallory is an active attacker. He could attempt several things; break the communication path in step 4 thus both parties could not take to each other, intercept the message from Alice, replace it with his own,or if he has the key he could encrypt and send the message to Bob pretending to be Alice. Bob wouldn’t have a way to know the message isn’t from Alice. Even if he didn’t know the key, he can still replace the message which would decrypt to gibberish at Bobs end. We would conclude that the network has problems. In addition, authentication ascertains the origin of the message and that alteration has not occurred.
## Reference: 
Bruce Schneier. March 2015. Applied Cryptography: Protocols, Algorithms and Source Code in C, 20th Anniversary Edition. Wiley. E-book. Accessed: 3 November 2024.
Password management. Demonstrate use of a password manager. What kind of attacks take advantage of people not using password managers? (You can use any password manager, some examples include pass and KeePassXC.)
## Brute Force Attack.
This involves attempting numerous (sometimes in the trillions) of possible password or combinations. Most users, that do not use password managers can most likely use simple to recall or remember password that are susceptible to brute force attachs.
## Dictionary Attack.
This involves using password possibitlies that are personal to the user. For example, pet name, birth date, first surname and birthday date etc. Again, having predictable passwords that the user finds easy to recall and remember.
Its also possible for users to have their credentials in plaintext written on papers, physical and electronic notepads. A malicious user can land on this credentials in plain text. Infact, some are left in the open or in the even these items holding the credentials are lost of misplace. Infact, other users use the same credentials for different platforms.
## Install the pass:
 ![image](https://github.com/user-attachments/assets/58c7c14b-30c6-442b-9334-3dd9bbeca6be)
## Get the GPG key pair:
 ![image](https://github.com/user-attachments/assets/384cbe6e-3a76-4e05-b73a-9e92f79009b5)
## Initialize the password store:
 ![image](https://github.com/user-attachments/assets/4bcfeabc-fb0f-420a-bdbf-3b522505d249)
## Add passwords to the Store
![image](https://github.com/user-attachments/assets/caf923dd-cc43-4259-91e9-0aad2938051f)
![image](https://github.com/user-attachments/assets/82493313-bfba-4c9e-8c24-f2a958746765)
![image](https://github.com/user-attachments/assets/dc372ef8-2774-4554-9c7d-213c0dfa3923)
## Show the password:
 ![image](https://github.com/user-attachments/assets/00e8ab01-3f0d-499a-9e41-ef8c1ce304eb)
## Reference
OneLogin. 2024. Six Types of Password Attacks & How to Stop Them. URL:https://www.onelogin.com/learn/6-types-password-attacks. Accessed: 5 November 2024.

Jason A. Donenfeld, 2024. Pass the standard unix password manager. URL: https://www.passwordstore.org/. Accessed: 5 November 2024.

Massimo Musumeci. 29 September 2024. Configuring Password store on Debian. URL:https://massmux.org/p/configuring-password-store-on-debian. Accessed: 5 November 2024.

