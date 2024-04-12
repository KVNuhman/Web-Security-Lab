# SQL injection UNION attack, retrieving multiple values in a single column

## Lab Description

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/eedf783c-bf99-4d8a-bd2d-58016006683e)

# Solution

We find out there resultset return two columns by injecting the `NULL` payload. Then by using strings we find the second columns returns strings.
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/ff63c12a-d95b-47f3-af52-f5f315fc1492)

By using the payload `'+UNION+SELECT+NULL,username||'~'||password+FROM+users--` we concatenate username and passowrd by using the `||` operator.
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/92579d67-144f-4a4d-9979-b920629927e0)

The username and password obtained from the previous attack was used to successfully login to administrator account.
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/2eec120e-e2ee-4156-a395-6de7c4955504)
