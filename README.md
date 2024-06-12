# ETH PROOF: Beginner EVM Course Project 
## MyToken Smart Contract

This Solidity program is a simple implementation to demonstrate the basic functionalities of an ERC-20-like token on the Ethereum blockchain. This repository contains the MyToken smart contract, including functionalities for mining and burning token.
### Executing program

To run this program, I used Remix, an online Solidity IDE. The Remix website at https://remix.ethereum.org/#lang=en&optimize=false&runs=200&evmVersion=null&version=soljson-v0.8.18+commit.87f61d96.js.

1. Primarily , created a new workspace naming Solidity_Assignment while intializing git with it and then created a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., Mytoken.sol). 

```javascript
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

/*
       REQUIREMENTS
    1. Your contract will have public variables that store the details about your coin (Token Name, Token Abbrv., Total Supply)
    2. Your contract will have a mapping of addresses to balances (address => uint)
    3. You will have a mint function that takes two parameters: an address and a value. 
       The function then increases the total supply by that number and increases the balance 
       of the “sender” address by that amount
    4. Your contract will have a burn function, which works the opposite of the mint function, as it will destroy tokens. 
       It will take an address and value just like the mint functions. It will then deduct the value from the total supply 
       and from the balance of the “sender”.
    5. Lastly, your burn function should have conditionals to make sure the balance of "sender" is greater than or equal 
       to the amount that is supposed to be burned.
*/

contract MyToken {

    // public variables here
    string public  tokenName = "Jay_token";
    string public  tokenAbbrv =  "JAY";
    uint public totalSupply =0;
    
    // mapping variable here
    mapping(address => uint) public  balances;

    // mint function
    function mint(address _address, uint _value) public {
        totalSupply += _value;
        balances[_address] += _value ;
    }

    // burn function
    function  burn(address _address, uint _value) public {
        if(balances[_address] >= _value){
        totalSupply -= _value;
        balances[_address] -= _value ;
        }
       
    }
}

```

2. To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar.While making sure the "Compiler" option is set to "0.8.18", and then clicked on the "Compile Meta_Project2.sol" button.

3. Once my code compiled succesfully, I deployed the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Selected the "Meta_Project2" contract from the dropdown menu, and then clicked on the "Deploy" button.

## Authors
JAY AGARWAL 
[jayagarwal164@gmail.com]


## License

This project is licensed under the [jay Agarwal] 
