![roulette_action](https://user-images.githubusercontent.com/29624403/50574000-1d042a80-0e22-11e9-9271-4a7b937b3178.gif)

Roulette on Ethereum https://roulethereum.herokuapp.com/ (this is old version)


## Random Number Generation is NOT secure !
This contract uses the blockhash for creating a random number, and it is NOT secure.
```solidity
uint public winner;

// create random number (0 ~ (userNumber-1) ) 
function getBlockHash() public{
    uint userNumber = 4; // 0 ~ 3
    bytes32 myblockhash = blockhash(block.number - 1);
    uint mywinner = uint(myblockhash) % (userNumber);
    winner = mywinner;
}
```
