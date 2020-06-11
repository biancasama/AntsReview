[![#ubuntu 18.04](https://img.shields.io/badge/ubuntu-v18.04-orange?style=plastic)](https://ubuntu.com/download/desktop)
[![#npm 12.16.2](https://img.shields.io/badge/npm-v12.16.2-blue?style=plastic)](https://github.com/nvm-sh/nvm#installation-and-update)
[![#built_with_Truffle](https://img.shields.io/badge/built%20with-Truffle-blueviolet?style=plastic)](https://www.trufflesuite.com/)
[![#solc v0.6.6](https://img.shields.io/badge/solc-v0.6.6-brown?style=plastic)](https://github.com/ethereum/solidity/releases/tag/v0.6.6)
[![#testnet rinkeby](https://img.shields.io/badge/testnet-Rinkeby-yellow?style=plastic&logo=Ethereum)](https://rinkeby.etherscan.io/address/0x6956dF88120c44fb446761947cD4B83b553F229F)

[![ETH Turin 2020](https://img.shields.io/badge/%CE%9E-ETH%20Turin%202020-F64060.svg)](https://ethturin.com)
[![DOI](https://zenodo.org/badge/258342275.svg)](https://zenodo.org/badge/latestdoi/258342275)  

<img src="ants_review_logo.png" width="30%">

# Ants-Review
> A Protocol for Open Anonymous Scientific Peer-Reviews  
> :1st_place_medal: 1st Place at [ETHTurin Hackathon](https://ethturin.com/hacks) (open with MetaMask disabled)

The Project implements a basic Bounty-like contract called AntsReview to allow anyone to issue an AntReview in ETH, a bounty for peer-review in scientific publication, linked to requirements stored on ipfs which anyone can fufill by submitting the ipfs hash which contains evidence of their fufillment.  
After the submission of successful peer-reviews, they will be audited by an external Editor and payed by the Issuer.  
To incentivise ethical behaviour the system will implement a quadratic funding on AntsReview.

The Project is intended to be used as a template for developing the idea presented in the white paper, extending its functionality via the following steps:

- Quadratic Funding Gitcoin-like for AntsReview.
- ERC20 token, name Ant, symbol ANT.
- zkANT, allowing private ANT transactions on Ethereum using ZK-SNARKs via AZTEC Protocol.
- Timestamped on Ethereum via PoE (Proof of Existence).
- Storing on IPFS.
- ENS, allowing human-readable Ethereum addresses
- Upgradability, to allow the logic to be extended and improved.
- ...
  
[White Paper](https://zenodo.org/record/3828087#.Xr8XVXVKg5k)  
[Presentation](https://zenodo.org/record/3828067#.Xr8Pv3VKg5k)  
[Demo](https://youtu.be/9FMsM5otQVM)  

Project Setup
============

Clone this GitHub repository.

# Steps to compile and deploy

  - Global dependencies
    - Truffle:
    ```sh
    $ npm install -g truffle
    ```
    - Ganache:
    ```sh
    $ npm install -g ganache-cli
    ```
    - OpenZeppelin Library v3.0:
    ```sh
    $ npm install -g @openzeppelin/contracts
    ```
    - MythX for Truffle (optional):
    ```sh
    $ npm install -g truffle-security
    ```
## Running the project with local test network (ganache-cli)

   - Start ganache-cli with the following command:
     ```sh
     $ ganache-cli
     ```
   - Compile the smart contract using Truffle with the following command:
     ```sh
     $ truffle compile
     ```
   - Deploy the smart contracts using Truffle & Ganache with the following command:
     ```sh
     $ truffle migrate
     ```
   - Test the smart contracts using Truffle & Ganache with the following command:
     ```sh
     $ truffle test
     ```
   - Analyze the smart contracts using MythX for Truffle with the following command (optional):
     ```sh
     $ truffle run verify
     ```
## Deploying on Rinkeby's Testnet
  - Get an Ethereum Account on Metamask.
  - On the landing page, click “Get Chrome Extension.”
  - Create a .secret file cointaining the menomic.
  - Get some test ether from a [Rinkeby's faucet](https://faucet.rinkeby.io/).
  - Signup [Infura](https://infura.io/).
  - Create new project.
  - Copy the rinkeby URL into truffle-config.js.
  - Uncomment the following lines in truffle-config.js:
    ```
    // const HDWalletProvider = require("@truffle/hdwallet-provider");
    // const infuraKey = '...';
    // const infuraURL = 'https://rinkeby.infura.io/...';

    // const fs = require('fs');
    // const mnemonic = fs.readFileSync(".secret").toString().trim();
    ```
  - Install Truffle HD Wallet Provider:
    ```sh
    $ npm install @truffle/hdwallet-provider
    ```
  - Deploy the smart contract using Truffle & Infura with the following command:
    ```sh
    $ truffle migrate --network rinkeby
    ```
    
    The Project's smart contract have been deployed on [Rinkeby](https://rinkeby.etherscan.io/address/0x6956dF88120c44fb446761947cD4B83b553F229F).  
   The ABIs are available to test the project on Rinkeby's Network.
   
   ## Using the DApp
  - Install [Ganache GUI](https://www.trufflesuite.com/ganache).
  - Change Ganache GUI port to 8545.
  - Import Ganache GUI mnemonic into MetaMask.
  - Connect MetaMask to Ganache GUI, adding a custom RPC specifing the Ganache GUI's RPC server URL.
  - Deploy the smart contracts to Ganache GUI:
    ```
    $ truffle migrate
    ```
  - Move to client directory on the project:
    ```
    $ cd client
    ```
  - Install dependencies:
    ```
    $ npm install
    ```
  - Start the Local Web Server:
    ```sh
    $ npm run start
    ```
  - Interacting with the User Interface (Proof of Concept):
    - Anyone can add an AntReview specifying IPFS Has of requirements, Deadline Timestamp, Ether value of the AntReview reward.
    
 The DApp (PoC) has been deployed on IPFS via [Fleek](https://fleek.co/): https://antsreview.on.fleek.co
    
    
## Inspiration & References
- [oscoin](http://oscoin.io/oscoin.pdf)
- [Towards Open Science: The Case for a Decentralized Autonomous Academic Endorsement System](https://zenodo.org/record/60054#.XqMYqnVKg5k)
- [ERC20](https://eips.ethereum.org/EIPS/eip-20)
- [Bounties-Network](https://bounties.network/)
- [Gitcion](https://gitcoin.co)
- [Gitcoin Quadratic Funding](https://vitalik.ca/general/2020/01/28/round4.html)
- [Quadratic Payments](https://vitalik.ca/general/2019/12/07/quadratic.html)
- [IPFS](https://ipfs.io/)
- [ZKPs](https://people.csail.mit.edu/silvio/Selected%20Scientific%20Papers/Zero%20Knowledge/Noninteractive_Zero-Knowkedge.pdf)
- [AZTEC Protocol](https://www.aztecprotocol.com/)
- [Ethereum 9 3/4](https://ethresear.ch/t/ethereum-9-send-erc20-privately-using-mimblewimble-and-zk-snarks/6217)

## About
Project created by Team MetaBounty for ETHTurin 2020 Hackathon.  
Conception & design by [Bianca Trovò](https://www.linkedin.com/in/bianca-m-trovo/)  
Implementation & code development by [Nazzareno Massari](http://nazzarenomassari.com)  
Pixel Art by [Marcelo Colmenero](https://www.instagram.com/isometricpixelart/?hl=en) 
