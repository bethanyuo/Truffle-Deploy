# Develop and Deploy Smart Contracts with Truffle
Create a smart contract, compile and deploy it using the Truffle Framework and add Unit Tests for the contract logic using Truffle. Deploy the smart contract in Ganache-CLI with Truffle. Then write unit tests for the smart contract and test it with Truffle. The contract will be written in Solidity. Before getting started, Truffle and Ganache-cli must be installed. Ganache-cli will be the tool we will use to create a private blockchain that runs on our machine only. 
For this exercise we will use Ubuntu 16.04.3.

## Requirements
*  Ubuntu 16.04.3
* Ganache-CLI
* Truffle

## Truffle Init
1.	Set the Truffle and Ganache-cli

2.	If you already have Ganache-cli installed just skip this step, otherwise open terminal console and write command:
```bash
$ sudo npm install -g ganache-cli@6.4.5
```
If you are running Windows, the recommended way to do this exercise is to install Windows Subsystem for Linux.

3.	Create folder Exercise and open console. Create truffle project here by writing command: `truffle init`. Truffle will install three folders. 
*	In folder contracts: we will save our smart contracts. 
*	In migrations: we will hold configuration files for migrations. They are _.js_ files starts with number, like _1_initial_migration.js_ and _2_deploy_contracts.js_.
*	Folder test: holds unit test files.

The file _truffle-config.js_ is the truffle configuration file.

4. The `port` in which ganache-cli communicates is `8545`. 
 
## Deploy a Smart Contract

1.	Now is time to write our smart contract. Open Remix Solidity IDE. The contract allows you to publish a time-limited article with name and text. Modifier `onlyOwner` allows only the owner of the contract to modify the `articleName` and `articleText`. Modifier `limitedTime` restricts for how long the article is readable. Write the following solidity code in Remix. Click Start to compile to compile and verify the contract.
 
2.	Now, copy the code of the smart contract. Open the contracts directory, create file _PublicArticle.sol_ in there and pastе the copied code in the file.
 
3.	Go to migrations folder and create file _2_deploy_contracts.js_ with the following content:
 
4.	Now, you are ready to compile the contract and migrate it to ganache-cli blockchain. Open console and run ganache-cli. The local testnet will started and gives you `10 addresses` and `10 private keys`. If you don't declare something else the first `“0”` address will be used by default. If you deploy contract with him, it will be the owner's address.
```bash
$ ganache-cli
```
 
5.	Open second terminal, go to Exercise directory and type:
```bash
$ truffle migrate
```
The smart contract was successfully deployed. You can see the transaction number wrote in `block 4` of the blockchain.

6.	Now run the truffle console and call the info for block 4.  There is the transaction number which we see in migration info.
```bash
$ truffle console
$ > web3.eth.getBlock(4)
```

## Module
MI4: Module 1: E3
