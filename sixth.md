# Part6
------
## Reward
The reward is just a coinbase transaction. When a mining node starts mining a new block, it takes transactions from the queue and prepends a coinbase transaction to them. The coinbase transaction’s only output contains miner’s public key hash.
##### Blockchain.FindUnspentTransactions 
the main function that finds transactions with unspent outputs. It’s this function where the iteration of all blocks happens.
##### Blockchain.FindSpendableOutputs  
this function is used when a new transaction is created. If finds the enough number of outputs holding required amount. Uses Blockchain.FindUnspentTransactions.
##### Blockchain.FindUTXO 
finds unspent outputs for a public key hash, used to get balance. Uses Blockchain.FindUnspentTransactions.
##### Blockchain.FindTransaction 
finds a transaction in the blockchain by its ID. It iterates over all blocks until finds it.
## Merkle Tree
Merkle trees are used by Bitcoin to obtain transactions hash, which is then saved in block headers and is considered by the proof-of-work system. Until now, we just concatenated hashes of each transaction in a block and applied SHA-256 to them. This is also a good way of getting a unique representation of block transactions, but it doesn’t have benefits of Merkle trees.
The script is actually stored in two parts:
1)The first piece, <signature> <pubKey>, is stored in input’s ScriptSig field.
2)The second piece, OP_DUP OP_HASH160 <pubKeyHash> OP_EQUALVERIFY OP_CHECKSIG is stored in output’s ScriptPubKey.

```sh

```
