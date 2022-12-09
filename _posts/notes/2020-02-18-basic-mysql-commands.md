---
title: "Basic Mysql Commands"
date: 2020-02-18T17:21:09-07:00
draft: false
tags: ["mysql","cheatsheet", "database"]
---

Thanks for coming to this particular blog among many mysql commands cheatsheet. I am gathering all the mysql commands that I go through and update them here.

#### Create User and Grant Privileges

```sql
CREATE USER 'flaskuser'@'localhost' IDENTIFIED BY 'flaskpassword';

GRANT ALL PRIVILEGES ON flaskdb.* TO 'flaskuser'@'localhost';

FLUSH PRIVILEGES;
```

### Mysql Dumps

```shell

# Export Database
$ mysqldump -u[mysql_user] -p [db_name] > `date +%Y-%m-%d-%H:%M:%S`.sql

# Import Database
$ mysql -uroot -p [db_name] < 2018-09-01.sql

```


### Create Database :
```sql
CREATE DATABASE my_database;
```

### Create Table :
```sql
CREATE TABLE my_table (
    id int primary key auto_increment,
    Name varchar(50),
    Address varchar(40),
    Gender enum ("Male", "Female")
)
```

### Alter Table :
```sql
ALTER TABLE my_table RENAME my_tbl;
```


### Deleting Table :
```sql
DROP TABLE my_tbl;
```

### Renaming Column Name :
```sql
ALTER TABLE my_tbl
CHANGE full_name name varchar(50);
```

### Delete Column
```sql
ALTER TABLE my_tbl drop name;
```

### Adding Column
```sql
ALTER TABLE my_tbl ADD roll int;
```

##### Basic CRUD commands

```sql
-- Insert
INSERT INTO my_tbl
  (id,name,address,gender)
  values (‘1’,’sisir’,’ktm’,’male’);

-- Update
UPDATE my_tbl
  set name = ‘ccr’ where id=‘1’;

-- Select
SELECT * FROM my_tbl where id=‘2’;

-- Delete
DELETE from my_tbl where id = ‘2';

```
