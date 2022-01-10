---
title: 'Dapp Workflow'
date: '2021-12-14'
---

# Load up starter project

I'm going to use this space to write down the workflow for developing and deploying a dapp.

To get started fast we will clone a [starter project](https://github.com/tomhirst/solidity-nextjs-starter) from github. This project is A full stack dApp starter built on Ethereum (Solidity) with Next.js (React). In terminal change to a directory where you want to store your projects then `git clone git@github.com:tomhirst/solidity-nextjs-starter.git` then `cd solidity-nextjs-starter`

Lets get this project running locally with [hardhat](https://hardhat.org/getting-started/). 

	npm install
	npm install --save-dev hardhat
	npx hardhat accounts
	npx hardhat compile  
	npx hardhat test

	npx hardhat run scripts/deploy.js

You will get a response like: 

> Deploying a Greeter with greeting: Hello world!
> Greeter deployed to: 0x5FbDB2315678afecb367f032d93F642f64180aa3

You will need paste the contract address into the .env file NEXT_PUBLIC_GREETER_ADDRESS

	npx hardhat node

> Started HTTP and WebSocket JSON-RPC server at http://127.0.0.1:8545/
> 
> Accounts
> 
> WARNING: These accounts, and their private keys, are publicly known.
> Any funds sent to them on Mainnet or any other live network WILL BE LOST.
> 
> Account #0: 0xf39fd6e51aad88f6f4ce6ab8827279cfffb92266 (10000 ETH)
> Private Key: 0xac0974bec39a17e36ba4a6b4d238ff944bacb478cbed5efcae784d7bf4f2ff80

	npx hardhat run scripts/deploy.js --network localhost

In another terminal

	npm run dev

Open up the page at http://localhost:3000/ and test by reading from your local hardhat blockchain and writing to the blockchain. If you get an error from metamask that nonce is too high you need to go to metamask setings > advanced > reset account.

We now have a starter Dapp running locally that can read and write from our local blockchain.

Next steps to make our dapp a little more useful... 

We can deploy to avax fuji testnet
Update our dapp to do something a little more useful

# Deploy to avax fuji testnet with remix

Need to learn how to set up a new network in hardhat.config.js 

So for now just deployed contract to fuji testnet with remix. Create the Greeter.sol contract in remix. Then set the environment to injected web3. Compile the contract. The deploy the contract.

Copy the contract address to NEXT_PUBLIC_GREETER_ADDRESS and chain id to .env

Now restart the frontend

	npm run dev

Test that the contract works yay!

Next up lets edit hardhat.config to make deploying easier with hardhat.

# Deploy to avax fuji testnet with hardhat




# Connect Metamask to Hardhat

Change network to localhost://8545
Make sure the port is correct in Settings > Networks > Localhost 8545 > Chain ID should be what you set in .env HARDHAT_CHAIN_ID

Import an account from the output of `npx hardhat node` using the private key.



# github

to deploy to vercel we just have to push changes to github.

	 git add .
	 git commit -m"COMMIT MESSAGE"
	 git push origin main

