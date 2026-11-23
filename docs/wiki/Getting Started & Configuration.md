# Q702 — Getting Started & Configuration

## Requirements
- Node.js and npm.
- Dependencies declared in the root `package.json`.
- A local Ethereum development node for the configured Truffle development network.

## Install and compile
From the repository root:

```bash
npm install
npm run compile
```

The Truffle compiler version is pinned to Solidity 0.8.9 in `truffle-config.js`.

## Run the contract tests
The repository contains `test/NFT.test.js`, but the `npm test` script is only a failing placeholder. The configured development network points to `127.0.0.1:8545`; start the local Ganache CLI process in one terminal, then run Truffle tests in another:

```bash
npx ganache-cli --host 127.0.0.1 --port 8545
npx truffle test --network development
```

The test file currently covers contract name/symbol, minting and token URI, balance, transfer, and owner pause/unpause behavior. This documentation review did not execute these commands, so successful compilation or tests are not claimed.

## Configuration and deployment boundary
The active Truffle configuration contains a local development network. Infura/HDWalletProvider and Truffle Dashboard examples are comments only. No public deployment network or deployment procedure is currently configured.

Do not connect a funded wallet, expose a mnemonic/private key, or deploy to a public chain as part of local setup.