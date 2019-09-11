# AZTEC 0.1.0

# Introduction

AZTEC is an on chain privacy protocol for Ethereum which enables efficient zero knowledge transactions. We are focussed on private value transfer and asset governance.

### **Confidential representations of ERC20-tokens**

The AZTEC protocol can enable confidential transactions for *any* generic digital asset on Ethereum, including *existing* assets. [For our proof of concept implementation of the AZTEC protocol](https://etherscan.io/address/0xcf65A4e884373Ad12cd91c8C868F1DE9DA48501F), we attached an AZTEC token to MakerDAO's DAI token. This smart contract can be used to convert DAI from its public ERC-20 form into a confidential AZTEC note form.

### **Fully confidential digital assets**

The AZTEC protocol can be utilized as a stand-alone confidential token, with value transfers described entirely through AZTEC **join-split** transactions

# Getting started

Go to [Quick Start]() for code examples of how AZTEC.

To read in more detail about the AZTEC protocol, go to our [Technical Specification]().

Consult the guides for an overview of [AZTEC](),  additional [explanations]() and documentation on our [Range Proofs](). 

# **Support**

Please [reach out]() to our team if you have any questions about AZTEC, need help developing your own confidential digital assets or wish to to discuss an integration. We are happy to help! 

# Trusted Setup - Ignition

The deployed AZTEC smart contracts currently use a trusted setup created by AZTEC in-house and should only be used for testing and development purposes. 

In Q4 we will be running a multiparty computation protocol to create a trusted setup that is secured by the wider Ethereum community, where only one person has to act honestly for the setup database to be secure. If you wish to participate please let us know at [hello@aztecprotocol.com](mailto:hello@aztecprotocol.com)

# Packages

| [`@aztec/contract-artifacts`](https://github.com/AztecProtocol/AZTEC/blob/develop/packages/contract-artifacts) | [![npm](https://camo.githubusercontent.com/d922b2c083af868baa4c9fad2e3e2a9fbf1e0da7/68747470733a2f2f696d672e736869656c64732e696f2f6e706d2f762f40617a7465632f636f6e74726163742d6172746966616374732e737667)](https://www.npmjs.com/package/@aztec/contract-artifacts) | AZTEC smart contract compiled artifacts                      |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| [`@aztec/contract-addresses`](https://github.com/AztecProtocol/AZTEC/blob/develop/packages/contract-addresses) | [![npm](https://camo.githubusercontent.com/bf762ca95837b808c9bdf2257a2c5eecb8faafd3/68747470733a2f2f696d672e736869656c64732e696f2f6e706d2f762f40617a7465632f636f6e74726163742d6164647265737365732e737667)](https://www.npmjs.com/package/@aztec/contract-addresses) | A tiny utility library for getting known deployed contract addresses for a particular network |
| [`@aztec/dev-utils`](https://github.com/AztecProtocol/AZTEC/blob/develop/packages/dev-utils) | [![npm](https://camo.githubusercontent.com/f6bdb4baef746fb9237f34fda2b3ad989f60a011/68747470733a2f2f696d672e736869656c64732e696f2f6e706d2f762f40617a7465632f6465762d7574696c732e737667)](https://www.npmjs.com/package/@aztec/dev-utils) | Dev utils to be shared across AZTEC projects and packages    |

# AZTEC.js

The methods required to construct AZTEC zero-knowledge proofs and to create the required EIP712 signatures (to spend notes) can be found in our [AZTEC.js library](https://aztecprotocol.github.io/AZTEC/). 

# Gas Costs

The gas costs for AZTEC transactions scale with the number of input and output notes in a **join-split** transaction. For a fully confidential transfer, with 2 input notes and 2 output notes, the gas cost is approximately 900,000 gas. [Planned EIP improvements](https://github.com/ethereum/EIPs/blob/master/EIPS/eip-1108.md) will reduce the cost of these transactions dramatically, to approximately 200,000 - 300,000 gas.

# The AZTEC Developer Extension

AZTEC uses a UTXO model under the hood. A users balance is made up of the total of all the UTXO notes they own for any given AZTEC asset. Each UTXO note has a unique viewing key, that anyone in possession of can use to decrypt the UTXO notes value. Managing a particular users UTXO notes and associated viewing keys is complicated and can have an impact on the confidentiality set which can affect the privacy a particular user gets from the AZTEC protocol.

To make this easier for developers and users we have built a chrome extension that manages a users notes and associated viewing keys.

This extension is in **ALPHA** form and only suitable for hackathon projects currently. We expect the full BETA with a UI to be available at the start of September.

# **Getting Started**

## **Step 1 - installing the developer extension**

Head to our GitHub and clone the Developer Extension Bundle [here](https://github.com/AztecProtocol/developer-extension).

Open Chrome and navigate to **chrome://extensions.** Slide the top right toggle to 'Developer Mode' and click 'Load unpacked'. Select the developer-extension folder from your files. The extension will be installed automatically. 

![img](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LhZjaocaF34Y4jZgGiC%2F-Ll2D5nm7micradYaxk_%2F-Ll1UH5t50HS4D2bxNR0%2FScreenshot%202019-07-30%20at%2011.45.36.png?alt=media&token=63d4a357-eb90-49b2-975a-45129008d467)

Click Load Unpacked to load the extension source code. Make sure you are in developer mode.

## **Step 2 - setting up a MetaMask test account**

Import into MetaMask one of the test Ethereum accounts using the private key below. This account is loaded with 1000 test ETH which you can use to pay for gas. Select the LocalHost 8545 Network from the Network dropdown. 

Private Key:

```
0xb8a23114e720d45005b608f8741639464a341c32c61920bf341b5cbddae7651d
```

### **Step 3 - interact with the ETH-Global-starter-kit** 

Navigate back to [localhost:3000](http://localhost:3000/) and click the 'Enable AZTEC' button after refreshing the page. You are now ready to send private transactions![🕵️‍♀️](https://emojipedia.org/female-sleuth/) 

**IMPORTANT NOTE**

In this alpha release you will have to sign a number of MetaMask contract interactions in order to send AZTEC transactions. In future releases these will be abstracted. 

The extension will persist note data. If you restart Ganache or need to clear out the extension data, the fastest way to clear the extension is to remove the extension in **chrome://extensions** as shown below. Simply re-add the extension to restart.

![img](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LhZjaocaF34Y4jZgGiC%2F-LlFL6KWiVkm0hL1IwaB%2F-LlCcdfJa4JJF8xWqU7Y%2FScreenshot%202019-08-01%20at%2015.42.10.png?alt=media&token=52ffc234-ed28-4c01-9d71-2053db0d628a)





Once the extension is installed it will inject the following object to the window of every page:



```
window.aztec = {    enable: async function (options) {}}
```

# **`.enable(options)`**

This function takes one argument options which can take the following keys these are optional and will default to the values below:



```
{    __graphUrl: 'localhost:8020', // change this value if you want to run your own graph node    web3Provider: window.web3.currentProvider, // change this value to use a different web3 provider    contractAddresses: {        ace: '0xFA8eD6F76e8f769872a1f8a89085c56909EC8Cfc', // the address of the ace contract on the local network        aztecAccountRegistry: '0xFA8eD6F76e8f769872a1f8a89085c56909EC8Cfc', // the address of the aztec account registry contract on the local network.        }}
```

This function will perform the following checks:

1. Create a keypair in the extension for encrypting and decrypting viewing keys
2. Store the keypair in an encrypted keyvault in the extension, encrypted with the users password.
3. Ensure the encryption public key of the keypair has been linked to an ethereum address on chain via the AZTECAccountRegistry.sol contract.

The function returns a promise which resolves to the full AZTEC api if all  checks pass.

## **Registering the Extension**

When window.aztec.enable is called for the first time two things will happen:

The web3 provider will request approval to be enabled on the page. If you are using MetaMask (recommended) this will show a popup like this: 

![img](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LhZjaocaF34Y4jZgGiC%2F-LlBmNxz4z_3jPTk-va_%2F-LlBjyZDUgB_TCsp5ngn%2FScreenshot%202019-08-01%20at%2011.33.33.png?alt=media&token=3dfd62ad-08c1-463c-b1b4-e7abe6a45da6)



Once clicked, the AZTEC Extension will open a window asking the user to register the extension:

![img](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LhZjaocaF34Y4jZgGiC%2F-LlBmNxz4z_3jPTk-va_%2F-LlBkCaR_OEzy8omBrZQ%2FScreenshot%202019-08-01%20at%2011.31.34.png?alt=media&token=0198f753-07a2-4003-8194-c157134f7b50)



The user can either restore an existing set of keys or register a new set. 

![img](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LhZjaocaF34Y4jZgGiC%2F-LlBmNxz4z_3jPTk-va_%2F-LlBl19frBIp_9U8LOJG%2FScreenshot%202019-08-01%20at%2011.37.41.png?alt=media&token=b1f46750-6bf8-43f5-8b89-c3832e669c73)



![img](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LhZjaocaF34Y4jZgGiC%2F-LlBmNxz4z_3jPTk-va_%2F-LlBl3FKvyjj5o0NU7TG%2FScreenshot%202019-08-01%20at%2011.37.47.png?alt=media&token=37e2eeed-c56f-4370-a433-fb6ef54ecf8f)



# **.asset**



```
const asset = await window.aztec.asset('0x3339C3c842732F4DAaCf12aed335661cf4eab66b');
```

The asset method is used to fetch information about the ZkAsset and return a set of methods that rely on the stored UTXO notes and viewing keys inside the extension.

If the page has not already requested access to a users balance, the extension will open a popup asking the user to grant the domain to have access to the assets balance and allow the extension to construct proofs for this asset.

![img](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LhZjaocaF34Y4jZgGiC%2F-Ll7iYPNSP0iiC7shyWp%2F-Ll7juQhHge2A62dlAqy%2FScreenshot%202019-07-31%20at%2016.56.38.png?alt=media&token=04a826e9-b33b-46a8-a836-d9b08df05aa0)





Once this has been granted the following methods will be available on the `asset` class.

## **`async asset.balance()`**

Returns a promise that resolves to an integer representing the balance of the asset.

## **`async asset.deposit(amount)`**

This method is used to convert ERC20 tokens of the  `linkedTokenAddress` into AZTEC note form. It returns a proof class with the following methods



```
const proof = asset.deposit(50);await proof.approve() // calls the necessary ERC20 approvals to permit ACE to spend public tokensawait proof.send() // sends the proof to the blockchain for validation await proof.export() // exports the proofdata for sending later
```

## **`async asset.withdraw()`**

This method is used to convert AZTEC notes into ERC20 tokens of the  `linkedTokenAddress` 

## **`async .send({amount: 50, to})`**

This method is used to send AZTEC notes to another owner. 



```
const tx = {    amount: 50,    to: '0x3339C3c842732F4DAaCf12aed335661cf4eab66b'};
```

## **`async .createNoteFromBalance(amount)`**

This method is used to create a particular AZTEC note for use in one of the proofs.

It will return a join split proof that can be sent to the blockchain to create the resultant note.

## **`async .refresh()`**

This method is used to refresh the balance of the asset to the latest indexed version. 

# **`async .note(noteHash)`**

If the domain requesting this has access to the ZkAsset

## **`async .grantNoteAccess(address)`**

This method grants the passed in address access to the note. This is needed if another party needs to use the note in a proof. e.g `PrivateRange` proof, or `Swap` proof.

This method will trigger a MetaMask transaction as the notes meta ata needs to be updated and broadcast on chain.

## **`.value`**

This is a static integer representing the value of the note if the user has access to it.

## **`.hash`**

This is a static string containing the hash of the note.

## **`.owner`**

This is a static `string` containing the ethereum address of the notes owner.

# **Use with AZTEC.js methods**

The library is compatible with the 7 aztec proofs under `window.aztec.proofs` . These are `PrivateRange`, `PublicRange`, `JoinSplit`, `BilateralSwap`, `Mint` and `Burn`

The extension API is in alpha and the API not fully implemented. The most useful functionality that is implemented is the ability for the extension to keep track of user balances and viewing keys, and then create new notes from a users existing balance via the `createNoteFromBalance` method.

 **IMPORTANT NOTES:**

The send of any transfer instructions that result in a note being destroyed will first have to have been approved by the note owner to spend that note. This applies to the Send, Burn, Swap, CreateNoteFromBalance methods of the extension API.

```
ZkAsset.confidentialApprove(spender, status, eip712signature)
```

The `eip712signature`  can be omitted if the note owner is the `msg.sender.`

# Loan dApp Starter Kit

An example of what you can build with AZTEC

The loan [dApp](https://github.com/AztecProtocol/loan-dapp-starter-kit) and accompanying Medium articles is the fastest way to get started with AZTEC. 

1. [An Introduction to AZTEC](https://medium.com/aztec-protocol/an-introduction-to-aztec-47c70e875dc7)
2. [Deploying AZTEC to Ganache](https://medium.com/aztec-protocol/deploying-aztec-to-ganache-dc02d538b24f)
3. [Constructing Proofs, Signing Flows and Key Management](https://medium.com/aztec-protocol/constructing-proofs-signing-flows-and-key-management-6fceb99b2951)
4. [Creating, Settling, & Streaming Confidential Assets](https://medium.com/aztec-protocol/creating-settling-streaming-confidential-assets-256d09e4c8c5)

# Deploying AZTEC to Ganache

For most dApp builders, deploying to Ganache is essential to test smart contract interactions with AZTEC.

To get started, check out the starter kit on the AZTEC [github here.](https://github.com/AztecProtocol/aztec-ganache-starter-kit) This kit contains the required migrations to deploy AZTEC to a local blockchain as well as example flows. This flow is the same for deploying AZTEC to a private fork of Ethereum.

1. Clone the repository `git clone git@github.com:AztecProtocol/aztec-ganache-starter-kit.git`
2. Install the dependencies `cd aztec-ganache-starter-kit && yarn install`
3. Rename the `.env` file `mv RENAME_ME.env .env`
4. Start up Ganache with`yarn start` (This will create 5 test Ethereum accounts from the credentials in `.env`)
5. Deploy AZTEC! `yarn migrate`

If you would like to have a look under the hood at the required migrations and what they do,  read the full article [here](https://medium.com/aztec-protocol/deploying-aztec-to-ganache-dc02d538b24f). 

# An introduction to AZTEC





# **Why AZTEC exists**

One of the much heralded uses of a blockchain is encompassed by the phrase “*programmable money*” — a smart contract controlling the movement of capital inside a financial application. *e.g. A bond transfer will only process if the buyers total position is less than a 4% regulatory limit.* If this can be achieved, large swathes of the financial system can be rebuilt on top of public blockchains and in the process remove intermediaries, end reconciliation and delete counter-party risk. Using the Ethereum blockchain today, it is straightforward to create “*programmable money*”. However there is a problem — **privacy**.

> The inputs and outputs of any blockchain transaction are publicly broadcast inside the transaction payload.

In the bond transfer example, the notional being traded and a traders current position would have to be broadcast, in order for a smart contract to validate the trade complies with the the 4% regulatory limit. This is a non-starter for real world financial applications in where transaction privacy is a ***pre-requisite***.

### **The \**AZTEC protocol\** was created to enable privacy on public blockchains. It enables logical checks to be performed on encrypted values without the underlying values being revealed to the blockchain. The inputs and outputs of a transaction are encrypted using a series of zero-knowledge proofs and homomorphic encryption, yet the blockchain can still test the logical correctness of these encrypted statements.**

# ***\*Under the hood\****

The validation of traditional Zero-knowledge systems on Ethereum is unworkable. This is due to a combination of on-chain verification gas costs, slow proof construction, and a lack of interoperability between assets. The lack of interoperability and inability for proof construction to run on a clients browser make these systems unsuitable for use in real world financial applications. One of the largest costs inside a Zero-knowledge system is the range proof. A ***range proof*** allows the prover to prove to a verifier, that a number is within a specific range. This is critically important when dealing with addition of elliptic curve points. On an elliptic curve, a negative number is in fact a very large positive number and a range proof is used to ensure that any point is within a usable range and to prevent double spend attacks by wrapping around the modulo. AZTEC’s range proof utilises a trusted setup to drastically reduce the cost of this check.

Once an encrypted number is proven to be inside the usable range the additive properties of an elliptic curve allow logical checks to be performed on it. This concept known as ***homomorphic encryption*** allows logical checks to be carried out on encrypted numbers as if they had not been encrypted. i.e the same checks can be performed as in a public transaction but without ever revealing the underlying values of the encrypted numbers.

These two cryptographic methods are combined into a set of sigma protocols that allow specific logical statements to be validated on chain. If you would like to find out more about the cryptography underpinning the protocol, please read the [**white-paper**](https://github.com/AztecProtocol/AZTEC/blob/develop/AZTEC.pdf)**.**

# ***\*AZTEC’s Mental Model\****

AZTEC follows a UTXO model similar to that of Bitcoin. The core of any AZTEC transaction is a ***Note.*** The state of notes are managed by a ***Note Registry*** for any given asset.

> The user’s balance of any AZTEC asset is made up of the sum of all of the valid notes their address owns in a given ***Note Registry***.

![img](https://cdn-images-1.medium.com/max/1600/1*U6jUMkM_62Sp8BMA0jxmoQ.png)

AZTEC’s UTXO model

Public blockchains offer two main benefits, an independent economic guarantee around the correctness of state and interoperability of capital. (The capital received as an interest payment for a loan can also be used to settle a trade for a different asset). Most Zero Knowledge systems lack this interoperability. They create siloed pools of private capital. AZTEC is designed to solve this. It allows interoperability between dApps interacting in zero knowledge.

To achieve this interoperability, all AZTEC assets share a common trusted setup and their state is managed by a single smart contract, the AZTEC Cryptography Engine or ACE. ACE has two primary functions; first to delegate the validation of proofs to specific validation contracts and secondly to process state update instructions inside note registries that result from the successful validated proofs.AZTEC Architecture

![img](https://cdn-images-1.medium.com/max/1600/1*kBQuG0z7Bnd1oFK-tCoTpA.png)



# ***\*A set of building blocks to enable privacy\****

The AZTEC protocol is designed to offer dApp builders a set of modular building blocks, each enabling a specific piece of functionality. A developer can compose together these building blocks to build a private dApp, without the need for a cryptographer. Under the hood these toolkits are Sigma protocols that prove a relationship between the supplied input and output notes. Currently AZTEC supports 7 of these toolkits:

**Join Split (Transfer)**

The Join Split proof allows a set of input notes to be joined or split into a set of output notes. Usually this is used to combine note values into a larger note, or split a note into multiple notes with different owners. This proof ensures that the sum of the input notes is equal to the sum of the output notes.

There are also two variants of the Join Split transactions that are used to deal with public ERC20 values. One in which a public ERC20 value is converted into an AZTEC note and it’s reciprocal, where an AZTEC note is converted into a public ERC20 value.

**Bilateral Swap (Trade)**

The bilateral swap proof allows an atomic swap of two notes to take place. This is useful for trading two assets *e.g fiat and a loan/bond/security*. A validated proof, proves that the makers bid note is equal to the takers ask note and the makers ask note is equal to the takers bid note.

**Dividend Proof**

This proof allows the prover to prove that the input note is equal to an output note multiplied by a ratio. This is useful for paying interest from an asset.

**Mint**

The mint proof allows the supply of AZTEC notes to be increased by a trusted party. *e.g a stable coin mints an AZTEC note equal to the value of a bank transfer it receives.*

**Burn**

The burn proof allows the supply of AZTEC notes to be decrease by a trusted party. *e.g a stable coin burns an AZTEC note of equal value of the bank transfer it sends to the note owner.*

**Private Range**

This is used to prove that an AZTEC note is greater than another AZTEC note or vice versa. This is useful for proving that ownership of an asset post trade is below a regulatory maximum. It can also be used to build identity and group membership schemes.

**Public** **Range**

Similar to the private range proof. This is used to prove that an AZTEC note is greater than a public integer or vice versa. This is useful for proving that ownership of an asset post trade is below a regulatory maximum.

# ***\*Privacy, Anonymity and Confidentiality\****

These terms are often used when discussing zero-knowledge systems. It is important to define the meaning of each and address how AZTEC handles them.

***Privacy:*** *all aspects of a transaction remain hidden from the public or third parties.*

***Confidentiality:*** *the inputs and outputs of a transaction are hidden from the public but the transaction parties remain public.*

***Anonymity:*** *the inputs and outputs of a transaction are public but the transaction graph is obscured from one transaction to the next, preventing the identification of the transaction parties.*

**AZTEC enables confidential transactions out of the box**. The inputs and outputs of any transactions are represented as encrypted numbers and the value hidden from public view.

Using normal Ethereum addresses the transaction graph of AZTEC is not anonymous. However anonymous transactions are possible. The protocol is forward compatible stealth addresses and as AZTEC does not mandate the transaction sender to be a party in the transaction, the transaction graph can be hidden. Combining stealth addresses and a trusted party to relay transactions achieves full anonymity. Using a trusted third party hides the payment of gas and provides full anonymity. Future updates to the protocol will allow the relay of transactions whilst obscuring the payment of gas in a decentralised manor. At that point **fully private transactions** will be possible.

# ***\*Creating Confidential Assets\****

[EIP1724](https://github.com/ethereum/EIPs/issues/1724) aims to standardise the interface for interacting with confidential assets that conform to a UTXO based models. AZTEC has reference implementations of EIP1724 for the supported asset types in the `@aztec/protocol` NPM package.

![img](https://cdn-images-1.medium.com/max/1600/1*QeBVwGYtjsCh3KgBGqjyAw.png)

The EIP 1724 ZkAsset Standard

Let’s look at an example:

Imagine the dApp in question needs to perform a logical check to ensure that a traders post trade asset balance is less than a regulatory maximum.

In a normal dApp, this check is simple to perform. The transaction inputs would contain the public variables `tradeNotional.` The contract could then perform a simple check ensuring the new `assetBalance[buyer]` is below the `regulatoryMax` .



```
if(regulatoryMax > tradeNotional + assetBalance[buyer]) { // the trade can proceed}
```

In a private AZTEC dApp, the same logical check can be performed using one of the AZTEC proofs. The mental model is slightly different as all of the variables are stored as encrypted AZTEC notes, then a proof is constructed, which if validated by ACE, ensures the desired logical statement is correct.



```
const {   proofData,} = await aztec.proof.privateRange.encodePrivateRangeTransaction({    originalNote: regulatoryMax,    comparisonNote: postTradeUserBalance,    senderAddress: accounts[0],  });
```

This proof proves that the `comparisonNote` is less than the `originalNote` . If the values are swapped it would prove the opposite. Once the proof is constructed it can be relayed to ACE for validation.



```
(bytes memory _proofOutputs) = ACE.validateProof(                                 PRIVATE_RANGE_PROOF,                                 address(this),                                 _proofData                               );
```



```
// if the above statement succeeds we know that the users post trade balance is below the regulatory minimum.
```

AZTEC is designed to allow the combination of these logical checks to build the complex flows required by financial dApps. 

# Confidential Transactions on Ethereum





Transaction privacy is a fundamental requirement for many kinds of financial services, and the inability to provide this privacy has prevented Ethereum from providing compelling alternatives to traditional financial instruments. There are several blockchains and blockchain projects that use cryptographic techniques to provide this privacy, but this privacy is reserved for the ‘native’ cryptocurrency of the blockchain in question. This transaction privacy is not accessible for digital assets built on top of blockchain protocols. For example, I can’t code up a corporate bond smart contract on Ethereum, where ownership notionals are private.

Well, until now, that is.

### ***\*Show and tell: the peculiar case of confidential DAI\****

Here, take a look at this:



```
{    "gamma": "0x20a92d2a4f0dd850314a745719dde20934db69cc8e9b5b84b5819e062d66bb7500",    "sigma": "0x17d62693c0c9a356e2fd6b0ce877b78c6a1f8a7f195e9db4c0b68e0693d73b3600"}
```

This curious jumble of characters is a form of DAI, the dollar-pegged stablecoin created by MakerDAO. But it looks a little *odd*, doesn’t it? This would normally just be an ethereum address, and a number representing how much DAI that ethereum address has. But this isn’t normal DAI.

You see, when I sent [this transaction](https://etherscan.io/tx/0xf9a101682c637f7741f281c858527d17036f4df284b7064bd1ca44531ab88374), my ethereum address (zac.creditmint.eth) became the owner of this DAI, but here’s the thing: nobody can figure out how much DAI I have. Unlike almost every other DAI holder in the world, my DAI balance is *encrypted* and represented in the form of zero-knowledge AZTEC notes. I can spend this DAI at will by sending some to a different address, but when I do nobody will be able to figure out how much of it I’m sending. For example, I sent a colleague some of my DAI in [this transaction](https://etherscan.io/tx/0xf9a101682c637f7741f281c858527d17036f4df284b7064bd1ca44531ab88374) and *good luck* figuring out how much they have.

This is all quite new, and I’m so *very* excited to be showing this to you and the wider Ethereum community. We’ve been developing this for almost a year now, but we’ve held off on making any formal announcements because I wanted to show you that specific, peculiar, jumble of hexademical characters.

Because this isn’t some imagined technology that will one-day be implemented.

It doesn’t require modifications to the Ethereum protocol.

It is a working demonstration that is live on the Ethereum main-net *today,* and that AZTEC zero-knowledge note is a real note that encrypts real DAI.

# ***\*A breakdown of AZTEC confidential transactions\****

There are really two questions here: *what* is the AZTEC protocol and *how* does it work? I can only answer *how* by getting into the guts of elliptic curve cryptography, which is a topic for another blog article (you can read a formal description in our [paper](https://github.com/AztecProtocol/AZTEC/blob/master/AZTEC.pdf). For a lightning summary of how this thing works: it’s not a ZK-SNARK, it’s an algebraic zero-knowledge proof that utilizes Boneh-Boyen signatures to create a commitment scheme with a highly efficient range proof embedded into each commitment.

Right, well that’s cleared everything up then. So I’m going to focus on answering *what* the AZTEC protocol is. What is it *doing when* transactions are sent to it? To start with, we need to describe what we mean by ‘confidential transaction’.

A confidential transaction is a transfer of value between two or more entities, where the *values* being transferred are not visible to observers.

Confidential transactions have come in several forms, from ring signatures to ZK-SNARK circuits. Similar to ZCash, the AZTEC protocol uses the concept of encrypted ‘notes’ and join-split transactions.

# ***\*Encrypted Digital Assets and the AZTEC note\****

The AZTEC protocol does not represent ‘value’ like a traditional balance, which maps owners to how much they own. Instead, value is represented by **notes**. A note contains the following **public** information:

- An AZTEC commitment: an encrypted representation of how much ‘value’ the note holds
- An Ethereum address of the note’s owner

A note has the following **private** information

- The value of the note
- The note’s ***viewing key****.* Knowledge of the viewing key enables a person to decrypt the note (but not spend it)

One owner can have multiple notes. A digital asset that conforms to the AZTEC protocol will contain a **note registry**, which allows a smart contract to recover the public information of every **unspent** note that currently exists.

# ***\*How can AZTEC notes be spent?\****

An AZTEC note owner can ‘spend’ their notes in a join-split style confidential transaction. In this transaction, the note owner will destroy some unspent AZTEC notes they own. In their place, they will create a set of new notes. The sum of the *values* of the new notes must be equal to the sum of the *values* of the old notes, plus a *public* commitment (I’ll get to that in a bit, but for now let’s assume this is worth 0).

So imagine Alice has two AZTEC notes worth 100 tokens combined. If she wants to send Bob 20 tokens, Alice would create one or more notes owned by Bob, whose values sum to 20. She would then create one or more notes owned by her, the sum of which is 80 tokens.

She would then create an AZTEC zero-knowledge proof that proves this relationship in zero-knowledge (i.e. Alice does not reveal to anybody how much the notes are actually worth, just that the balancing relationship holds). The AZTEC token smart contract will then validate this zero-knowledge proof, destroy Alice’s input notes and then create the output notes in its note registry.

When Alice is creating Bob’s notes, she constructs note viewing keys that Bob will be able to identify, via a non-interactive secret-sharing protocol. Bob is dependent on Alice to act ‘trustfully’ in this regard and not provide viewing keys that can be decoded by observers. This is already implicitly required — after all Alice could broadcast to the world how much she is sending Bob if she did not want the transaction to be confidential.

## ***\*How is note ‘ownership’ defined?\****

Every confidential transaction also requires digital signatures — a signature is required for every input note, signed by the input note’s owner. The message of the signature is a hash of the zero-knowledge proof. This provides an implicit acceptance that the note owners are satisfied with the outcome of the confidential transaction, and want the transaction to be processed.

## ***\*How do we get value into AZTEC note form?\****

Confidentially transfering value is nice, but without a way of getting ‘value’ (let’s call this ***v***) into the AZTEC cryptosystem it all seems a bit academic. This is done via that ‘public commitment’ in a confidential transaction. Assume that the AZTEC token is linked to a public ERC-20 token. If the AZTEC zero-knowledge proof requires a public commitment value ***v != 0*** in order for the balancing equation to be correct, this means one of two things:

\1. If ***v*** is negative, the output notes are worth ***-v*** more than the input notes

\2. If ***v*** is positive, the input notes are worth ***v*** more than the output notes

If Alice issues a confidential transaction where ***v*** is negative, the AZTEC token smart contract will transfer ***-v*** public ERC-20 tokens from Alice to its own contract address. Effectively, the AZTEC token smart contract acts as a custodian of the ERC-20 tokens while they are in confidential note form. Naturally, if this token transfer is rejected (e.g. Alice doesn’t have enough tokens) then the transaction will be aborted.

If Alice issues a confidential transaction where ***v*** is positive, this represents a conversion from AZTEC notes into public ERC-20 tokens. The AZTEC token smart contract will transfer Alice ***v*** public ERC-20 tokens.

There’s one small caveat — the amount of tokens being transferred is actually ***v*** multiplied by a scaling factor. This is because the range of integers an AZTEC note supports is smaller than that of an ERC-20 token. Our proof of concept deployment to main-net supports numbers from 0 to about 1 million and our full implementation of the AZTEC protocol will support approximately 32-bit integers (more on that in a bit). ERC-20 token balances, on the other hand, are represented by 256-bit integers.

The scaling factor picked depends on the ERC-20 token being linked to. For our proof of concept confidential DAI deployment, an AZTEC note with value ***1*** is equal to ***0.1*** DAI.

# ***\*What is the cost of all of this?\****

The AZTEC protocol uses a bespoke commitment scheme that enables highly efficient range proofs. As a result, the amount of computation required by the verification smart contract is much smaller than one might expect. The overwhelming contributor to a confidential transaction’s gas costs is the elliptic curve arithmetic required to validate the AZTEC zero knowledge proof. It costs `3i + 4j` *elliptic curve scalar multiplications* to validate a proof, where *i* is the number of input notes and *j* is the number of output notes. Each `confidentialTransfer` transaction also requires a single elliptic curve bilinear pariing comparison to verify.

The reason I’m using such odd wording is because the gas costs of these arithmetic operations is likely to go down in the future due to protocol upgrades implemented by geth and parity ([EIP-1108](https://github.com/ethereum/EIPs/blob/master/EIPS/eip-1108.md)). It currently costs about [900,000 **gas**](https://etherscan.io/tx/0x6cb6bccb6d51445ce026dd76b8526e8014a6a276255d22e4f5be26f8efb891fb) to issue a confidential transaction that contains 4 notes (this is the *total* gas cost, not just the cost of validating the cryptogrpahy of a transaction). If/when EIP-1108 goes live, the gas costs will fall to about 200,000–300,000.

# ***\*What information can be gleaned from confidential transactions?\****

The AZTEC protocol has been something of a obsession of mine for the past 11 months and I wouldn’t be comfortable releasing this out into the wild without giving a full account of the protocol’s strengths and limitations, I believe that being up-front about this is important.

With that out of the way, any protocol that converts something public into something private will reveal information at the entry and exit points of the cryptosystem.

If you’re adding tokens into note form, an observer will know that the value of the output notes is *at least* the amount you’ve converted.

Similarly, after redeeming ***v*** tokens, an observer will know that the remaining AZTEC notes are worth ***v*** less than the input notes.

These problems can be ameliorated by combining public conversions with additional AZTEC notes. For example, imagine Bob has a note worth ***100***tokens that he wants to convert into public token form. Instead of just issuing a conversion, Bob should add additional input notes into his transaction and also generate some output notes, even if the extra input and output notes are worth ***0***. This will prevent an observer from figuring out how much of Bob’s confidential holdings he has converted, even if he has converted all of it and is left with a pile of notes worth nothing.

AZTEC notes have ‘owners’ defined by Ethereum addresses. On the surface, note ownership is not anonymous (e.g. people can see [my ethereum address](https://etherscan.io/address/0xa9b16b8c2399510706cd275ad9f86ef668067351)has a zero-knowledge DAI note); the AZTEC protocol includes a Monero-style stealth-address protocol to derive Ethereum addresses that are single-use and cannot be linked to any other Ethereum address (e.g. if you have an AZTEC wallet, I can ‘send’ a note to an Ethereum address you control, but nobody but you and me will know this is the case). The protocol supports both stealth addresses (which require a specific wallet to work; you need two public/private key pairs so a regular Ethereum account won’t work) and regular Ethereum addresses (which are not anonymous — if you own a note everybody will be able to see that).

The more users of a dual public/confidential asset, the greater the privacy provided. For example, when testing our main-net deployment, I converted ***50*** DAI into AZTEC notes and sent a bunch to my colleagues. Obviously, the sum of all the notes is ***50*** DAI so a single note can’t encrypt very much. Now imagine that somebody else created ***1000*** DAI worth of confidential notes, and we split and merged a few of our notes — it would be impossible to identify how much DAI any of these notes had, other than they would have ***1050*** DAI as a maximum.

To reduce this to extremes — if I converted ***10*** DAI into a single AZTEC note, this gives no privacy at all. The ability to create notes worth *zero* is important to maximize privacy — if you were going to convert ***10*** DAI and wanted a single note for ease-of-use, you should also create a few notes worth ***0*** DAI to mask how much each note is worth.

Naturally, a ‘lazy’ use of the protocol will leak information. For example, imagine you converted ***10*** DAI into 5 notes, where 4 were worth ***0*** DAI. If you then forgot about these notes and never used them in future transactions, it would be fairly obvious to observers that the un-used notes were worth nothing. Always issuing zero-value notes in join-split transactions, and using them in future join-split transactions minimizes the amount of information available to external observers.

# ***\*The AZTEC protocol’s trusted setup\****

The reason the AZTEC protocol is highly efficient is that we combine Boneh-Boyen signature and Pedersen-style commitments into a single commitment scheme with a highly efficient range proof embedded into the commitment. This comes at the cost of requiring a database of elliptic curve points to be generated before the AZTEC protocol can be used. This database is required to *construct* proofs, but is not needed to *verify* them.

A bit like ZCash, this trusted setup generates a ‘toxic waste’ **private key** and if knowledge of that private key is leaked, it can be used to effectively double-spend, and the protocol becomes unusable.

So how do we deal with this? Well, for one we don’t just expect you to *trust* us. We have developed a scalable multiparty computation protocol that enables anybody to engage in the trusted setup process. If you participate, you generate a piece of ‘toxic waste’ that, naturally, should be destroyed. The trusted setup **private key**, the thing that must be destroyed at all costs, can only be recovered by piecing together *every participant’s* toxic waste. So if a *single* person acts honestly the scheme is completely secure and can only be ‘cracked’ by solving one of the discrete logarithm-based problems (of which the entireity of elliptic curve cryptography rests; if somebody cracks the discrete log problem we’ve all got bigger problems on our hands than the security of the AZTEC protocol!).

We will be announcing the formal description of our trusted setup process in the coming months and will begin to collect participants. It is similar to ZCash’s ‘powers of tau’ ceremony, albeit for a very different end as the AZTEC protocol is not a ZK-SNARK. We want the trusted setup protocol to be simple to take part in and we want to engage the wider Ethereum community in this process, to create a trusted setup database that has the trust and confidence of the community.

Our deployed proof-of-concept smart contracts use a trusted setup that was generated internally, as implementing our multiparty computation trusted setup is going to take several months. Until we have completed this phase the AZTEC protocol is very much use-at-your-own-risk. Whilst I *naturally* destroyed the toxic waste, there is no way to prove that I did.

One final point (zing…). The size of the trusted setup database grows linearly with the size of the protocol’s range proof. Our proof-of-concept database supports integers between 0 and 1,048,575 because I wanted a database small enough to fit inside a github repo without being a pain to download. Our full implementation will support a much larger range of integers.

# ***\*Why is the AZTEC protocol important?\****

Well of course *I’m* going to say this is important, I’m the most biased person you could ask on this topic! But here’s why I think this is a real game changer: The AZTEC protocol enables the creation of *generic* confidential digital assets. We picked DAI to start with but with the press of a button the AZTEC protocol can be applied to *any* ERC-20 token. It also enables the construction of *purely confidential* assets that don’t have any kind of ERC-20 token equivalent. No extra cryptographic circuits required, no additional trusted setup processes needed. For the first time ever, it’s possible to create confidential digital assets on Ethereum, obtaining the immutability and decentralization benefits of public blockchains without sacrificing privacy.

AZTEC zero-knowledge proofs are also very efficient to *construct*, and are well within the capabilities of hardware wallets. This opens up the exciting possibility of issuing confidential transactions directly from hardware wallets and never exposing sensitive private keys.

# ***\*What is in the AZTEC protocol’s future?\****

Of immediate relevance is releasing our AZTEC proof construction API, to accompany [our smart contract verifiers and technical paper](https://github.com/AZTECProtocol/AZTEC). We also have several extensions to the AZTEC protocol in the works, and will be releasing our full vision of the AZTEC protocol over the first half of 2019. This includes several important milestones:

\1. A confidential decentralized exchange, where people can trade different AZTEC assets in complete confidentiality — neither the quantities or prices of orders can be gleaned from processed orders. The decentralized exchange uses the relayer pattern to acheive this, as well as a bespoke AZTEC DeX zero-knowledge proof (three actually, I’ll be talking about this in depth once our DeX paper is finalized).

\2. Confidential weighted voting. Governance mechanics that respect the privacy of a user’s vote are essential a large range of financial applications and the AZTEC protocol’s efficient range proofs make this achievable.

\3. Anonymous identity sharing schemes. Being able to prove that you’re part of a group, without revealing *who* in the group you are is an essential component for many compliance and KYC processes and our AZTEC token standard will support this kind of identity system.

Combined together, this will give builders the tools needed to create the next wave of decentralized financial services; digital assets with *implicit* privacy and confidential governance mechanics built in from the ground up.

# Range proofs





This article is an in-depth look into how the AZTEC protocol enables efficient confidential transactions.

But before I start, I have a confession to make.

You see, I have a problem when it comes to explaining cryptography. It is in general quite confusing and unintuitive — the practise of proving you know relationships between data without having to share what that data *is*. It’s a little odd, and difficult to explain.

This problem isn’t something I alone struggle with. If you ever read cryptographic papers or articles, the author will usually attempt to translate these odd concepts into something more intuitive and familiar by wheeling out Alice and Bob.

Alice and Bob are the world’s most uninspiring double act and they only have one routine. When Alice and Bob turn up, they will immediately begin to embark on an abstract series of guessing games with seemingly arbitrary rules. Sometimes Alice or Bob don’t know some of the rules, which clears up precisely nothing. This game usually takes place in a cave and Alice might have some coins (public coins). You know you’re *really* in for a treat when Bob begins to monologue about how a uniformly distributed random number generator can be distinguished from a hash function.

I do not like Alice and Bob. I find their presence to be unhelpful. Still, as I have not managed to square the circle of intuitively explaining zero knowledge proofs I have invoked them in this article but I want to make one thing clear; I’m not happy about it.

# **Dissecting a confidential transaction**

Before describing what the protocol *does*, I want to start with what we *need* so that when I introduce a concept I can explain why it has value. We want a way of representing ‘balances’ with encrypted numbers. E.g. instead of a ledger recording that I have 20 Ethereum and that you have 5, these numbers are encrypted.

We can’t record this as a simple encrypted ledger, because if I want to send you money, I would need to be able to figure out what your new encrypted balance should be — but I don’t know your original balance so this is hard to do.

So instead of mapping owners to balances, we map balances to owners via the concept of an encrypted ‘note’.

- A note is worth some defined amount and has an owner.
- If I own multiple notes, I can combine them into a single note.
- If I own a note, I can split it into multiple notes. These notes can have different owners

I can transfer ‘value’ by splitting a note and having one (or more) notes owned by the recipient.The sum of the input notes equals the sum of the output notes

![img](https://cdn-images-1.medium.com/max/1600/1*-zMKwxuGPUjA7SnyfSGsDw.png)

A perfectly balanced ‘join-split’ transaction. 

In the world of encrypted notes, what do we need for a confidential transaction?

- A way of encrypting value into notes
- A way of proving that the sum of the values of some input notes, equal the sum of the values of some output notes

And in order to get those things, we need to dive into the world of elliptic curve cryptography.

# ***\*Elliptic curve cryptography and homomorphic encryption\****

Elliptic curves have relatively simple formulae, for example the curve we use has the formula **y² = x³ + 3** (the 3 is important…). If drawn on a piece of paper, we can pretend it looks like this:![img](https://cdn-images-1.medium.com/max/1600/1*8fvXapauisBEOHppacfjkw.png)An elliptic curve. Not the right elliptic curve, but this one looks nice

We use elliptic curves because they can be used to create one-way functions (can map from A → B, but if given B you can’t figure out A) that preserve some mathematical operations.

Here’s how it works. If you have two points on a curve, draw a line through them and find where that line hits the curve for the 3rd time (which will always happen), then invert that point in the y-axis. The resulting point is the result of our ‘addition’ operation.![img](https://cdn-images-1.medium.com/max/1600/1*UOZlpO50NVUb89W-0-lIWA.png)Elliptic cuve point addition

When adding a point to itself, the line that’s drawn is the tangent to the curve at that point.

We require the inversion in the y-axis because without out it our ‘addition’ is not associative: **(P+Q) + R** would not equal **P+ (Q+R).**

**But…why?**

Good question! We can use point addition to define **elliptic curve scalar multiplication**. If we have a point, **P**, and an integer **x**, we can ‘multiply’ **P** by **x**, but adding **P** to itself **x** times.

If the elliptic curve parameters are carefully chosen, scalar multiplication is a **one-way function**. If I have **x** and **P,** I can easily compute **x•P**. But if I have **P**and **x•P**, I can’t figure out **x.** Naturally, terms and conditions apply. This only works if **x** is a random number, or has randomness added into it (if **x** is predictable then it’s much easier to figure it out via trial-and-error brute force techniques).

**But…why?**

Good question! There are cheaper and faster one-way functions out there, like hashing algorithms. But elliptic curves preserve some of the mathematical properties of the values they encrypt.

Take two random integers **x** and **y** and calculate x**•G** and y**•G**. Now add them together. The resulting point is the same point you get by adding together x and y, *then* multiplying the result by **G**.

**P = x•G + y•G = (x+y)•G**

This ability to perform **homomorphic addition** means we can perform additions on encrypted numbers *as if they weren’t encrypted*, which is rather useful.

Naturally, terms and conditions apply. The problem (well, one of them) with homomorphic addition over elliptic curves is that the addition is performed modulo an *extremely* large prime number **p**. For the curve we use, this is equal to `21888242871839275222246405745257275088548364400416034343698204186575808495617`.

Imagine we want to validate a ‘transaction’. I have a note worth **0** and I want to convert it into a note worth **-1** and **1.** Let’s represent these values as ‘notes’ on an elliptic curve: **-1•G** and **1•G**.

Naturally, **0•G = -1•G + 1•G.** So we can satisfy the balancing relationship required by our join-split transaction. But for our elliptic curve, **-1** is actually **p-1**, which is a **huge** number!

If we used this kind of logic to validate dollar-denominated confidential transactions, we have just created a ‘note’ worth more dollars than the amount that exists in the observable universe, which is a bit of a problem.

# ***\*Range proofs to the rescue\****

We need a **range proof** to deal with this problem. If we check that every encrypted number that enters our cryptosystem is many orders of magnitude **less** than **p/2,** then it’s never possible to ‘wrap’ around the modulus boundary and create ‘negative’ numbers.

But we have another problem now. If the modular nature of homomorphic arithmetic is the villain in our story, then range proofs are less of a plucky hero with heart and plot armor, and more like a cut-throat mercenary who will pillage everything down to the elastic in your pants. Range proofs are **expensive.** The computational cost to verify most range proofs adds a significant overhead to the cryptographic protocols that use them.

For example, a common method is to create encrypted representations of every bit in a number, and then prove that every bit is either 0 or 1. However for, say, a 32-bit number, you would need to validate 32 zero-knowledge proofs. There are some ingenious techniques for squishing the size of these proofs down and combining them into a mega-proof, but the amount of computation required by a verification program will still scale with the number of bits your encrypted number can potentially contain.

For the Ethereum protocol, this translates into gas costs that quickly hit the block gas limit.

## **Range proofs via digital signatures**

Picture the scene. You are a proud and loyal citizen of the People’s Representative Democratic Party of Zero-Knowledgeandia. In this timeline, you are called Alice due to a clerical incident at the registry office; the Party does not make mistakes.

Today, you are stoically queuing at the bread line in order to feed your family for another week.

However, you have a problem. Commissar Bob will only sell bread to upstanding citizens who have a sufficiently low State Disobedience score.

Naturally, you are a proud and loyal citizen and *do* in fact posess a sufficiently low score. However if you simply *tell* Bob your score you will be sentenced to 5 years of hard labour in the acid-boron caves for not being GDPR-2.0 compilant.

Your one saving grace is that Bob, being a stickler for following rules, absolutely *loves* abstract guessing games with public coins. So you can use a zero-knowledge proof.

However, Bob only posesses an 8-bit *Robotron-1999 People’s Tabulating Machine* and only has one minute to process your proof before you get kicked out of the bread line for loitering.

How can Alice present Bob with an *efficient range proof* that her score is below a threshold? Will Alice’s family be fed for another week?

It is on this cliff-hanger that we will dive into the depths of the AZTEC protocol and its range proof.

## ***\*Saving the day with lazy range proofs\****

In software engineering we have a principle called **lazy evaluation.** Simply put, don’t bother doing something unless you have to, and only do it when you need to. It might be expensive to verify a range proof, but it is **much**cheaper to verify that **somebody else** has verified a range proof.

## ***\*Digital Signatures and range proofs\****

Making range proofs somebody else’s problem introduces a **trusted setup**into the protocol, performed by the “somebody else” in question. In this setup phase, we generate a random integer **y**, the trusted setup **private key** (this is the ‘toxic waste’ of our protocol)**.** The trusted setup **public key** is published (**y•G)**, along with *digital signatures* for **every** integer that we tolerate in our range proof (e.g. 0 to 1 million). Once this is done, knowledge of **y** must be destroyed.

Now, in order to perform a range proof, all we need to do is present a signature, and prove it was signed by **y**. If we have done our job properly, this means that the integer in the signature is also inside the allowed range, because those were the only signatures that were created.

This does introduce risk that **y** is not destroyed and information about it is leaked. However we have a multiparty computation protocol that enables our trusted setup to be performed by a large number of people (ideally thousands). Each person generates their own piece of ‘toxic waste’, performs their part of the computation, then destroys their waste. Only **one** person has to act honestly and destroy their toxic waste for the entire protocol to be secure.

With out of the way, here, hold these:![img](https://cdn-images-1.medium.com/max/1600/0*stBzRLAMYib9HgvR.png)

The point **μ** is a form of **Bohen-Boyen** (BB) signature and is part of the **trusted setup signature database**. The integer **k** represents a number that we accept in our range proof, so we have one signature for each integer in our range. The integer **y** represents a special **trusted-setup** private key and the point **T** represents the trusted-setup public key.

If we are given a point **μ** and a scalar **k**, we can check whether **μ** is indeed a signature without knowing what **y** is; we only need **T**.

Why is this? Well, our tactic is to embed the ratio **G** **: y•G** into the encryption of every number in the range register, so in a way that is somehow *testable* but also *irrecoverable.* **Bilinear parings** test ratios of exponents and enable us to blinding, magically, test that our ‘signature’ cam from a pre-constructed list signed by **y** (we can ‘fake’ a proof this proof by knowing **y**, which is why it is paramount that knowledge of **y** is destroyed).

We know the values of **G** and **y•G**. If we also can get **μ** and **y•μ**, we can validate that the mapping between (**G -> y•G)** and **(μ ->** **y•μ)** is the same and therefore we can **prove** that **μ** is a signature from the signature database. This is what we require for our **bilinear pairing** comparison.

In order to do this, we need **y•μ.** To get this, we need to compute this quantity:![img](https://cdn-images-1.medium.com/max/1600/0*7wgp7L2Oy12BmnG0.png)

This might make more sense if we re-write **G** as (**(y -k)/(y-k))•G**, and **μ** in terms of **G**:![img](https://cdn-images-1.medium.com/max/1600/0*pS3qj2fKW4Fsy7dS.png)

Because of homomorphic addition, the ‘scalar multiplier’ of **G** is **y/(y-k)**, leading us to this:![img](https://cdn-images-1.medium.com/max/1600/0*tolPfI7VyRBOBUcH.png)

# ***\*Validating Boneh-Boyen signatures: bilinear pairings\****

For any valid Boneh-Boyen signature **μ**, we can compute **y•μ** despite not knowing the value of **y**. But how do we know that this signature was signed by the trusted setup private key and is not a forgery?

If we have these two points, we can check that **y** is indeed the correct private key through a **bilinear pairing**.

Vitalik [wrote a great article on bilinear pairings](https://medium.com/@VitalikButerin/exploring-elliptic-curve-pairings-c73c1864e627) that explains it better than I can, if you want to know more I recommend reading it. To summarise, pairings perform a kind of multiplication of elliptic curve points. If I perform the pairing operation on two points: **e(a•P,b•R)**, it doesn’t matter which points contain the scalars **a** and **b** because the result multiplies them together. For example, the following four pairing operations create the same result:

**e(a•P,b•R) = e(b•P,a•R) = e(ab•P,R) = e(P,ab•R)**

So take our **trusted-setup** public key**, T = y•G.** If we are given elliptic curve points **μ** and **y•μ**, we can check that this is the case by pairing these points with **T** and **G** respectively and checking both sides of the following equation match:![img](https://cdn-images-1.medium.com/max/1600/0*LA-dKUXF2m1j9Squ.png)

Putting it all together, we can validate whether an elliptic curve point **μ** is a Boneh-Boyen signature over an integer **k**, signed by trusted-setup private key **y**, by validating the following equation:![img](https://cdn-images-1.medium.com/max/1600/0*mhCpV5mjBWehNQNK.png)

The takeaway from this, is that if a person can prove that they have a signature signed by **y,** and **link** the value **k** of the signature to an encrypted value, then we know that the encrypted value can only be one of the integers signed in the trusted setup. I.e. we have a range proof. Tadaaa…

It’s important that this can be done without anybody actually knowing what **y***is*, because **y** was destroyed at the end of the trusted setup process.

The value in all of this is that the verification equation does not care about how big **k** is. The bigger the range, the bigger the *signature database* created by the trusted setup, but the computational cost of verifying this range proof is always constant.

## ***\*But wait, there’s more! Creating an encryption scheme with an embedded range proof\****

During our trusted setup protocol, we created an elliptic curve point **μ** for every integer we accept in our range proof and put them in a database. We also publish the public key **T.**

So now, we can pick out one of these points and prove that it was signed by **T**. But this does **not** give us the confidentiality we need.

If I see somebody else use a signature point in a transaction, I can just look up which integer that point corresponds to in the database!

We need to add in a **randomizing** factor. Pick a random variable **a**. This is our **viewing key**. Now, if we want to construct a range proof over an integer **k**, we pick out the required point **μ** and multiply it by the viewing key. Let’s call this point **γ**![img](https://cdn-images-1.medium.com/max/1600/0*Ev_woruNmuW8nk6y.png)

In order to prove that **γ** is a signature signed by **y**, we need to be able to get **y•γ**. instead of **y•μ**. But this is straightforward, just compute **k•γ + a•G**instead of **k•μ + G:**![img](https://cdn-images-1.medium.com/max/1600/0*lX4TwPdympw2Q81P.png)

Let’s introduce a point, **σ**, to represent this: **σ** = **y•γ.** Now, to prove we have a valid signature given the pair of points **(γ, σ)**, a verifier must validate that the following equations are true:![img](https://cdn-images-1.medium.com/max/1600/0*TRbyUVx6r7umONT9.png)![img](https://cdn-images-1.medium.com/max/1600/0*sIz-4XMfupeatpxI.png)

The *value* in this is that an observer cannot link **γ** to a signature in the signature database, because we’ve scrambled the signature with our viewing key **a**. *However,* we can *still* prove that whatever **γ** contains, it is still a Boneh-Boyen signature signed by the trusted setup private key **y**, even though nobody actually knows what this is and all we have to work with is **T**.

# ***\*Putting it all together: the AZTEC ‘commitment’ function\****

You might have noticed that this bilinear pairing verification equation requires the integers **k** and **a**. The verification equations are being run inside a ‘smart contract’ validation algorithm, and we naturally **don’t** want to broadcast these integers! That’s kind of the whole point.

This is relatively straightforward and can be done through a **zero-knowledge proof**. But that is a whole other article in and of itself, for now let’s just assume this can be done.

The two points (**γ, σ**) represent an **encryption** of an integer **k**. Given these two points, only **one** specific value of **k** and **one** specific value of **a** will satisfy the verification equations.

This is because **γ** is a function of the trusted setup private key **y**, and the generator point **G** is not. Assuming the trusted setup is done properly, and knowledge of **y** has been destroyed, it is not possible to ‘factorize’ out the integer (**k**) multiplying **γ**, by adding terms to the integer (**a**) multiplying **G**, without breaking elliptic curve cryptography.

This is the **computational binding** property that is required for a useable encryption scheme.

It is also not possible to glean any information about **k** by examining the points **(γ, σ)**, other than the fact that it is within our range proof bounds. This is because the viewing key (**a)** acts as a randomizing factor that needs to be factored out before **k** can be extracted. This is the **perfectly hiding** property, the second property required for any encryption scheme.

Naturally, if I give you an encrypted point pair **(γ, σ)** and the viewing key (**a**), you can figure out what **k** is (I mean, it’s called a viewing key for a reason!). This is because we can compute **k•γ** by computing **σ — a•G**. Now that we have **k•γ** and **γ,** we can extract **k** via a brute-force algorithm (because the set of integers that **k** is from is relatively small, say between a million and a billion values).

It is this commitment function, an encryption scheme that contains an implicit range proof, that enables the AZTEC protocol’s zero-knowledge proofs to be efficiently verified.

# AZTEC Protocol 1.0.0

Technical specification of the AZTEC Protocol



# **Table of contents**

- Architecture
  - The AZTEC Cryptography Engine
  - AZTEC notes and ABI encoding
- The Note Registry
- ACE, the AZTEC Cryptography Engine
  - Validating AZTEC proofs - defining the proof's identifier
  - Enacting confidential transfer instructions - defining the ABI encoding of proofOutputs
  - ABI encoding for `bytes proofOutputs`
  - ABI encoding for `bytes proofOutput = proofOutputs[i]`
  - Cataloguing valid proofs inside ACE
  - ACE owner
- The key responsibilities of `ACE`
  - Separating proof validation and note registry interactions
- Contract Interactions
  - Zero-knowledge dApp contract interaction, an example flow with bilateral swaps
  - The rationale behind multilateral confidential transactions
- Validating an AZTEC proof
- Note registry implementation
  - Creating a note registry
  - Note Registry Variables
  - Smart contract implementation
  - Upgradeability functionality
- Processing a transfer instruction
  - A note on ERC20 token transfers
- Minting AZTEC notes
  - Minting and tokens
- Burning AZTEC notes
- Interacting with ACE: zkAsset
  - Creating a confidential asset
  - Issuing a confidential transaction: confidentialTransfer
  - Issuing delegated confidential transactions: confidentialTransferFrom
  - Permissioning
- Proof verification contracts
  - JoinSplit.sol
  - Swap.sol
  - Dividend.sol
  - PublicRange.sol
  - PrivateRange.sol
  - JoinSplitFluid.sol
- Specification of Utility libraries
- Appendix
  - A: Preventing collisions and front-running
  - B - Interest streaming via AZTEC notes
- Glossary

# **Architecture**

The AZTEC protocol enables efficient confidential transactions through the construction of AZTEC-compatible zero-knowledge proofs. Specifically, the protocol focuses on optimizing confidential *settlement* and other forms of value-transfer

The protocol is architected to optimize for the following factors:

1. customizability - AZTEC assets must have confidential transaction semantics that can be modified to suit the ends of the user
2. interoperability - different AZTEC assets must conform to a standard interface that dApps can use to settle confidential transactions
3. efficiency - no redundant computation should be performed when verifying confidential transactions
4. qualified upgradability - as improvements are made to the underlying cryptographic protocols, and additional proof systems are added into AZTEC, existing confidential assets should be able to enjoy the benefits of these improvements. At the same time, users of AZTEC must be able to have confidence that they can opt out of these upgrades - that the verification algorithms used to validate existing zero-knowledge proofs are immutable. In addition, as upgrades are made to the logic of note registries, user must have the option to benefit from these upgrades whilst also being able to opt out.

## **The AZTEC Cryptography Engine**

The focus of our protocol is this cryptography engine (ACE.sol). ACE is the ultimate arbiter of the correctness of an AZTEC zero-knowledge proof. AZTEC assets subscribe to ACE and call on it to validate proofs.

ACE converts zero-knowledge proof data into *instructions* - directions on the following:

1. AZTEC notes to be created
2. AZTEC notes to be destroyed
3. Public tokens that need to be transferred

Internally, ACE will create a unique representation of each proof instruction and store it

## **ABI encoding and AZTEC data 'types'**

The nature of zero-knowledge cryptography means that a significant volume of data is processed on-chain in the form of zero-knowlege proof *inputs* and zero-knowledge proof *outputs*.

Because using structs in external functions is still an experimental feature, the AZTEC protocol defines its own ABI encoding for struct-like data types. These objects are represented by the `bytes` type, where the contents of the bytes array contains data that is formatted according to the AZTEC protocol's ABI specification.

### **AZTEC note ABI**

One key feature of ACE is the ability to support multiple note 'types'. Different note types enable the engine to support zero-knowledge proofs that use different techniques to represent encrypted value.

For example, the currently implemented basic AZTEC note is the most efficient way to represent encrypted value, however it's UTXO-like form may be unsuitable for some applications. On the other hand, once implemented, ElGamal 'treasury' notes could be used to emulate a more traditional account-balance model, where the balance is encrypted.

All notes use the same basic structure, but with different `publicKey` values. Every AZTEC zero-knowlege proof explicitly defines the type of note that it utilizes. Under no circumstances should it be possible to use a note of the wrong 'type' in a zero-knowledge proof.

The ABI encoding of a note is as follows:

| Offset       | Length | Name      | Type    | Description                                               |
| ------------ | ------ | --------- | ------- | --------------------------------------------------------- |
| 0x00         | 0x20   | id        | uint256 | The 'type' identifier of the note                         |
| 0x20         | 0x20   | owner     | address | Ethereum address of note owner                            |
| 0x40         | 0x60   | noteHash  | bytes32 | Hash of the note's elliptic curve points: gamma and sigma |
| 0x60         | L_pub  | publicKey | bytes   | The public key of the note, that is used to encrypt value |
| 0x60 + L_pub | L_met  | metaData  | bytes   | Note-specific metaData                                    |

### **Type 1: UTXO notes**

This is the default note type and currently used by the protocol. The ABI formatting of this note's `publicKey` is as follows:

| Offset | Length | Name          | Type    | Description                                      |
| ------ | ------ | ------------- | ------- | ------------------------------------------------ |
| 0x00   | 0x20   | gamma         | bytes32 | (compressed) bn128 group element                 |
| 0x20   | 0x20   | sigma         | bytes32 | (compressed) bn128 group element                 |
| 0x40   | 0x21   | ephemeral key | bytes33 | ephemeral public key used to recover viewing key |

### **Type 2: El-Gamal treasury notes**

Treasury notes would enable a single 'account' to have their balance represented by a single treasury note (instead of a multitude of AZTEC UTXO-type notes). They are slightly more gas-expensive to use than AZTEC notes and are only used in a small subset of AZTEC zero-kowledge proofs.

| Offset | Length | Name             | Type    | Description                                                  |
| ------ | ------ | ---------------- | ------- | ------------------------------------------------------------ |
| 0x00   | 0x20   | ownerPubKey      | bytes32 | (compressed) bn128 group element that maps to the public key of the note's owner |
| 0x20   | 0x20   | noteEphemeralKey | bytes32 | (compressed) bn128 group element, a public key component of the note's ephemeral key |
| 0x40   | 0x20   | noteCommitment   | bytes32 | (compressed) bn128 group element, the core El-Gamal commitment |
| 0x60   | -      | metaData         | bytes   | custom metaData associated with note                         |

### **metaData**

`metaData` is a general purpose data field for notes. It is not used by the logic of AZTEC zero-knowlege proof validators, but instead contains implementation and application specific information and is broadcast by events involving a note.

The `metaData` schema has a default component and then an additional customData component that can be set if the associated functionality is required. By default, it is populated with the ephemeral key whichcan be used to recover a note viewing key (see below). Additional custom data can be appended by calling `note.setMetaData()`, resulting in a schema as below:

| Offset                                   | Length              | Name                    | Type      | Description                                      |
| ---------------------------------------- | ------------------- | ----------------------- | --------- | ------------------------------------------------ |
| 0x00                                     | 0x41                | ephemeralKey            | bytes32   | ephemeralKey used in key exchange                |
| 0x41                                     | 0x61                | approvedAddressesOffset | uint256   | relative offset to `address[] approvedAddresses` |
| 0x61                                     | 0x81                | encryptedViewKeysOffset | uint256   | relative offset to `bytes[] encryptedViewKeys`   |
| 0x81                                     | 0xa1                | appDataOffset           | int256    | relative offset to `bytes[] appData`             |
| 0xa1                                     | L_addresses         | approvedAddresses       | address[] | addresses approved for access to viewing key     |
| 0xa1 + L_addresses                       | L_encryptedViewKeys | encryptedViewKeys       | bytes[]   | IES encrypted viewing keys, for each address     |
| 0xa1 + L_addresses + L_encryptedViewKeys | L_appData           | appData                 | bytes[]   | application specific data                        |

Therefore, included in the `metaData` is: the note ephemeral key, addresses to be approved, a series of IES encrypted viewing keys for use in granting note access to third parties and data for application specific use cases. These are used to enable various functionality as defined below.

**Use 1: Recovering viewing key using the ephemeral key**

Every note viewing key should be distinct, however users should not have to manage a multitude of unique viewing keys. In addition, if user A wishes to send user B a note, they should be able to derive a viewing key that A can recover. This process should be non-interactive.

The solution is to use a shared secret protocol, between an 'ephemeral' public/private key pair and the public key of the note owner. An extension of this protocol can be used to derive 'stealth' addresses, if the recipient has a stealth wallet. Currently, our V1 APIs use the basic shared secret protocol for ease of use (traditional Ethereum wallets can own these kinds of AZTEC notes). At the smart contract level, the protocol is forward-compatible with stealth addresses.

Therefore, the first use of the metaData field is to store the data that a user requires to recover their note viewing key - the 'ephemeral' public key.

**Use 2: Granting view key access**

Note viewing key access can be directly granted to third parties by encoding an IES encrypted viewing key and the associated approved address into the `metaData`. This allows a method whereby viewing key access can be efficiently computed, without having to derive using the ephemeral key.

Granting of viewing keys is supported by the `zkAsset.updateNoteMetaData(bytes32 noteHash, bytes calldata metaData)` function. This allows the `metaData` of an already existing note to be updated, and so grant viewing key access to additional parties.

**Use 3: Application specific data**

Lastly, application specific data can be attached to the `metaData` of a note. This gives digital asset builders the option to attach custom data to an AZTEC note for an application specific utility.

# **The Note Registry**

The AZTEC note registry contract is a subset of the AZTEC Cryptography Engine, but we describe it explicitly given its importance to the protocol.

The note registry contains the storage variables that define the set of valid AZTEC notes for a given address. It is expected this address maps to a smart contract, but this is not enforced.

The note registry enacts the instructions generated by valid AZTEC proofs - creating and destroying the required notes, as well as transferring any required tokens.

The note registry's `owner` is the only entity that can issue instructions to update the registry. `NoteRegistry` will only enact instructions that have been generated by a valid AZTEC proofs as it is of critical importance that notes are not created/destroyed unless a **balancing relationship** has been satisfied.

Because every confidential asset that uses an ACE note registry can have 100% confidence in the integrity of the state of every *other* ACE note registry, it makes it possible to express AZTEC notes from one registry as a percentage of notes in a second registry, which in turn is useful for dividend-paying confidential assets and confidential assets that utilize income streaming.

# **ACE, the AZTEC Cryptography Engine**

The `ACE.sol` contract is responsible for validating the set of AZTEC zero-knowledge proofs and performing any transfer instructions involving AZTEC notes. ACE is the controller of all AZTEC note registries and acts as the custodian of both AZTEC notes and any tokens that have been converted into AZTEC notes.

While it is possible to define note registries that are external to ACE, the state of these contract's note registries cannot be guranteed and only a subset of proofs will be usable (i.e. if an asset uses an ACE note registry, transfer instructions from AZTEC proofs that involve multiple note registries are only enacted if every note registry is controlled by ACE).

The ACE has the following interface:



```
/** * @title IACE * @author AZTEC * @dev Standard defining the interface for ACE.sol * Copyright Spilsbury Holdings Ltd 2019. All rights reserved. **/interface IACE {    function mint(        uint24 _proof,        bytes calldata _proofData,        address _proofSender    ) external returns (bytes memory);    function burn(        uint24 _proof,        bytes calldata _proofData,        address _proofSender    ) external returns (bytes memory);    function validateProof(uint24 _proof, address _sender, bytes calldata) external returns (bytes memory);    function clearProofByHashes(uint24 _proof, bytes32[] calldata _proofHashes) external;    function setCommonReferenceString(bytes32[6] calldata _commonReferenceString) external;    function invalidateProof(uint24 _proof) external;    function validateProofByHash(        uint24 _proof,        bytes32 _proofHash,        address _sender    ) external view returns (bool);    function setProof(        uint24 _proof,        address _validatorAddress    ) external;    function incrementLatestEpoch() external;    function getCommonReferenceString() external view returns (bytes32[6] memory);    function getValidatorAddress(uint24 _proof) external view returns (address validatorAddress);    function getNote(address _registryOwner, bytes32 _noteHash) external view returns (        uint8 status,        uint40 createdOn,        uint40 destroyedOn,        address noteOwner    );}
```

## **Validating AZTEC proofs - defining the proof's identifier**

ACE supports multiple types of zero-knowlege proof and this family of proofs will grow over time. It is important to categorise these proofs in a systematic manner.

The ACE proof identification and versioning sytem has the following characteristics:

- Extendibility. AZTEC's modular proof system enables composable confidential transaction semantics - adding more proofs enables these semantics to be more expressive. Additionally, it allows the AZTEC protocol to support fundamentally new types of zero-knowledge proving technology as Ethereum scales (e.g. bulletproofs, zk-snarks)
- Opt-out functionality. If an asset controller only wants to listen to a subset of proofs (e.g. whether to listen to newly added proofs is on their terms. This is important for assets that have an internal review process for zero-knowledge proofs)
- Qualified immutability. The validator code for a given proof id should never change. AZTEC must be able to de-activate a proof if it is later found to contain a bug, but any upgrades or improvement to a proof are expressed by instantiating a new validator contract, with a new proof id.

A proof is uniquely defined by an identifier`uint24 _proof`. ACE stores a mapping that maps each `_proof` to the address of a smart contract that validates the zero-knowledge proof in question.

Instead of having a 'universal' validation smart contract, it was chosen to make these contracts discrete for maximum flexibility. Validator contracts should not be upgradable, to gurantee that users of AZTEC proofs can have confidence that the proofs they are using are not subject to change. Upgrades and changes are implemented by adding new validator contracts and new proofs.

The `uint24 _proof` variable contains the concatenation of three `uint8` variables (the rationale for this compression is to both reduce `calldata` size and to simplify the interface. Our javascript APIs automatically compose proofs with the correct `_proof`, minimizing the amount of variables that a builder on AZTEC has to keep track of.

The formatting as follows (from most significant byte to least significant byte)

| name     | type  | description                                                  |
| -------- | ----- | ------------------------------------------------------------ |
| epoch    | uint8 | the broad family that this proof belongs to                  |
| category | uint8 | the general function of this proof                           |
| id       | uint8 | the proof's identifier, for the specified category and epoch |

A semantic-style version system was not used because proof `epoch` defines functionality as well as a form of version control. Proofs with the same `uint8 id` but with different `uint8 epoch` do not neccesarily perform the same function and proofs from a later `epoch` are not strictly 'better' than proofs from an earlier `epoch`.

For example, if the basic family of AZTEC proofs was adapted for confidential transactions that do not use a trusted setup, these proofs would be categorized by a new `epoch`. However these would not be a strict upgrade over the earlier epoch because the gas costs to verify these proofs would be almost an order of magnitude greater.

Similarly, when confidential voting mechanics are implemented into `ACE`, these will be defined by a separate `epoch` to emphasise their different functionality vs confidential transactions.

The `uint8 category` variable represents an enum with the four following values:

| value | name     | description                                                  |
| ----- | -------- | ------------------------------------------------------------ |
| 0x01  | BALANCED | proofs that satisfy a balancing relationship                 |
| 0x02  | MINT     | proofs that can be used to mint AZTEC notes                  |
| 0x03  | BURN     | proofs that can be used to burn AZTEC notes                  |
| 0x04  | UTILITY  | utility proofs that can not, in isolation, be used to issue note transfers |

The `ACE` contract has separate logic to handle `BALANCED`, `MINT` and `BURN` proofs, as the latter two expressly violate the balancing relationship used to prevent double spending. The `MINT` and `BURN` proofs are designed for fully private AZTEC assets, ones with no ERC20 token equivalent, where AZTEC notes are the primary expression of value. Additional restrictions are placed on their use because of this.

For more information regarding minting and burning, see the mint and burn section.

The `UTILITY` proofs are designed for assets that require additional validation logic before a transaction can be performed. For example, an asset might require a trader to prove that they own less than 10% of the total supply of the asset before a trade is processed. This is supported by our `dividend` utility proof.

This specification contains descriptions for every currently supported proof id. Formal descriptions of the zero-knowledge proofs utilized by the verifiers can be found in the [AZTEC protocol paper](http://www.github.com/AZTECProtocol/AZTEC).

When combined together, `uint8 epoch, uint8 category, uint8 id` create 65025 unique proof identifies for each category. Given the complexity of zero-knowledge cryptographic protocols and the validation that must be performed before integration into `ACE`, it is infeasible for there to ever be demand for more than `65025` types of zero-knowledge proof inside `ACE`.

## **Enacting confidential transfer instructions - defining the ABI encoding of proofOutputs**

There is substantial variation between the zero-knowledge proofs that AZTEC utilizes. Because of this, and the desire to create a simple interface to validate proofs, the interface for proof *inputs* is generic. An AZTEC proof accepts three parameters: `bytes data, address sender, uint256[6] commonReferenceString`. The `commonReferenceString` is provided by ACE. The `data` variable contains the zero-knowledge proof data in question, the `address sender` field is utilized to eliminate front-running. The ABI-encoding of `bytes data` is specific to a given validator smart contract.

The **output** of a zero-knowledge proof is a list of instructions to be performed. It is important that these `proofOutput` variables conform to a common standard so that existing confidential assets can benefit from the addition of future proofs.

An instruction must contain the following:

- A list of the notes to be destroyed, the 'input notes'
- A list of the notes to be created, the 'output notes'
- If public tokens are being transferred, how many tokens are involved, who is the beneficiary and what is the direction of the transfer? (into ACE or out of ACE?)

In addition to this, ACE must support one zero-knowledge proof producing *multiple* instructions (e.g. the `Swap` proof provides transfer instructions for two distinct assets).

Proofs in the `UTILITY` category also conform to this specification, although in this context 'input' and 'output' notes are not created or destroyed.

To summarise, the output of any AZTEC validator smart contract is a `bytes proofOutputs` variable, that encodes a dynamic array of `bytes proofOutput` objects. The ABI encoding is as follows:

## **ABI encoding for `bytes proofOutputs`**

| Offset                                          | Length          | Name           | Type            | Description                                                  |
| ----------------------------------------------- | --------------- | -------------- | --------------- | ------------------------------------------------------------ |
| 0x00                                            | 0x20            | length         | uint256         | the number of `proofOutput` objects                          |
| 0x20                                            | (0x20 * length) | offsets        | uint256[length] | array of 0x20-sized variables that contain the relative offset to each respective `proofOutput` object |
| 0x20 + (0x20 * length) + (\sum_{j=0}^{i-1}L[j]) | L[i]            | proofOutput[i] | bytes           | the `bytes proofOutput` object                               |

## **ABI encoding for `bytes proofOutput = proofOutputs[i]`**

| Offset     | Length | Name          | Type    | Description                                                  |
| ---------- | ------ | ------------- | ------- | ------------------------------------------------------------ |
| 0x00       | 0x20   | inputsOffset  | uint256 | the relative offset to `bytes inputNotes`                    |
| 0x20       | 0x20   | outputsOffset | uint256 | the relative offset to `bytes outputNotes`                   |
| 0x40       | 0x20   | publicOwner   | address | the Ethereum address of the owner of tokens being transferred |
| 0x60       | 0x20   | publicValue   | int256  | the amount of public 'value' being transferred               |
| 0x80       | 0x20   | challenge     | uint256 | the 'challenge' variable used in the zero-knowledge proof that produced this output |
| 0xa0       | L_1    | inputNotes    | bytes   | the `bytes inputNotes` variable                              |
| 0xa0 + L_1 | L_2    | outputNotes   | bytes   | the `bytes outputNotes` variable                             |

Both `bytes inputNotes` and `bytes outputNotes` are dynamic arrays of AZTEC notes, encoded according to the AZTEC note ABI spec.

The `int256 publicValue` variable is a *signed* integer, because negative values are interpreted as tokens being transferred *from* `address publicOwner` and into `ACE`. Similarly, positive values are interpreted as tokens being transferred *to* `address publicOwner`.

It should be noted that `int256 publicValue` does not represent an absolute number of tokens. Each registry inside `NoteRegistry` has an associated `uint256 scalingFactor`, that defines how many ERC20 tokens are represented by 1 unit of AZTEC note 'value'. This mapping is neccessary because AZTEC note values are approximately 30-bit integers (CAVEAT HERE) and a scaling factor is required to map 256-bit ERC20 token volumes to 30-bit AZTEC values.

The `uint256 challenge` variable is used to ensure that each `bytes proofOutput` produces a unique hash. The challenge variable is required for every AZTEC zero-knowledge proof, and is itself a unique pseudorandom identifier for the proof (two satisfying zero-knowledge proofs cannot produce matching challenge variables without a hash collision). For a proof that produces multiple `bytes proofOutput` entries inside `bytes proofOutputs`, it is the responsibility of the verifier smart contract to ensure each challenge variable is unique (i.e. each `bytes proofOutput` contains a challenge variable that is a hash of the challenge variable for the previous entry).

Consequently, a hash of `bytes proofOutput` creates a unique identifier for a proof instruction because of the uniqueness of the challenge variable.

## **Cataloguing valid proofs inside ACE**

Once a `BALANCED`, `MINT` or `BURN` proof has been validated, ACE records this fact so that future transactions can query the proof in question. This is done by creating a keccak256 hash of the following variables (encoded in an unpacked form)

| Offset | Length | Name       | Type    | Description                             |
| ------ | ------ | ---------- | ------- | --------------------------------------- |
| 0x00   | 0x20   | proofHash  | bytes32 | a keccak256 hash of `bytes proofOutput` |
| 0x20   | 0x20   | _proof     | uint24  | the _proof of the proof                 |
| 0x40   | 0x20   | msg.sender | address | the address of the entity calling `ACE` |

This creates a unique key, that is mapped to `true` if the proof is valid (invalid proofs are not stored).

Contracts can query `ACE` with a `bytes proofOutput`, combined with a `uint24 _proof` and the `address` of the entity that issued the instruction. `ACE` can validate whether this instruction came from a valid proof.

This mechanism enables smart contracts to issue transfer instructions on behalf of both users and other smart contracts, enabling zero-knowledge confidential dApps.

## **ACE owner**

It should be noted that in upon deployment, the owner of the ACE will be a multi-signature wallet.

# **The key responsibilities of `ACE`**

The `ACE` engine has two critical responsibilities:

1. Determine the correctness of valid AZTEC zero-knowledge proofs and permanently record the existence of validated `BALANCED` proofs
2. Update the state of its note registries when presented with valid transfer instructions

When processing a transfer instruction, the following criteria must be met:

- Did the transfer instruction originate from the note registry's owner?
- Is the transfer instruction sourced from a *mathematically legitimate* AZTEC proof?

Because of these dual responsibilities, valid AZTEC proofs are *not* catalogued against specific note registries. The outputs of any valid proof can, theoretically, be issued to any note ,registry. After all, the existence of a valid proof indicates the resulting transfer instructions are balanced. This is the critical property that `ACE` *must* ensure, that all of its note registries are balanced and that there is no double spending.

Restricting note registry updates to the creator of a given note registry provides a natural separation of concerns - `ACE` determines whether a transfer instruction *can* happen and the note registry owner determines whether the instruction *should* happen.

### **Separating proof validation and note registry interactions**

Because of these dual responsibilities, it might seem intuitive to roll proof validation and note registry updates into a single function. However, this would undermine one of the key strengths of the AZTEC protocol - that third party dApps can validate zero-knowledge proofs and send the resulting transfer instructions to AZTEC-compatible confidential assets. [Zero-knowledge dApp contract interaction, an example flow with bilateral swaps] (#zero-knowledge-dapp-contract-interaction-an-example-flow-with-Swaps) demonstrates this type of interaction and, consequently, the importance of separating proof validation from note registry updates.

# **Contract Interactions**

![img](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LhZjaocaF34Y4jZgGiC%2F-LmzM2WPPAOS4yOuiFKi%2F-LmzMtbnuav2OyT8YAGi%2Fimage.png?alt=media&token=f94cec5e-65ee-4f49-adad-249c0a3a6cca)

user-to-validator

Transaction #1

1. `ACE.validateProof(uint24 _proof, address sender, bytes data)`

2. `Validator.validate(bytes data, address sender, uint[6] commonReferenceString)` (revert on failure, return `bytes proofOutputs`)

3. return `address publicOwner, uint256 transferValue, int256 publicValue` to ACE, if `int256 publicValue` is non-zero, `ACE.transferPublicTokens(address _publicOwner, uint256 _transferValue, int256 _publicValue, bytes32 _proofHash)` (revert on failure)

4. a. (if `proofOutput.publicValue > 0`) `ERC20.transfer(proofOutput.publicOwner, uint256(proofOutput.publicValue))` (revert on failure)

   b. (if `proofOutput.publicValue < 0`) `ERC20.transferFrom(proofOutput.publicOwner, this, uint256(-proofOutput.publicValue))` (revert on failure)

5. return `bytes proofOutputs` to caller, log valid proof if category != `UTILITY`, revert on failure

![img](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LhZjaocaF34Y4jZgGiC%2F-LmzM2WPPAOS4yOuiFKi%2F-LmzN27kClFFrybYKPzD%2Fimage.png?alt=media&token=7172d0f7-009a-487a-99d7-623f7b4322ce)

user-to-registry

Transaction #1

1. `ACE.updateNoteRegistry(uint24 _proof, bytes proofOutput, address sender)`

2. `NoteRegistry.validateProofByHash(uint24 _proof, bytes proofOutput, address sender)` (revert on failure)

   3a. (if `proofOutput.publicValue > 0`) `ERC20.transfer(proofOutput.publicOwner, uint256(proofOutput.publicValue))` (revert on failure)

   3b. (if `proofOutput.publicValue < 0`) `ERC20.transferFrom(proofOutput.publicOwner, this, uint256(-proofOutput.publicValue))` (revert on failure)

3. NoteRegistry: (revert on failure)

4. ACE: (revert on failure)

## **Zero-knowledge dApp contract interaction, an example flow with bilateral swaps**

The following image depicts the flow of a zero-knowledge dApp that utilizes the `Swap` proof to issue transfer instructions to two zkAsset confidential digital assets. This example aims to illustrate the kind of confidential cross-asset interactions that are possible with AZTEC. Later iterations of the protocol will include proofs that enable similar multilateral flows.

The dApp-to-zkAsset interactions are identical for both `zkAsset A` and `zkAsset B`. To simplify the description we only describe the interactions for one of these two assets.

![img](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LhZjaocaF34Y4jZgGiC%2F-LmzM2WPPAOS4yOuiFKi%2F-LmzNDFxnnHMwpIFASS8%2Fimage.png?alt=media&token=ebfc5fdd-fa34-47b1-b3ef-26edcfb486fd)

zk-dapp-flow

### **(1-5) : Validating the proof**

1. `zk dApp` receives a `Swap` zero-knowledge proof from `caller` (with a defined `uint24 _proof` and `bytes data`.
2. The `zk-dApp` contract queries `ACE` to validate the received proof, via `ACE.validateProof(_proof, msg.sender, data)`. If `_proof` is not supported by `zk-dApp` the transaction will `revert`.
3. On receipt of a valid proof, `ACE` will identify the `validator` smart contract associated with `_proof` (in this case, `Swap.sol`). `ACE` will then call `validator.validateProof(data, sender, commonReferenceString)`. If the `_proof` provided does not map to a valid `validator` smart contract, the transaction will `revert`.
4. If the proof is valid, the `validator` contract will return a `bytes proofOutputs` object to `ACE`. If the proof is invalid, the transaction will `revert`.
5. On receipt of a valid `bytes proofOutputs`, `ACE` will examine `_proof` to determine if the proof is of the `BALANCED` category. If this is the case, `ACE` will iterate over each `bytes proofOutput` in `bytes proofOutputs`. For each `proofOutput`, the `bytes32 proofHash` is computed. A unique proof identifier, `bytes32 _proofIdentifier = keccak256(abi.encode(_proof, msg.sender, proofHash))`, is then computed. This is used as a key to log the existence of a valid proof - `validProofs[_proofIdentifier] = true`.

Once this has been completed, `ACE` will return `bytes proofOutputs` to `zk-dApp`.

### **(6-8): Issuing a transfer instruction to `zkAsset A`**

At this stage, `zk-dApp` is in posession of transfer instructions that result from a valid `Swap` proof, in the form of a `bytes proofOutputs` object received from `ACE`.

For the `Swap` proof, there will be `2` entries inside `proofOutputs`, with each entry mapping to one of the two confidential assets - `zkAsset A` and `zkAsset B`.

1. The `zk-dApp` contract issues a transfer instruction to `zkAsset A` via `zkAsset.confidentialTransferFrom(_proof, proofOutput)`.
2. On receipt of `uint24 _proof, bytes proofOutput`. The `zkAsset A` contract validates that `_proof` is on the contract's proof whitlelist. If this is not the case, the transaction will `revert`.

`zkAsset A` computes `bytes32 proofHash` and query `ACE` as to the legitimacy of the received instructions, via `ACE.validateProofByHash(_proof, proofHash, msg.sender)`.

1. `ACE` queries its `validProofs` mapping to determine if a proof that produced `bytes proofOutput` was previously validated and return a boolean indicating whether this is the case.

If no matching proof was previously validated by `ACE`, `zkAsset A` will `revert` the transaction.

### **(9-16): Processing the transfer instruction**

Having been provided with a valid `proofOutput` that satisfies a balancing relationship, `zkAsset A` will validate the following:

- For every input `note`, is `approved[note.noteHash][msg.sender] == true`?

If this is not the case, the transaction will `revert`.

1. If all input notes have been `approved`, `zkAsset A` will instruct `ACE` to update its note registry according to the instructions in `proofOutput`, via `ACE.updateNoteRegistry(_proof, proofOutput, msg.sender)`.
2. On receipt of `bytes proofOutput`, `ACE` will also validate that the `proofOutput` instruction came from a valid zero-knowledge proof (and `revert` if this is not the case). Having been satisfied of the proof's correctness, `ACE` will instruct the note registry owned by `msg.sender` (`zkAsset A`) to process the transfer instruction.
3. `NoteRegistry A` will validate the following is correct:
4. For every input `note`, is `note.noteHash` present inside the `registry`?
5. For every output `note`, is `note.noteHash` *not* present inside the `registry`?

If `proofOutput.publicValue > 0`, the registry will call `erc20.transfer(proofOutput.publicOwner, uint256(proofOutput.publicValue))`.

If `proofOutput.publicValue < 0`, the registry will call `erc20.transferFrom(proofOutput.publicOwner, this, uint256(-proofOutput.publicValue))`.

1. If the resulting transfer instruction fails, the transaction is `reverted`, otherwise control is returned to `Note Registry A`

13-15. If the transaction is successful, control is returned to `ACE`, followed by `zkAsset A` and `zk-dApp`.

1. Following the successful completion of the confidential transfer (from both `zkAsset A` and `zkAsset B`), control is returned to `caller`. It is assumed that `zk-dApp` will emit relevant transfer events, according to the ERC-1724 confidential token standard.

## **The rationale behind multilateral confidential transactions**

The above instruction demonstrates a practical confidential cross-asset settlement mechanism. Without `ACE`, a confidential digital asset could only process a transfer instruction after validating the instruction conforms to its own internal confidential transaction semantics, a process that would require validating a zero-knowledge proof.

This would result in 3 distinct zero-knowledge proofs being validated (one each by `zk-dApp`, `zkAsset A`, `zkAsset B`). Because zero-knowledge proof validation is the overwhelming contributor to the cost of confidential transactions, this creates a severe obstacle to practical cross-asset confidential interactions.

However, by subscribing to `ACE` as the arbiter of valid proofs, these three smart contracts can work in concert to process a multilateral confidential transfer having validated only a single zero-knowledge proof (this is because the `Swap` proof produces transfer instructions that lead to two balancing relationships. Whilst `zkAsset A` and `zkAsset B` do not know this (the proof in question could have been added to `ACE` *after* the creation of these contracts), `ACE` does, and can act as the ultimate arbiter of whether a transfer instruction is valid or not.

Whilst it may apear that this situation requires AZTEC-compatible assets to 'trust' that ACE will correctly validate proofs, it should be emphasized that `ACE` is a completely deterministic smart-contract whose code is fully available to be examined. No real-world trust (e.g. oracles or staking mechanisms) is required. The source of the guarantees around the correctness of AZTEC's confidential transactions come from its zero-knowledge proofs, all of which have the properties of completeness, soundness and honest-verifier zero-knowledge.

# **Validating an AZTEC proof**

AZTEC zero-knowledge proofs can be validated via `ACE.validateProof(uint24 _proof, address sender, bytes calldata data) external returns (bytes memory proofOutputs)`.

The `bytes data` uses a custom ABI encoding that is unique to each proof that AZTEC supports. It is intended that, if a contract requires data from a proof, that data is extracted from `bytes proofOutputs` and not the input data.

If the `uint8 category` inside `_proof` is of type `BALANCED`, `ACE` will record the validity of the proof as a state variable inside `mapping(bytes32 => bool) validatedProofs`.

If the proof is not valid, an error will be thrown. If the proof is valid, a `bytes proofOutputs` variable will be returned, describing the instructions to be performed to enact the proof. For `BALANCED` proofs, each individual `bytes proofOutput` variable inside `bytes proofOutputs` will satisfy a balancing relationship.

# **Note registry implementation**

## **Creating a note registry**

An instance of a note registry is created inside ACE, via `createNoteRegistry(address _linkedTokenAddress, uint256 _scalingFactor, bool _canAdjustSupply, bool _canConvert)`.

The `_canAdjustSupply` flag defines whether the note registry owner an directly modify the note registry state by minting and burning AZTEC notes. The `_canConvert` flags defines whether ERC20 tokens from `_linkedTokenAddress` can be converted into AZTEC notes. If `_canConvert` is `false`, then `_linkedTokenAddress = address(0)` and the asset is a fully private asset.

For a given note registry, only the owner can call `ACE.updateNoteRegistry`, `ACE.mint` or `ACE.burn`. Traditionally this is imagined to be a `zkAsset` smart contract. This allows the `zkAsset` contract to have absolute control over what types of proof can be used to update the note registry, as well as the conditions under which updates can occur (if extra validation logic is required, for example).

## **Note Registry Variables**

### **`bytes32 confidentialTotalMinted`**

This variable is the keccak256 hash of an AZTEC UTXO note that defines the total amount of value that a note registry has directly minted.

When a note registry is created, this note is set to be an AZTEC UTXO note that has a value of `0` and a viewing key of `1`.

### **`bytes32 confidentialTotalBurned`**

This variable is the kecckak256 hash of an AZTEC UTXO note that defines the total amount of value that a note registry has directly burned.

When a note registry is created, this note is set to be an AZTEC UTXO note that has a value of `0` and a viewing key of `1`.

### **`uint256 scalingFactor`**

If this registry permits conversions from AZTEC notes into tokens, `scalingFactor` defines the number of tokens that an AZTEC note value of `1` maps to.

This is required because the maximum value of an AZTEC note is approximately `2^26` (it is dependent on ACE's common reference string) - there is an associated loss of precision when converting a `256` bit variable into a `26` bit variable.

### **`uint256 totalSupply`**

This variable represents the total amount of tokens that currently reside within `ACE` as a result of tokens being converted into AZTEC notes, for a given note registry.

### **`ERC20 linkedToken`**

This is the address of the registry's linked ERC20 token. Only one token can be linked to an address.

### **`canAdjustSupply`**

Flag determining whether the note registry has minting and burning priviledges.

### **`canConvert`**

Flag determining whether the note registry has public to private, and vice versa, conversion priviledges

### **`totalSupplemented`**

Total number of tokens supplemented to the ACE, as a result of tokens being transferred when conversion of minted notes to public value was attempted and there were not sufficient tokens held by ACE.

## **Smart contract implementation**

The note registry functionality is enabled by a suite of smart contracts. This is principally to enable upgradeability and given that ACE is immutable, the decision was taken to break the note registries out into their own upgradeable modules.

Despite being encapsulated inside of ACE, note registries are owned by ZkAssets. The only entities which should be allowed to upgrade the note registry associated to a particular ZkAsset is its owner.

The implementation of all behaviour which affects the state of all note registries should be controlled and vetted by the owner of ACE, and ZkAsset owners should not be able to upgrade to arbitrary implementations.

The upgrade pattern, or any individual upgrade itself, should not compromise the hard link between a ZkAsset and its note registry (i.e. no non-authorised contract or account should be able to affect the state of the note registry through an upgrade or because note registries are upgradeable).

The data stored in these registries is obviously very sensitive, and valuable. Upgrades should be rare, backwards compatible, and no upgrade should result in funds becoming inaccessible, partly or wholly un-spendable, or otherwise compromised.

Of the various upgradeability patterns available, the unstructured storage proxy pattern developed by Open Zeppelin is used. The foundation of this pattern is to seperate the storage of the note registry, which defines the set of valid notes, from the logic, behaviour and methods of the note registry. There are four base contracts involved in this implementation: `Behaviour.sol`, `AdminUpgradeabilityProxy.sol` , `Factory.sol` and `NoteRegistryManager.sol` .

**Behaviour contract -** **Behaviour.sol**

The behaviour contract defines the methods and contains the logic of the note registry. It is this contract that is the mutable, upgradeable contract and the method whereby the implementation of note registry methods is upgraded. All behaviour contracts must abide by a set minimum API in order to maintain compatibility with ACE:



```
/**  * @title/** * @title NoteRegistryBehaviour interface which defines the base API        which must be implemented for every behaviour contract. * @author AZTEC * @dev This interface will mostly be used by ACE, in order to have an API to        interact with note registries through proxies. * The implementation of all write methods should have an onlyOwner modifier. * * Copyright Spilsbury Holdings Ltd 2019. All rights reserved. **/contract NoteRegistryBehaviour is Ownable, IAZTEC {    using SafeMath for uint256;    bool public isActiveBehaviour;    bool public initialised;    address public dataLocation;    constructor () Ownable() public {        isActiveBehaviour = true;    }    /**        * @dev Initialises the data of a noteRegistry. Should be called exactly once.        *        * @param _newOwner - the address which the initialise call will transfer ownership to        * @param _scalingFactor - defines the number of tokens that an AZTEC note value of 1 maps to.        * @param _canAdjustSupply - whether the noteRegistry can make use of minting and burning        * @param _canConvert - whether the noteRegistry can transfer value from private to public            representation and vice versa    */    function initialise(        address _newOwner,        uint256 _scalingFactor,        bool _canAdjustSupply,        bool _canConvert    ) public;    /**        * @dev Fetches data of the registry        *        * @return scalingFactor - defines the number of tokens that an AZTEC note value of 1 maps to.        * @return confidentialTotalMinted - the hash of the AZTEC note representing the total amount            which has been minted.        * @return confidentialTotalBurned - the hash of the AZTEC note representing the total amount            which has been burned.        * @return canConvert - the boolean whih defines if the noteRegistry can convert between            public and private.        * @return canConvert - the boolean whih defines if the noteRegistry can make use of            minting and burning methods.    */    function getRegistry() public view returns (        uint256 scalingFactor,        bytes32 confidentialTotalMinted,        bytes32 confidentialTotalBurned,        bool canConvert,        bool canAdjustSupply    );    /**        * @dev Enacts the state modifications needed given a successfully validated burn proof        *        * @param _proofOutputs - the output of the burn validator    */    function burn(bytes calldata _proofOutputs) external;    /**        * @dev Enacts the state modifications needed given a successfully validated mint proof        *        * @param _proofOutputs - the output of the mint validator    */    function mint(bytes calldata _proofOutputs) external;    /**        * @dev Enacts the state modifications needed given the output of a successfully validated proof.        * The _proofId param is used by the behaviour contract to (if needed) restrict the versions of proofs        * which the note registry supports, useful in case the proofOutputs schema changes for example.        *        * @param _proof - the id of the proof        * @param _proofOutput - the output of the proof validator        *        * @return publicOwner - the non-ACE party involved in this transaction. Either current or desired        *   owner of public tokens        * @return transferValue - the total public token value to transfer. Seperate value to abstract        *   away scaling factors in first version of AZTEC        * @return publicValue - the kPublic value to be used in zero-knowledge proofs    */    function updateNoteRegistry(        uint24 _proof,        bytes memory _proofOutput    ) public returns (        address publicOwner,        uint256 transferValue,        int256 publicValue    );    /**        * @dev Sets confidentialTotalMinted to a new value. The value must be the hash of a note;        *        * @param _newTotalNoteHash - the hash of the note representing the total minted value for an asset.    */    function setConfidentialTotalMinted(bytes32 _newTotalNoteHash) internal returns (bytes32);    /**        * @dev Sets confidentialTotalBurned to a new value. The value must be the hash of a note;        *        * @param _newTotalNoteHash - the hash of the note representing the total burned value for an asset.    */    function setConfidentialTotalBurned(bytes32 _newTotalNoteHash) internal returns (bytes32);    /**        * @dev Gets a defined note from the note registry, and returns the deconstructed object.            This is to avoid the interface to be        * _too_ opninated on types, even though it does require any subsequent note type to have            (or be able to mock) the return fields.        *        * @param _noteHash - the hash of the note being fetched        *        * @return status - whether a note has been spent or not        * @return createdOn - timestamp of the creation time of the note        * @return destroyedOn - timestamp of the time the note was destroyed (if it has been destroyed, 0 otherwise)        * @return noteOwner - address of the stored owner of the note    */    function getNote(bytes32 _noteHash) public view returns (        uint8 status,        uint40 createdOn,        uint40 destroyedOn,        address noteOwner    );    /**        * @dev Internal function to update the noteRegistry given a bytes array.        *        * @param _inputNotes - a bytes array containing notes    */    function updateInputNotes(bytes memory _inputNotes) internal;    /**        * @dev Internal function to update the noteRegistry given a bytes array.        *        * @param _outputNotes - a bytes array containing notes    */    function updateOutputNotes(bytes memory _outputNotes) internal;    /**        * @dev Internal function to create a new note object.        *        * @param _noteHash - the noteHash        * @param _noteOwner - the address of the owner of the note    */    function createNote(bytes32 _noteHash, address _noteOwner) internal;    /**        * @dev Internal function to delete a note object.        *        * @param _noteHash - the noteHash        * @param _noteOwner - the address of the owner of the note    */    function deleteNote(bytes32 _noteHash, address _noteOwner) internal;} 
```

**Storage/proxy contract -** **AdminUpgradeabilityProxy.sol**

The storage contract is referred to as the Proxy and it has four main responsibilities:

- Store the storage variables which define the set of unspent notes
- Implement the delegation of calls to behaviour contracts via `delegatecall()`. In this way, note registry functionality on the behaviour contract is executed in the context of the calling proxy storage contract - allowing behaviour methods access to notes
- Point the proxy to an upgraded behaviour implementation. This functionality is protected by an authorisation mechanism
- Faciliate a possible change of admin

The interface is defined as:



```
/** * @title ProxyAdmin * @dev Minimal interface for the proxy contract to be used by the Factory contract. */contract ProxyAdmin {    function admin() external returns (address);    function upgradeTo(address _newImplementation) external;    function changeAdmin(address _newAdmin) external;}
```

In order to facilitate the process of upgrading the behaviour contract to a new instance, there are two further classes of contracts: factory contracts and the note registry manager.

**Factory contracts -** **Factory.sol**

Factory contracts are used to deploy and link an upgraded behaviour instance to ACE. They are owned by the ACE and there is a factory contract for each type of behaviour instance that can be deployed: adjustable and mixed.



```
/**  * @title/** * @title NoteRegistryFactory * @author AZTEC * @dev Interface definition for factories. Factory contracts have the responsibility of managing the full lifecycle of * Behaviour contracts, from deploy to eventual upgrade. They are owned by ACE, and all methods should only be callable * by ACE. **/contract NoteRegistryFactory is IAZTEC, Ownable  {    event NoteRegistryDeployed(address behaviourContract);    constructor(address _aceAddress) public Ownable() {        transferOwnership(_aceAddress);    }    function deployNewBehaviourInstance() public returns (address);    function handoverBehaviour(address _proxy, address _newImplementation, address _newProxyAdmin) public onlyOwner {        require(ProxyAdmin(_proxy).admin() == address(this), "this is not the admin of the proxy");        ProxyAdmin(_proxy).upgradeTo(_newImplementation);        ProxyAdmin(_proxy).changeAdmin(_newProxyAdmin);    }} }
```

It is important to detail the versioning system used to keep track of the various factory versions - each factory is associated with a unique ID. The purpose of this ID is to identify the following properties of the factory and the resulting deployed behaviour contract:

- Epoch - the version number
- Cryptosystem - the crypto system that the note registry is interfacing with
- Asset type - the type of asset that the note registry belongs to i.e. is it convertable, adjustable, various combinations of these

Each of these variables is represented by a `uint8` , which are then packed together into a `uint24` to give the unique factory ID. Epoch number can only ever increase and all newly deployed behaviours must be backwards compatible.

**Note registry manager -** **NoteRegistryManager.sol**

The note registry manager is inherited by ACE. Its responsibilities include:

- Define the methods uses to deploy and upgrade registries
- Define the methods uses to enact state changes sent by the owner of a registry
- Manage the list of factories that are available

An overview of this architecture is provided below:

![img](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LhZjaocaF34Y4jZgGiC%2F-LmzM2WPPAOS4yOuiFKi%2F-LmzPCa66UQW3KHrcquo%2Fimage.png?alt=media&token=572c265c-b657-4e01-aeaf-ad9968786607)

Illustration of the note registry architecture

## **Upgradeability functionality**

The above system of smart contracts can be used to deploy both non-upgradeable and upgradable `zkAssets` . Only ownable `ZkAsset`s are able to be upgraded through this upgrade pattern and in the case where there is no owner, the latest note registry behaviour is deployed.

**Deploying a new non-upgradeable ZkAsset**

1. A user deploys a ZkAsset contract, feeding in constructor arguments `aceAddress, erc20Address, ERC20_SCALING_FACTOR, canAdjustSupply`.
2. The ZkAsset calls ACE, telling it to instantiate a note registry
3. ACE, through the NoteRegistryManager, finds the latest Factory, and tells it to deploy a new Proxy contract, and then to deploy a new Behaviour contract, passing the address of the Proxy contract in its constructor.
4. Once deployed, the Factory transfers ownership of the Behaviour to ACE
5. The Factory returns the address of the new Behaviour contract, and ACE adds to a mapping from address of ZkAsset to NoteRegistry.

**Deploying a new NoteRegistry version**

1. A new Factory.sol is deployed, which has the ability to deploy new NoteRegistryBehaviour contracts, and can manage transferring ownership from itself to an address it received
2. The Owner of ACE sends a Tx associating a unique identifier with the address of the new Factory

**Upgrading a ZkAsset's NoteRegistry**

![img](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LhZjaocaF34Y4jZgGiC%2F-LmzM2WPPAOS4yOuiFKi%2F-LmzPL4iOjSjFv1I3kzn%2Fimage.png?alt=media&token=56e16681-693a-489a-897b-b6f2272a1768)

Overview of the process involved in upgrading a note registry behaviour

1. The Owner of a ZkAsset makes a call to upgrade its NoteRegistry, giving a specific unique id of a particular factory. 
2. The ZkAsset calls ACE, telling it to upgrade its NoteRegistry, and passing it a specific version to use. 
3. ACE finds the NoteRegistry, fetches its associated Proxy address, and finds the relevant factory to call
4. ACE tells the factory to deploy a new Behaviour, passing in the Proxy address it received.
5. The factory deploys the new Behaviour contract
6. Once deployed, the factory transfers ownership to ACE
7. The address of the deployed Behaviour is sent back to ACE, 
8. ACE tells the old Factory to abdicate control over the Proxy contract in favour of the new Factory 

# **Processing a transfer instruction**

Once a proof instruction has been received (either through `ACE` or via a third party that validated a proof through `ACE`, for example a confidential decentralized exchange dApp), it can be processed by calling `ACE.updateNoteRegistry(uint24 _proof, bytes proofOutput, address sender)`.

- If `msg.sender` has not registered a note registry inside `ACE`, the transaction will throw
- If the the proof instruction was **not** sourced from a proof that `ACE` validated, the transaction will throw
- If `validatedProofs[keccak256(abi.encode(_proof, sender, keccak256(proofOutput)))] == false`, the transaction will throw

If the above criteria are satisfied, the instruction is passed to `NoteRegistry`, where the following checks are validated against:

- If any note in `proofOutput.inputNotes` does not hash to a key that does not exist inside `noteRegistry`, the transaction will throw
- If any note in `proofOutput.outputNotes` hashes to a key that *already* exists inside `noteRegistry`, the transaction will throw
- If `proofOutput.publicValue != 0` and the asset is not `mixed`, the transaction will throw

Once these conditions have been satisfied, every note in `proofOutput.inputNotes` is destroyed, and every note in `proofOutput.outputNotes` is created.

Additionally, if `proofOutput.publicValue < 0`, `linkedToken.transferFrom(proofOutput.publicOwner, this, uint256(-proofOutput.publicValue))` is called. If this call fails, the transaction will throw. If `proofOutput.publicValue > 0`, `linkedToken.transfer(proofOutput.publicOwner, uint256(proofOutput.publicValue))` will be called. If this call fails, the transaction will throw.

### **A note on ERC20 token transfers**

For `mixed` assets, if tokens are withdrawn from AZTEC then, from the balancing relationships checked by AZTEC's zero-knowledge proofs, `ACE` will always have a sufficient balance, as the only way to create AZTEC notes is by depositing tokens in the first place.

For `mintable` assets that are also `mixed`, there are additional steps that a digital asset builder must implement. If an AZTEC note is directly minted, and then converted into tokens, `ACE` will not have a sufficient token balance to initiate the transfer.

# **Minting AZTEC notes**

Under certain circumstances, a digital asset owner may wish to directly mint AZTEC notes. One example is a confidential digital loan, where the loan originators create the initial loan register directly in the form of AZTEC notes.

At the creation of a note registry, the registry owner can choose whether their registry is 'mintable' by setting `bool _canAdjustSupply` to `true` in `ACE.createNoteRegistry(address _linkedTokenAddress, uint256 _scalingFactor, bool _canAdjustSupply, bool _canConvert)`.

A 'mintable' note registry has access to the `ACE.mint(uint24 __proof, bytes _proofData, address _proofSender)` function. This function will validate the proof defined by `__proof, _data, _proofSender` (and assert that this is a `MINTABLE` proof) and then immediately enact the produced `bytes proofOutput` at the note registry controlled by `msg.sender`.

A `MINTABLE` proof follows a defined standard. The note registry contains a `bytes32 totalMinted` variable that is the hash of an AZTEC UTXO note that contains the total value of AZTEC notes that been minted by the registry owner.

A `MINTABLE` proof will produce a `proofOutputs` object with two entries.

- The first entry contains the old `confidentialTotalMinted` note and the new `confidentialTotalMinted` value
- The second entry contains a list of notes that are to be minted

If the `confidentialTotalMinted` value does not match the old `confidentialTotalMinted` value in `proofOutputs`, the transaction will revert.

If all checks pass, the relevant AZTEC notes will be added to the note registry.

## **Minting and tokens**

Care should be taken if AZTEC notes are directly minted into an asset that can be converted into ERC20 tokens. It is possible that a conversion is attempted on a note and the token balance of the note registry in question is insufficient. Under these circumstances the transaction will revert. It is the responsibility of the note registry owner to provide `ACE` with sufficient tokens to enable such a transfer, as it falls far outside the remit of the Cryptography Engine to request minting priviledges for any given ERC20 token.

This can be performed via `ACE.supplementTokens(uint256 _value)`, which will cause `ACE` to call `transferFrom` on the relevant ERC20 token, using `msg.sender` both as the transferee and the note registry owner. It is assumed that the private digital asset in question has ERC20 minting priviledges, if the note registry is also mintable.

# **Burning AZTEC notes**

Burning is enacted in an identical fashion to note minting. The total amount of burned AZTEC notes is tracked by a `bytes32 confidentialTotalBurned` variable.

Burn proofs follow a similar pattern - updating the `totalBurned` variable and destroying the specified AZTEC notes.

It should be stressed that only a note registry owner, who has set the relevant permissions on their note registry, can call `ACE.mint` and `ACE.burn`.

If ERC20 tokens have been converted into AZTEC notes, which are subsequently burned, the resulting tokens will be permanently locked inside `ACE` and will be unretrievable. Care should be taken by a note registry owner that this behaviour is desired when they burn notes.

# **Interacting with ACE: zkAsset**

The `zkAsset.sol` contract is an implementation of a confidential token, that follows the [EIP-1724 standard](https://github.com/ethereum/EIPs/issues/1724). It is designed as a template that confidential digital asset builders can follow, to create an AZTEC-compatible asset. All `zkAssets` must follow the following minimum interface:



```
/** * @title IZkAsset * @author AZTEC * @dev An interface defining the ZkAsset standard  * Copyright Spilsbury Holdings Ltd 2019. All rights reserved. **/contract IZkAsset {    event CreateZkAsset(        address indexed aceAddress,        address indexed linkedTokenAddress,        uint256 scalingFactor,        bool indexed _canAdjustSupply,        bool _canConvert    );    event CreateNoteRegistry(uint256 noteRegistryId);    event CreateNote(address indexed owner, bytes32 indexed noteHash, bytes metadata);    event DestroyNote(address indexed owner, bytes32 indexed noteHash, bytes metadata);    event ConvertTokens(address indexed owner, uint256 value);    event RedeemTokens(address indexed owner, uint256 value);    event UpdateNoteMetaData(address indexed owner, bytes32 indexed noteHash, bytes metadata);        function confidentialApprove(        bytes32 _noteHash,        address _spender,        bool _status,        bytes calldata _signature    ) external;    function confidentialTransferFrom(uint24 _proof, bytes calldata _proofOutput) external;        function confidentialTransfer(bytes memory _proofData, bytes memory _signatures) public;}
```

### **Creating a confidential asset**

A `zkAsset` contract must instantiate a note registry inside `ACE` via `ACE.createNoteRegistry`. If the asset is a mixed, the contract address of the linked `ERC20` token must be supplied.

### **Issuing a confidential transaction: confidentialTransfer()**

The primary method of unilateral value transfer occurs via `zkAsset.confidentialTransfer(bytes _proofData, bytes _signatures)`. In this method, the `joinSplit` AZTEC proof is used to enact a value transfer. The beneficiaries of the transaction are defined entirely by the contents of `bytes _proofData`.

Both `ACE.validateProof(data)` and `ACE.updateNoteRegistry(proofOutput)` must be called, with `proofOutput` being extracted from `ACE.validateProof`'s return data.

### **Issuing delegated confidential transactions: confidentialTransferFrom()**

The `confidentialTransferFrom(uint24 __proof, bytes _proofOutput)` method is used to perform a delegated transfer. As opposed to `confidentialTransfer`, `confidentialTransferFrom` can use any proof supported by `ACE` (assuming the `zkAsset` contract accepts this type of proof).

## **Permissioning**

It is the responsibility of the `zkAsset` to perform the required permissioning checks when value transfer occurs. The permissioning mechanism used in a `confidentialTransfer()` call is different to that used for a `confidentialTransferFrom()` call.

The `confidentialTransfer` method takes a set of EIP712 ECDSA `signatures` over each `inputNote` that is involved in the transfer. These are then validated in the method `confidentialTransferInternal()`.

However, this method is not suitable for a delegated transfer calling `confidentialTransferFrom()`. In this case, the note 'owners' may be smart contracts and so unable to create digitial signatures. Therefore, for `confidentialTransferFrom()` to be used, a permission granting function `confidentialApprove()` must be called on every input note that is consumed.

### **confidentialApprove**

The `confidentialApprove(bytes32 _noteHash, address _spender, bool _status, bytes memory _signature)` method gives the `_spender` address permission to use an AZTEC note, whose hash is defined by `_noteHash`, to be used in a zero-knowledge proof.

The `_status` boolean defines whether permission is being given or revoked.

The `_signature` variable defines an ECDSA signature over an EIP712 message. This signature is signed by the `address owner` of the AZTEC note being approved.

If `_signature = bytes(0x00)`, then `msg.sender` is expected to be the `address owner` of the AZTEC note being approved.

This interface is designed to facilitate stealth addresses. For a stealth address, it is unlikely that the address will have any Ethereum funds to pay for gas costs, and a meta-transaction style transaction is required. In this situation, `msg.sender` will not map to the owner of the note and so an ECDSA signatue is used.

For other uses, such as a smart contract or a non-stealth address, a direct transaction sent by the correct `msg.sender` is possible by sending a null signature.

### **Granting note view key access**

AZTEC notes contain a `metaData` field, with a specification as outlined in the note ABI discussion. One of the principal uses of this data field, is to store encrypted viewing keys - to allow note view access to be granted to third parties. The `metaData` of a note is not stored in storage, rather it is emitted as an event along with the successful creation of a note:



```
emit CreateNote(noteOwner, noteHash, metadata);
```

It may be desirable to grant note view key access to parties, beyond those for which an encrypted viewing key was initially provided when the note was created. To facilitate this, the `ZkAssetBase.sol` has an `updateNoteMetaData()` method:



```
/*** @dev Update the metadata of a note that already exists in storage. * @param noteHash - hash of a note, used as a unique identifier for the note* @param metaData - metadata to update the note with*/function updateNoteMetaData(bytes32 noteHash, bytes memory metaData) public {    // Get the note from this assets registry    ( uint8 status, , , address noteOwner ) = ace.getNote(address(this), noteHash);    bytes32 addressID = keccak256(abi.encodePacked(msg.sender, noteHash));    require(        (noteAccess[addressID] >= metaDataTimeLog[noteHash] || noteOwner == msg.sender) && status == 1,        'caller does not have permission to update metaData'    );    // Approve the addresses in the note metaData    approveAddresses(metaData, noteHash);    // Set the metaDataTimeLog to the latest block time    setMetaDataTimeLog(noteHash);    emit UpdateNoteMetaData(noteOwner, noteHash, metaData);}
```

The purpose of this method is to ultimately emit a new event `UpdateNoteMetaData(noteOwner, noteHash, metaData`with updated `metaData`.The  `metaData` is the updated `metaData` which contains the IES encrypted  viewing keys for all parties that are to be granted note view access. 

**Permissioning**

The permissioning of this function is of critical importance - as being able to call this function allows note view access to be given to an arbitrary address. To this end, there is a `require()` statement which enforces that one of the two valid groups of users are calling this function. It will revert if not.

The first category of permissioned caller is the `noteOwner` . A note owner should have complete agency over to whom they grant view key access to their note.  

The second category of permissioned callers are those Ethereum addresses that are being granted view key access in the `metaData`. These addresses are explicitly  stated in the `approvedAddresses` section of `metaData`.  

To enact this check, an `addressID` is first calculated - the `keccak256` hash of `msg.sender` and the hash of the note in question. We then make use of the `noteAccess`  mapping declared in the `ZkAsset`:



```
mapping(bytes32 => uint256) public noteAccess;
```

This is a mapping of `addressIDs` to a `uint256` , where the `uint256` is the `block.timestamp` of the block in which the particular address was originally granted approval via `approveAddresses()`.

We then compare  `noteAccess[addressID]` to the value stored in `metaDataTimeLog[noteHash]`. `metaDataTimeLog` is a second mapping of the form:



```
mapping(bytes32 => uint256) public metaDataTimeLog;
```

It is a mapping of  `noteHash` to the `block.timestamp` when the method `setMetaDataTimeLog()` was last called. This mapping is used to keep track of when the `metaData` for a particular note was last updated. 

By checking that `noteAccess[addressID] >= metaDataTimeLog[noteHash]` we satisfy two conditions. Firstly, that `msg.sender` is an address which has been previously approved view access in the `metaData` of a note. Secondly, that `msg.sender` still has view access to a note and has not since been revoked (by `metaData` being updated and not including this Ethereum address as an approved address).  

## **setProofs()**

It should be noted that `ZkAssets` which are ownable and inherit from the `ZkAssetOwnable.sol` contract have a concept of `supporting proofs'. The owner is able to choose which proofs the ZkAsset supports and can interact with. 

This is achieved through the `setProofs()` function, restricted to `onlyOwner`:



```
function setProofs(    uint8 _epoch,    uint256 _proofs) external onlyOwner {    proofs[_epoch] = _proofs;}
```

In order for a ZkAsset to be able to listen to and interact with a particular proof, it must be first registered with this function. 

By default, all `ZkAssetOwnable` contracts have the basic unilateral transfer `joinSplit` proof enabled in their constructor. 

## **Types of ZkAssets**

There are various types of `zkAssets`, which are differentiated based on the flags `canAdjustSupply` ,`canConvert` and whether or not the asset is ownable.

`canAdjustSupply` determines whether the asset is able to `mint` or `burn` whilst `canConvert` determines whether public ERC20 tokens can be converted into AZTEC notes and vice versa. These flags are not exposed to the user instantiating the asset and are instead hardcoded into the constructor of the asset or derived from existing properties. `canAdjustSupply` is hardcoded into the constructor of the relevant asset, whilst `canConvert` is derived from whether a `linkedTokenAddress` was set in the asset's constructor.

These flags give rise to the contracts whose properties are summarised in the below table:

| Contract          | canAdjustSupply | canConvert | Ownable |
| ----------------- | --------------- | ---------- | ------- |
| ZkAsset           | N               | P          | N       |
| ZkAssetAdjustable | Y               | P          | Y       |
| ZkAssetMintable   | Y               | P          | Y       |
| ZkAssetBurnable   | Y               | P          | Y       |
| ZkAssetOwnable    | N               | P          | Y       |

where `Y` is yes, `N` no and `P` is possible (it is at the discretion of the instantiator). `ZkAssetMintable` is only able to mint, `ZkAssetBurnable` is only able to burn, whilst `ZkAssetAdjustable` is able to both `mint` and `burn`.

# **Proof verification contracts**

## **JoinSplit.sol**

The `JoinSplit` contract validates the AZTEC join-split proof. It takes a series of `inputNotes` , to be removed from a note registry, and a series of `outputNotes` to be added to the note registry. In addition, an integer `publicValue` can be supplied - this specifies the number of ERC20 tokens to be converted into AZTEC note form or from AZTEC note form. 

The ABI of `bytes data` is the following:

| offset                                    | length        | name               | type      | description                                      |
| ----------------------------------------- | ------------- | ------------------ | --------- | ------------------------------------------------ |
| 0x00                                      | 0x20          | m                  | uint256   | number of input notes                            |
| 0x20                                      | 0x20          | challenge          | uint256   | zero-knowledge proof challenge                   |
| 0x40                                      | 0x20          | publicOwner        | address   | beneficiary of public tokens being used in proof |
| 0x60                                      | 0x20          | notesOffset        | uint256   | relative offset to `uint[6][] notes`             |
| 0x80                                      | 0x20          | inputOwnerOffset   | uint256   | relative offset to `address[] inputOwners`       |
| 0xa0                                      | 0x20          | outputOwnersOffset | uint256   | relative offset to `address[] outputOwners`      |
| 0xc0                                      | 0x20          | notemetaDataOffset | uint256   | relative offset to `bytes[] notemetaData`        |
| 0xe0                                      | L_notes       | notes              | uint[6][] | zero-knowledge proof data for notes              |
| 0xe0 + L_notes                            | L_inputOwners | inputOwners        | address[] | address of input note owners                     |
| 0xe0 + L_notes + L_inputOwners            | L_owners      | outputOwners       | address[] | address of output note owners                    |
| 0xe0 + L_notes + L_inputOwners + L_owners | L_metaData    | notemetaData       | bytes[]   | note metaData, used for event broadcasts         |

`**uint[6][] notes**` contains the zero-knowledge proof data required for the set of input and output UTXO notes used inside `JoinSplit`. The ABI encoding is as follows:

| offset | length | name   | type    | description                             |
| ------ | ------ | ------ | ------- | --------------------------------------- |
| 0x00   | 0x20   | kBar   | uint256 | blinded form of the note's value        |
| 0x20   | 0x20   | aBar   | uint256 | blinded form of the note's viewing key  |
| 0x40   | 0x20   | gammaX | uint256 | x-coordinate of UTXO note point 'gamma' |
| 0x60   | 0x20   | gammaY | uint256 | y-coordinate of UTXO note point 'gamma' |
| 0x80   | 0x20   | sigmaX | uint256 | x-coordinate of UTXO note point 'sigma' |
| 0xa0   | 0x20   | sigmaY | uint256 | y-coordinate of UTXO note point 'sigma' |

The amount of public 'value' being used in the join-split proof, `publicValue`, is defined as the `kBar` value of the last entry in the `uint[6][] notes` array. This value is traditionally empty (the last note does not have a `kBar` parameter) and the space is re-used to house `publicValue`.

# **Swap.sol**

The `Swap` contract validates a zero-knowledge proof that defines an exchange of notes between two counter-parties, an order *maker* and an order *taker*.

The proof involves 4 AZTEC UTXO notes, and proves the following:

1. `note[0].value = note[2].value`
2. `note[1].value = note[3].value`

In this context, the notes are interpreted as the following:

- `note[0]`: order maker bid note
- `note[1]`: order maker ask note
- `note[2]`: order taker ask note
- `note[3]`: order taker bid note

This proof does not perform any authorization logic - it is the responsibility of the asset smart contracts involved in a trade to perform required permissioning checks.

The ABI of `bytes data` is identical to the ABI-encoding of the `JoinSplit.sol` verification smart contract. The `Swap` contract will throw if `n != 4` or `m != 2`.

Once a proof has been successfully validated, `bytes proofOutputs` will contain two entries, with the following note assignments:

- `proofOutputs[0].inputNotes = [note[0]]`
- `proofOutputs[0].outputNotes = [note[2]]`
- `proofOutputs[1].inputNotes = [note[3]]`
- `proofOutputs[1].outputNotes = [note[1]]`

i.e. Both the order maker and order taker are destroying their *bid* notes in exchange for creating their *ask* notes.

Each entry inside `proofOutputs` defines a balancing relationship. If `proofOutputs[0]` and `proofOutputs[1]` are sent to different ZKAsset smart contracts, this proof can be used to define a bilateral swap of AZTEC notes, between two counter-parties and across two asset classes.

The ABI of `bytes data` is the following:

| offset                                    | length        | name               | type      | description                                 |
| ----------------------------------------- | ------------- | ------------------ | --------- | ------------------------------------------- |
| 0x00                                      | 0x20          | challenge          | uint256   | zero-knowledge proof challenge              |
| 0x20                                      | 0x20          | notesOffset        | uint256   | relative offset to `uint[6][] notes`        |
| 0x40                                      | 0x20          | inputOwnersOffset  | uint256   | relative offset to `address[] inputOwners`  |
| 0x60                                      | 0x20          | outputOwnersOffset | uint256   | relative offset to `address[] outputOwners` |
| 0x80                                      | 0x20          | notemetaDataOffset | uint256   | relative offset to `bytes[] notemetaData`   |
| 0xa0                                      | L_notes       | notes              | uint[6][] | zero-knowledge proof data for notes         |
| 0xe0 + L_notes                            | L_inputOwners | inputOwners        | address[] | address of input note owners                |
| 0xa0 + L_notes + L_inputOwners            | L_owners      | outputOwners       | address[] | address of output note owners               |
| 0xa0 + L_notes + L_inputOwners + L_owners | L_metaData    | notemetaData       | bytes[]   | note metaData, used for event broadcasts    |

# **Dividend.sol**

The `Dividend` proof validates that an AZTEC UTXO note is equal to a public percentage of a second AZTEC UTXO note. This proof is belongs to the `UTILITY` category, as in isolation it does not describe a balancing relationship.

The `Dividend` proof involves three AZTEC notes and two scalars `za, zb`. The scalars `za, zb` define a ratio and the proof proves the following:

- `note[1].value * za = note[2].value * zb + note[3].value`

In this context, `note[3]` is a **residual** note. The residual note is required in order to accommodate rounding errors. Consider the scenario of a user computing an interest rate payment for values `za, zb` that are fixed by a smart contract.

In this context, `zb > za` and `note[1].value` is the **source** note. The **target** note is `note[2]`. The owner of `note[1]` wishes to prove that `note[2].value = note[1].value * (za / zb)`, or as close as they can manage given the confines of integer arithmetic.

As the value of `note[1]` is unknown to all but the note owner, they have a free choice in choosing values for `note[2]` and `note[3]`. However in order to maximize the value of `note[2]`, it is in the note owner's interest to minimize `note[3].value`.

It is worth highlighting the fact that the `Dividend` proof, like all AZTEC proofs, it is impossible to present a satisfying proof if any notes have negative value.

When utilizing the `Dividend` proof inside a smart contract, care should be taken to determine whether the proof is being utilized to validate a *debit* computation or a *credit* computation, as it important to ensure that the sender of the proof is incentivized to minimize the value of `note[3]` (not to maximize it).

In a *debit* computation, the note owner is proving that an AZTEC note correctly represents a transfer of value *from* the note owner. For example, a loan repayment. In this context, it is in the note owner's interest to *minimize* the value of the **target** note. It is therefore important to set `note[1]` as the **target** note and `note[2]` as the **source** note. Under this formulism, increasing `note[3].value` will also increase the value of the target note. The note owner, therefore, is incentivized to ensure that `note[3].value` is as small as possible. In this situation, malicious behaviour is prevented because of the AZTEC range proof: `note[3].value` cannot be negative.

In a *credit* computation, the incentives are reversed and it is neccessary to set `note[1]` as the **source** note, and `note[2]` as the **target** note.

Similarly to `Swap`, this proof performs no permissioning checks. It is the responsibliity of the smart contract invoking `Dividend` to imbue meaning into the notes being used in the proof, and to ensure that the correct permissioning flows have been observed.

The ABI of `bytes data` is the following:

| offset                                         | length         | name               | type      | description                                 |
| ---------------------------------------------- | -------------- | ------------------ | --------- | ------------------------------------------- |
| 0x00                                           | 0x20           | challenge          | uint256   | zero-knowledge proof challenge              |
| 0x20                                           | 0x20           | za                 | uint256   | dividend computation scalar                 |
| 0x40                                           | 0x20           | zb                 | uint256   | dividend computation scalar                 |
| 0x60                                           | 0x20           | notesOffset        | uint256   | relative offset to `uint[6][] notes`        |
| 0x80                                           | 0x20           | inputOwnersOffset  | uint256   | relative offset to `address[] inputOwners`  |
| 0xa0                                           | 0x20           | outputOwnersOffset | uint256   | relative offset to `address[] outputOwners` |
| 0xc0                                           | 0x20           | notemetaDataOffset | uint256   | relative offset to `bytes[] notemetaData`   |
| 0xe0                                           | L_notes        | notes              | uint[6][] | zero-knowledge proof data for notes         |
| 0xe0 + L_notes                                 | L_inputOwners  | inputOwners        | address[] | address of input note owners                |
| 0xe0 + L_notes + L_inputOwners                 | L_outputOwners | outputOwners       | address[] | address of output note owners               |
| 0xe0 + L_notes + L_inputOwers + L_outputOwners | L_metaData     | notemetaData       | bytes[]   | note metaData, used for event broadcasts    |

# **PublicRange.sol**

The `PublicRange` proof validates in zero-knowledge that the value of one AZTEC note is greater than or equal to, or less than or equal to a public integer. It belongs to the `UTILITY` proof category.

The proof involves three quantities:

- `originalNote` = note who's inequality relation we seek to prove
- `publicComparison` = public integer, which the `originalNote` is being compared against
- `utilityNote` = helper note, used to construct an appropriate proof relation

These quantities are then used to construct a proof relation: `originalNoteValue = publicComparison + utilityNoteValue`.

In addition, a boolean `isGreaterOrEqual` is supplied to the proof. This is used to control whether the proof is for a greater than or equal to, or less than or equal to scenario.

If `isGreaterOrEqual` is true, then it is a greater than or equal proof and `originalNoteValue >= publicComparison`. If `false`, it is a less than or equal to proof that `originalNoteValue <= publicComparison`.

The ABI of `bytes data` is the following:

| offset                                         | length         | name               | type      | description                                 |
| ---------------------------------------------- | -------------- | ------------------ | --------- | ------------------------------------------- |
| 0x00                                           | 0x20           | challenge          | uint256   | zero-knowledge proof challenge              |
| 0x20                                           | 0x20           | publicComparison   | uint256   | public integer note value compared against  |
| 0x40                                           | 0x20           | notesOffset        | uint256   | relative offset to `uint[6][] notes`        |
| 0x60                                           | 0x20           | inputOwnersOffset  | uint256   | relative offset to `address[] inputOwners`  |
| 0x80                                           | 0x20           | outputOwnersOffset | uint256   | relative offset to `address[] outputOwners` |
| 0xa0                                           | 0x20           | notemetaDataOffset | uint256   | relative offset to `bytes[] notemetaData`   |
| 0xc0                                           | L_notes        | notes              | uint[6][] | zero-knowledge proof data for notes         |
| 0xc0 + L_notes                                 | L_inputOwners  | inputOwners        | address[] | address of input note owners                |
| 0xc0 + L_notes + L_inputOwners                 | L_outputOwners | outputOwners       | address[] | address of output note owners               |
| 0xc0 + L_notes + L_inputOwers + L_outputOwners | L_metaData     | notemetaData       | bytes[]   | note metaData, used for event broadcasts    |

# **PrivateRange.sol**

The `PrivateRange` proof validates in zero-knowledge that the value of one AZTEC note is greater than or less than the value of a second AZTEC note. It belongs to the `UTILITY` proof category as no true balancing relationship is satisfied.

The proof involves three AZTEC notes:

- `originalNote` = note who's inequality relation we seek to prove
- `comparisonNote` = note being compared against
- `utilityNote` = helper note, used to construct an appropriate proof relation

These notes are used to construct the following proof relation: `originalNote.value = comparisonNote.value + utilityNote.value`

If this is satisfied, it means that `originalNote.value > comparisonNote.value`. Note, that the range proof means it is not possible to construct notes with a value less than zero. In order to construct a less than proof (i.e. `originalNote.value < comparisonNote.value`), the user must change the input order to show that `comparisonNote.value > originalNote.value`

The `proofOutputs` object returned contains one `proofOutput` object. The `inputNotes` corresponds to `originalNote` and `comparisonNote`, with the `outputNotes` corresponding to `utilityNote`. The output note has no physical meaning and is used to construct a mathematically appropriate proof relation.

The ABI of `bytes data` is the following:

| offset                                         | length         | name               | type      | description                                 |
| ---------------------------------------------- | -------------- | ------------------ | --------- | ------------------------------------------- |
| 0x00                                           | 0x20           | challenge          | uint256   | zero-knowledge proof challenge              |
| 0x20                                           | 0x20           | notesOffset        | uint256   | relative offset to `uint[6][] notes`        |
| 0x40                                           | 0x20           | inputOwnersOffset  | uint256   | relative offset to `address[] inputOwners`  |
| 0x60                                           | 0x20           | outputOwnersOffset | uint256   | relative offset to `address[] outputOwners` |
| 0x80                                           | 0x20           | notemetaDataOffset | uint256   | relative offset to `bytes[] notemetaData`   |
| 0xa0                                           | L_notes        | notes              | uint[6][] | zero-knowledge proof data for notes         |
| 0xa0 + L_notes                                 | L_inputOwners  | inputOwners        | address[] | address of input note owners                |
| 0xa0 + L_notes + L_inputOwners                 | L_outputOwners | outputOwners       | address[] | address of output note owners               |
| 0xa0 + L_notes + L_inputOwers + L_outputOwners | L_metaData     | notemetaData       | bytes[]   | note metaData, used for event broadcasts    |

# **JoinSplitFluid.sol**

The `JoinSplitFluid` contract enables proofs to be validated for the direct minting or burning of AZTEC notes, if`Registry.adjustSupply = true`. 

Mint and burn proofs are both special cases of the `joinSplit` proof - they are the `joinSplit` proof but they have a restricted, specified set of inputs. This validator contract is used to validate both `mint` and `burn` proofs. 

In the `mint` proof, notes are being directly created and added to a note registry, whilst in the `burn` proof notes are being removed from a note registry. In terms of notes, the `joinSplitFluid` validator takes three inputs:

- `currentCounterNote` - note that describes the existing total minted/burned value in this note registry
- `newCounterNote` - note that describes the new total minted/burned value in this note registry once the proof has been validated and the results enacted
- `minted/burned notes` - the notes that are to be minted and created in the note registry, or burned and removed from the note registry

The `minted/burned` notes are the notes being added or removed from the note registry. The purpose of the counter notes is to keep track of the total value that has been minted or burned in this note registry - this informatiom may be for accounting purposes, or an audit. 

It is important to note that for a given note registry, only the registry owner can call `ACE.mint` or `ACE.burn` . Only the registry owner must know the value of the total notes - hashes of these notes are represented by the registry variables `confidentialTotalMinted` and `confidentialTotalBurned.`

The ABI-encoding of `bytes data` is identical to that of an AZTEC `JoinSplit` transaction. There is the added restriction that `m = 1` and `n >= 2`.

When encoding `bytes proofOutputs`, the following mapping between input `notes` and notes in `proofOutputs` is used:

- `proofOutputs.length = 2`
- `proofOutputs[0].inputNotes = [currentCounterNote]`
- `proofOutputs[0].outputNotes = [newCounterNote]`
- `proofOutputs[0].publicOwner = address(0)`
- `proofOutputs[0].publicValue = 0`
- `proofOutputs[1].inputNotes = []`
- `proofOutputs[1].outputNotes = [minted/burned notes]`

The ABI of `bytes data` is the following:

| offset                                         | length         | name               | type      | description                                 |
| ---------------------------------------------- | -------------- | ------------------ | --------- | ------------------------------------------- |
| 0x00                                           | 0x20           | challenge          | uint256   | zero-knowledge proof challenge              |
| 0x20                                           | 0x20           | notesOffset        | uint256   | relative offset to `uint[6][] notes`        |
| 0x40                                           | 0x20           | inputOwnersOffset  | uint256   | relative offset to `address[] inputOwners`  |
| 0x60                                           | 0x20           | outputOwnersOffset | uint256   | relative offset to `address[] outputOwners` |
| 0x80                                           | 0x20           | notemetaDataOffset | uint256   | relative offset to `bytes[] notemetaData`   |
| 0xa0                                           | L_notes        | notes              | uint[6][] | zero-knowledge proof data for notes         |
| 0xa0 + L_notes                                 | L_inputOwners  | inputOwners        | address[] | address of input note owners                |
| 0xa0 + L_notes + L_inputOwners                 | L_outputOwners | outputOwners       | address[] | address of output note owners               |
| 0xa0 + L_notes + L_inputOwers + L_outputOwners | L_metaData     | notemetaData       | bytes[]   | note metaData, used for event broadcasts    |

# **Specification of Utility libraries**

Due to the complex ABI-encodings of AZTEC proofs, it is neccessary to define utility libraries that abstract away this complexity from a digital asset builder.

## **NoteUtils.sol**

The `NoteUtils` library provides helper methods that enable data to be extracted from `bytes memory proofOutputs`.

### **`NoteUtils.getLength(bytes memory proofOutputsOrNotes) internal pure returns (uint256 length)`**

When provided with an AZTEC ABI-encoded array (any one of `bytes memory proofOutputs, bytes memory inputNotes, bytes memory outputNotes`), this method will return the number of entries.

### **`NoteUtils.get(bytes memory proofOutputsOrNotes, uint256 i) internal pure returns (bytes memory out)`**

This method will return the `i`'th entry of an AZTEC ABI-encoded array. If `i` is an invalid index an error will be thrown.

### **`NoteUtils.extractProofOutput(bytes memory proofOutput) internal pure returns (bytes memory inputNotes, bytes memory outputNotes, address publicOwner, int256 publicValue)`**

This method will extract the constituent members of `bytes proofOutput`.

### **`NoteUtils.extractNote(bytes memory note) internal pure returns (address owner, bytes32 noteHash, bytes memory metaData)`**

This method will extract the constituent members of an AZTEC ABI-encoded note. Such as the notes contained inside `proofOutput.inputNotes` and `proofOutput.outputNotes`.

### **`NoteUtils.getNoteType(bytes memory note) internal pure returns (uint256 noteType)`**

Extracting the 'type' of a note is provided as a separate method, as this is a rare requirement and its including inside `NoteUtils.extractNote` would bloat the number of stack variables required by the method.

There are in addition the following custom utilities libraries:

- `ProofUtils.sol`
- `LibEIP712.sol`
- `VersioningUtils.sol`

# **Appendix**

## **A: Preventing collisions and front-running**

For any AZTEC verification smart contract, the underlying zero-knowledge protocol must have a formal proof describing the protocol's completeness, soundness and honest-verifier zero-knowledge properties.

In addition to this, and faithfully implementing the logic of the protocol inside a smart contract, steps must be undertaken to prevent 'proof collision', where a `bytes proofOutput` instruction from a proof has an identical structure to a `bytes proofOutput` instruction from a different smart contract verifier. This is done by integrating the `uint24 _proof` variable associated with that specific verification smart contract into the `uint256 challenge` variable contained in each `bytes proofOutput` entry.

Secondly, the front-running of proofs must be prevented. This is the act of taking a valid zero-knowledge proof that is inside the transaction pool but not yet mined, and integrating the proof into a malicious transaction for some purpose that is different to that of the transaction sender. This is achieved by integrating the message sender into challenge variable - it will not be possible for a malicious actor to modify such a proof to create a valid proof of their own construction, unless they know the secret witnesses used in the proof.

Getting `msg.sender` into the verification contract is done by passing through this variable as an input argument from the contract that is calling `ACE.sol`. If this is not done correctly, the asset in question is susceptible to front-running. This does not expose any security risk for the protocol, as assets that correctly use ACE are not affected by assets that incorrectly implement the protocol.

## **B - Interest streaming via AZTEC notes**

Consider a contract that accepts a DAI note (let's call it the origination note), and issues confidential Loan notes in exchange, where the sum of the values of the loan notes is equal to the sum of the values of the origination note (this is enforced).

When a deposit of confidential DAI is supplied to the contract in the form of an interest payment (call it an interest note), a ratio is defined between the value of the interest note and the origination note.

The AZTEC Cryptography Engine supports a zero-knowledge proof that allows loan 'note' holders to stream value out of the interest note. Effectively printing zkDAI notes whose value is defined by the above ratio and the absolute value of their loan note. In exchange, the interest note is destroyed.

What is important to highlight in this exchange, is that the zk-DAI contract is not having to make any assumptions about the zk-Loan contract, or trust in the correctness of the zk-Loan contract's logic.

The zero-knowledge proofs in ACE enable the above exchange to occur with a gaurantee that there is no double spending. The above mechanism cannot be used to 'print' zk-DAI notes whose sum is greater than the interest note. `NoteRegistry` and `ACE` only validate the mathematical correctness of the transaction - whether the loan notes (and resulting interest payments) are correctly distrubted according to the semantics of the loan's protocol is not relevant to ensure that there is no double spending.

# **Glossary**

| term                   | description                                                  |
| ---------------------- | ------------------------------------------------------------ |
| balancing relationship | a instance of AZTEC note creation / destruction, where the sum of the values of the created notes is equal to the sum of the values of the destroyed notes |
| mixed asset            | a zero-knowledge AZTEC asset that both has a private representation (via AZTEC notes) and a public representation (via ERC20-like tokens) |
| private asset          | a zero-knowledge AZTEC asset where ownership is defined entirely through AZTEC notes and there is no linked ERC20 token. Such assets must directly create AZTEC notes via `confidentialMint` instructions |

Link to our specification on [Github](https://github.com/AztecProtocol/specification). 

# Overview

Huff is designed for developing highly optimized algorithms where direct manipulation of the program's bytecode is preferred.

## **Huff is a domain-specific language created for the purposes of writing highly optimized Ethereum Virtual Machine program code and, ultimately, smart contracts.**

Huff enables the construction of EVM assembly macros - blocks of bytecode that can be rigorously tested and evaluated. Macros can themselves be composed of Huff macros.

Huff doesn't hide the workings of the EVM behind syntactic sugar. In fact, Huff doesn't hide anything at all. Huff does not have variables, instead directly exposing the EVM's program stack to the developer to be directly manipulated.

Huff supports a form of templating - Huff macros can accept template parameters, which in turn are Huff macros. This allows for customizable macros that are ideal for loop unrolling.

Huff algorithms can be broken down into their constituent macros and rigorously ested without having to split the algorithm into functions and invoke jump instructions.

# **Additional resources** 

If you would like to learn more about Huff, please refer to our Github [repo](https://github.com/AztecProtocol/huff) or  Zac's series of articles on [Medium](https://medium.com/aztec-protocol/from-zero-to-nowhere-smart-contract-programming-in-huff-1-2-ba2b6de7fa83).

# Weierstrudel

## **Weierstrudel makes zero-knowledge cryptosystems that utilize the bn254 curve, such as the AZTEC protocol substantially cheaper.**

`weierstrudel` is a highly optimized smart contract that performs elliptic curve scalar multiplication on the short Weierstrass 254-bit Barreto-Naehrig curve, formerly used by ZCash and currently available as a precompile smart-contract in the Ethereum protocol. 

The current gas schedule for Ethereum's scalar multiplication precompile smart contract is `40,000` gas. When multiplying more than one point, weierstrudel is **substantially more efficient than the precompile contract** (see [Benchmarks](https://github.com/AztecProtocol/weierstrudel#benchmarks)).

# **Huff**

weierstrudel is written entirely in [Huff](https://github.com/AztecProtocol/huff), a low-level domain-specific language that compiles to Ethereum Virtual Machine opcodes. In addition, the following techniques are used to minimize gas costs:

- Using the GLV technique to exploit a curve endomorphism and reduce the number of 'point doubling' operations in half.
- Using Shamir's trick to combine multiple scalar multiplications into a single algorithm, fixing the number of 'point doubling' operations to ~127
- Using Windowed-Non-Adjacent-Form representations for scalar multipliers, reducing the number of 'point addition' operations to ~50 per point
- Using the difference between the bn254 curve's 254-bit field modulus and the EVM's 256 word size to defer modular reductions until absolutely neccessary

`weierstrudel` makes extensive use of bit-shift opcodes and is only compatible with Ethereum once the Constantinople hard-fork has been activated.

# **Additional resources**

If you would like to learn more about Weierstrudel, please refer to our Github [repo](https://github.com/AztecProtocol/weierstrudel) or  Zac's Medium [article](https://medium.com/aztec-protocol/huffing-for-crypto-with-weierstrudel-9c9568c06901).