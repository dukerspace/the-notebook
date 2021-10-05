# Soldility

- Common function types
  - public : anyone can call this function
  - private : only this contract can call this function
  - view : this function returns data and does not modify the contracts data
  - constant : this function returns data and does not modify the contracts data
  - pure : function will not modify or even read the contract's data
  - payable : when someone call this function they might send ether along

# There are 3 types of variables in Solidity

- local
  - declared inside a function
  - not stored on the blockchain
- state
  - declared outside a function
  - stored on the blockchain
- global (provides information about the blockchain)
