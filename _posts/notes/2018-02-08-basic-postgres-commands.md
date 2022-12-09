---
title: "Basic Postgresql Commands"
date: 2018-02-08
draft: false
tags: ["postgresql","cheatsheet", "database"]
---

### Create user, database and grant roles

#### Drop Database :
```shell
$ drop database john_db;
```

#### Create Database :
```shell
$ create database john_db;
```

#### Create User :
```shell
$ create user john;
```

or,

```shell
$ create user john with encrypted password 'john@password';
```

#### Alter User :
```shell
$ alter user john with encrypted password 'john@password';
```

#### Grant Privileges :
```shell
$ grant all privileges on database john_db to john;
```

---

#### Postgres Dumps


```shell
# Export database

$ pg_dump -U {{db_user}} {{db_name}} > `date +%Y-%m-%d-%H:%M:%S`.pgsql

# Import database

$ psql -U {{db_user}} {{db_name}} < db_backup_to_be_imported.pgsql
```

#### Unix Domain Socket
```shell
psql: error: could not connect to server: could not connect to server: No such file or directory
        Is the server running locally and accepting
        connections on Unix domain socket "/tmp/.s.PGSQL.5432"?
```

```
$ rm /usr/local/var/postgres/postmaster.pid
$ brew services restart postgresql
```

https://stackoverflow.com/questions/13410686/postgres-could-not-connect-to-server
