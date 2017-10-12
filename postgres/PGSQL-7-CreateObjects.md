# Create Objects

## Features

* Limited to 63 characters for definition of objects
* Identifiers must begin with alpha characters
* Used to create DBs, tables, indexes, functions, schemas etc. Note on PostgresSQL hierarchy,
  * DB
    * Schema(s) - Default schema is named `public`
      * Objects - Tables, Functions, Triggers

    Note: All DBs have `public` and `pg_catalog` schema  
    Note: All users | roles have `CREATE`, `USAGE` access t the `public` schema for ALL DBs  
    Note: Create distinct schemas f security beyond `public` is necessary

## Tasks

1. Db Creation
    * Create user named 'abc' with `CREATEROLE CREATEDB` rights  
         `createuser -e -U postgres abc;` and follow the steps
    * Create a DB named 'abc'  
        `create database 'abc';`
    * Create a table named 'messages'  
        `create table messages(date date);`
    * Create a SCHEMA named 'logs'  
        `create schema abc.logs;`
