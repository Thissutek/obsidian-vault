2025-07-15 12:47

Status:

Tags: [[Web3]]

## Dao
Community owned platform
**Traditional Company Structure**
CEO makes decisions --> Board approves --> Company executes

**DAO structure**
Token Holders propose --> Community Votes --> Smart contract executes

### Important Note
When developing a smart contract with a DAO governance it needs to be planned from day 1 as [[Smart Contract ISA]] can't be changed once deployed. Choices that DAO governance can make is programmed into the Smart contract so new upgrades aren't possible or at least its limited 

### Scale of Possible upgrades for DAO governance
- New features (loyalty programs, subscriptions, NFT's)
- Algorithm changes Complete replacement of business logic
- Integration changesSwitch oracles, add new data sources
- UI/UX improvements: better batch processing, gas optimization
Not possible
- Core data structure: Can't rearrange existing structure
- Token fundamentals: Can't change total supply, decimals
- Architecture: Can't easily switch from single-contract to multi-contract

**Key Insight**
You must design for upgradeability from day 1. Once deployed you can only upgrade with the constraints you originally built in. 
## References 
[[Proxy Patterns]]
[[Dao Edgecase]]