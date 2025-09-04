## Connecting to a Database
- Python by default comes with sqlite, just do an import: ```import sqlite3```
- to create a database file on your storage and connect to it:
  - ```connec = sqlite3.connect('[database name goes here with (dot) db extension]')```
  - this auto creates the db file and connects to it
  - you can also connect to just memory instead of creating file in storage by typing memory between two ':' inside the connect() but such a db will be destroyed once you close the program

## Creating a Cursor
- cursor is like a pointer - an abstraction layer between programming language and db
- ```curs = connec.cursor()```
- Now we can pass queries in single line strings or multiline strings

## Creating a Table
- Now it's just regular sql queries that you can pass using the created cursor using the execute function
- ```
  curs.execute("""
  [sql
  query
  goes
  here]
  """)
  ```
- Note that SQLite is case sensitive so it's better to follow general SQL naming and case conventions

## SQLite Storages Classes
- There are five:
  - REAL: For floating point numbers
  - INTEGER: Signed Integers (1, 2, 3, 4, 6, or 8 bytes)
  - TEXT: Strings
  - BLOB: Binary data, stored exactly as input - example: media files
  - NULL: Null values
 
- For example, BOOLEAN maps to INTEGER (0 or 1)

## Common Type Names (Type Affinity)
- ```
  (REAL affinity):
  REAL, DOUBLE, FLOAT, DOUBLE PRECISION
  
  (INTEGER affinity):
  INTEGER, INT, TINYINT, SMALLINT, MEDIUMINT, BIGINT, UNSIGNED BIG INT, INT2, INT8
  
  (NUMERIC affinity):
  NUMERIC, DECIMAL, BOOLEAN, DATE, DATETIME
  
  (TEXT affinity):
  TEXT, CHAR, VARCHAR, CLOB, CHARACTER(20), VARCHAR(255), NCHAR(55)

  (BLOB affinity):
  BLOB, No specified type defaults to BLOB
  ```
- Note: Length limits are ignored, so something like varchar(10) and varchar(100) will be the same
- Note: You can technically store any type in any column but that's dangerous

## Commiting and Closing
- Commit to actually save data to the database - ```connec.commit()```
- Close the connection like in every db - ```connec.close()```
