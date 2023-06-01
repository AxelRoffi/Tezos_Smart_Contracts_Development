
In addition to these features, Tezos is designed to facilitate code safety through Formal Verification. This means that developers can use mathematical proofs to verify the correctness of their smart contracts, reducing the risk of bugs, errors, and vulnerabilities.

Overall, Tezos offers a powerful platform for developers to build decentralized applications and execute secure transactions on a blockchain network that is both efficient and adaptable.

### How it all Started

Arthur and Kathleen Breitman wanted to address the weaknesses of first blockchains:

- Governance
- High-energy consuming Proof-of-Work consensus algorithm
- Security issues

Main dates:

- 2014: white paper
- 2014-2017: development of the Tezos prototype
- July 2017: **232 million usd** raised in bitcoins and eth to develop the ecosystem
- July 2018: **launch of Tezos’ Mainnet**
- 2018-2022:**12 upgrades** validated through the on-chain governance system

### The Difference between Tezos, Tez, XTZ and ꜩ

- Protocol Name: **Tezos**
- Native Cryptocurrency: **tez**
- Ticker: **XTZ**
- LOGO: ꜩ

![TezosLogo_Horizontal_Blue.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/1056ce13-d99c-4812-b32e-af300c509fa1/TezosLogo_Horizontal_Blue.png)

## **Overview of the Key Elements of Tezos**

### Accounts

Tezos is based on a system of accounts, where each account has a balance in tez.

There are two types of accounts on Tezos:

- Implicit accounts are held directly by users.
- Originated accounts are smart contracts that hold data and code.

Accounts are identified by their public address:

- Implicit account addresses start with "tz" and a digit, such as "tz1", "tz2", etc.
- Originated account addresses start with "KT1".

### Transactions can be:

A transfer of tez from **one account to another**

A transaction can also be a **call to a smart contract digitally signed** by the caller

Transactions are one of the many types of operations

### Smart Contracts

A Smart Contract (SC) is a unique form of account that possesses several distinct characteristics. It has a balance of tez, the blockchain's native cryptocurrency, as well as data storage and executable code written in Michelson, a specialized programming language.

When we call a smart contract, we send it some tez and provide parameters for the code to execute. The code, in turn, can manipulate the stored data, generate new transactions, and carry out various other tasks.

One crucial aspect of smart contracts is that, once deployed, their code becomes immutable, meaning that it cannot be altered or tampered with in any way. This ensures that the contract's rules and logic remain consistent and transparent, providing a high level of security and trust for all parties involved.

In short, a Smart Contract (SC)  is a special type of account that has:

- A balance of tez
- Data (the storage)
- Executable code (in Michelson)

When calling a contract, we send some tez and pass parameters for the code.
The code may change the data, or generate new transactions.
Once deployed, the code is immutable

### Smart Contract Structure Example

Let’s imagine a database of tickets for a concert. Each ticket has an owner. 

The owner of a ticket can transfer it to someone else.

This is how the Smart Contract could look like.

**STORAGE**

| Row | Seat | Owner |
| --- | --- | --- |
| 5
8
9 | 15
16
17 | tz1abc…
tz1ebc…
tz1fgc… |

**PSEUDO CODE**

update_owner(row, seat, new_owner): Fetch item in seating for (row, seat)

Verify(item.owner == caller)

seat.owner = new_owner

### Blockchain

The Tezos blockchain is a distributed ledger comprised of a chain of interconnected blocks that are collectively maintained by a decentralized network of nodes. Every 30 seconds, a new block is added to this chain, marking the latest state of the network.

Each block contains a sequence of operations that have been executed since the last block was added. The state of the blockchain is the cumulative result of all these operations, reflecting the current balances and data of all accounts on the network.

For example:

- If after block 1427, Bob’s account has a balance of 1000 tez
- Block 1428 contains the transaction “Alice transfers 100 tez to Bob”
- Then in the state of Tezos after block 1428, Bob’s balance is 1100 tez

Overall, the Tezos blockchain's continuous addition of new blocks and execution of operations ensures that the network is always up-to-date and reflects the most current state of its participants' activities.

A block on the Tezos blockchain primarily consists of two key components: a header and a list of operations.

