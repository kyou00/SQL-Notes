# Learning SQL Commands

Just taking some notes about different SQL commands.

---------------------------------------------

##### - SELECT * FROM users;
	- Selecting all columns from users table

##### - SELECT username,password FROM users
	- Selecting username and password column from users table

##### - SELECT * FROM users LIMIT 1
	- Selecting only one row from the users table

##### - SELECT * FROM users LIMIT 2,1
	- Skipping two rows and returning one row

##### - SELECT * FROM users WHERE username='admin'
	- Selecting all columns from users table where the username is equal to admin

##### - SELECT * FROM users WHERE username != 'admin'
	- Selecting all columns from users table where the username is not equal to admin

##### - SELECT * FROM users WHERE username='admin' or username='jon'
	- Selecting all columns from users table where the username is equal to admin or jon

##### - SELECT * FROM users WHERE username='admin' and password='p4ssword'
	- Selecting all columns from users table where the username is equal to admin and password is equal to p4ssword

##### - SELECT * FROM users WHERE username like 'a%'
	- Selecting all columns from users table where the username starts with the letter a

##### - SELECT * FROM users WHERE username like '%n'
	- Selecting all columns from users table where the username ends with the letter n

##### - SELECT * FROM users WHERE username like '%mi%'
	- Selecting all columns from users table where the username containing the characters mi within them.


### UNION

##### - SELECT name,address,city,postcode FROM customers UNION SELECT company,address,city,postcode FROM suppliers
	- Selecting name, address, city and postcode columns from customers table then also selecting company, address, city and postcode from the suppliers table


### INSERT

##### - INSERT into users (username,password) values ('bob','password123')
	- The table is users and inserting bob in username column and password123 in password column.


### UPDATE

##### - UPDATE users SET username='root',password='pass123' WHERE username='admin'
	- Update the old value in username column and will set the new value then also include the changes in password column.


### DELETE

##### - DELETE FROM users WHERE username='martin'
	- Deletes the value martin in username column.

##### - DELETE FROM users 
	- Deletes the entire value of table users


