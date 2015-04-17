# MySQL

## Basics

### Import dump ###

Import to an existing local database
```
sudo mysql -u root -p -h localhost DATABASE_NAME < data.sql
```
### Show the size of the databases ###

```
SELECT table_schema "Data Base Name",
sum( data_length + index_length ) / 1024 /
1024 "Data Base Size in MB",
sum( data_free )/ 1024 / 1024 "Free Space in MB"
FROM information_schema.TABLES
GROUP BY table_schema;
```

## Tools

### Percona Toolkit

**pt-archiver**

Archive rows from a MySQL table into another table or a file. It could also delete them directly.

* Remove useless data, safely and slowly

Benefits:

* Faster queries
* Easier backups

**pt-duplicate-key-checker**

Find duplicate indexes and foreign keys on MySQL tables.
* Remove useless indexes, safely

Benefits:
* Simpler tables
* Faster INSERTs

```
pt-duplicate-key-checker --host=localhost --databases=db1,db2 --user=root --password=secret
```

**pt-mysql-summary**

Summarize MySQL information nicely.

* MySQL tricorder

Benefits:
* Easily learn about a MySQL server

```
pt-mysql-summary --user=root --password=secret
```

**pt-online-schema-change**

ALTER table without locking them.

* Hot online ALTER TABLE

Benefits:
* Zero downtime
* Low impact
* Tries and retries

Flags:
* dry-run
  Test before the real run
* execute

**pt-query-digest**

Analyze MySQL queries from logs, processlist, and tcpdump

* Find slow queries

Benefits:
* \#1 performance optimization task
  * find and fix slow queries
* Track and review queries

```
pt-query-digest /var/log/mysql/mysql-slow.log
```

**pt-summary**

Summarize system information nicely.

* System tricorder

Benefits:
* Easily learn about a system

```
pt-summary
```
