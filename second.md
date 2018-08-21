# Proof-of-Work
A key idea of blockchain is that one has to perform some hard work to put data in it. It is this hard work that makes blockchain secure and consistent.This mechanism is  one has to work hard to get a reward and to sustain their life. In blockchain, some participants  of the network work to sustain the network, to add new blocks to it, and get a reward for their work. As a result of their work, a block is incorporated into the blockchain in a secure way, which maintains the stability of the whole blockchain database. The finding a proof is the actual work.Proof-of-Work algorithms must meet a requirement: doing the work is hard, but verifying the proof is easy. A proof is usually handed to someone else to verify it.

Take some publicly known data.Add a counter to it. The counter starts at 0.Get a hash of the data + counter combination.Check that the hash meets certain requirements.If it does, you’re done.If it doesn’t, increase the counter and repeat the steps 3 and 4. In the original Hashcash implementation, the requirement sounds like “first 20 bits of a hash must be zeros”.In the loop we:
Prepare data.Hash it with SHA-256.Convert the hash to a big integer.Compare the integer with the target.


```sh
import hashlib as hasher
import datetime as date
import sys

nonce = 0

class Block:
  def __init__(self, index, timestamp, data, previous_hash, nonce):
    self.index = index
    self.timestamp = timestamp
    self.data = data 
    self.previous_hash = previous_hash
    self.hash = self.hash_block()
    self.nonce = nonce 
  
  def hash_block(self):
    sha = hasher.sha256()
    sha.update(str(self.index) + 
               str(self.timestamp) + 
               str(self.data) + 
               str(self.previous_hash)+
               hex(nonce))
    return sha.hexdigest()



#creating genesis Block
def create_genesis_block():
  return Block(0, date.datetime.now(), "Genesis Block", "0", 0) 
  #


#adding blocks one-by-one
def next_block(last_block):
  this_index = last_block.index + 1
  this_timestamp = date.datetime.now()
  this_data = "Hey! I'm block " + str(this_index)
  this_hash = last_block.hash
  this_nonce = last_block.nonce
  return Block(this_index, this_timestamp, this_data, this_hash, nonce)


# Create the blockchain and add the genesis block
blockchain = [create_genesis_block()]
previous_block = blockchain[0]

# How many blocks should we add to the chain
#  after the genesis block
num_of_blocks_to_add = 2



# Add blocks to the chain
for i in range(0, num_of_blocks_to_add):
  
 
  
    


  #print("mining the block containing {}".format(block_to_add.data))
  
  target_bits = 24
  #target = 1
   



    # calculate the difficulty target
    #target = 2 ** (256-difficulty_bits)
  target = 2 ** (256-target_bits)
  nonce = 0
  
  while nonce < sys.maxint:
    block_to_add = next_block(previous_block)    
    
    if(long(block_to_add.hash, 16) < target):
      blockchain.append(block_to_add)
      previous_block = block_to_add
      
      break
    else:
      nonce = nonce + 1
  

  print("Block #{} has been added to the blockchain!".format(block_to_add.index))
  print("Previous Hash: {}".format(block_to_add.previous_hash))
  print("Hash: {}".format(block_to_add.hash)) 
  print("data: {}\n".format(block_to_add.data))
  print("nonce: {}\n".format(nonce))









```
