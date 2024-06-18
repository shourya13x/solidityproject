# MyToken Smart Contract Project

## Overview

This is my project for the Solidity course by Metacrafters. In this project, I have created a smart contract to create and manage a token on the Ethereum blockchain. It includes functionalities like minting, burning, and tracking balances.

## Getting Started

### Prerequisites

- Access [Remix IDE](https://remix.ethereum.org/)
- Modern web browser

### Steps to Run

1. **Create a New File**:
    - Open Remix and create a new file named `MyToken.sol`.

2. **Copy and Paste the Code**:
    ```solidity
    // SPDX-License-Identifier: MIT
    pragma solidity 0.8.18;

    contract MyToken {
        string public tokenName = "BHALU";
        string public tokenAbbrv = "bhai";
        uint public totalSupply = 0;

        mapping(address => uint) public balances;

        function mint(address _address, uint _value) public {
            totalSupply += _value;
            balances[_address] += _value;
        }

        function burn(address _address, uint _value) public {
            if (balances[_address] >= _value) {
                totalSupply -= _value;
                balances[_address] -= _value;
            }
        }
    }
    ```
