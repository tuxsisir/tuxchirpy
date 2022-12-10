---
title: "Basic Postgresql Commands"
date: 2018-02-08
draft: false
tags: ["postgresql","cheatsheet", "database"]
categories: [database]
---

### Create user, database and grant roles

#### Drop Database :
```sql
DROP database john_db;
```

#### Create Database :
```sql
CREATE DATABASE john_db;
```

#### Create User :
```sql
CREATE USER john;
```

or,

```sql
CREATE USER john WITH ENCRYPTED PASSWORD 'john@password';
```

#### Alter User :
```sql
ALTER USER john WITH ENCRYPTED PASSWORD 'john@password';
```

#### Grant Privileges :
```sql
GRANT ALL PRIVILEGES ON DATABASE john_db TO john;
```

#### Grant Privileges of everything to postgres, if not given with:

```sql

grant all privileges on all tables in schema public to postgres;

grant all privileges on all sequences in schema public to postgres;

```
> Note: A schema is a namespace that contains a collection of database objects, such as tables, views, and functions. The schema public is the default schema.
{: .prompt-warning }

#### Query all the tables in database

```sql
SELECT    table_name
FROM      information_schema.tables
WHERE     table_schema = 'public'
ORDER BY  table_name;
```

---

#### Postgres Dumps

{% raw %}
```shell
# Export database

$ pg_dump -U {{ db_user }} {{ db_name }} > `date +%Y-%m-%d-%H:%M:%S`.pgsql

# Import database

$ psql -U {{ db_user }} {{ db_name }} < db_backup_to_be_imported.pgsql
```
{% endraw %}

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

References:
- [https://stackoverflow.com/questions/13410686/postgres-could-not-connect-to-server](https://stackoverflow.com/questions/13410686/postgres-could-not-connect-to-server)
