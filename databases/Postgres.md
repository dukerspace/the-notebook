### PostgreSQL

#### Backup
##### pg_dump <db-name> <backup-file>
- pg_dump postgres > postgres_db.bak

#### Restore
- psql -U <username> -d <dbname> -1 -f <filename>.sql
- pg_restore -U <username> -d <dbname> -1 <filename>.dump