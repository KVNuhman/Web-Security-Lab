# Insecure direct object references

## Lab Description

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/4b4fab09-57fb-4979-b5d5-9186b977e87a)

## Solution

Go to the live chat section and select transcript.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/e73e8b05-52cc-4632-b41c-3fd090de8217)

In the HTTP history we can see that the transcript is being shown from a text file in the server.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/d42d1508-872e-4c6c-bc7b-16a54bf751be)

We use Burp Repeater to edit the request, we change the file to `1.txt` and we can see the passoword of carlos `jmbwtmgqgqf82fefngqq` .

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/a907c41f-3933-4ad9-aaf7-3e02650361d1)

Using the password recieved, loggin into Carlos's account is successful.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/75f9532f-2018-4e82-bf11-c18259ed27d6)
