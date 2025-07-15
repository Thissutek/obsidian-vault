2025-07-15 10:44

Status:
Tag: [[Solidity]] [[Web3]]
## What is it?
A Reentrancy Attack occurs when a malicious contract calls back into your contract before the first function has finished executing. This can allow attackers to drain funds or manipulate state in unexpected ways.

## How it works?
Imagine a contract has a withdrawal function that first sends Ether to the caller, then updates their balance. A malicious contract can implement a fallback function that calls your  withdrawal function again before the balance is updated. This creates a loop where they can withdraw more then they should.

## Prevention
Use the 'checks-effects-interactions' pattern - perform all checks first, update state variables second, and interact with external contracts last. Modern solutions include reentrancy guardsand using OpenZeppelin's Reentrancy Guard