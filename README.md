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

7. What are the challenges of creating a random number on the blockchain?
 - Blockchain is deterministic, making true randomness difficult. Miners could potentially manipulate the outcome if they can influence the source of randomness (like block hashes).

8. What is the difference between a Dutch Auction and an English Auction?
 - Dutch Auction: Starts with a high price that decreases over time until a bid is made.
 - English Auction: Starts with a low price and participants bid higher until no one outbids.

9. What is the difference between transfer and transferFrom in ERC20?
- Transfer: Moves tokens directly from the sender's account.
- TransferFrom: Moves tokens from one account to another on behalf of the token owner, requiring prior approval.

10. Which is better to use for an address allowlist: a mapping or an array? Why?
 - Mapping is better because it provides O(1) lookup time for checking if an address is allowed, while an array requires O(n) time.

11. Why shouldn’t tx.origin be used for authentication?
- `tx.origin` refers to the original caller and can be manipulated in the case of phishing attacks, leading to potential security vulnerabilities.

12. What hash function does Ethereum primarily use?
- Ethereum primarily uses Keccak-256, commonly referred to as SHA3.

13. How much is 1 gwei of Ether?
- 1 gwei is 0.000000001 Ether (10^-9 Ether).

14. How much is 1 wei of Ether?
- 1 wei is 0.000000000000000001 Ether (10^-18 Ether).

15. What is the difference between assert and require?
 - Require is used to check conditions before execution (refunds gas on failure).
 - Assert is used for checking invariants, typically for internal errors, and consumes all gas if failed.

