# Error.sol

# Solidity Error Handling Contract

This Solidity contract shows how to use error handling: require, revert, and assert.

Contract Overview

The contract error has three functions that use different error handling methods:
requirecheck(uint i)
revertcheck(uint j)
assertcheck()

Functions

requirecheck(uint i)
This function checks if i is less than or equal to 10. If i is greater than 10, it shows an error message "No is greater than 9".


revertcheck(uint j)
This function checks if j is less than 10. If j is 10 or more, it shows an error message "j is greater then 9".

function revertcheck(uint j) public pure returns (uint) {
    if (j >= 10) {
        revert("j is greater then 9");
    }
    return j;
}
assertcheck()
This function checks if k is less than or equal to 10. k is set to 121, so calling this function will cause an error.

uint public k = 121;

function assertcheck() public view {
    assert(k <= 10);
}

How to Use

Deploy the contract using a Solidity environment.
Call requirecheck(uint i) with a value to see the require statement.
Call revertcheck(uint j) with a value to see the revert statement.
Call assertcheck() to see the assert statement with the initial value of k.

License

This project is licensed under the MIT License.