The header of a block contains essential information, such as the block number (also known as the level), the timestamp when the block was created, and the hash of the previous block in the chain. The hash of the previous block creates a chain of blocks, commonly known as the blockchain, providing a secure and tamper-proof history of all the transactions and operations carried out on the network.

Additionally, the header also includes the hash of all the data present in the block, ensuring that any changes to the block's contents will result in a different hash and, hence, be detected as invalid.

The list of operations present in a block includes all the transactions, smart contract calls, and other operations that have been executed since the previous block was created. These operations are validated and executed by nodes on the network, and their results are reflected in the updated state of the blockchain.

A block mostly contains:

- A header: the block number (level),the hash of the previous blockA timestamp…the hash of all the data in the block
- The list of all operations: transactions, smart contract calls…

To get a better idea of what a Tezos block looks like, you can refer to the following link: **https://tzkt.io/2832089/**

### Wallets

A wallet is a crucial tool that allows you to securely manage your digital assets on the Tezos blockchain. It is typically a software or hardware device that stores your private keys, which are used to sign and authenticate transactions such as transfers and calls to smart contracts.

A wallet does not store your actual tez or other digital assets but instead holds the keys required to access and control them. For example, if Alice wants to make a transaction to transfer 100 tez to Bob, she would need to sign the transaction with her private key to make it valid.

