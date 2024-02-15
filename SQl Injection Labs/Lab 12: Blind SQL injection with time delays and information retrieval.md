# Blind SQL injection with time delays and information retrieval

## Lab Description

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/f0045410-37ca-4611-a98a-c2a65c0982f1)

## Solution

We use the statement `x'%3BSELECT+CASE+WHEN+(1=1)+THEN+pg_sleep(10)+ELSE+pg_sleep(0)+END--` to see if we can cause a delay in the execution and it is successfull.
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/bc116081-c334-4bbd-99b1-d941fe7ee5a0)

Next we try to see if there is a user named `administrator` in the user table by changing tracking id to `x'%3BSELECT+CASE+WHEN+(username='administrator')+THEN+pg_sleep(10)+ELSE+pg_sleep(0)+END+FROM+users--`.
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/765ec5de-e031-48fc-87e9-f14d0d34dc0e)

Since there was a delay in the response we understand that user called `administrator` exists.

Now that we know that administrator we try to find the password length of the user by using a sniper attack.
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/5a8b163b-c5d2-4e53-9a81-cc54e59421b0)

Whenn we look at the results we can see that after 20 the response time is reduced hence we can understand the password length is 20.
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/3f82a5d0-a851-446f-84aa-37ec54389d0a)

Now we use a cluster attack to brute force the password of `administrator` by setting two payloads.
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/b9a8f5e7-4c83-488d-8ad5-9e3d001e70ab)

By looking at the response time we understand the password is `atk9xhf5dwuv5f6kozfz`.
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/ec273b59-a1bb-4d22-aa89-8726183571fa)

By using the username and password we found earlier we are successfully able to login.
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/0dfaa3c0-eee8-4e8e-9f12-5f310393cf88)
