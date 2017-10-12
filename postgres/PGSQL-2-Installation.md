# Installation

Download binary from EnterpriseDB
Install following the GUI prompts

## Footprint

1. `psql` is terminal monitor
2. `createdb` and `dropdb` for creating and dropping the databases
3. `createuser` and `dropuser` for creating and dropping user
4. `postgres` is the server process
5. data/ - top level data/config files and log files
6. data/pg_log - log files(default is STDERR)
7. data/pg_xlog - Write ahead log - maintains changes to DB files at all time
8. data/postmaster.opts - defines how the server starts usually with -D and data directory path
9. `/etc/init.d/postgresql-9.0` - initd manager
    File except initd file are contained within /opt/postgresql/version hierarchy
10. Add necessary PATH variables for accessing the binaries