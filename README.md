# Create and Mint Token
Creating and minting a token involves deploying a smart contract on a blockchain platform like Ethereum.

## Description
creating and minting tokens involves gas fees (transaction fees) and requires some familiarity with blockchain development and smart contracts. 

## Getting Started

### Executing the Program

Using Remix IDE, a online development environment for Ethereum smart contracts, execute the provided Solidity smart contract by creating a new file, pasting the code, compiling it using the Solidity Compiler tab, deploying it to a chosen Ethereum network via the Deploy & Run Transactions tab, and subsequently interacting with its functions, allowing us to test and validate the contract's behavior comprehensively.

Code:

//SPDX-License-Identifier: MIT
  pragma solidity ^0.8.18;
        
        contract Tokens{

            address public MainOwner;

            constructor(address Owner){
                MainOwner = Owner;
            }
                    mapping (address Address => uint Etherium)public Balances;

                function Minting (address Sender, uint _Etherium)public{
                        if(Sender == MainOwner){
                            Balances[Sender] += _Etherium;
                        }else{
                            revert("Only owner can mint an Etherium");
                        }
                }

                function Burning (address Sender, uint _Etherium)public{
                       if(Balances[Sender] <= _Etherium){
                            revert("You don't have enough balances");
                       }else{
                            Balances[Sender] -= _Etherium;
                       }
                }

                function Transferring(address From, address To, uint _Etherium)public{
                        if(Balances[From] <= _Etherium){
                            revert("You don't have enough balances");
                       }else{
                            Balances[From] -= _Etherium;
                            Balances[To] += _Etherium;
                       }
                }
         }


### Author
Name: Mica Ella Gonzaga Santos

Email: 8213946@ntc.edu.ph
