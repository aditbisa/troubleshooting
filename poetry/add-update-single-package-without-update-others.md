# Add/Update single package without update unrelated packages


## TLDR

1. Update `pyproject.toml` manually.
2. Run `poetry lock --no-update` to update the lock file.
2. Run `poetry install` to update environment with the updated lock file.


## The Story

Poetry tend to update all packages when doing add/update a single package.
And it takes a long time to resolve the dependencies.

Future breaking changes in v2 with `--no-update` as default is in ~~plan~~ [issue](https://github.com/python-poetry/poetry/issues/3248).


## Reproduce

*None*


## Environment

- OS:
    - Poetry v1.1.8
- Language:
    - Python
- Framework: []


## Issue

- Degree: how-to
- Keywords:
    - poetry update single package
- References:
    - https://github.com/python-poetry/poetry/discussions/3723#discussioncomment-1625454
    - https://github.com/python-poetry/poetry/issues/3248
