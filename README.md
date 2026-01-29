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

### Nested Mapping Practice
This is a practive mapping from address to string and to boolen

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.26;

contract NestedMappingPractice {

    //Declare a state variale as nested mapping datatype

    mapping (address => mapping (string => bool)) private attendanceSheet;

    //Declare a function to set values for a students
    function setAttendance (address _addr, string memory _name, bool _isPresent) public {
        attendanceSheet[_addr][_name] = _isPresent;
    }


    //Declare a function to get the value for a student
    function getAttendance (address _addr, string memory _name) public view returns (bool) {
        return attendanceSheet[_addr][_name];
    }

    // Declare a function to toggle the value for  a student
    function toggleAttendance (address _addr, string memory _name) public {
        attendanceSheet[_addr][_name] = !attendanceSheet [_addr][_name];
    }

}
```

### Nested Mapping using struct
This is a practive mapping from address to string and to boolen

```solidity

// SPDX-License-Identifier: MIT
pragma solidity ^0.8.26;

contract MappingStructPractice {

    // Declare a student structure having three attriutes
    struct Student{
        string name;
        string email;
        bool isAttended;

    }


    // Declare a mapping from address to struct Student
    mapping (address => Student) private students;

    // Declare a function to set student attendance 
    function setStudentAttendance (address _addr, string memory _name, string memory _email, bool _isAttended) public {
        students[_addr] = Student ({
            name: _name,
            email: _email,
            isAttended: _isAttended
        });

}
    // Declare a funtion to get studetn attendance info
    function getStudentAttendance (address _addr) public view returns (string memory, string memory, bool) {
     return (students[_addr].name,
            students[_addr].email, 
            students[_addr].isAttended
            );
}

// Declare a funtion to toggle the student attendance
    function toggleStudentAttendance (address _addr) public {
        students[_addr].isAttended = !students[_addr].isAttended;   
}

}
}
```

```
