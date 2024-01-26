// SPDX-License-Identifier: MIT
pragma solidity ^0.8.18;
contract Donation {
    address immutable public owner;
    mapping (address => uint256)public _Donor;
    constructor ()
    {
        owner =msg.sender;
    }
    function Transfer (uint256 amount) public {
        _Donor[msg.sender] -= amount;
        if (amount>50000000) {
            revert ("you can not transfer this amount");
        }

        }
        
        
    function Receive (uint256 amount) public{
        _Donor [msg.sender] += amount;
        if (amount==0) {
            revert ("you cant receive from zero");
        }
    }
    function showbalance (address ) public view returns (uint256){
        return _Donor[owner];
    }

}
