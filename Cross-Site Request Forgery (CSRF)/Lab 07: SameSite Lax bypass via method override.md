# Lab: SameSite Lax bypass via method override

## Lab Description

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/612e58dc-da6a-4dd9-8969-05b12a972adc)

## Solution

Log in using the given username and password and make an email update request using some random email address.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/1e9436b1-bf98-4b16-ab31-13ed7eab3b99)

Send the email change request to repeater and on inspection it's evident that there is no csrf key or tokens present.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/b928ac4b-edff-4add-92f5-5971cf7baa5c)

When inspecting the cooikie of POST request of login the cookie is set without any SameSite restriction.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/f653f704-9236-48df-8325-d6c2a23820a2)

If we change the email change POST request to GET, the result says **Method not allowed**.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/a565933d-765d-4ae3-9690-1894baf38f4f)

If we add `&_method=POST` the GET request is allowed.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/bb87bd09-9a51-42d4-8a4b-a86bd2cf3c6a)

Generate an **Generate CSRF PoC** using engagement tools.
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/f2b7c953-9885-499c-b059-76b13f3dab2f)

Change the method to `GET` and add another input element `<input type="hidden" name="_method" value="POST">` and then **Store** and **Deliver to victim** to finish the lab.
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/022f0f77-6b66-4f87-9de1-f8277564905b)
