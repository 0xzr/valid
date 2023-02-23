# 🥩 Awesome SSV Staking Frontend 🥩

🚀 By staking their ETH to a staking contract, users receive a liquid staked derivative token called ssvETH. This allows them to earn compound interest on their staked ETH, while also being able to use the ssvETH tokens in other DeFi protocols without having to unstake their original ETH.

# Demo 

You can find our live demo [Here](https://awesome-ssv-staking.surge.sh)

# Run the frontend app locally

Prerequisites: [Node (v18 LTS)](https://nodejs.org/en/download/) plus [Yarn (v1.x)](https://classic.yarnpkg.com/en/docs/install/) and [Git](https://git-scm.com/downloads)

> 1️⃣ clone/fork  awesome SSV Staking repo:

```bash
git clone https://github.com/bloxapp/awesome-ssv
```
> 2️⃣ make sure you have the right network set

> 3️⃣ install and start the frontend:

```bash
cd frontend
yarn install
yarn react-app:start
```
📱 Open http://localhost:3000 to see the app

🎉 If you already have the contracts deployed from the [backend](https://github.com/bloxapp/awesome-ssv), you just need to update the default network in `packages/react-app/src/App.jsx` and your new contract addresses and ABIs in `packages/react-app/src/contracts/external_contracts`.

✏ You can edit the home view and the manager view in  `packages/react-app/src/views/Home.jsx` and `packages/react-app/src/views/Manager.jsx`respectively.

# Contracts

🚨 Local deployment (Goerli fork) :

if you want to deploy the contracts locally using the Goerli fork using hardhat, you need to fork the Goerli network locally with :

```bash
yarn fork
```
After setting up your default network in `hardhat-config.js` you can run 

```bash
yarn deploy
```
🎇 after this your new staking pool and ssvETH contracts should reflect on automatically in `packages/react-app/src/contracts/localhost/`

🚨 Goerli live deployment :

If you want to deploy on the live Goerli testnet, you'll only need to run this :

```bash
yarn deploy-goerli
```
🎇 after this your new staking pool and ssvETH contracts should reflect on automatically in `packages/react-app/src/contracts/goerli/`

✅ to verify your staking pool contract on Goerli  : 

```bash
yarn verify --constructor-args arguments.js --network goerli NEW_DEPLOYED_CONTRACT_ADDRESS
```
and your ssvETH token contract with 

✅ to verify your ssvETH contract on Goerli : 

```bash
yarn verify --network goerli NEW_DEPLOYED_CONTRACT_ADDRESS
```

❗❗ Important : 
💥 Once you have your contracts deployed you will need to update the default network in `App.jsx` to match your default network in `hardhat-config.js`. And your new contracts addresses and ABIs in `packages/react-app/src/contracts/external_contracts`.

# Backend   

🚀 You can run your own instance of the solution using our backend repo to deploy contracts and run scripts [here](https://github.com/bloxapp/awesome-ssv/blob/main/RUN_BACKEND.md) 

# Extra

🔏 Edit the smart contracts in `packages/hardhat/contracts`

📝 Edit your frontend `App.jsx` in `packages/react-app/src`

💼 Add/Edit your deployment scripts in `packages/hardhat/scripts/deploy` for Goerli and in `packages/hardhat/deploy` for localhost (Goerli fork)

🚨📡 To deploy to a public domain, use `yarn surge`. You will need to have a surge account and have the surge CLI installed. There is also the option to deploy to IPFS using `yarn ipfs` and `yarn s3` to deploy to an AWS bucket 🪣 There are scripts in the `packages/react-app/src/scripts` folder to help with this.`

---

🙏 Built on top of the amazing [scaffold-eth](https://github.com/scaffold-eth/scaffold-eth) !



