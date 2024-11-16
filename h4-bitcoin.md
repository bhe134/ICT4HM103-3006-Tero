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
