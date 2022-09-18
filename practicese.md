```js
// SPDX-License-Identifier: GPL-3.0
pragma solidity >=0.7.0 <0.9.0;

contract MyContract {
    uint256 public peopleCount = 0;
    mapping(uint => Person) public people;

    struct Person {
        uint id;
        string firstName;
        string lastName;
    }
    function addPerson(string memory _firstName, string memory _lastName) public {
        peopleCount +=1;
        people[peopleCount] = Person(peopleCount, _firstName, _lastName);
    }
} 
```
