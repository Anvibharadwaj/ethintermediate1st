# Create Smart Contract using error handling functions.

This Solidity program is a simple "Error Handling" program that demonstrates the basic syntax and functionality of the Solidity programming language. The purpose of this program is to serve as a starting point for those who are new to Solidity and want to get a feel for how it works.

## Description

This program is a simple contract written in Solidity, a programming language used for developing smart contracts on the Ethereum blockchain. The contract has a 4 functions one constructor and 2 state variables. The role of 1st function is one has to add an amount to the cart's balance, and provided the amount is greater than 700.
Role of 2nd function allows the owner to reduce the balance by a specified amount, given certain conditions by using require function.
Usingassert returns the current balance and checks for a critical invariant.
by using last function that includes revert with sepicific if condition owner can change the address and give access to new owner.
This program serves as a simple and straightforward introduction to Solidity programming, and can be used as a stepping stone for more complex projects in the future.

## Getting Started

### Executing program
To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., Errorhandling.sol). Copy and paste the following code into the file:

```
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract purchasingfromcart {
    address private owner;
    uint256 private balance;
    constructor() {
        owner = msg.sender;
        balance = 0;
    }
    function fordiscountoncart(uint256 amount) public {
        require(amount > 700, "Opps! you will not get discount your amount must be greater than 700");
        balance += amount;
        
    }

    function forshopping(uint256 amount) public {
        require(msg.sender == owner, "only owner can go for shopping");
        require(amount >= 100,"Balance must be greater than 100 to get removed from cart");
        balance -= amount;
    }
    function usingassert() public view returns (uint256) {
        assert(balance >= 0);

        return balance;
    }
    function changingownership(address newowner) public {
        require(msg.sender == owner,"only owner can change ownership");
        if (newowner == address(0)){
            revert("Cannot change ownership with 0 as address");
        }
        owner=newowner;
    }
}
```
To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.0" (or another compatible version), and then click on the "Compile errorhandling.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "purchasingfromcart" contract from the dropdown menu, and then click on the "fordiscount" button and transact, to see the value click on usingassert function call.Similarly, for another 3 function i.e. forshopping,changingownership and using assert function one can follow same procedure and you will get appropriate messages accordingly..

##Author
Anvi Bhardwaj
