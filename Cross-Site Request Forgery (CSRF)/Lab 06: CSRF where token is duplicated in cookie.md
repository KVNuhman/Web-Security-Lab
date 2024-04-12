# Lab: CSRF where token is duplicated in cookie

## Lab Description

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/56f19920-6d47-4934-8eb5-5357df7dcf9f)

## Solution

Log in using the given username and password and do and email update request.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/beae60f8-5cb4-4032-8cbe-8e4d6787036f)

Find the request in HTTP history and in the request the csrf value in the cookie and token is the same.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/5172ed1a-fbad-4610-bed2-35f3c45548de)

If we change the csrf value at both places the request still goes through as there is no proper validation.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/e7f682e9-1e71-4f52-9b16-c6f589dc5c4f)

Search for someting and find the request in HTTP history, even the search request has csrf value in the cookie.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/e31a67bd-99c2-41b0-b5cd-19c9e266b76b)

Generate an HTML template including `<img src="https://YOUR-LAB-ID.web-security-academy.net/?search=test%0d%0aSet-Cookie:%20csrf=fake%3b%20SameSite=None" onerror="document.forms[0].submit();"/>` .

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/2ea8299a-c0b0-4830-a1bf-cfc736912c65)

Copy the template and paste it in the body of the exploit server, click on **store** and **Deliver to victim** to finish the lab.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/19aeabf2-1c76-41e8-84e6-83b65c1b0c25)
