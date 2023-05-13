# Blockchains

## What does a block look like?

```
block_1038 = {
 'index': 1038,
 'timestamp': "2020-02-25T08:07:42.170675",
 'data': [
 {
 'sender': "bob",
 'recipient': "alice",
 'amount': "$5",
  }
 ],
 'hash': "83b2ac5b",
 'previous_hash': "2cf24ba5f"
}
```

## Immutability and the importance of hashes

Each block contains within itself the hash of the previous block, forming a chain.

## A basic blockchain in Python

### Representing a blockchain using a class

``` python
class Blockchain(object):
    def __init__ (self):
        self.chain = []
    
    def new_block(self):
    # Generates a new block and adds it to the chain
    pass

    @staticmethod
    def hash(block):
    # Hashes a Block
    pass

    def last_block(self):
    # Gets the latest block in the chain
    pass
```

### Supporting transactions

``` python
def __init__ (self):
    self.chain = []
    self.pending_transactions = []
```

``` python
def new_transaction(self, sender, recipient, amount):
    # Adds a new transaction to the list of pending transactions
    self.pending_transactions.append({
    "recipient": recipient,
    "sender": sender,
    "amount": amount,
    })
```

### Adding blocks

```python
import json

from datetime import datetime
from hashlib import sha256


class Blockchain(object):
    def __init__(self):
        self.chain = []
        self.pending_transactions = []

        # Create the genesis block
        print("Creating genesis block")
        self.new_block()

    def last_block(self):
        # Returns the last block in the chain (if there are blocks)
        return self.chain[-1] if self.chain else None

    def new_block(self, previous_hash=None):
        block = {
            'index': len(self.chain),
            'timestamp': datetime.utcnow().isoformat(),
            'transactions': self.pending_transactions,
            'previous_hash': previous_hash,
        }
        # Get the hash of this new block, and add it to the block
        block_hash = self.hash(block)
        block["hash"] = block_hash

        # Reset the list of pending transactions
        self.pending_transactions = []
        # Add the block to the chain
        self.chain.append(block)

        print(f"Created block {block['index']}")
        return block

    @staticmethod
    def hash(block):
        # We ensure the dictionary is sorted or we'll have inconsistent hashes
        block_string = json.dumps(block, sort_keys=True).encode()
        return sha256(block_string).hexdigest()
```
