# psql Usage

## Features

1. (Non) Interactive usage
2. Command History with up and down arrow
3.  Tab completion
4. Commands terminate with semi colon and may wrap lines
5. Defaults to supplying the currently logged in user

## Tasks

1. Explore usage
    * `psql --version`
    * `psql -l -U postgres` - lists DBs then exits.  
        Note: 'postgres' and 'template0' and 'template1' are the DBs created by default
    * `psql` or `postgres -U postgres` enters the interactive mode
    * `\h` - returns SQL specific help
    * `\?` - returns psql specific help
    * `\l[+]` returns list of DBs
    * `\du[+]` - returns the list of users in the system
    * `\!` - returns user the $SHELL
    * `\! command` - executes the command non interactively
    * `\i path/to/file` - executes the commands in the file, psql or SQL commands
    * `\q` - quits
    * `\c postgres` or `\c DBNAME [REMOTE HOST]` - connects to different DB on may be different host. Current DB is displayed in the prompt.
    * `\d[+]`, `\dS[+]` - reveals database objects 
