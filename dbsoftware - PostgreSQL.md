# note
these might NOT work on *Linux* or *Windows*
read these possibly useful st-answers/artcles
  [How to configure postgresql for the first time?](https://stackoverflow.com/a/52161836/6273859)

# principles
reading
  ignore any out-dated answers (stackoverflow)
  ignore any obscure   answers (stackoverflow)
coding
  NEVER use *f-strings*, *`format()`*, or *%-style* formatting for your SQL
  ~ http://initd.org/psycopg/docs/sql.html
  ~ https://stackoverflow.com/a/48870677/6273859
  ~ https://www.reddit.com/r/learnpython/comments/9kjw47/f_string_and_sql/
  ~ https://stackoverflow.com/a/56083704/6273859

# rules in psql
1. enter by `psql -d postgres` (at lease for the 1st time)
2. always ended with ***`;`***
3. no need to use `root` for entering `psql` if you're using *macOS*
4. some *SQL* commands require higher-level roles <small>(e.g. `$(whoami)`, `root`)</small>

-----

# install
brew install postgresql@11
brew services restart postgresql@11

# going in
enter specific db (with specific user)
  $ psql --username=trypsycopg --dbname=trypsycopgdb

# create
new user|database
  $ createuser -dP trypsycopg
  $ createdb trypsycopg_db
  psql# GRANT ALL PRIVILEGES ON DATABASE trypsycopg_db TO trypsycopg;

new database with existing user
  $ createdb -E utf-8 -U trypsycopg trypsycopgdb
  
change password
  psql# ALTER user trypsycopg WITH PASSWORD 'NEW_PASSWORD';

# delete
delete user     DROP USER "ROLE_NAME";
                DROP ROLE "ROLE_NAME";    (same as `USER`)
delete table    DROP TABLE "TABLE_NAME";
delete database DROP DATABASE "DB_NAME";

# help
help
  $ psql --help | less
  psql# \?          # help for psql itself
  psql# \help       # help for SQL commands

# info
common-used commands <small>(simplified description)</small>
  psql# \l              show databases
  psql# \c DATABASE     switch database (\c == \connect)

  psql# \dt+            show tables

  psql# \du             show users
  psql# \dg             show roles

  psql# \d+             show tables
  psql# \d+ TABLE_NAME  show table info (detailed)
                        ~ SQL equivalent
                        SELECT  *
                        FROM    information_schema.COLUMNS
                        WHERE   TABLE_NAME = 'TABLE_NAME';

-----

# Specific needs
where the data directory is
  $ psql --username=$(whoami) --dbname=trypsycopgdb <small>(require *higher-level* user)</small>
  psql# SHOW data_directory;

dump definition/data
  help
    $ pg_dump --help
  
  optional args
    -U USER_NAME

  export table data
    psql# \copy TABLE_NAME to 'FILENAME.csv' csv;

  import table data
    ~ the table must havn't created
    ~ the table doesn't have to be the previous one
    ~ it can be imported as long as they both have the same columns
    psql# \copy TABLE_NAME FROM 'FILENAME.csv' DELIMITER ',' CSV;

  definition of db, index, tables etc.
    $ pg_dump -s trypsycopgdb >| export.sql

  table definition only
    $ pg_dump -s trypsycopgdb | awk 'RS="";/CREATE TABLE[^;]*;/' >| export.sql 

-----

# solutions for issues you might encounter
1. conn issue   
  `rm -fv /usr/local/var/postgres/postmaster.id`
2. sudo: unknown user: postgres
  no need to do `sudo -u postgres psql`, at least on *macOS*
  do this instead `psql -U CURRENT_USER postgres` (-U === --username)

# stuff you should care
- [`execute`](http://initd.org/psycopg/docs/cursor.html#cursor.execute): `(query, vars=None)`
- [String formatting named parameters <small>(useful to `sql.SQL`)</small>](https://stackoverflow.com/a/2451826/6273859)

-----
 

# references
- []()
- []()
- []()
- [<u>How to import CSV file data into a PostgreSQL table?</u>](https://stackoverflow.com/questions/2987433/how-to-import-csv-file-data-into-a-postgresql-table)
- [<u>How to create a backup of a single table in a postgres database?</u>](https://stackoverflow.com/questions/3682866/how-to-create-a-backup-of-a-single-table-in-a-postgres-database)
- [How to export/import table data to/from a file](https://stackoverflow.com/questions/4791288/how-to-export-table-data-to-file)
- [How can I export the schema of a database in PostgreSQL?](https://stackoverflow.com/questions/14486241/how-can-i-export-the-schema-of-a-database-in-postgresql)
- [PostgreSQL "DESCRIBE TABLE"](https://stackoverflow.com/questions/109325/postgresql-describe-table)
- [String formatting named parameters](https://stackoverflow.com/questions/2451821/string-formatting-named-parameters)
- [Moving the PostgreSQL Data Directory](https://www.digitalocean.com/community/tutorials/how-to-move-a-postgresql-data-directory-to-a-new-location-on-ubuntu-18-04#step-1-%E2%80%94-moving-the-postgresql-data-directory)
- [psycopg2 - `execute()`](http://initd.org/psycopg/docs/cursor.html#cursor.execute)
- [Mac OSX: "sudo: unknown user: postgres"](https://github.com/sleede/fab-manager/issues/34)
- [sudo: unknown user: postgres](https://stackoverflow.com/a/30301755/6273859)
- [PostgreSQL: Drop Database but DB is still there](https://stackoverflow.com/a/9044624/6273859)
- [PostgreSQL `DROP USER`](https://www.postgresql.org/docs/current/sql-dropuser.html)
- [PostgreSQL `DROP DATABASE`](http://www.postgresqltutorial.com/postgresql-drop-database/)
- [How to change PostgreSQL user password?](https://stackoverflow.com/a/12721095/6273859)
- [Create database from command line](https://stackoverflow.com/a/30642050/6273859)
- [Calling the `psql` command without selecting any database](https://superuser.com/a/655401)
