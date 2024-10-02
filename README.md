# solidity-interview
Solidity interview by level

1. What is the difference between private, internal, public, and external functions?

 - Private: Can only be called from within the contract they are defined in.
 - Internal: Can be called within the contract and derived contracts.
 - Public: Can be called both internally and externally.
 - External: Can only be called from outside the contract.
Example: You use private for functions that should not be accessible from outside or child contracts.
