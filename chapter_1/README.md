# Getting Ready for Application Development

## Installing Poetry

``` bash
curl -sSL https://install.python-poetry.org | python3 -
export PATH="/Users/usr/.local/bin:$PATH"
```

[Poetry Documentation](https://python-poetry.org/docs/)

## Creating a Python project with Poetry

``` bash
poetry new my-project
```

## Installing dependencies

``` bash
poetry add requests
```

## Activating the virtualenv

``` bash
poetry shell
```

## Example

* [Getting the Bitcoin price](my-project)
