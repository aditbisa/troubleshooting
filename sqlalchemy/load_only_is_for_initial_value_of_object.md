# `load_only` is for initial value of object


## TLDR

Even using `load_only`, the entity can still access other fields value.
That's because when the entity access the other fields, SqlAlchemy query to database again for those fields.

Use this query to prevent other fields access.
```
session.query(Table.id, Table.column)
```


## The Story


## Reproduction


## Environment
- Language:
    - Python
- Framework:
    - SqlAlchemy


## Issue
- Degree: i-didnt-know-that
- Keywords:
    - load_only not working
    - load_only didn't exclude/defer other fields
- References:
    - https://stackoverflow.com/a/50330608
    - https://github.com/sqlalchemy/sqlalchemy/issues/7322
