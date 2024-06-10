TOKEN CREATION 
This Solidity program is based on token creation. In this program we have created a smart contract that will have the four requirements of the project that were mentioned.

DESCRIPTION 
This program is a simple contract written in Solidity, In this program we will create a contract that will include  public variables that will store the details about our coin such as token name , token abbrv..
and total supply. After this contract will have a mapping of addresses to balances (address => uint). A mint function and burn function will be created with two parameters address and value  to either
increases the total supply by that number and  increases the balance of the address by that amount or  It will then deduct the value from the total supply and from the balance of the address.
A condition is set for burn function so that it does not burn more than the amount we have.


GETTING STARTED 

EXECUTING PROGRAM 

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension . Copy and paste the following code into the file:
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.18;

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
    string public myToken="Hybe";
    string public myAbbr="TMA";
    uint public totalSupply=0;

    // mapping variable here
    mapping (address => uint) public balances;

    // mint function
    function mint (address add , uint value) public 
    {
        totalSupply += value;
        balances[add] += value;
    }

    // burn function
    function burn (address add , uint value) public 
    {
        if (balances[add] >= value) {
        totalSupply -= value;
        balances[add] -= value;
        }
    }
}


To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.4" (or another compatible version), and then click on the "Compile etherum beginner assignment.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "etherum beginner assignment" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it by calling the mint and burn function . click on the mint function and pass the address and value . Finally, click on the "transact" button to execute the function and retrieve the total supply.

License
This project is licensed under the MIT License - see the LICENSE.md file for details
