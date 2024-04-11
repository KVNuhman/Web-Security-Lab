# Lab: CSRF where token validation depends on request method

## Lab Description

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/c6f06e8a-79fc-4926-bf6e-078a0e8e2be8)

## Solution

Log in to the website using the given username and password.Then update your email with some random email address.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/c149a299-59e8-4eec-9530-3f22cc6b29cd)

Find the request in HTTP history and send it to repeater. Remove the CSRF token and send the reques, we get a status 400 saying `Missing parameter csrf`.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/90e45432-dca8-4be3-a324-c55f10a777f2)

Change the request method to `GET` and the request is successful.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/9804f7c3-f977-4118-8c42-7a198a038f9b)

Now get the original request change it's request method to `GET` and generate HTML template using Engagement tools.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/8cad24a9-5c4f-4502-894f-d759dc4cf849)

Copy the HTML template.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/ca437ae2-d8d6-4079-bf27-686a6955452d)

Go to exploit server, copy the HTML in the body and click on **Store** and then **Deliver to victim** to finish the lab.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/324f0bbf-d702-4da0-867b-f1f1a4ce68f1)
