
---
# MyToken Smart Contract

This repository contains the Solidity code for the **MyToken** smart contract, a simple token system built on the Ethereum blockchain. The contract allows users to mint and burn tokens, making it suitable for basic token management.

## Contract Overview

The **MyToken** smart contract defines the following properties:
- **Token Name**: The name of the token.
- **Token Abbreviation**: A short representation of the token.
- **Total Supply**: The total number of tokens in circulation.

A **mapping** is used to store the token balances associated with each address. It links an Ethereum address to a `uint` value, representing the token balance.

### Functions

#### Mint

The `mint` function allows new tokens to be added to the total supply and credited to a specific address.

**Parameters:**
- `Addr`: The Ethereum address that will receive the newly minted tokens.
- `Val`: The amount of tokens to mint.

**Behavior:**
- Increases the `Token_TotalSupply` by the value of `Val`.
- Increases the balance of `Addr` by `Val`.

#### Burn

The `burn` function destroys tokens, reducing the total supply and the balance of a specified address.

**Parameters:**
- `Addr`: The Ethereum address from which the tokens will be burned.
- `Val`: The number of tokens to burn.

**Behavior:**
- Decreases the `Token_TotalSupply` by `Val` if the balance of `Addr` is sufficient.
- Decreases the balance of `Addr` by `Val`.

**Error Handling:**
- If `Addr` has fewer tokens than `Val`, the transaction is reverted with the error: `Insufficient balance to burn`.

## Usage

To deploy and interact with this contract, you can use tools like [Remix IDE](https://remix.ethereum.org/) or Ethereum development frameworks such as [Hardhat](https://hardhat.org/) or [Truffle](https://trufflesuite.com/).

### Deploying the Contract

1. Compile and deploy the contract using your preferred tool.
2. Once deployed, you can interact with the contract's functions to manage token balances and supply.

### Example Interactions

#### Minting Tokens
To mint tokens, call the `mint` function with the recipient address and the desired amount.

```solidity
mint(0xYourAddress, 100);
```
This will:
- Increase the total supply by 100.
- Credit 100 tokens to `0xYourAddress`.

#### Burning Tokens
To burn tokens, call the `burn` function with the address and the amount of tokens to be burned.

```solidity
burn(0xYourAddress, 50);
```
This will:
- Reduce the total supply by 50.
- Deduct 50 tokens from `0xYourAddress`, provided it has enough balance.

## License

This project is licensed under the MIT License.

---
