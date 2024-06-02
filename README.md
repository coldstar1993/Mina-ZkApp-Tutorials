# Tutorial Video - Step into Mina ZkApp Development

Created by: coldstar1993
Created time: June 2, 2024 1:51 PM
Tags: Mina, zkApp

This tutorial will lead you step by step to go into Mina network and ZkApp Development. The video tutorials cover 4 series:

1) **Starter Series(入门系列)**: basic knowledge for new joiners to learn about Mina & zkApp

2) **Advanced Series(进阶系列)**: step deeper into zkApp development

3) **Practices Series(实践系列)**: share more good practices during zkApp development

4) **Framework Series(框架系列)**: share frameworks to accelerate zkApp development

<br>

# 《Starter Series》

**\<Video1> Learn about Zero Knowledge Proof**

1) start from "*Ali and the Cave*" story

2) Color-Blind experiment

3) Intro on general zk proof systems

    1. what’s arithmetic circuits
    2. zkSnark/zkStark/Halo/BulletProofs
    3. cooresponding blockchains, like
        1. Zcash/Ironfish/Loopring on Groth16_zksnark
        2. Mina/Aztec/zkSync/Anoma on Plonk_zksnark
        3. Aleo on Halo
        4. StarkNet/Polygon on STARK
        5. Grin on BulletProofs

4) Intro on zkSNARK family members & their features

5) Intro on Plonk

    1. recursion zkSnark
    2. general-purpose zkp
    3. simplified trusted setup
    4. small proof size
    5. …

**\<Video2> What & Why & How of Mina chain**

1)  Scalability&Privacy issue of current blockchain industry

2)  Why&How Mina solves these issue

    1. **Data Compression**: Recursive zkp & Succinct(22kb)
    2. **Computation compression**: offchain execution & onchain verification
    3. Ouroboros Samasika POS **Consensus**
    4. Programmable **Privacy**

3)  How to be ‘The Universal ZK Layer for Web3’

    1. zkApps Smart Contracts based on O1js
    2. What’s **Httpz** & #ProofOfEverything
    3. Future expectations - How to **interoperate** with other blockchains(eth/evm chains,etc.)
    4. …

**\<Video3>  First Look at Mina**

1) installation & usage of Auro wallet

2) chain explorers & other community resources

3) delegate MINA and receive staking rewards

4) high-level intro on main components of Mina network

    1. daemon nodes & archive nodes & snark workers
    2. how these roles cooperate together
    3. lifecycle of a Payment
    4. …

**\<Video4>  Intro on Mina Ecology & Community**

1) into on o1js DSL

    1. background of O1Labs & MF & Mina Protocol
    2. kimchi-pickles proof system from Plonk 
    3. comparison to Circom+Snarkjs & Leo & Noir
    4. go into o1js repo structure

2) resources & activities for community builders

    1. Wechat & discord & tw & tg
    2. O1lab-blog / MIPs / MF-blog
    3. Navigator Programs & zkIgnite Cohort & Core Grants
    4. …

**\<Video5>  Go deeper into o1js**

1) what’s arithmetic circuits 

    1. common flows: compile -> witness calc -> proof-gen -> verify
    2. Prover Functions & Verification Keys
    3. Trusted Setup & why no need in o1js

2) Basic Concepts

    1. Data types & Utils
        1. Primitive types & Custom data types**(**Struct**)**
        2. reason on why cannot use js data type within a circuit
        3. Poseidon.hash & Signature & Encryption & PrivateKey & PublicKey…
    2. Conditionals
        1. Provable
        2. **!!!** Traditional conditional statements *VS* conditional statements within Circuit 
    3. Functions

    3) ZkProgram Overview

        1. talk about Recursion
        2. design a simple zkProgram
        3. What’s happenning under zkProgram.compile()

**\<Video5>  First Look at zkApps**

1) comparison to Solidity-contract

    1. design two simple contracts with same functions in solidity & o1js and compare them
    2. **!!! thinking pattern** of Onchain-Exec-Pattern & Offchain-Exec-Pattern
    3. other differences like gas&fee, onchain storage, etc.

2) how zkApp works

    1. prover & verifier
    2. private/public inputs & onchain states of a contract
    3. onchain states & offchain states

**\<Video6>  ZkApps Getting Started**

1) Install or update the zkApp CLI
2) Create a project
3) Add testing code
4) Add functionality

**\<Video7>  ZkApps Getting Started I**

1) Create an integration test
2) What’s LocalBlockchain

    1. test accounts
    2. proofEnabled: true/false

3) Test locally

**\<Video8>  ZkApps Getting Started II**

1) What’s Lightnet 

2) Setup Lightnet

3) Test with Lightnet

**\<Video9>  ZkApps Getting Started III**

