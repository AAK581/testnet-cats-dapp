# Testnet Cats: A Gamified Multi-Network Testnet Faucet

## About this project

### Project Description
This project combines a blockchain faucet with RPG mechanics. Players collect kittens in an RPG Maker MZ game, then sync their progress online using an in-game Teleporter item. Upon collecting at least 15 kittens, a user can claim a testnet-token reward from the dApp, with a maximum of 4 rewards per day. On some networks, reaching kitten milestones also mints a Milestone NFT.

It started as a Sepolia-only faucet and now supports 5 testnets: Sepolia, Scroll Sepolia, Monad Testnet, Polkadot Moonbase Alpha, and Flow Testnet.

The stack is a React frontend using Reown AppKit and Wagmi, with Foundry-tested smart contracts.

### Directory Structure

- **/react-reown**: the frontend React application
- **/foundry-smartContract**: the smart contract code, tests, and Foundry configuration

## Design Patterns

The implementation uses OpenZeppelin's Ownable contract for inheritance. Access control restricts key functions (contract funding, game address configuration, reward modification) to the contract owner.

## Security Measures

The codebase favors require statements over conditionals and uses a modifier to restrict kitten-setting functions to the authorized game contract only. The setKittens function caps a user at 60 kittens. The rewardUser function validates kitten sufficiency, daily reward limits, and contract funding before processing transactions, following the checks-effects-interactions pattern.

## Supported Networks

| Network | Chain ID | Game Contract | Game |
|---|---|---|---|
| Sepolia | 11155111 | [0xa9C4cd6C657f5110C6966c78962D47c24D27BD57](https://sepolia.etherscan.io/address/0xa9C4cd6C657f5110C6966c78962D47c24D27BD57) | [play](https://rpg-game-sepolia-cats.vercel.app/) |
| Scroll Sepolia | 534351 | [0xA45a75B3523334bf4017b0BB9D76d4E06661fba3](https://sepolia.scrollscan.com/address/0xA45a75B3523334bf4017b0BB9D76d4E06661fba3) | [play](https://rpg-game-sepolia-cats.vercel.app/) |
| Monad Testnet | 10143 | 0x0968F5BF2EdEEEEf0bdB42C304DB24d5CE90B9D7 | [play](https://monad-cats-game.vercel.app/) |
| Polkadot Moonbase Alpha | 1287 | [0xEDDe9fc8ca8668046f9EAf9b64FDc94620518E26](https://moonbase.moonscan.io/address/0xEDDe9fc8ca8668046f9EAf9b64FDc94620518E26) | [play](https://polkadot-cats-game.vercel.app/) |
| Flow Testnet | 545 | [0x292Fe1de6ce0ca4917fB6163ECb4C00b395D5804](https://evm-testnet.flowscan.io/address/0x292Fe1de6ce0ca4917fB6163ECb4C00b395D5804) | [play](https://flow-cats-rpg-game.vercel.app/) |

### Milestone NFT Contracts

| Network | NFT Contract |
|---|---|
| Polkadot Moonbase Alpha | [0x3BDFaEA81A965643ECD5Bee47dBE28434FF740C8](https://moonbase.moonscan.io/token/0x3BDFaEA81A965643ECD5Bee47dBE28434FF740C8) |
| Flow Testnet | [0x335777beD22AdA837E46D28AE83ba697eDD09d62](https://evm-testnet.flowscan.io/token/0x335777beD22AdA837E46D28AE83ba697eDD09d62) |

### Application Link
https://testnet-cats-dapp.vercel.app/

## How To Run Tests

Install Foundry (https://book.getfoundry.sh/introduction/installation/), then run "forge test" inside /foundry-smartContract.

## How To Run The Program

For the frontend: navigate to /react-reown, run "npm install", then "npm run dev". The games are hosted at the links in the table above.

## Demo
Video of the original Sepolia version: https://drive.google.com/file/d/1JIVIAH64-9euZEi7hedDiXJMlxMTK9NS/view?usp=drive_link
