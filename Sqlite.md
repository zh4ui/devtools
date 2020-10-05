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
* [DBeaver](https://dbeaver.io) is a DB management tool. It has a free community edition. It comes with some [Optional Extensions](https://github.com/dbeaver/dbeaver/wiki/Optional-extensions)
* [ValentineStudio]
* [Navicat for SQLite]
* [DB Browser for SQLite]
* [SQLite/SQLServer Compact Toolbox]
* [DbVisualizer]