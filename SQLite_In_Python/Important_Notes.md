## Data Types & Type System
- SQLite has dynamic typing: Columns don't enforce strict types like PostgreSQL. You can insert a string into an "INTEGER" column without errors
- No native BOOLEAN type: Use INTEGER with 0/1 or TEXT with 'true'/'false'
- No ARRAY types: You'll need to serialize/deserialize or use separate tables
- Date/time handling is different: SQLite stores dates as TEXT, INTEGER, or REAL, not native DATE/TIMESTAMP types

## Schema & Constraints
- ALTER TABLE is very limited - you can't drop columns, modify column types, or add constraints (except renaming tables/columns)
- Foreign key constraints are disabled by default - run PRAGMA foreign_keys = ON to enable
- Check constraints might not be enforced depending on version
- No SERIAL or IDENTITY - use INTEGER PRIMARY KEY AUTOINCREMENT

## Concurrency & Locking
- Much more limited concurrent write access - only one writer at a time
- Long transactions can block other operations
- BEGIN IMMEDIATE or BEGIN EXCLUSIVE for better concurrency control
