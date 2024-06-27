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
