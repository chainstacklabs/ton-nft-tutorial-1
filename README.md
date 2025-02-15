# TON: How to develop non-fungible tokens (NFT)

For the full breakdown, see [TON: How to develop non-fungible tokens (NFT)](https://docs.chainstack.com/docs/ton-how-to-develop-non-fungible-tokens).

## References

This project is inspired by and based on examples from the following repositories:

- [TON Blockchain Token Contract](https://github.com/ton-blockchain/token-contract/tree/main)

## Project structure

-   `contracts` - source code of all the smart contracts of the project and their dependencies.
-   `wrappers` - wrapper classes (implementing `Contract` from ton-core) for the contracts, including any [de]serialization primitives and compilation functions.
-   `tests` - tests for the contracts.

## How to use

### Build

`npx blueprint build` or `yarn blueprint build`

### Test

`npx blueprint test` or `yarn blueprint test`

### Deploy or run another script

`npx blueprint run` or `yarn blueprint run`

### Add a new contract

`npx blueprint create ContractName` or `yarn blueprint create ContractName`
