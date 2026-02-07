2025-07-15 10:17

Status:
Tag: [[Software Engineering]] [[Web3 & Blockchain]] [[Smart Contract ISA]] [[Web3]] [[Solidity]]

# ERC

## What is it?
ERC stands for Ethereum Request for Comments. They are basically technical standards that define how a smart contract should behave on the blockchain. In other words they are basically kind of like API's or protocols that ensure different apps can work together. 

### ERC-20: Fungible Tokens
**What it is:** ERC-20 is the standard for creating fungible tokens where each unit it identical and interchangeable

**Example:** Think of dollars in your bank account. One dollar is exactly the same as any other dollar. You can split, combine and exchange them freely.

**Common Examples:** USDC (stablecoin), DAI (Decentralized stablecoin), LINK (Chainlink token), Majority of cryptocurrency tokens you can see in the exchange

```
// Basic functions every ERC-20 token must have
function totalSupply() public view returns (uint256)
function balanceOf(address account) public view returns (uint256)
function transfer(address recipient, uint256 amount) public returns (bool)
function approve(address spender, uint256 amount) public returns (bool)
function transferFrom(address sender, address recipient, uint256 amount) public returns (bool)
```
## ERC-721
**What it is:** This is the standard for creating non-fungible tokens - unique, indivisible tokens where each one is different.

**Example:** They are like concert tickets, art pieces, or house deeds. Each one is unique and can't be split into smaller pieces.

```
// Basic functions every ERC-721 token must have
function balanceOf(address owner) public view returns (uint256)
function ownerOf(uint256 tokenId) public view returns (address)
function transferFrom(address from, address to, uint256 tokenId) public
function approve(address to, uint256 tokenId) public
function setApprovalForAll(address operator, bool approved) public
```
## When to Use
**ERC-20**
- Creating a currency or payment system
- Building governance tokens
- Making reward/loyalty points
- You need tokens that can be easily split and combined

**ERC-721**
- Creating unique collectibles
- Building gaming items
- Making certificates or credentials
- Each token represents something distinct