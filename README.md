
# MyToken Smart Contract

This repository contains the Solidity code for the MyToken smart contract. This contract implements a basic token system with functionalities to mint and burn tokens. It is written in Solidity version 0.8.26 and is intended for deployment on the Ethereum blockchain.
## Getting Started

### Executing Program
1. Open Remix IDE or your preferred development environment.
2. Copy the MyToken contract code into a new Solidity file (e.g., MyToken.sol).
3. Compile the contract using Solidity version 0.8.26.
4. Deploy the contract to a local blockchain or any Ethereum testnet/mainnet.


```
pragma solidity >=0.6.12 <0.9.0;

// SPDX-License-Identifier: MIT

contract CustomToken {
    // State variables
    string public name = "META";
    string public symbol = "MTA";
    uint256 public supply = 0;

    // Balances mapping
    mapping(address => uint256) public accountBalances;

    // Function to mint tokens
    function issueTokens(address recipient, uint256 amount) public {
        supply += amount;
        accountBalances[recipient] += amount;
    }

    // Function to burn tokens
    function destroyTokens(address holder, uint256 amount) public {
        require(accountBalances[holder] >= amount, "Not enough tokens to burn");
        supply -= amount;
        accountBalances[holder] -= amount;
    }
}

```
## Authors

Aditya Upadhyay
- [@adtiyaupadhyay](https://github.com/adtiyaupadhyay)


## License

This project is licensed under the MIT License - see the LICENSE file for details.

