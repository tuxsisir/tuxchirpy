---
title: "Database - All Inclusive"
date: 2020-08-19
draft: false
tags: ["database"]
---

### Dynamic Typing
so this happened:

- jupyterhub creates the table user with blob encrypted auth state
- inserts data its fine..

working on sqlite everything is fine cause of "dynamic typing"

however mysql doesn't supports it

so when sqlalchemy fetches the data, it's from mysql and typerror occurs.

https://stackoverflow.com/questions/49183577/typeerror-string-argument-without-an-encoding-flask-and-sqlalchemy?rq=1

- MORAL OF THE STORY: mysqlconnector is the culprit here...
- pymysql saved the day (hope so)

---

### Transaction Isolation Level
https://www.red-gate.com/simple-talk/sql/t-sql-programming/questions-about-t-sql-transaction-isolation-levels-you-were-too-shy-to-ask/

### Run sqlalchemy
```python
from sqlalchemy import create_engine
from sqlalchemy.orm import sessionmaker

from jupyterhub.orm import User

engine = create_engine("mysql+pymysql://root:rootpassword@localhost:3306/dbname")
Session = sessionmaker(bind=engine)
session = Session()
session.query(User).all()
```


### postgres user
---

https://www.postgresql.org/docs/9.1/static/sql-alterrole.html


### .pgpass
---
```
192.168.99.55:5432:*:db_user:%6X*|7Ih6^"]4ZF
127.0.0.1:5432:*:postgres:postgres
192.168.99.61:5432:*:db_user:%6X*|7Ih6^"]4ZF
localhost:5432:*:postgres:postgres
```


#### sqlite3 db django : reference

```python
DATABASES = {
   'default': {
       'ENGINE': 'django.db.backends.sqlite3',
       'NAME': os.path.join(BASE_DIR, 'db.sqlite3'),
   }
}
```
