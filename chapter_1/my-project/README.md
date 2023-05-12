# Getting the Bitcoin price

``` bash
cd $(git rev-parse --show-toplevel)
cd chapter_1/my-project
poetry shell
poetry update package
poetry run python my_project/current_price.py
```
