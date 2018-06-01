### MySql

#### Backup
- mysqldump -u [uname] -p[pass] db_name > db_backup.sql
- mysqldump -u [uname] -p[pass] db_name | gzip > db_backup.sql.gz
#### Restore