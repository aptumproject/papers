| AIP | Title | Author | Type | Category | Status | Created |
|---|---|---|---|---|---|---|
| 11 | Sharding | Lucas Nestler | Standards | Network | In Progress | 17th of July |

To successfully implement sharding, all tasks the participants in the network have, have to be splitted to dedicated groups of nodes. While this does create additional overhead, it also enables scalability, to increase the speed in addition to the security of the network with the number of nodes. Those are the four possible tasks one could perform for the network:
- **Gathering**: Receiving data, checking it for syntax and grouping it into blocks.
- **Validating**: Confirming the monetary movement of a transaction and remove invalid data from a block what's invalid from a block. 
- **Witnessing**: Voting for blocks to ensure a minimum stake is behind it.
- **Execution**: Running a smart-contract (interactions) from a transaction.
- **Checkpointing**: Remebering the entire state, saving it and adding blocks to it

**Terminology**
- **Layer**: A group of nodes performing similar tasks.
- **Blocktime**: The size of the intervall between broadcasting data up a layer.
- **Period**: A period is the time it takes for data from arriving at a gathering node to their inclusion in a checkpoint. Due to the usage of four layers, it is equal to 4*Blocktime.

Each of those tasks is important, as they all display a fundamental functionality in the blockchain ecosystem. Gathering and grouping data to broadcast it to the next layer allows for reduced latencies and optimised package-based data transmission, it also makes sure the basic transaction layout and syntax is correct, so that spam of useless data or even a DoS-attack does not reach any of the higher layers. Validating is required to ensure someone has the funds needed for a transaction, without it, anyone could spend any funds. Witnessing allows to increase the security of the validation layer, since the number of witnesses required to pass a block can be set to any arbitrary number. Without smart-contract execution, smart-contracts could not be used. Execution is bypassed if it is not needed. Checkpointing nodes are the most-trusted nodes of the network, which are allowed to summarise all data and act as reliable memory-cells.

Due to the high reliability requirement, checkpointing nodes are not changed frequently. There is an arbitrary number of nodes, for example 100, which are required to store the entire state. Those are the most-trusted nodes in the network with the highest cumulative weight, where the weight is calculated by taking votes, trustscore and stake in account. Out of those 100 nodes, the top 10 nodes 
will always be a checkpointing node, for as long as they have their spot. Another 10 nodes are randomly selected out of the other 100 nodes. Those 20 nodes are then held accountable for storing all the data and updating it for the next block. If they do not store the data, they will not receive rewards and may get reduced trustscores due to bad (no) responses.

In contrast to checkpointing, a task that is strongly rewarded, is not wanted to be performed by everyone. Some nodes may have weak RAM and can only perform gathering, while others have a lot of resources they want to lend out, making them execution nodes. That is why the rest of the nodes are not sampled randomly but instead every node can place a flag, what their prefered position is. A subgroup of the weight-based ranking is then used to determine who will receive a specific position. This allows nodes which have acquired more trust to be more often in the sample than rather new ones, while still giving them a chance to take their place in the consensus. 

Participating in the consensus requires some kind of reward, especially for work requiring a lot of energy, such as the execution of smart-contracts. That's why gatherers, validators and witnesses receive eigentrust score points for participating. In case AIP-04: Deflation is implemented, those nodes can also work their "negativity credits" off by being active, which reduces the amount their wallets gets decreased by every block; when sufficiently active, no slashing at all will take place. For executors on the other hand, not just the previous activity-based bonus is active but they will also receive resource-credits (AIP-10a: Resource-based Feelessness) or fees for executing smart contracts (AIP-10b: Sidechain-based Feelessness). This system allows every party to be sufficiently rewarded while also giving them a chance to rise up to the top checkpointers to receive rewards.




