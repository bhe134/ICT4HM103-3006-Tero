## 1 Introduction
  * The commerce over the internet has predominantly relied on financial institutions as the main trust parties for the processing of all the electronic payments.
  * This works for most transactions; however, this system suffers the weakness of the trust-based model that is completely non-irreversible transactions aren’t possible.
  * In turn, this drives up the transaction costs, limits minimum transactions sizes.
  * Merchants also collect so much information from potential customers as the need for trust spreads.
  * Thus, a certain percentage of fraud is accepted as being inevitable.
  * The peer-to-peer electronic cash systems removes the need for the trusted party since its based on cryptographic proof of trust. 
  * Two parties can directly transact with each other without the need of a trusted party.
  * Transactions are computationally impossible to reverse.
  *  Double spend is eliminated by using the peer-to-peer distributed time stamp server that generate a chronological order of transactions.
  *  The system is secure when collectively the honest nodes control the CPU power than any group of attacker nodes.

## 2 Transactions
  * Electronic coin is a chain of digital signatures.
  * At each transfer an owner digitally signs a hash of the previous transaction and the public key of the next owner adding this at the end of the coin.
  * Payee verifies the signatures to verify the chain of ownership.
  * There isn’t a way for the payee to verify if the coin has been doublespent. This check would need a central party (mint) just like a bank to verify and create a new coin each time.
  * The payee cares only about the earliest transaction and doesn’t care about later attempts to double spend.
  * Transactions are publicly announced and the majority of the trusted nodes must agree it was the first transaction received.

## 3 Timestamp Server
  * Timestamp server works by taking the hash of block of items and widely publishing the hash.
  * It proves that the data must have existed before the timestamp and then the hash was created.
  * Timestamps are consecutive such that each timestamp includes the hash of the previous timestamp and so forth.

## 4 Proof-of-Work
  * Proof of works involves scanning for a value when hashed the resulting hash begins with a number of zero bits.
  * Average work required is exponential in the number of zero bits required.
  * Implementing a nonce in the block until a value is found gives the hash the required number of zeros.
  * Proof of work is one-CPU-one-vote
  * To modify a past block, the attacker would have to re-do the proof of work of that block and all the blocks after it, catch up and then surpass the work of honest nodes.
  * The success rate of an attacker decreases exponentially as subsequent blocks are added. Infact, if blocks are generated too fast, the attackers success rate is severely decreased exponentially.

## 5 Network
  * Nodes accept the longest chain as the correct one and keep working on extending it.
  * Procedure:
      * New transactions are broadcast to all nodes
      * Each node collects these transactions into a block
      * Each node does a proof of work for its block
      * Proof of worked blocks are then broadcasted to all nodes
      * Nodes accept block if all transactions are valid and there is no double spend.
      * Nodes accept the longest block and continue by working on next block by creating a hash of the previous block.
  * New transactions dont need to reach all nodes, as long as they reach many nodes they will get into a block before long.

##6 Incentive
  * First transaction is a special transaction that starts a new coin owned by the creator of the coin.
  * CPU time and electricity is expended to add to the coin.
  * Incentive can be funded with transaction fees.
  * Output value of a transaction is less that input value, the difference is a transaction fee that is added to the incentive value of the block containing the transaction.

## Reference
Satoshi Nakamoto, Bitcoin: A Peer-to-Peer Electronic Cash System

## a). Install electrum bitcoin testnet wallet. Create a BitCoin testnet wallet. 

install the necessary dependencies

![image](https://github.com/user-attachments/assets/cea1753c-12fa-495e-92b5-3a68757612ae)
![image](https://github.com/user-attachments/assets/989b7839-d679-4d99-995b-240345916a4e)

download the latest version of the Electrum wallet from the official website by using the wget command.
The .tar.gz and .asc files already downloaded in the steps above.

![image](https://github.com/user-attachments/assets/1a8d6622-dda2-470f-b0ed-9cff04ce77f3)
![image](https://github.com/user-attachments/assets/0001d148-4d95-4397-a140-6cb1daaea176)

Verify the GPG signature of the download
![image](https://github.com/user-attachments/assets/4a376dc5-91e2-4813-9b05-1a8c2ab60384)

Generate your own private key. No need to generate a private key. There is a private key from another exercise.
![image](https://github.com/user-attachments/assets/3f6162b2-98dd-4495-9cf5-865100851349)

Sign the electrum public key downloaded with the private key
![image](https://github.com/user-attachments/assets/ca9833d6-24e2-4aa6-9713-ca8847f3ff92)

We can now download the key file and verify the signature:
![image](https://github.com/user-attachments/assets/f117a509-0262-463f-abc0-17b05a206b56)

Install the application on your system
![image](https://github.com/user-attachments/assets/1fb776f0-4a3d-4271-b0c2-d096e44d5b71)

Problemo running the installation!
![image](https://github.com/user-attachments/assets/87ce2215-848d-46ef-8969-54546f64afca)
![image](https://github.com/user-attachments/assets/4d87429c-50fa-46eb-b37e-028b62323172)

Installation
![image](https://github.com/user-attachments/assets/58842450-4690-4eea-a2b6-aad4e606befa)
![image](https://github.com/user-attachments/assets/5f22d68f-aefe-43f3-afd8-e496eb4ab928)
![image](https://github.com/user-attachments/assets/6204bd4c-27cf-4e3b-946f-a05e9a65fc8e)
![image](https://github.com/user-attachments/assets/277a2cd5-f0c8-4e52-bad7-830040db67f1)

Start Electrum wallet
![image](https://github.com/user-attachments/assets/e67421a0-17ca-4b06-97dd-03e0d6d7177f)

Create a BitCoin testnet wallet
![image](https://github.com/user-attachments/assets/e122ed26-6c62-434e-8072-5d3c9076b747)

## Reference
https://linuxconfig.org/how-to-install-electrum-bitcoin-wallet-on-debian-ubuntu-linux

## b) Faucet. Get worthless fake money from a testnet Bitcoin faucet.
Create a test request and copy the address
![image](https://github.com/user-attachments/assets/0301b4f1-acf7-4a37-be4b-475d18adcc2a)

Copy the address into the faucet for the test bitcoins and press get Get bitcoins.
![image](https://github.com/user-attachments/assets/ebcd02d1-2b36-4028-9b8e-0aa6d9e4df1f)
![image](https://github.com/user-attachments/assets/ea1a6994-841e-4309-a88f-9c957716c033)
![image](https://github.com/user-attachments/assets/56a8b6f9-c11e-4a90-b2af-db176d82bcda)

## c) Giveway. Move money to another Bitcoin wallet. Choose an amount where the last two digists are 73.

## d) Recycle. Move the testnet money back to the same faucet you got it from.
![image](https://github.com/user-attachments/assets/ac591975-4419-4d55-88ce-3231435eb38d)
![image](https://github.com/user-attachments/assets/b0a1fae1-a518-4d2f-b3a9-247c62bf4610)

## e) Explorer. Use a block explorer to analyze a block on the real Bitcoin blockchain

## f) RogeCoin


