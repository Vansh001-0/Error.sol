# Error Handling Contract

This Solidity contract demonstrates basic error handling mechanisms using `require`, `revert`, and `assert`.

## Contract Overview

The contract includes three primary functions to illustrate different error handling techniques:
- `requirecheck(uint i)`: Uses the `require` statement.
- `revertcheck(uint j)`: Uses the `revert` statement.
- `assertcheck()`: Uses the `assert` statement.

## Contract Code

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.7;

contract error{

    function requirecheck(uint i) public pure returns (uint){

        require(i <= 10, "No is greater than 9");
        
        return i;

    }

    function revertcheck(uint j) public pure returns (uint){

        if(j >= 10){
            revert("j is greater than 9");
        }

        return j;

    }

    uint public k = 121;
    function assertcheck() public view{
        
        assert(k <= 10);

    }

}
```

## Usage

Deploy the contract to an Ethereum-compatible blockchain and call the functions as needed to see the error handling in action.

### Example

```javascript
const ErrorHandlingContract = await error.deployed();

// Test requirecheck
try {
    await ErrorHandlingContract.requirecheck(11);
} catch (error) {
    console.error(error.message); // "No is greater than 9"
}

// Test revertcheck
try {
    await ErrorHandlingContract.revertcheck(10);
} catch (error) {
    console.error(error.message); // "j is greater than 9"
}

// Test assertcheck
try {
    await ErrorHandlingContract.assertcheck();
} catch (error) {
    console.error(error.message); // assertion error
}
```

## License

This project is licensed under the MIT License.
