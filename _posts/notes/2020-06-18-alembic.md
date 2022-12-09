---
title: "Alembic Commands"
date: 2020-06-18
draft: false
tags: ["python", "database"]
---

### Commands

`$ alembic init alembic`
- creates the migration folder
    - env.py (for path configuration)
    - script.mako (the script itself)
    - versions/ (where the migrations scripts are located)

`$ alembic revision -m 'base-revision'`
- creates the base empty revision
** Renamed the revision ID to that of jupyterhub (which already resides in the DB) No luck other than that. **

`$ alembic current`
- checks where the current head is at (now everything is fine)


* Use same Base while writing the models. i.e. from Jupyterhub orm
    - Stating different Base leads to missing foreign key


`$ alembic revision --autogenerate -m "create spawner log"`
- create new spawner log migration

`$ alembic upgrade head`
- to migrate the migrations from versions/

-- Up to date migrations --
