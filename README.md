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

## Mapping Practice ##

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.26;

contract MappingPractice {

    //Declare a state variable to sae the value 
    mapping (address => string) private students;


    // Declare a function to set value for a student
    function setStudent (address _addr, string memory _name) public {
        students[_addr] = _name;
    }

    //Declare a function to get the value from state variable
    function getStudent (address _addr) public view returns ( string memory) {
        return students[_addr];
    }

    //Declare a function to remove the student
    function removeStudent (address _addr) public {
        delete students[_addr];

    }

```



}
