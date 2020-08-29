# Unit18_Blockchain
## Overview
- In this project, I used the Go Ethereum tool that was installed on my personal computerto create a testnet blockchain; and then I used MyCrypto app, which serves the purpose of a cryptocurrency virtual wallet, to make a test transaction between two nodes I created using puppeth tool. 

## Package Installation and Setup
  - Geth and its related tools are all downloaded from https://geth.ethereum.org/downloads/. After the installation, all tools and softwares are extracted into a local file folder, which includes tools such as puppeth and geth. All the following procedures are run through this file folder directory. 

## Setting up nodes
- After getting into the tool directory, the following geth commands were run to create two seperate nodes: ./geth account new --datadir node1 and ./geth account new --datadir node2. What it does was basically creating two new accounts for two nodes for the network I created, which was named fintechunit18. A password is also created when setting up both accounts. After successfully creating the nodes, I copied and pasted the public address of the keys and the path of the secret key file into a local notebook for storage purpose. 
![capture1](capture1.PNG)

## Configurations
- By running ./puppeth command, I created the network: fintechunit18; chose proof-of-authority as consensus algorithm. A default 15 seconds was set for block time. Then both nodes accounts were allowed to seal, and pre-funded. The chain ID was specified to be 111
- The next step was exporting genesis configurations to the folder; and fintechunit18.json, fintechunit18-aleth.json, fintechunit18-harmony.json, and fintechunit18-parity.json were exported. 
- Then I need to initialize and tell the nodes to use my genesis block by using the following commands: ./geth init fintechunit18.json --datadir node1, and ./geth init fintechunit18.json --datadir node2. 
- After initialization, the command: ./geth --datadir node1 --mine --minerthreads 1 was run to launch the first node into mining mode. The --mind flag tells the nodes to mine new blocks. On a seperate terminal, the command: ./geth --datadir node2 --port 30304 --rpc --bootnodes "enode://246ad41ec5f329c68cb9e4afda2ec8e329705fd0f6b13be07b87e8b25486cbf5cb8f1f3aa19842fcb1ed76f0de2a2a2b43c1e05143229559a56b2acc64ee729b@127.0.0.1:30303" --ipcdisable was run to let me talk to the chain via RPC. The enode:// address was copied from the first terminal and pasted to the second for finding the first node. 
![capture2](capture2.PNG)

## MyCrypto
  - We need to use the MyCrypto wallet to connect to the node with the exposed RPC port. I first need to use a custom network, and include the chain ID, and use ETH as the currency, shown in the following (note: it's showing cannot share chain ID becuse I took the screenshot after I've already created this custom network): 
  ![capture4](capture4.PNG)
  - After successfully set up custome network, we need to unlock our keystore file by select the wallet file from the local folder where it was first created and stored, and type in the passwork. 
  ![capture5](capture5.PNG)
  - After getting into my wallet, I can now start the test transaction by sending 10,000 ETH to my second address.
  ![capture6](capture6.PNG) 
  - After making the transaction, by clicking on TX Status, I will be able to see the transation status:
  ![capture3](capture3.PNG)






