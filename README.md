This repository contains the Solidity code for the MyToken smart contract.
The contract is a simple implementation of a token system on the Ethereum blockchain, where users can mint and burn tokens.
We have created a contract "MyToken" in which we have create a Token name, Token Abbravation and total token supply.

Mapping stores the token balance for each address. It associates an address with a uint (the balance).

The mint function allows new tokens to be created.
It takes two parameters: Addr (the address to receive the tokens) and Val (the amount of tokens to mint).
It increases the Token_TotalSupply by the value of Val and also increases the balance of the specified address by Val.

The burn function allows tokens to be destroyed.
It takes two parameters: Addr (the address from which tokens will be burned) and Val (the amount of tokens to burn).
It checks if the balance of the specified address is greater than or equal to Val.
If the balance is sufficient, it decreases the Token_TotalSupply by Val and also decreases the balance of the specified address by Val.

**Usage**
To deploy and interact with this contract, you can use tools like Remix IDE or any Ethereum development framework such as Hardhat or Truffle. After deploying the contract, you can call the mint and burn functions to manage token balances and supply.

Example Interactions
Minting Tokens:

Call the mint function with the desired address and amount to create new tokens.
For example:
solidity
mint(0xYourAddress, 100);
This will increase the total supply by 100 and add 100 tokens to the balance of 0xYourAddress.
Burning Tokens:

Call the burn function with the address and amount of tokens to be burned. 
For example:
solidity
burn(0xYourAddress, 50);
This will decrease the total supply by 50 and deduct 50 tokens from the balance of 0xYourAddress, provided 0xYourAddress has at least 50 tokens.

Error Handling
The burn function includes a check to ensure that an address has enough tokens to burn. If the balance is insufficient, the function will revert with the message "Insufficient balance to burn".
