| AIP | Title | Author | Type | Category | Status | Created |
|---|---|---|---|---|---|---|
| 9 | Smart Contract | Lucas Nestler | Standards | Monetary Policy | In Progress | 17th of July |

A smart-contract platform outside of side-chaining allows for trustless contracts and allows scaling solutions such as the lightning network to be implemented, allowing transactions to be made and confirmed while being offline.

Of course such an implementation would not come without issues for the average user. The Aptum platform is designed to be as small and efficient as possible, yet another bit would have to be added, to indicate whether or not a transaction is a smart contract interaction. Luckily this can be done by halving the number of possible nonces from 2^40 (1.1 trillion) to 2^39 (550 billion) and using the now-free bit to store the type of the transaction. Since 550 billion still is a sufficiently large number, this should be of no big issue.

Additionally it would be required to write a language which can be compiled and executed by any party within a secure virtual machine while being sufficiently optimised.

Lastly, said contracts need to be stored on-chain to be immutable, which is not possible in the case of Aptum. Since creating a contract-chain is not possible either, implying that there has to be a market with a high fee, giving a reward to those who store a contract and indirectly punishing those who don't. Note that in this approach, there are two seperate kind of identities. One set of code-executing entities and one set of entities interacting with smart-contracts. When having a system in which a different, random, executor is chosen, if the previous one either did not respond or gave a bad response, those who store contracts receive a monetary bonus while those who don't wont.
