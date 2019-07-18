| AIP | Title | Author | Type | Category | Status | Created |
|---|---|---|---|---|---|---|
| 8 | Pruning | Lucas Nestler | Standards | Usernames | In Progress | 5th of July |


### Description
Pruning, as seen in cryptocurrencies like aeon or grin, can be used to reduce the size of the database a node has to carry around as well as make sure old or useless data is being removed, so that an attack based on memory-spam requires more resources. In the case of Aptum, a network which is oriented to be as memory-saving as possible, the history is always summarised into a small and easily transferable database. While transactions are reduced to a transaction database, usernames are all added to the username database and never removed. This proposal covers the removal of usernames inside of the aptum protocol, removing all traces of old and unused data.

### Implications
When removing old, balanceless usernames from the database, space-savings of 37 byte per username are possible. While this might not be of real use, the removal of a username also allows it to be re-registered by any user, allowing the username to change its owner frequently without troubles. In combination with AIP-4 (Deflation), the limit of removal can be increased to a number such as 10 XAP, before an account becomes erased and it's funds will be redistributed. This allows the chain to get rid of all old and unaccessed data in a matter of years.
