// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract ErrorHandling {
    address public owner;
    uint256 public value;

    constructor() {
        owner = msg.sender;
        value = 0;
    }

    // Function that uses require() to check conditions
    function setValue(uint256 _value) public {
        // Ensure the value is positive
        require(_value > 0, "Value must be greater than 0");
        value = _value;
    }

    // Function that uses assert() to check for invariants
    function incrementValue(uint256 _increment) public {
        value += _increment;

        // Assert to ensure the value is always positive after increment
        assert(value > 0);
    }

    // Function that uses revert() for custom error handling
    function resetValue() public {
        // Only the owner can reset the value
        if (msg.sender != owner) {
            revert("Only the owner can reset the value");
        }
        value = 0;
    }

    // Function to demonstrate require() with multiple conditions
    function transferOwnership(address newOwner) public {
        // Ensure the new owner address is valid and the sender is the current owner
        require(newOwner != address(0), "New owner address must be valid");
        require(msg.sender == owner, "Only the current owner can transfer ownership");

        owner = newOwner;
    }
}
