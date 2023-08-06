# The Blockchain Talk @ Tower

* What should the contents be?

* Where do animations make sense?
    * Where to steal them from?

## Contents

### My talk

* Abstract

* L+C-T

* Why
    * Historical perspective
    * Before we move ahead, why would anyone want to do this?
    * Taking a look at the historical setting will help us understand where 

* Ledger
    * ABC Y
        * Exchange money for goods/services
        * Cash can be inconvenient
    * Ledger
        * Record txns
    * Ledger Book
        * Soon enough, as more txns are added your ledger grows, so you add more pages!
        * Do note that txn order matters

* Blockchain data-structure
    - You sprinkle some computer science onto this ledger and you get BC DS
    - Is it just a prev-ptr based linked list?
    - Hash ptrs and not memory addresses

* Crypto hashing 
    * Hash as a fingerprint of a block
    * Chain contains hash ptrs
        * First block is special - null ptr!
    * If a block changes - all following blocks must change as well!

* Why?
    * Let's think about why we're doing this & that'll take us to the heart of the issue - which is Trust!
    * Where is the ledger stored?

* Who? Where?
* Traditional Txns
* P2P Network
* Blockchain Network
    * Decentralized
    * Okay so what we're proposing is P2P Network
    * New Block
        * Everyone has a copy of the entire chain
        * They all have 3 blocks each
        * And a 4th one arrives
        * They all add it onto the top and all is well!
        * If only, life were this easy!
    * 

* Git repo as a blockchain

* Bitcoin
    - What exactly did Nakamoto invent?
    - Txns & Blocks, Timestamping
    - Proof-of-Work based consensus
    - Network, Incentives

* Issues
    * Scalability
        * Latency
        * Throughput
    * Efficiency

* Ethereum
    - PoW vs PoS
    - The merge!
    - Layer 2

### Others

* Bitcoin paper
    - Abstract
        - P2P eCash
        - Digi Sign - Trusted 3rd Party
        - Double spending
        - Network timestamps transactions
        - Hashing
        - PoW
        - Immutability
        - Longest chain
        - CPU power
        - Majority
        - Attackers
    - Intro
        - Commerce on internet
        - Crypto proof - trust
    - Transactions
    - Timestamp server
    - Proof of Work
    - Network
        - 6 steps
    - Incentive
    - Disk Space
    - Simplified Verification
    - Combining / Splitting Value
    - Privacy
    - Calculations
    - 

* Simply Explained
    * Digital Timestamps like a notary
    * Consensus?
    * Good & Clean diagrams
        * Chain / Hash / Hash-ptr based links
        * P2P Network - New Block animation

* 3b1b
    * Introduction
    * Ledgers and digital signatures
    * The ledger is the currency
    * Decentralization
    * Cryptographic hash functions
    * Proof of work and blockchains
    * Double spending
    * Block times, halvenings, and transaction fees

