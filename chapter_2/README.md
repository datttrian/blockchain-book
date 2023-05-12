# Getting Ready for Application Development

## Project setup

``` bash
poetry new funcoin
cd funcoin
```

## Project Structure

```
.
├── funcoin
│ └── __init__.py
├── pyproject.toml
└── tests
 ├── __init__.py
 └── test_funcoin.py
```

This folder structure is loosely what all modern
Python projects look like. It was defined by PEP (Python Enhancement
Proposal) 518. Poetry enforced this folder structure when you create
a new project

## Hash functions

Hashing is the process of assigning a unique and random value to data. It uses hash functions to generate an identification value for different types of input. Although hashes are not truly unique and random, cryptographic hash functions aim to select values from a large pool to make it highly improbable for two inputs to share the same value in our known universe.

## Example

* [Hashing in Python](hashing-strings)
* [Hashing images](hashing-images)
* [Sending untamperable emails](hashing-emails)
