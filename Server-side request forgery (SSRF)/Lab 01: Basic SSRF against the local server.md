# Lab: Basic SSRF against the local server

## Lab Description

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/d5869a3d-2ce6-4a07-9729-7aeb679e4a64)

## Solution

If you browse to `/admin`, it will block your request as it only allows access if you logged in as administrator.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/29a37d57-7f50-4bd7-9099-4cf74839afc4)

Go to any product page and there is a stock checker endpoint.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/601bd02c-01b2-4158-b009-4fa1615cc3b8)

The request includes a stockApi parameter to which were the URL is provided for checking stocks.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/65c9875c-17d0-4cca-babc-bacb6159d8c5)

Change the stockApi parameter to `http://localhost/admin` and now the restrcted admin page is accessible.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/9b31049e-f3c8-4fd0-addf-07daaad9482a)

Go `http://localhost/admin/delete?username=carlos` to delete user carlos and finish the lab.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/2ed2ca48-f60d-4f64-bae0-86f4ef95cff5)
