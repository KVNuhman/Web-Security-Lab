# Blind SQL injection with conditional responses

## Lab Description

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/1381a1af-ac2f-43ba-9a66-0ad5248f5e21)

## Solution

We see the welcome back message which verifies the usage of trackingID cookie.
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/7614b49d-11be-4c23-a3d4-707db20258f8)

We first check if the trackingId is valid which turns out to be true as we can see the welcome back message.
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/a4d4df17-cf4a-4742-a7a6-067ee103d76d)

Now we inject a SQL payload `'AND 1=0--` and in the response we can see the welcome back message and it can be confirmed that SQL is being used.
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/5efec87f-7947-48d5-b9c7-54ac582bdf7b)

Next we inject `'AND (SELECT 'x' FROM USERS LIMIT 1)='x'--` to see if there exist a table named `users` which successful.
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/41982629-76ee-41b7-9f4e-5dab0c45b914)

To check if there is a username as administrator bu injecting `'AND (SELECT 'x' FROM USERS WHERE USERNAME = 'ADMINISTRATOR')='x'--`. Since we can see welcome back in the response we can confirm there is a user called administrator.
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/ccba717b-9b34-44e4-b368-751f19c65037)

Next step is finding out the length of the password for the administrator account. We first do a simple SQL injection `'AND (SELECT 'x' FROM USERS WHERE USERNAME='administrator' AND LENGTH(password)>1)='x'--`.
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/fb8e3f64-1d38-4c33-b41d-2cac44c19ad7)

Instead of doing the above injection manually we can use burpsuite intrudent and use a sniper attack to brute force the injection. In the response we can see that the passowrd length is 20.
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/86c171ad-aa7f-40cd-a57f-001f5e47896d)

Next step is finding out the password. We can do this by the payload `'AND (SELECT SUBSTRING(PASSWORD,1,1) FROM USERS WHERE USERNAME = 'administrator') = 'a'--`. Here we can understand the first letter is not a.
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/509e65ea-1f59-4ce6-99b9-03119512701b)

Instead of doing this manually we can user intruder and use a cluster bomb attack to bruteforce the password. The retrived passoword is `pca83q1cqyw69q2arcyt`.
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/4375a429-993a-4eb7-a98d-c0b3ebfe3b55)

By using the username as `administrator` and passoword as `pca83q1cqyw69q2arcyt` login into admin acconunt was successful.
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/067e0c39-0c9e-4e59-ae39-3be435c39a46)
