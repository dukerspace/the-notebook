---
id: postgres
title: PostgreSQL
type: docs
path: the-notebook/database/postgres
---

### PostgreSQL

#### Backup
##### pg_dump <db-name> <backup-file>
- pg_dump -U username table > file.bak
```
pg_dump -U postgres project > backup_db.bak
```

#### Restore
- psql -U <username> <dbname> < <filename>.sql
```
psql -U postgres project < backup.bak
```
- pg_restore -U <username> -d <dbname> -1 <filename>.dump
```
pg_restore -U postgres -d project -1 backup.dump
```
