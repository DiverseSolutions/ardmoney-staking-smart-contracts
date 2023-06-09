### ArdMoney Staking Smart Contract
---
# Project Overview
ARDM token staking contract , this contract is a fork of Sushiswap staking contract.
When users deposit their ARDM token they will reserve sARDM token. sARDM token rate is being defined by the supply of sARDM & ARDM in the contract.
Weekly ARDM tokens will be added to the contract. Allowing sARDM token holders sARDM rate to increase. Which brings the concept of rewards.
The staking contract also has penalty features. Which means when the penalty feature is on users will have penalty deadlines. When their penalty deadline has passed
their withdraw will not have penalty. Vice versa when users withdraw their ARDM tokens by giving sARDM tokens while their penalty deadline hasnt been passed their
withdraw amount will have a penalty fee. The penalty fee will be sent to the treasury address. The contract also has pausibility features allowing for quick withdraw
and deposit functionality freeze. In case of any error happens.

---

## Technical Requirement
 - Smart Contracts are written with Solidity language.
 - Smart Contracts mostly uses OpenZeppelin Contracts.
 - Smart Contracts follow the Natspec Format.
 - Smart Contracts must be written with full flexibility.
 - Solidity compiler version 0.8.19 is used.
 - Using the Hardhat development framework.
 - Typescript is used for testing & deployment scripts.
 - Using the hardhat-abi-exporter plugin for ABI export when smart contracts compiled.
 - Smart contracts are designed to be deployed to BSC chain.

---

## Deployment flow
 1. ArdMoney token must be deployed
 2. Treasury address must be defined
 3. Penalty fee must be defined
 4. Penalty deadline must be defined
 5. sARDM token must be deployed
 6. Staking then must be deployed with all the above parameters
 7. Mint role must be given from sARDM to Staking Contract
 8. Staking contract is ready to be used

---

## Functionality Requirement

### Roles
 - Pauser : Can pause Penalty,Withdraw,Deposit features
 - Admin : Can change penalty fee, penalty deadline, treasury address, revoke roles
 - Treasury : Must add reward ARDM to staking contract & also receives penalty fees
 - User : Can deposit ARDM and receive sARDM also withdraw their ARDM by giving back their sARDM by the current rate

### Features
 - Withdraw Pausibility
 - Deposit Pausibility
 - Penalty Pausibility
 - Recieves Reward from 1 address
 - Reward functionality that adds value to sARDM weekly
 - Locks ARDM and gives back sARDM
 - sARDM token must have MINTER ROLE and only should point to 1 Staking Contract. IF in the future staking contract needs to be closed then minter role of that staking contract needs to be revoked and new staking contract needs to have minter role. Giving us full flexibility and migration abilities of sARDM token

### Use Case
 1. User deposits ARDM and recieves sARDM by using the deposit functionality of contract.
 2. Treasury Address adds ARDM to contract by using the reward functionality of contract. This will increase the sARDM rate
 3. User withdraws their ARDM + Reward by using the withdraw functionality of contract. sARDM rate is up henceforth user receives more ARDM than initial deposit

---

## Getting Started
---
Recommended Node version is 16.0.0 and above.

### Available commands
```

# install dependencies
$ npm install

# run tests
$ npm run test

# compile contracts & generate ABI and Typescript types
$ npm run compile

# check test coverage
$ npm run coverage

# force compile contracts & generate ABI and Typescript types
$ npm run force-compile

# deploy contracts locally
$ npm run deploy-local

# deploy contracts to ganache
$ npm run deploy-ganache

# deploy contracts to bsc
$ npm run deploy-bsc

# deploy contracts to testnet bsc
$ npm run deploy-test-bsc

```

## Project Structure
---
This a template hardhat typescript project composed of contracts, tests, and deploy instructions that provides a great starting point for developers to quickly get up and running and deploying smart contracts on the Ethereum blockchain.

### Tests
---
Tests are found in the ./test/ folder.

### Contracts
---
Solidity smart contracts are found in ./contracts/

### Coverage
---
Coverages are generated after running the "npm run coverage" command

### ABI
---
Solidity smart contracts ABI's are generated in ./abi/ when contracts are compiled.

### Deploy
---
Deploy script can be found in the ./scripts/deployment.ts.

Rename ./.env.example to ./.env in the project root. To add the private key of a deployer account, assign the environment variables.

```
# deploy contracts locally
$ npm run deploy-local

# deploy contracts to ganache
$ npm run deploy-ganache

# deploy contracts to bsc
$ npm run deploy-bsc

# deploy contracts to testnet bsc
$ npm run deploy-test-bsc
```

---

#### BSC Deployment
  - Owner Address : 0x23D4B44F92d416F3FFC75B4651B96De48616Cf20
  - Treasury Address : 0x23D4B44F92d416F3FFC75B4651B96De48616Cf20
  - Penalty Fee : 0.6%
  - Penalty Deadline : 2 weeks - 1209600
  - Staking Contract : 0x1410dACb719Cbd809f79b10CE82170f2407FdBC3
  - sARDM : 0x1aae7Fc607092A12812a97DDf51D4f679f951679


## Old Version Deployment History

#### BSC Deployment
  - Owner Address : 0xE033abBF894e108a827Dcc33b97399bF34e94524
  - Treasury Address : 0xE033abBF894e108a827Dcc33b97399bF34e94524
  - Penalty Fee : 0.6%
  - Penalty Deadline : 2 weeks 
  - Staking Contract : 0x29100E56924CD94816747478486e7b592001cFEc
  - xARDM : 0x1b911938C3aD76De1DFaACcF508f9018b93FfB93

#### BSC TestNet Deployment
  - Owner Address : 0xA24ed6345301afC508d2B5cD523105E9501088F6
  - Penalty Fee : 5%
  - Penalty Deadline : 1hour
  - Treasury Address : 0x5214ae4310b4F8059CD801992115283692FBE6eB
  - Staking Contract : 0xb68EBb0Cd8247829072A24724259b6ED42FF18f2
  - xARDM : 0x1baD908B21a6198B3CdefCeEdd4B7812DDFD0b2C

