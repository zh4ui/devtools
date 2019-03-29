# Sqlite


## commands

### attach a database

```sql
-- attach db from path_to_db
ATTACH path_to_db AS dbname;

-- list databases
.database
```

### set page size

```sql
-- set default pagesize
PRAGMA page_size=1024;

-- set for a specific attached database
PRAGMA dbname.page_size=1024;
```

## Utils

* [LiteCli](https://litecli.com/)， A command line interface for SQLite with auto-completion and syntax highlighting. LiteCli is part of [DBCLI](https://www.dbcli.com/)

