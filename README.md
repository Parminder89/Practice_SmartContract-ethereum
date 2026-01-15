# Practice_SmartContract-ethereum
Repo for Practicing Solidity Smart Contract

## First Smart contract Practice ##

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.26;

contract MyHashString{

    bytes32 private HashString;

    function hasing (string memory _str) public{
        HashString = keccak256(bytes(_str));
    }

    function getDigest () public view returns (bytes32) {
        return HashString;
    }


}


```
