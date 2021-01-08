---
id: mysql
title: Mysql
type: docs
path: the-notebook/database/mysql
---

### MySql

#### Backup

- mysqldump -u [username] -p[pass] db_name > db_backup.sql

```
mysqldump -u root -psqlr00t project > db_backup.sql
mysqldump -u root -psqlr00t project | gzip > db_backup.sql.gz
```

#### Restore

- mysql -u [user] -p [database_name] < [filename].sql

```
mysql -u root -p project < db_backup.sql
```
