### MySql

#### Backup
- mysqldump -u [username] -p[pass] db_name > db_backup.sql
```
mysqldump -u root -psqlr00t project > db_backup.sql
mysqldump -u root -psqlr00t project | gzip > db_backup.sql.gz
```
#### Restore