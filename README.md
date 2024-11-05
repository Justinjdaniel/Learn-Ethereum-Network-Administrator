# Learn-Ethereum-Network-Administrator

> [!TIP]
> Offical Besu [documentation](https://besu.hyperledger.org/) 

> [!NOTE]
> This is a note taken during the exploration of **Ethereum Network Administrator [ENA]** (self paced learning).

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

> [!NOTE]
> For more information visit offical [wiki](https://lf-hyperledger.atlassian.net/wiki/spaces/BESU/overview).

Hyperledger Besu is an Ethereum client under Hyperledger Foundation’s projects. It serves as a collaborative platform for open-source blockchain projects and associated tools, aiming to advance the application and understanding of blockchain across different sectors.

Besu not only serves public Ethereum networks as an Execution client but is also tailored to fit private permissioned ones. Its unique feature is its adaptable EVM (Ethereum Virtual Machine) implementation

Hyperledger Besu offers compatibility with 
1. **Proof of Work (PoW)** 
2. **Proof of Authority (PoA)**,This includes IBFT 2.0 (Istanbul BFT), QBFT (Quorum Byzantine Fault Tolerance), and Clique varients. PoA algorithms rely on a selected group of approved validators who take turns creating blocks and securing the network. This approach ensures high transaction throughput, low latency, and efficient network governance, making it well-suited for consortium-based blockchain networks.
3. **Proof of Stake**: Alongside a consensus client, Besu can be used to connect to and participate in Ethereum Mainnet proof-of-stake. 
4. Hyperledger Besu offers comprehensive permissioning schemes designed explicitly for use in consortium environments. These permissioning mechanisms allow organizations to control access, define roles and responsibilities, and establish governance rules within the network. Hyperledger Besu facilitates secure collaboration and fosters trust among consortium members by providing granular control over participants’ actions and data visibility. Now that we’ve covered the theoretical aspects let’s explore the practical side of creating customized Ethereum networks.

## Installing Hyperledger Besu

To install Hyperledger Besu, ensure your system has Java installed since Besu is Java-based. This tutorial is tailored for Ubuntu systems.

1. ### Install Java:

    ```sh
    sudo apt update
    sudo apt install openjdk-21-jdk
    ```

2. ### Verify the installation:

    ```sh
    java --version
    ```

3. ### Download Hyperledger Besu:
    Visit [Hyperledger Besu Releases](https://github.com/hyperledger/besu/releases) and download the latest version. For this guide, we'll use Hyperledger Besu 23.4.4.

4. ### Set Up Besu:

    Create a folder named besu and navigate into it:

    ```sh
    mkdir besu
    cd besu
    ```

    Extract the downloaded ZIP file into the besu folder. Then, verify the Besu version:

    ```sh
    ./bin/besu --version
    ```
5. ### Set Environment Variable:

    To access Besu globally, set the environment variable. Copy the path to the bin folder, then open the environment file:

    ```sh
    sudo nano /etc/environment
    ```
    Append the copied path at the end of the current data, separating values with a colon `:`.

    Use `Ctrl+O` to save and `Ctrl+X` to exit the editor.

6. ### Apply Changes:

    Restart the system to reflect the updates. Verify the changes with:

    ```sh
    besu
    ```


## Setting Up Single Node Private Ethereum Network

> [!TIP]
> Check out the offical tutorials [Private Network QuickStart](https://besu.hyperledger.org/stable/private-networks/tutorials/quickstart)

> [!NOTE]  
> ### Ethash Consensus Algorithm: 
> Ethash was Ethereum's proof-of-work mining algorithm. For more details visit this [link](https://ethereum.org/en/developers/docs/consensus-mechanisms/pow/mining/mining-algorithms/ethash/).

1. Make sure perquisite are meet and installed Hyperledger Besu.
    ```sh
    besu --version
    ```
    Create a New Folder: (optional)
    ```sh
    mkdir PrivateNetwork
    cdPrivateNetwork
    ```
    
2. Create a configuration file. 
3. Start the Node.
4. Interaction with the Node using JSON-RPC calls or command-line interfaces to send transactions, deploy smart contracts, or request blockchain data.

## Genesis Block Configuration

The genesis block is the foundational starting point of any blockchain, ensuring the integrity and continuity of the entire system. It’s hardcoded into network nodes, making it a critical point of trust. Each block contains the hash of its predecessor, so tampering with the genesis block invalidates the entire blockchain.

## Besu Genesis Block Configuration

By default, Besu creates the mainnet’s genesis block. For a private network, a distinct genesis block is required. Below is the configuration for a Proof of Work-based network.

### Steps to Create Genesis File

1. Create a file named `genesis.json` in the `PrivateNetwork` folder.
2. Copy the content below and replace the highlighted section with your account address.

```json
{
  "config": {
    "berlinBlock": 0,
    "ethash": {
      "fixeddifficulty": 1000
    },
    "chainID": "1100001"
  },
  "gasLimit": "0x1000000",
  "difficulty": "0x10000",
  "contractSizeLimit": "24576",
  "alloc": {
    "pasteYourAccountAddressHere": {
      "balance": "90000000000000000000000"
    }
  }
}
```
### Key Configuration Parameters
make the content shorter
Sure! Here’s a more concise version of the content:

markdown
## Genesis Block Configuration

The genesis block is the foundational starting point of any blockchain, ensuring the integrity and continuity of the entire system. It’s hardcoded into network nodes, making it a critical point of trust. Each block contains the hash of its predecessor, so tampering with the genesis block invalidates the entire blockchain.

### Besu Genesis Block Configuration

By default, Besu creates the mainnet’s genesis block. For a private network, a distinct genesis block is required. Below is the configuration for a Proof of Work-based network.

#### Steps to Create Genesis File

1. Create a file named `genesis.json` in the `PrivateNetwork` folder.
2. Copy the content below and replace the highlighted section with your account address.

```json
{
  "config": {
    "berlinBlock": 0,
    "ethash": {
      "fixeddifficulty": 1000
    },
    "chainID": "1100001"
  },
  "gasLimit": "0x1000000",
  "difficulty": "0x10000",
  "contractSizeLimit": "24576",
  "alloc": {
    "pasteYourAccountAddressHere": {
      "balance": "90000000000000000000000"
    }
  }
}
```

#### Key Configuration Parameters

 - **berlinBlock:**
In Besu private networks, the `berlinBlock` parameter marks Ethereum protocol changes. Setting it to `0` ensures the network uses the latest Ethereum protocol from its genesis block.

 - **chainID:**
Ethereum uses two identifiers: a network ID for peer-to-peer communication, and a chain ID for transaction signing. These IDs should be numerical and not start with zero to avoid errors.

 - **gasLimit:**
Sets the maximum gas cost per block, dictating the extent of EVM computation permissible within a single block.

 - **ethash:**
Indicates the Proof of Work algorithm. The `fixeddifficulty` field maintains constant network difficulty for testing environments. For production networks, it's recommended to set a low difficulty in the genesis file for Ethash to adjust based on hashrate.

 - **alloc:**
Specifies addresses and their initial balances in wei. Include an address you can access with a private key, such as one from MetaMask.


> [!NOTE] 
> Besu doesn’t support private key management. So make use of a familiar wallet like MetaMask.

## Running a Private Node

To run a private node, use the following command:

```sh
besu  --identity=”NodeA” --network-id 1000001 --data-path=Node1/data --genesis-file=./genesis.json --rpc-http-enabled --rpc-http-host="0.0.0.0" --rpc-http-port "8545" --rpc-http-api=ADMIN,ETH,NET,MINER,WEB3 --host-allowlist="*" --rpc-http-cors-origins="all" --miner-enabled --miner-coinbase="pasteYourAccountAddressHere"
```

### Command Parameters
 - **identity:** Name of the node, e.g., NodeA.
 - **network-id:** Numeric identifier for the network (e.g., 1000001).
 - **data-path:** Directory for storing blockchain data.
 - **rpc-http-enabled:** Enables RPC communication.
 - **rpc-http-port:** Default port 8545.
 - **host-allowlist:** Accepts a comma-separated list of hostnames, * for any host.
 - **rpc-http-cors-origins:** Accepts cross-origin requests, all for all origins.
 - **rpc-http-api:** Lists APIs accessible through RPC (e.g., ADMIN, ETH, NET, MINER, WEB3).
 - **miner-coinbase:** Account for mining rewards, replace with your account address.
 - **miner-enabled:** Activates mining on the node.

Execute the command to start the node. The node will begin mining and its status will be displayed in the console.

> [!NOTE]
> Mining is resource-intensive and may cause high CPU utilization. Ensure your system has adequate resources to avoid performance issues.

## Ethereum Node Functionality Testing

### Testing the Ethereum Node

To test our Ethereum node, we will deploy a simple storage smart contract. 

#### Smart Contract (MessageContract.sol)

```solidity
// SPDX-License-Identifier: GPL-3.0
pragma solidity 0.8.21;

contract MessageContract {
    string message;

    function getMessage() public view returns (string memory) {
        return message;
    }

    function setMessage(string memory _message) public {
        message = _message;
    }
}
```

This contract allows storing and retrieving a string value with two functions: setMessage to store the value, and getMessage to retrieve it.

#### Deploying the Contract

1. Open Remix IDE.
2. Create and Compile Contract:
    - Create a file MessageContract.sol and copy the above code.
    - Compile the contract.
3. Connect MetaMask:
    - Use the Injected Provider – MetaMask option in the Environment dropdown under the Deploy & Run Transactions tab.
4. Configure MetaMask to connect to our private network:
    - Network name: Test Network (any name)
    - New RPC URL: http://127.0.0.1:8545 (from node console)
    - Chain ID: 1100001 (from genesis file)
    - Currency symbol: TETH (any symbol)

Finally, load your address, deploy the contract to our network, and test it. Refer to the accompanying [video](https://youtu.be/7fWQzc_eFYo) for guidance.


> [!NOTE] 
> This is just an overview, and you should refer to our course materials for more detailed instructions.