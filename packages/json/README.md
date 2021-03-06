# SolDoc JSON theme

A simple markdown theme for SolDoc.

## Example

The following solidity code:
```Solidity
pragma solidity 0.4.19;

import 'zeppelin-solidity/contracts/ownership/Ownable.sol';

/// @title A simulator for Bug Bunny, the most famous Rabbit
/// @author Warned Bros
/// @notice You can use this contract for only the most basic simulation
/// @dev All function calls are currently implement without side effects
contract BugsBunny is Ownable{
    /// @author Bob Clampett
    /// @notice Determine if Bugs will accept `(_food)` to eat
    /// @dev String comparison may be inefficient
    /// @param _food The name of a food to evaluate (English)
    /// @return true if Bugs will eat it, false otherwise
    function doesEat(string _food) external pure returns (bool) {
        return keccak256(_food) == keccak256("carrot");
    }
}
```

Produces the following output:

```JSON
{
  "filepath": "contracts/BugsBunny.sol",
  "contractName": "BugsBunny",
  "info": {
    "constructor": null,
    "events": {
      "OwnershipTransferred(address,address)": {
        "anonymous": false,
        "name": "OwnershipTransferred",
        "params": {
          "previousOwner": {
            "indexed": true,
            "type": "address"
          },
          "newOwner": {
            "indexed": true,
            "type": "address"
          }
        }
      }
    },
    "fallback": null,
    "methods": {
      "doesEat(string)": {
        "constant": true,
        "name": "doesEat",
        "outputs": {
          "output_0": {
            "type": "bool"
          }
        },
        "payable": false,
        "stateMutability": "pure",
        "params": {
          "_food": {
            "type": "string",
            "details": "The name of a food to evaluate (English)"
          }
        },
        "author": "Bob Clampett",
        "details": "String comparison may be inefficient",
        "return": "true if Bugs will eat it, false otherwise",
        "notice": "Determine if Bugs will accept `(_food)` to eat"
      },
      "owner()": {
        "constant": true,
        "name": "owner",
        "outputs": {
          "output_0": {
            "type": "address"
          }
        },
        "payable": false,
        "stateMutability": "view",
        "params": {},
        "executionCost": 526
      },
      "transferOwnership(address)": {
        "constant": false,
        "name": "transferOwnership",
        "outputs": {},
        "payable": false,
        "stateMutability": "nonpayable",
        "params": {
          "newOwner": {
            "type": "address",
            "details": "The address to transfer ownership to."
          }
        },
        "details": "Allows the current owner to transfer control of the contract to a newOwner.",
        "executionCost": 22788
      }
    },
    "author": "Warned Bros",
    "title": "A simulator for Bug Bunny, the most famous Rabbit",
    "executionCost": 20502,
    "deploymentCost": 105000
  },
  "options": {}
}
```
