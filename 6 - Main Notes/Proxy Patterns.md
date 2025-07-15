2025-07-15 13:23

Status:

Tags: [[Dao]] [[Web3]]

## Proxy Patterns
A way for smart contracts to be upgraded without having to start a new contract. Basically creating the upgrades at different locations and having it point towards those proxies.

### Explanation
**Basic Problem**
Normal smart contract --> Deployed to Address Ox123...... --> Immutable forever

If you want to change anything you need:
- Deploy a new contract to Ox456
- Migrate all user data manually
- Tell all users to use new address 
- Tell all users to use new address
- Lose all integrations/partnerships

**Proxy Solution**
Proxy Pattern: 
Proxy Contract at Ox123 --> Points to --> Logic Contract at Ox456
								|
								|
					When upgrade needed: 
					Points to --> New Logic Contract at Ox789
## References 
