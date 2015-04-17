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

Archive rows from a MySQL table into another table or a file.

* Remove useless data, safely and slowly

Benefits:

* Faster queries
* Easier backups
