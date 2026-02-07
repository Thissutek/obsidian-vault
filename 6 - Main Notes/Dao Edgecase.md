2025-07-15 13:46

Status:

Tag: [[Software Engineering]] [[Web3 & Blockchain]] [[Dao]] [[Proxy Patterns]]

## Dao Edgecase
With the idea of DAO governance and immutable smart contracts here is a edge case. 

Scenario
DAO governance votes to have an upgrade, the current smart contract doesn't implement this upgrade cause it can't it uses proxy patterns to create the a new contract that links to the old one, but this can only be handled by the developer. This breaks that trust.

DAO wants upgrade --> But original contract has no upgrade mechanism -> stuck forever 

OR

--> Need Human Developer to write new contract --> Breaks Trustlessness


### Summary
Human intervention is needed for the upgrade because someone has to write the code, deploy it, and audit it 

But DAO controls whether to use the code, when to activate it, features to enable, and how to configure it. 
## References 