1) DevNet & Faucet & MinaScan Explorer

2) Test with a live network

**\<Video10>  ZkApps Getting Started IV**

1) Write a sample zkApp UI by Vite+Vue3 

2) Enabling COOP and COEP headers

3) Connecting your zkApp with a user's wallet

**\<Video11>  Write a Smart Contract by hand**

1) Intro on base class: SmartContract 

2) Regular account & zkApp account

3) On-chain state & Reading state & Assertions & Debugging

4) Public and private inputs

5) design a simple sample contract

    1. What’s happenning under contrat.compile()
        1. What the @method decorator do

6) deploy to Devnet & trigger a @method

    1. tx.prove()/sign()/send()/wait()

**\<Video12>  Inspect a Transaction**

1) transaction strutures

    1. { feePayer, accountUpdates: [...], memo }

2) AccoutUpdates & Account update tree structures

    1. structure:
        1. publicKey & tokenId
        2. states updates & balance changes
        3. preconditions & Auth
    2. Account update tree & Forest
    3. pre-order traversal
    4. Visualize the AccountUpdates

3) What’s happenning under tx.prove/sign()

<br>

# 《Advanced Series》

**\<Video13>  On-Chain Values**

1) onchain states

2) Precondition - Network/Account 

3) Setting account fields

4) Accessing accounts other than the zkApp's account

**\<Video14>  Permissions**

1) Types of Permissions & Types of Authorization

2) default-permissions

3) upgradeability-of-smart-contracts

    1. why we need TransactionVersion
    2. example-impossible-to-upgrade
    3. example-upgradeable-with-a-proof

4) design a sample contract

**\<Video15>  Events**

1) intro about Archive Nodes & archive graph endpoint

2) design event and try getEvents&fetchEvents

3) design a sample contract

**\<Video16>  Actions & Reducer**

1) What&Why of Action(SequencedEvent) and related #issue #pr

2) Mechenism of 5 onchain ActionState

3) this.reducer.reduce(*) & Actions.updateSequenceState(*)

4) how Actions works for concurrent state updates (simple rollup)

5) design actions and try getActions&fetchActions

6) design a sample contract 

7) best practices to fetchActions

**\<Video17>  Time-Locked Accounts**

1) vesting mechenism

2) design a sample contract

**\<Video18>  Custom Tokens**

1) ProofAuth & SignatureAuth

2) Design a sample for ProofAuth

2) Inspect into TokenContract source code & basic usage

**\<Video19>  Off-Chain Storage**

1) talk about Merkle Tree family

    1. Basic features & membership witness & non-membership witness 
    2. AppendOnly Merkle Tree & Sparse Merkle Tree & Updatable Merkle Tree
    3. Merkle Mountain Range

3) inspect classes : MerkleTree&MerkleWitness, MerkleMap&MerkleMapWitness

4) classes: OffchainState & OffchainStateCommitments…

5) Intro about **o1js-merkle** & design usage samples

<br>

# 《Practices Series》

**\<Video20> Cached Proving Key**

1) talk about: **#pr1187**: caching prover and verifier keys in Node.js

2) reduce circuit compiling time cost → improve performances

**\<Video21> Side-Loaded VK** 

1) what’s Generic Recursive Proving Primitives

2) talk about: #**RFC-0002 & #pr1606**

2) Dynamic Proof to reduce circuit dependencies&memory resources cost → improve performances

**\<Video22> Gadgets**

1) bitwise-operations samples & usage

2) foreign-fields samples & usage

**\<Video23> ECDSA & SHA-256**

1) ECDSA & Schnorr 

2) SHA256 & Poseidon

2) how to **verify Bitcoin block headers** using zero-knowledge proofs with o1js

**\<Video24> Some Best Practices for zkApp**

1) about fetchActions & fetchEvents

2) about how to merge actions by hand within zkProgram rather than reducer

3) about tx.send&wait

4) about interoperate with auro wallet on UI

5) about contract permissions design

6) about token contract & token account usage

7) about how to store more data onchain: packing&store

8) about dynamic import o1js to improve ui loading

9) about nodejs params config

10) about debug circuits

11) about inspect/analyse failed tx

12) …TODO…

**\<Video25> Security issue during zkApp contracts**

1) normal design flaws

2) …TODO…

**\<Video26> Setup Daemon node & Archive Nodes for your zkApps**

1) Redundancy & keep nodes stable 

2) Monitoring

3) Archive Tooling

<br>

# 《Frameworks Series》

**\<Video27> Protocol development framework**

1) Application specific rollups & General-Purpose rollups

2) Protocol Arch

    1. Runtime
    2. Protocol
    3. Sequencer

3) …TODO…

**\<Video28> Zeko**

1) …TODO…