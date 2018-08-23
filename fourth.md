# Part4
------
## Transactions 1
The only purpose of blockchain is to store transactions in a secure and reliable way, so no one could modify them after they are created.A transaction is a combination of inputs and outputs.Inputs of a new transaction reference outputs of a previous transaction.When a miner starts mining a block, it adds a coinbase transaction to it. A coinbase transaction is a special type of transactions, which doesn’t require previously existing outputs. It creates outputs (i.e., “coins”) out of nowhere.This is the reward miners get for mining new blocks.

From now on, every block must store at least one transaction and it’s no more possible to mine blocks without transactions. This means that we should remove the Data field of Block and store transactions instead. Before creating new outputs, we first have to find all unspent outputs and ensure that they store enough value. This is what FindSpendableOutputs method does. After that, for each found output an input referencing it is created. Next, we create two outputs:
1)One that’s locked with the receiver address. This is the actual transferring of coins to other address.
2)One that’s locked with the sender address. This is a change. It’s only created when unspent outputs hold more value than required for the new transaction. Remember: outputs are indivisib

```sh

```
