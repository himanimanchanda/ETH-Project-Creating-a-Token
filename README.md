# ETH-Project-Creating-a-Token

# Description
MyToken is a simple Solidity smart contract that defines a custom token named "Himani" with the abbreviation "Manchanda". It supports basic token functionalities such as minting and burning tokens while keeping track of the total supply and individual balances.  This project demonstrates how to create, manage, and manipulate a token's supply on the Ethereum blockchain.

# Getting Started
## Contract Decleration:
     contract MyToken 

## Public Variables:
tokenName: The name of the token (Himani).

tokenAbbrv: The abbreviation of the token (Manchanda).

totalSupply: The total number of tokens in circulation.

    string public tokenName = "Himani";
    string public tokenAbbrv = "Manchanda";
    uint public totalSupply = 0; 

## Mapping:
Here I created variable balances: A mapping from addresses to their respective token balances.

    mapping(address => uint) public balances;

## Mint Function:
This Function increases the total supply and the balance of a specified address.

    function mint(address _address, uint _value) public 
    {
    totalSupply += _value;
    balances[_address] += _value;
    }

## Burn Function:
This function decreases the total supply and the balance of a specified address, with a condition that the balance must be greater than or equal to the amount to be burned.
     // burn function
    function burn (address _address, uint _value) public 
    {
        if (balances[_address] >= _value)
        {
          totalSupply -= _value;
          balances[_address] -= _value;
        }
    }
