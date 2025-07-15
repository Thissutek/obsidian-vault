2025-07-15 13:46

Status:

Tags:[[Dao]] [[Proxy Patterns]]

## Dao Edgecase
With the idea of DAO governance and immutable smart contracts here is a edge case. 

Scenario
DAO governance votes to have an upgrade, the current smart contract doesn't implement this upgrade cause it can't it uses proxy patterns to create the a new contract that links to the old one, but this can only be handled by the developer. This breaks that trust.

DAO wants upgrade --> But original contract has no upgrade mechanism -> stuck forever 

OR

--> Need Human Developer to write new contract --> Breaks Trustlessness

## References 