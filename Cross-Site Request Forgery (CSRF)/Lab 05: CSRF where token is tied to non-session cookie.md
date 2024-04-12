# Lab: CSRF where token is tied to non-session cookie

## Lab Description

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/6f76fff9-e914-49c9-b39c-ff2b8c51d7ee)

## Solution

Login using the given username and password `wiener:peter` which we will assume to be the victim.

![image](https://github.com/KVNuhman/Cyber-Forensics/assets/46161259/c4d20500-a7d5-477c-a5eb-a62ea279fe24)

Each email update request has a csrf token and a csrf key.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/8465684b-72d5-42dc-8054-75c010d87494)

Log in using the other username and password `carlos:montoya` which we assume to be the attackers id and do an email update with some random email id.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/d15ca302-a21d-4e70-9a3e-032d12d2a7c7)

Find the request in HTTP history.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/af58bc44-4ba3-4f12-aee5-6358b3d72c10)

Change the csrfkey and csrf token of victim with the attacker's and the request still works.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/50d25fe6-7ee5-411a-a05e-f7fa8ef8cca1)

If something is searched, the request will also include the csrf key.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/1efe6c3d-d9e5-4783-baa4-1f122f9c3567)

Now go to the original request made with atackers csrfkey and csrf token and **generate HTML** using **engagement tools**.
instead of `document.forms[0].submit()` change it to `<img src="https://YOUR-LAB-ID.web-security-academy.net/?search=test%0d%0aSet-Cookie:%20csrfKey=YOUR-KEY%3b%20SameSite=None" onerror="document.forms[0].submit()">` so that we can include the csrf key too.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/fc855e6f-ab02-4518-b547-bd616791e097)

Paste the template in the body of the exploit server, click on **Store** and then **Deliver to victim** to solve the lab.
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/29b70998-bedd-4e96-8420-ec109aa67197)
