# DegenToken Smart Contract
The DegenToken contract is an ERC20 token smart contract that enables various functionalities for players in the Degen Gaming platform. The contract is designed to provide the following features:

```
function mintTokens(address to, uint amount)
```
The platform owner can create new tokens and distribute them as rewards to players. Only the contract owner has the authority to mint tokens, which is verified using a require function.

```
function transferTokens(address receiver, uint amount)
```
Players can transfer their tokens to others. They can initiate token transfers to any address by specifying the recipient and the amount of tokens they wish to transfer.

```
function checkBalance()
```
Players can check their token balance at any time by calling the checkBalance function. It returns the balance of tokens held by the caller's address.

```
function addItem(string memory item, uint price)
```
The owner can add game items which can be purchased by the players if they have sufficient funds and the required allowance to spend the given funds

```
function getPrice(string memory item)
```
The players can get the price of the items that are available in the menu using this function.

```
function burnTokens(uint amount)
```
Any token holder can burn their own tokens if they are no longer needed. The burnTokens function allows token holders to burn a specific amount of tokens from their own balance.

## Importing Dependencies

You have to import the following dependencies to run and deploy this smart contract

```solidity
import "@openzeppelin/contracts/token/ERC20/ERC20.sol";
import "@openzeppelin/contracts/access/Ownable.sol";
import "@openzeppelin/contracts/token/ERC20/extensions/ERC20Burnable.sol";
```

## Compiling and Deploying

Compile and Deploy the smart contract using Remix IDE and you can then interact with the various functions present and burn and mint DegenTokens
