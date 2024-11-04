# Learn-Ethereum-Network-Administrator
>[!NOTE]
> This is a note taken during the exploration of **Ethereum Network Administrator [ENA]**

## Need for Building Customizable Ethereum Networks
Private Ethereum networks, or customizable Ethereum networks, have various uses in the blockchain ecosystem:

1. Testing and Development: Developers use private networks to test and develop smart contracts and applications without using real Ether or impacting the public mainnet.

2. Privacy: Private networks can keep transactions and contracts private, unlike public blockchains.

3. Scalability: Private networks can process transactions more quickly and cheaply than the congested Ethereum mainnet.

4. Control: Users can define the blockchain’s rules, making them crucial for permissioned blockchains.

5. Interoperability and Integration: Private networks can be built to cater to an organization’s existing IT systems.

6. Learning and Education: Creating a private Ethereum network can be a great way to learn blockchain development in a low-risk environment.

It's important to note that private networks do not offer the same level of security, decentralization, or robustness as the public Ethereum network. The appropriate solution should be chosen based on the specific needs and trade-offs of a given project or organization.

## Layer 1 and Layer 2 Solutions

### Ethereum-Compatible Layer 1 Chains

Networks like Binance Smart Chain (BSC), Tron, Celo, Avalanche, and Genesis have forked or re-engineered versions of the Ethereum blockchain to create their own standalone networks, often referred to as Layer 1 chains. These chains adapt Ethereum's smart contracts and decentralized applications to their specific needs, tweaking parameters for speed, decentralization, or security. They are EVM-compatible, allowing developers to deploy applications using the same codebase as Ethereum.

### Layer 2 Chains and Scaling Solutions

Layer 2 chains like Polygon, xDai, Optimism, Arbitrum, and StarkNet are built on top of Ethereum to improve scalability, enabling faster and cheaper transactions while maintaining the security of the Ethereum network.

## Ethereum Enterprise Alliance (EEA)
The Ethereum Enterprise Alliance (EEA) was formed to empower organizations to embrace the Ethereum blockchain for their specific enterprise requirements. Leveraging the native features of Ethereum, enterprises can streamline their business operations, enhance security and auditability, and foster improvements in transparency throughout their processes.

## Ethereum Client

An Ethereum client is vital software that connects to create the Ethereum network. After "The Merge" upgrade, Ethereum consists of the execution layer (EL) and the consensus layer (CL), each operated by distinct client software. The execution client processes transactions in the Ethereum Virtual Machine (EVM), while the consensus client implements the proof-of-stake consensus algorithm. Examples of execution clients include Geth, Nethermind, Hyperledger Besu, and Erigon, while examples of consensus clients include Prysm, Lighthouse, Teku, Nimbus, and Lodestar. These clients enable the seamless operation of the Ethereum blockchain.

These clients encompass a range of essential components, including:

1. Execution Environment: The Ethereum client provides an execution environment for processing transactions within the blockchain, ensuring that smart contracts and dApps function as intended.

2. Storage: Ethereum clients have built-in storage capabilities to persistently store data relevant to transaction execution, ensuring the integrity and continuity of the blockchain network.

3. Peer-to-Peer Network: Peer-to-peer (P2P) networking is crucial for Ethereum clients as it enables communication and synchronization with other network nodes. P2P networking enhances decentralization and consensus mechanisms by sharing information and collectively validating transactions.

4. APIs for Application Developers: Ethereum clients provide APIs for developers to interact with the blockchain, enabling decentralized app development, blockchain data querying, and transaction submission.

An Ethereum client is the software backbone of the Ethereum blockchain, enabling machines to connect, execute transactions, store data, and support decentralized application development.


### Hyperledger Besu

Hyperledger Besu is an Ethereum client under Hyperledger Foundation’s projects. It serves as a collaborative platform for open-source blockchain projects and associated tools, aiming to advance the application and understanding of blockchain across different sectors.

Besu not only serves public Ethereum networks as an Execution client but is also tailored to fit private permissioned ones. Its unique feature is its adaptable EVM (Ethereum Virtual Machine) implementation

Hyperledger Besu offers compatibility with 
1. **Proof of Work (PoW)** 
2. **Proof of Authority (PoA)**,This includes IBFT 2.0 (Istanbul BFT), QBFT (Quorum Byzantine Fault Tolerance), and Clique varients. PoA algorithms rely on a selected group of approved validators who take turns creating blocks and securing the network. This approach ensures high transaction throughput, low latency, and efficient network governance, making it well-suited for consortium-based blockchain networks.
3. Hyperledger Besu offers comprehensive permissioning schemes designed explicitly for use in consortium environments. These permissioning mechanisms allow organizations to control access, define roles and responsibilities, and establish governance rules within the network. Hyperledger Besu facilitates secure collaboration and fosters trust among consortium members by providing granular control over participants’ actions and data visibility. Now that we’ve covered the theoretical aspects let’s explore the practical side of creating customized Ethereum networks.

## Setting Up Single Node Private Network

> [!NOTE]  
> ### Ethash Consensus Algorithm: 
> Ethash was Ethereum's proof-of-work mining algorithm. For more details visit this [link](https://ethereum.org/en/developers/docs/consensus-mechanisms/pow/mining/mining-algorithms/ethash/).

1. Make sure perquisite are meet. 
2. Create a configuration file. 
3. Start the Node.
4. Interaction with the Node using JSON-RPC calls or command-line interfaces to send transactions, deploy smart contracts, or request blockchain data.

