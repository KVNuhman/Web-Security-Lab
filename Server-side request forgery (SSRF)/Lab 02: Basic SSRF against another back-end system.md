# Lab: Basic SSRF against another back-end system

## Lab Description

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/e37c8be5-3628-440c-8d4e-788fe3fe50ba)

## Solution

There is an endpoint to check the number of stock available.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/9fa81f76-8ca8-49b4-8b19-fc93bd731300)

The stock checker works with a stockApi parameter.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/26a50ba7-cadf-4ec1-ba54-1b624cefdacb)

Send the stock checker request to intruder and change the stockApi parameter to `http://192.168.0.§1§:8080/admin` where we will brute force the ip to find the administrative interface at the back-end URL.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/9560536f-653e-46e5-9ad5-fdb47e024190)

Set payload to numbers from 1 to 255 and a step of 1.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/3d373b8d-0793-45e3-bf9d-0bfffd9c1277)

At payload 170 we get a status code of 200 and the `/admin` page is accessible.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/ec09603e-23dd-48d4-889d-7d42b657159f)

Use the URL `http://192.168.0.170:8080/admin/delete?username=carlos` to delete user carlos and finish the lab.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/6f11e1e8-b278-4bd3-ba96-8cb7c9162250)
