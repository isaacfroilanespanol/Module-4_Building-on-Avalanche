Overview
The IsaacMarket contract is an ERC-20 token implementation designed for a decentralized marketplace where players can mint, transfer, redeem, and burn tokens. It leverages OpenZeppelin libraries to ensure security and standardization.
Features
1. Minting Tokens: The contract owner can mint new DGN tokens and distribute them to players as rewards.
2. Transferring Tokens: Players can transfer DGN tokens to other players.
3. Redeeming Tokens: Players can redeem DGN tokens for items available in the in-game store.
4. Checking Token Balance: Players can check their DGN token balance.
5. Burning Tokens: Players can burn their own DGN tokens if they are no longer needed.
Contract Details
Inheritance
The contract inherits from:
* ERC20: Standard interface for ERC-20 tokens.
* Ownable: Provides ownership control to the contract deployer.
Constructor
* Initializes the token with the name "Degen" and symbol "DGN".
* Sets up initial prices for shop items.
Functions
Minting Tokens
solidity
function mintDGN(address _to, uint256 _amount) public onlyOwner

* Mints _amount of DGN tokens to the address _to.
* Can only be called by the contract owner.

Transferring Tokens
solidity
function transferDGN(address _to, uint256 _amount) public

* Transfers _amount of DGN tokens to the address _to.
* Ensures the sender has sufficient balance.
* Approves the sender's balance before transferring.

Redeeming Tokens
solidity
function redeemDGN(uint256 _item) public

* Redeems tokens for an item in the store.
* Ensures the item is available and the sender has sufficient balance.
* Transfers the item price in DGN tokens to the owner.

Burning Tokens
solidity
function burnDGN(uint256 _amount) public

* Burns _amount of DGN tokens from the sender's balance.
* Ensures the sender has sufficient balance.
* Approves the sender's balance before burning.

Checking Token Balance
solidity
function getBalance() external view returns (uint256)

* Returns the balance of DGN tokens for the caller.

Shop Items
solidity
function showShopItems() external pure returns (string memory)

* Returns a string listing the available items in the shop and their prices.

Token Decimals
solidity
function decimals() override public pure returns (uint8)

* Overrides the default decimals function to return 0, indicating the token does not use fractional units.

Deployment
1. Deploy the contract to the Ethereum blockchain.
2. The deployer will become the owner of the contract and have the ability to mint tokens.
3. Initialize shop item prices in the constructor.

Usage
1. Mint Tokens: Owner mints tokens to players as rewards.
2. Transfer Tokens: Players can transfer tokens to others.
3. Redeem Tokens: Players redeem tokens for in-game items.
4. Check Balance: Players check their token balance.
5. Burn Tokens: Players burn their unwanted tokens.

Requirements
* Solidity ^0.8.20
* OpenZeppelin Contracts

License
This contract is licensed under the MIT License. See the LICENSE file for details.

Disclaimer
Use this contract at your own risk. Ensure thorough testing and auditing before deploying to a live environment.

This README provides a detailed overview of the IsaacMarket smart contract, including its features, functions, and usage. For further questions or issues, please refer to the contract code and comments within the code for additional context
