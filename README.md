# Web3-Cheatsheet
Cheatsheet for Web3JS.

# Setup
Connect to Blockchain - simple:
```
const web3 = new Web3('url-to-ethereum-node')
```

Connect to Blockchain - Metamask:
```
const web3 = new Web3(ethereum.provider)
```
Connect to Blockchain - Infura:
```
const web3 = new Web3(
 HDWalletProvider(mnemonic, "http://localhost:8545")
) /* HDWalletProvider = require('@truffle/hdwallet-provider') /*
```
Instantiate contract:
```
const contract = new web3.eth.Contract(abi, address)
```
Get list of wallet addresses:
```
web3.eth.getAccounts()
```
Get block number:
```
web3.eth.getBlockNumber()
```

# Interacting with smart contract:
Call a smart contract function:
```
contract.methods
 .foo(arg1, arg2, etc...)
 .call()
```

Send a transaction:
```
contract.methods
 .foo(arg1, arg2, etc...)
 .send({from: address, value: /*if sending ether*/})
```

Events:
```
contracts.events
 .MyEvent(
 {fromBlock: 0, filter: {field1: val1, etc...} /* for indexed parameter */},
 (error, event) => {/* callback here */}
);
```

# Utils:
Transform Ether to Wei:
```
web3.utils.toWei('1') /* notice the quotes */
```
Transform Wei to Ether:
```
web3.utils.fromWei('100000') /* notice the quotes */
```

