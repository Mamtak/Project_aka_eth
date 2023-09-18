# Project_aka_eth

This beginner-level Solidity Smart Contract serves as an introduction to the language. 

# Definition

The Name, SecondaryName, and Supply are three state variables included in the contract. 

It has a mapping named balances that connects addresses to the corresponding balances (Address => uint). 

Additionally, it has two features—deposit and withdraw—that function as their names would imply. Deposit adds a specific amount that is supplied to the function as a parameter, increasing the supply as well as the user's Total_balance. 

The Withdraw function determines whether the user running the function has enough tokens, and if so, it subtracts that number of tokens from both the supply and the user's total_balance. It uses the keyword require, which results in an error if the requisite is not satisfied.



## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. Go to https://remix.ethereum.org/.

Once you are on the website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., Test.sol). Copy and paste the following code into the file:

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

contract Atm {

    // public variables here

    string public Name="bird";
    string public SecondaryName="flower";

    uint public Supply = 0;
    
    // mapping variable here

    mapping(address => uint )public Total_Balance;

    // mint function

    function desposit (address _address,uint _value) public 
    {
        Supply += _value;
       Total_Balance[_address] += _value;
    }

    // burn function
     function withdraw (address _address,uint _value) public 
    {
        if(Total_Balance[_address] >= _value)
        {
        Supply -= _value;
        Total_Balance[_address] -= _value;
        }
    }

}


```

Click the "Solidity Compiler" tab in the left-hand sidebar to compile the code. Click the "Compile Test.sol" button after making sure the "Compiler" option is set to "0.8.18" (or another compatible version).

Using the "Deploy & Run Transactions" tab in the left-hand sidebar, you can deploy the contract after the code has been compiled. From the drop-down menu, choose the "Atm" contract, and then press the "Deploy" button.

You can communicate with the contract after it has been deployed by executing the Deposit or Withdraw function. Click the "Deposit" button after selecting the "Atm" contract in the left-sidebar. 

## Help

To prevent version dependant errors, make sure the compiler option is set to 0.8.18. 
```
pragma solidity ^0.8.18
```

## Authors

  
[Mamta Kaundal]


## License

This project is licensed under the MIT License - see the LICENSE.md file for details
