# Referer-based access control

## Lab Description

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/023dd4a3-9917-4513-8003-0102117d5c9d)

## Solution

Log in as administrator using the given admin username and password and upgrade user carlos as admin.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/2d609b61-aa2e-44a4-992d-1e25780d91f7)

Identify the request in HTTP History and send it to proxy.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/0472648e-9dab-4523-ac6f-84effc0cbb07)

Login as normal user `wiener:peter` and get the session cookie.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/afb20ee9-676f-4ade-818c-be6c8f98026e)

Change the username, cookie of the request in repeater and remove the referer header from it. When we send this request it says `unauthorized`.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/b73b0848-09d2-48d0-9234-16eb888c53ae)

When the refere header is added back in the upgrade is successful and the lab is solved.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/10c8b503-56df-413e-b536-25b0918c27e2)
