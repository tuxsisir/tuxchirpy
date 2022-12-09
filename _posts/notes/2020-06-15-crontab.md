---
title: "Crontab"
date: 2020-06-15
draft: false
tags: ["other"]
---

### https://crontab.guru/

`$ crontab -e`

`0 3 * * * pg_dump -U db_user db_name > ~/db_dumps/$(date +\%Y-\%m-\%d-\%H:\%M:\%S).pgsql;`

`$ vim ~/.pgpass`

`localhost:5432:db_name:db_user:secret_password`

`$ chmod 0600 ~/.pgpass`

### cron and .pgpass
---

`$ crontab -l`

`0 3 * * * pg_dump -U <db_user> <db_name>  > ~/cron_dumps/$(date +\%Y-\%m-\%d-\%H:\%M:\%S).pgsql`

`$ crontab -e`


`~/.pgpass`
