# Features of PostgresSQL

1. Object relational database management
   - Objects can be related in hierarchy from Parent to Child
2. Transactional RDBMS
   Transactional statements must execute ALL or NONE
   - SQL statements have implicit _BEGIN_ and _COMMIT_
   - SQL statements may also have explicit _BEGIN_ and _COMMIT_
3. One process per connection auto spawned per new connection
   - Managed by master process called _postmater_
4. Processes use only one CPU
5. Multiple helper processes, which appear as _postgres_ instances, running always, e.g
   - Stats collector
   - Background writer
   - Auto vacuum for cleanup/space reclaim
   - WALsender or write ahead log
6. Max DB Size is unlimited contingent on OS and available storage
7. Max table size is 32TB - stored as multiple 1GB files
8. Max row size is 400GB
9. Max Column Size is 1GB
10. Max Indexes on table is unlimited
11. Max identifiers(DB objects) length is 63 bytes
12. Made by UC Berkeley
13. Default listener is TCP:5432
    - You may install as non privileged user
14. Users are distinct from OS users similar to MySQL
15. Users are shared across DBs
16. Inheritance
    - Tables lower hierarchy may inherit columns from higher tables
    - No unique constraints or foreign keys support in this case
17. Case insensitive commands are used without quotes
18. Case sensitive commands are used with double quotes
19. Three primary config files: \$POSTGRESROOT/data/\*.conf
    - `pgh_ba.conf` for host/user/DB connectivity
    - `postgresql.conf` for general settings
    - `pg_ident.conf` for user mapping
20. Integrated log rotation - configured in `postgresql.conf`
    - Criteria on Age|Size
