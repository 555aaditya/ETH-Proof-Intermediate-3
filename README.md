# DegenToken Smart Contract
The DegenToken contract is an ERC20 token smart contract that enables various functionalities for players in the Degen Gaming platform. The contract is designed to provide the following features:

* `Minting new tokens`: The platform owner can create new tokens and distribute them as rewards to players. Only the contract owner has the authority to mint tokens, which is verified using a require function.

* `Transferring tokens`: Players can transfer their tokens to others. They can initiate token transfers to any address by specifying the recipient and the amount of tokens they wish to transfer.

* `Redeeming tokens`: Players can redeem their tokens for items in the in-game store. The contract provides a list of available items that can be redeemed using the corresponding token values.

* `Checking token balance`: Players can check their token balance at any time by calling the checkBalance function. It returns the balance of tokens held by the caller's address.

* `Burning tokens`: Any token holder can burn their own tokens if they are no longer needed. The burnTokens function allows token holders to burn a specific amount of tokens from their own balance.

## Importing Dependencies

You have to import the following dependencies to run and deploy this smart contract

```solidity
import "@openzeppelin/contracts/token/ERC20/ERC20.sol";
import "@openzeppelin/contracts/access/Ownable.sol";
import "@openzeppelin/contracts/token/ERC20/extensions/ERC20Burnable.sol";
```

## Functions Available

`mint`
```solidity
 function mint(address to, uint256 amount) public onlyOwner
```
The `mint` function allows the contract owner to create new tokens and distribute them to specified addresses. It takes two parameters: `to` which will be the receiver's address and `amount` which is the number of tokens to mint. Only the contract owner can call this function.

`transferToken`
```solidity
function transferTokens(address _reciever, uint amount) external
```
The `transferTokens` function enables players to transfer their tokens to others. Players can initiate transfers by providing the recipient's address in `_receiver` and the amount of tokens `amount` to transfer. This function requires that the caller has a sufficient balance of tokens.

`checkBalance`
```solidity
function checkBalance() external view returns(uint)
```
The `checkBalance` function allows players to check their token balance at any time. It returns the balance of tokens held by the caller's address.

`burnTokens`
```solidity
function burnTokens(uint amount) external
```
The `burnTokens` function enables any token holder to burn their own tokens if they are no longer needed. Token holders can specify the amount of tokens `amount` they wish to burn. The function requires that the caller has a sufficient balance of tokens.

`gameStore`
```solidity
function gameStore() public pure returns(string memory) 
```
The `gameStore` function provides information about the available items in the in-game store. It returns a string with the options and their corresponding values. Players can choose from these items to redeem with their tokens.
      
```solidity
return "1. Diamond Player = 200 \n 2. Gold Player = 100 \n 3. Silver Player = 50"
```

`reedemTokens`
```solidity
function reedemTokens(uint choice) external payable
```
The `redeemTokens` function allows players to redeem tokens for items in the in-game store. Players need to provide the choice parameter, representing the sequence number of the desired item to redeem. The function checks the player's token balance and verifies if it is sufficient for the selected item. If the conditions are met, it transfers the corresponding token value to the contract owner.



## Compiling and Deploying

Compile and Deploy the smart contract using Remix IDE and you can then interact with the various functions present and burn and mint DegenTokens
