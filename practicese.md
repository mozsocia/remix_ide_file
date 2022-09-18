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

```js
// Solidity program to
// count number of
// values in a mapping
pragma solidity ^0.4.18;

contract mapping_example {
	
	// Defining structure
	struct Student {

		// Declaring different
		// structure elements
		string name;
		string subject;
		uint8 marks;
	}
	
	// Creating mapping
	mapping (address => Student) public result;
	address[] student_result;
	
	//Function adding values to the mapping
	function adding_values(string _name, string _sub, uint8 _mark) public {
        Student memory stu2 = Student(_name,_sub,_mark);

        result[0xDEE7796E89C82C36BAdd1375076f39D69FafE252] = stu2;

		student_result.push(
		0xDEE7796E89C82C36BAdd1375076f39D69FafE252) -1;

	}
	
	// Function to retrieve
	// values from the mapping
	function get_student_result(
	) view public returns (address[]) {
		return student_result;
	}

	// Function to count number
	// of values in a mapping
	function count_students(
	) view public returns (uint) {
		return student_result.length;
	}
}
```

```js
// SPDX-License-Identifier: GPL-3.0
pragma solidity >=0.7.0 <0.9.0;

contract MyContract2 {
     struct Person {
        uint id;
        string firstName;
        string lastName;
    }

    uint256 public peopleCount = 0;
    mapping(uint => Person) public people;

    address public owner;

    modifier onlyOwner() {
        require(msg.sender == owner);
        _;
    }
    constructor() {
        owner = msg.sender;
    }

   
    function addPerson(string memory _firstName, string memory _lastName) public onlyOwner {
        incrementCount();
        people[peopleCount] = Person(peopleCount, _firstName, _lastName);
    }
    function incrementCount() internal {
        peopleCount +=1;
    }
} 
```
