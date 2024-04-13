# SQL injection attack, querying the database type and version on MySQL and Microsoft

## Lab Description

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/0278eb82-ecba-4491-8275-f0cb3ad4df65)

## Solution

By using the payload `UNION SELECT NULL,NULL#` and `UNION SELECT 'abc','def'#` we can understand that the resultset has two columns and both are string. Since the comment is `#` we can understand the SQL being used here is MYSQL
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/d0035d86-298c-449e-8294-6d5377417216)

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/cad541eb-813e-4f92-b562-66be9d49a95e)

Now to know the version of the MYSQL databse the payload `UNION SELECT @@version,NULL#`. `@@version` return the version of the MYSQL.
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/70a58a56-b665-47f9-89ce-4d7923f45394)
