| AIP | Title | Author | Type | Category | Status | Created |
|---|---|---|---|---|---|---|
| 1 | EigenTrust-P2P | Lucas Nestler | Standards | P2P | In Progress | 4th of July |


### Description
EigenTrust is a reputation management algorithm for peer-to-peer networks, which provides each peer in the network a unique global trust value based on the peer's history of uploads and thus aims to reduce the number of inauthentic data in a P2P network.[1](http://web.archive.org/web/20190627152815/https://en.wikipedia.org/wiki/EigenTrust)

EigenTrust takes the power away from untrusted users, to reduce the impact a malicious node could have. Generally speaking, trust is a resource which is easily lost and hard to be acquired. This allows the network to be more resistant against attacks[2](http://ilpubs.stanford.edu:8090/562/1/2002-56.pdf) while also increasing the average response performance, since an incentive is added to behave honesty. This extends the game-theory of cryptocurrency to the previously-exploitable gossiping of a distributed P2P network. 

Advantages of using the EigenTrust algorithm to create an honesty-rewarding peer-to-peer network include creating accountability in an anonymous network as well as reducing the overhead needed to verify data. Additionally local EigenTrust values can be aggregated to global values, which can be used to form consenus [3, Pages 25ff](https://nem.io/wp-content/themes/nem/files/NEM_techRef.pdf).

The final algorithm which would be used by aptum as well as the calculations necessary for an attack-resilient EigenTrust Variant (called EigenTrust++) can be found here[4](https://www.researchgate.net/profile/Xinxin_Fan3/publication/261093756_EigenTrust_Attack_Resilient_Trust_Management/links/5922a236a6fdcc4443f61a6b/EigenTrust-Attack-Resilient-Trust-Management.pdf).
