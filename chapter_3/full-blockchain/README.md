# Experimenting with your Blockchain class

``` bash
cd $(git rev-parse --show-toplevel)
cd chapter_3/full-blockchain
poetry shell
python -i full_blockchain/full_blockchain.py
```

``` python
>>> bc = Blockchain()
>>> bc.chain
>>> bc.new_block(previous_hash="80ad...01bd")
```