On the Tezos network, there are several popular wallet options available, including [Temple](https://templewallet.com/), and [Umami](https://umamiwallet.com/), among others. For this course, we will be using the Umami Wallet as our preferred choice.

Overall, wallets are an essential component for securely managing and transacting with your digital assets on the Tezos blockchain, ensuring the safety and integrity of your funds and data.

> If you lose your private keys, you lose access to your digital assets
> 

### Nodes

The Tezos network is a  decentralized ecosystem powered by a vast network of nodes operated by the community. Each node is a computer that runs the Tezos protocol, enabling it to communicate with other nodes in the network and collectively maintain the blockchain.

These nodes work together to form a peer-to-peer (p2p) decentralized network, often referred to as the gossip network. This network facilitates the secure and transparent sharing of information, allowing nodes to collaborate and reach consensus on the current state of the blockchain.

As a distributed system, the Tezos network relies on the collective efforts of its nodes to maintain the integrity and accuracy of its blockchain. All transactions, operations, and blocks are propagated through this network of nodes, enabling them to be validated, executed, and recorded on the blockchain.

Overall, the Tezos network's decentralized and community-driven approach to maintaining the blockchain ensures the network's robustness, security, and accessibility, providing a foundation for a wide range of innovative use cases and applications.

### Bakers

<aside>
💡 Creating the next block

</aside>

Every node in the Tezos network is responsible for executing all transactions within a block and storing their associated metadata, such as transaction amounts and public keys.

However, only a single entity can create the next block and determine which operations to include in it. To ensure the decentralization and security of the Tezos network, this responsibility needs to be shared among many nodes rather than concentrated in the hands of a few.

The process of selecting who gets to create the next block is one of the most critical aspects of any blockchain network, and Tezos is no exception. This involves a complex and computationally intensive process of reaching consensus among nodes to determine the next valid block in the blockchain.

Ensuring this block is valid and legitimate is also a vital aspect of the blockchain's security and integrity. Any fraudulent or malicious activity on the network can compromise its trustworthiness, making it crucial to have a robust and decentralized system for validating transactions and securing the network.

Overall, the decentralized nature of the Tezos network, along with its rigorous consensus mechanisms, ensures that the network remains secure, reliable, and accessible to everyone, providing a powerful platform for a wide range of decentralized applications and use cases.

<aside>
💡 Bakers: Fair Selection

</aside>

On Tezos, the entities responsible for creating new blocks are known as bakers. Unlike traditional mining processes, anyone with at least 6000 tez can volunteer to be a baker, and the baker for each level is randomly selected. To ensure fairness, the chance of being selected as a baker is proportional to the amount of stake they have in the network.

This approach is known as Proof-of-Stake (PoS), which is an eco-friendly alternative to the energy-intensive Proof-of-Work (PoW) used on Bitcoin. In PoW, the chance of being selected to create a new block is proportional to the amount of computational power a miner is willing to dedicate to the network, often measured by the energy they consume.

In contrast, PoS ensures that the network is secured and maintained by entities with a vested interest in the network's success. By requiring bakers to hold a minimum amount of tez, PoS aligns the incentives of participants with the network's overall goals, promoting long-term stability and security.

<aside>
💡 Bakers: Validation

</aside>

Before a new block proposed by a baker can be added to the blockchain, it must go through a validation process. The validation process involves ensuring that the proposed block includes the correct hashes for the previous block and its own block, all operations have valid signatures, and that transaction execution does not fail due to gas limits or errors. The total amount of gas used in the block must also not exceed the maximum allowed gas limit.

After validation, the proposed block is broadcasted to the network of nodes for endorsement. For a block to be officially added to the blockchain, it must receive enough endorsements from other delegates within a specific time frame. This helps ensure the security and integrity of the network by ensuring that a proposed block has been approved by multiple participants before it is added to the blockchain.

<aside>
💡 Bakers: Financial Incentives

</aside>

When a baker successfully creates and validates a block, they are rewarded with 10 new tez as well as any potential bonus. In addition, they receive all the fees associated with transactions included in the block. To maximize their profits, bakers typically prioritize transactions with the highest fees.

For those who do not have the required amount of tez to become a baker, there is the option to delegate their tez to a baker. In exchange, they receive a share of the rewards earned by the baker. Sufficiently active bakers also share 20 tez per block reserved for endorsing rewards.

It is important to note that bakers who propagate fake data or act maliciously risk losing a portion of their stake, which is known as "slashing." However, accounts that delegate their tez to a baker are not subject to punishment for the baker's actions. This helps incentivize good behavior among bakers and ensures the security and integrity of the Tezos network.

# First Interactions with the Tezos Blockchain

## ****Set Up of the Wallet****

### Go to https://umamiwallet.com/

![UmamiWalletHomePage.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/b88e874d-461f-40ae-a504-34fbab452a37/UmamiWalletHomePage.png)

### Choose your OS / Download Installer / Open Umami Application

![UmamiDownloadForYourdevice.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/945ca294-c9ec-4ba0-98bf-0701a064322b/UmamiDownloadForYourdevice.png)

### Click User Agreement

![CheckUserAgreementUmami1.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/a29e0e4c-6081-445f-bddb-e71f96d9c9ad/CheckUserAgreementUmami1.png)

### Create new Secret

![CreateNewSecretUmami2.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/ab3a3a07-c79b-4719-b032-bb3311f88894/CreateNewSecretUmami2.png)

### Record recovery phrase and confirm it is recorded

<aside>
💡 NEVER SHARE THIS RECOVERY PHRASE. IN OUR CASE THIS IS DONE FOR ILLUSTRATION PURPOSE ONLY

</aside>

![RecoveryPhraseUmami.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/98c8619f-a4e9-4f5a-b93f-44641ab88e7c/RecoveryPhraseUmami.png)

### Verify recovery passphrase

![CheckRecoveryPhrase.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/4d36b18a-d58c-4242-9832-76048e15990d/CheckRecoveryPhrase.png)

### Choose default path

![DefaultPath.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/f396911b-6b49-410e-b1da-02fe46196575/DefaultPath.png)

### Choose your location for storage backup

![ChooseBackUpStorageLocation.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/99121832-9b83-47a5-bde9-4f71a24373a5/ChooseBackUpStorageLocation.png)

### Record Strong Password

![ChooseWalletPassword.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/d94925c5-4857-4404-86a0-bcfd815b130d/ChooseWalletPassword.png)

### You should get to the Account Home Page of your Umami Wallet

![WalletAccountUmami.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/139fe88a-83c1-48ec-aded-632c22889c87/WalletAccountUmami.png)

### Go to Settings and select Chain/Network GhostNet

![Settings_Ghostnet.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/147f82ac-0539-4336-8cd0-1f12bcbb2679/Settings_Ghostnet.png)

### Go Back to Account and make sure you are on the Ghostnet Network

![Account_GhostNet.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/c47339a7-cd99-4cf7-a363-3cb09409c9db/Account_GhostNet.png)

### Seed Phrases, Keys, Password

When you create an account with Umami Wallet, you'll be generating a pair of keys - a private key for digitally signing your transactions, and a public key that can be used by anyone to verify your signatures. However, since a private key is essentially a random sequence of bytes that can be difficult to remember or write down, Umami Wallet has streamlined the process by generating a seed phrase consisting of 12 or 24 random English words.

This seed phrase is used to seed the random generator that produces the private key, which is then stored locally and encrypted using a password of your choosing. This ensures that your private key is both secure and easy to manage, giving you peace of mind when using Umami Wallet to manage your digital assets.

### Funding your account with “tez” via faucet:

Open your **Umami Wallet and copy your address**

![umami_copy_address.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/538e3b1c-a8a5-4013-9f8a-aa0773f460cf/umami_copy_address.png)

Go to **https://faucet.ghostnet.teztnets.xyz/** and paste your address in the fund address field and click Request 2001 tez

![Tezos_Faucet_wallet.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/02ac147a-c230-4b6a-b78b-b49a4267b7d0/Tezos_Faucet_wallet.png)

Wait a bit, then check your balance, you should have 2001 tez in your account

![2001tezinUmamiWallet.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/2a8e1cd5-5ae4-4e23-b436-333d93f42790/2001tezinUmamiWallet.png)

### ****Transferring tez, checking operations****

Go to Send tab and fill in the pop-up

![first_popup_transaction_umami_wallet.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/af93551f-2b85-4564-b881-068fc2a1b47e/first_popup_transaction_umami_wallet.png)

you can create a new address for you or send tez to this address on the Ghostnet testnet: tz1c6WNFznrCyjKqcbxpzyP5htZRNo1u25Rf

![click_submit_transaction.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/5320a619-b0b7-478f-a822-b399ccf58eb7/click_submit_transaction.png)

And type in your password and confirm the transaction

![typein_password_click_confirm.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/ed1cdab2-ede0-4a16-85f2-815830c0e3e4/typein_password_click_confirm.png)

Go to operations in your operations tab

![operations_umami_wallet.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/e073ff27-4007-41bb-97b1-53ce3b1dad85/operations_umami_wallet.png)

And click the link, it will take you to the operation details in the [Tezos explorer tzkt](https://ghostnet.tzkt.io/)

![blockexplorer_operation_details_tzkt.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/1c3ad380-443a-467d-a105-ec4811923a52/blockexplorer_operation_details_tzkt.png)

### Finality of Transactions

To ensure the finalization of your transaction, the following steps need to occur:

1. A baker must create a block that includes your transaction.
2. Other bakers must endorse this block.
3. Another block needs to include these endorsements.
4. This block also needs to be endorsed.

In summary, your transaction will be considered final two blocks after the block that initially includes it. This process typically takes approximately 90 seconds (assuming a block is created every 30 seconds) once a baker has included your transaction. If you wish to expedite the process, you can consider using higher transaction fees to reduce the waiting time.

**Warning: a block is produced every 30s on the mainet, on ghostnet, block are produced ≈15s**

# ****Why developing on Tezos?****

## **Benefits of Developing on Tezos**

Tezos boasts a cutting-edge on-chain governance system, allowing any tez holder to vote on proposed amendments to the protocol. The platform has already undergone 12 successful upgrades, providing users with a continuous stream of new capabilities without the need for hard forks.

Tezos' energy-efficient Proof-of-Stake mechanism enables it to scale without compromising decentralization, while also maintaining institutional-grade security. Its friendly and diverse community is focused on long-term innovation, attracting blockchain enthusiasts, artists, and multinational corporations alike. Developers benefit from a robust ecosystem, complete with great tooling and funding opportunities. Overall, Tezos offers a comprehensive solution for those seeking an innovative and reliable blockchain platform.

- On-chain governance
- Energy-efficient thanks to Proof-of-Stake
- Focused on scaling without compromising decentralization
- Institutional Grade Security
- A friendly and diverse community that focuses on long term innovation
- Great ecosystem, from blockchain enthusiasts and artist to multinational companies
- Great tooling
- and funding opportunities to help developers

## **Being Part of the Tezos Ecosystem**

In 2017, $232,000,000 was raised to support the development of Tezos. These funds are overseen by the Tezos Foundation, an independent organization with a clear mission: to foster growth within the Tezos ecosystem.

The Foundation achieves this through a variety of means, including grants that support developers' experience, education and training initiatives, security and privacy enhancements, and the development of end-user applications. Those seeking more information on the Tezos Foundation's mission and initiatives can visit their website at **https://tezos.foundation/**.
