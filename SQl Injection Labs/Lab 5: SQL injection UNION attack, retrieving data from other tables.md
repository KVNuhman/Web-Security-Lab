# SQL injection UNION attack, retrieving data from other tables

# Lab Descriptions

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/b533f3bb-b525-4c83-96f3-fc929ecaea08)

# Solution

First step is finding out the number of columns in resultset using `UNION SELECT NULL` paylod. Which we find to be two columns.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/58eb6abb-9479-4b2c-955b-86ca4aac71c6)

Next step is finding if both resultset where returning string values which van de done by chaning the `NULL` in the payload to some string values.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/5a1bfb7a-d003-43f3-b43e-aea36cb4d576)
We understand that both columns in the resulset are of string value.

Next we use the payload `'+UNION+SELECT+username,+password+FROM+users-- ` to get the username and passwords.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/087b7906-ac45-4cc7-a57a-a9d83f07a65f)
