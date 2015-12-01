# MySQL

## Basics

### Export database

```
mysqldump -u [uname] -p[pass] db_name > db_backup.sql
```

### Import dump

Import to an existing local database
```
sudo mysql -u root -p -h localhost DATABASE_NAME < data.sql
```
### Show the size of the databases

```
SELECT table_schema "Data Base Name",
sum( data_length + index_length ) / 1024 /
1024 "Data Base Size in MB",
sum( data_free )/ 1024 / 1024 "Free Space in MB"
FROM information_schema.TABLES
GROUP BY table_schema;
```

## Indexing

### B-Tree

**Strengths**

* Match the full value
* Match a leftmost prefix
* Match a column prefix
* Match a range of values
* Match one part exactly and match a range on another part
* Index-only queries

**Weaknesses**

* If lookup doesn't start from the leftmost side of the indexed columns
* You can't skip columns in the index

## Schema Optimizations

## Query Optimizations

### Access types

**Slowest last**

1. Single value access (constants)
2. Range accesses (range scan)
3. Scanning an index (index scans)
4. Scanning a table (full table scan)

### Column selectivity

In general you should use the column with the highest selectivity first in the index and queries.

```sql
SELECT COUNT(DISTINCT staff_id)/COUNT(*) AS staff_id_selectivity,
COUNT(DISTINCT customer_id)/COUNT(*) AS customer_id_selectivity,
COUNT(*)
FROM payment
```

## Tools

### Percona Toolkit

http://www.percona.com/software/percona-toolkit

**pt-archiver**

http://www.percona.com/doc/percona-toolkit/2.2/pt-archiver.html

Archive rows from a MySQL table into another table or a file. It could also delete them directly.

* Remove useless data, safely and slowly

Benefits:

* Faster queries
* Easier backups

**pt-duplicate-key-checker**

http://www.percona.com/doc/percona-toolkit/2.2/pt-duplicate-key-checker.html

Find duplicate indexes and foreign keys on MySQL tables.
* Remove useless indexes, safely

Benefits:
* Simpler tables
* Faster INSERTs

```
pt-duplicate-key-checker --host=localhost --databases=db1,db2 --user=root --password=secret
```

**pt-mysql-summary**

http://www.percona.com/doc/percona-toolkit/2.2/pt-mysql-summary.html

Summarize MySQL information nicely.

* MySQL tricorder

Benefits:
* Easily learn about a MySQL server

```
pt-mysql-summary --user=root --password=secret
```

**pt-online-schema-change**

http://www.percona.com/doc/percona-toolkit/2.2/pt-online-schema-change.html

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

http://www.percona.com/doc/percona-toolkit/2.2/pt-query-digest.html

Analyze MySQL queries from logs, processlist, and tcpdump

* Find slow queries

Benefits:
* \#1 performance optimization task
  * find and fix slow queries
* Track and review queries

```
pt-query-digest /var/log/mysql/mysql-slow.log
```

**pt-stalk**

http://www.percona.com/doc/percona-toolkit/2.2/pt-stalk.html

Collect forensic data about MySQL when problems occur.

* Postmortem analysis of MySQL problem

Benefits:
* Never sleeps, so you can
* Collects a lot of vital data

**pt-summary**

http://www.percona.com/doc/percona-toolkit/2.2/pt-summary.html

Summarize system information nicely.

* System tricorder

Benefits:
* Easily learn about a system

```
pt-summary
```

**pt-table-checksum**

http://www.percona.com/doc/percona-toolkit/2.2/pt-table-checksum.html

Verify MySQL replication integrity.

* Find slaves with incorrect data

Benefits:
* Important knowledge for very little effort
* Knowing a problem exists is the first step towards fixing it

**pt-table-sync**

http://www.percona.com/doc/percona-toolkit/2.2/pt-table-sync.html

Synchronize MySQL table data efficiently.

* Fix slaves with incorrect data

Benefits:
* Easily fix problems found by pt-table-checksum

**pt-visual-explain**

http://www.percona.com/doc/percona-toolkit/2.2/pt-visual-explain.html
