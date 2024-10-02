# solidity-interview
Solidity interview by level

1. What is the difference between private, internal, public, and external functions? 
 - `Private`: Can only be called from within the contract they are defined in.
 - `Internal`: Can be called within the contract and derived contracts.
 - `Public`: Can be called both internally and externally.
 - `External`: Can only be called from outside the contract.

Example: You use private for functions that should not be accessible from outside or child contracts.


2. Approximately, how large can a smart contract be? 
Ethereum smart contracts can be up to `24 KB` in size. If a contract exceeds this size, it cannot be deployed.

3. What is the difference between create and create2? 
 - `create`: Generates a contract at a random address based on the deployer and nonce.
 - `create2`: Allows specifying a salt, making the resulting address predictable, useful for counterfactual contract deployments.

4. What major change with arithmetic happened with Solidity 0.8.0? 
Solidity 0.8.0 introduced automatic overflow and underflow checks for arithmetic operations, whereas earlier versions required libraries like SafeMath.

5. What special CALL is required for proxies to work? 
`DELEGATECALL` is the special call, which allows a proxy contract to execute code in the context of another contract while preserving the caller's storage and context.

6. How do you calculate the dollar cost of an Ethereum transaction? 
 - The cost is calculated by multiplying `Gas Used` by `Gas Price` (in gwei), then converting that to Ether and using the ETH/USD exchange rate to convert it into dollars. 
Example: Transaction uses `21,000` gas at 100 gwei gas price, ETH is $2000. Cost = 21,000 * 100 gwei / 1e9 = 0.0021 ETH. In USD, that’s 0.0021 * 2000 = $4.2.
