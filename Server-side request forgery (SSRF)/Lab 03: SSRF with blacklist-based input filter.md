# Lab: SSRF with blacklist-based input filter

## Lab Description

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/31122fac-f982-40c9-bff5-5eb452ebe9bf)

## Solution

Acessing `/admin` is blocked as it is accessible only if logged in as administrator.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/6d4ea20b-fe40-44e1-a3d4-ee3af4996068)

The stock checker uses a stockApi parameter which is provided with a URL.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/cbc688f7-bee7-4ffe-917d-d02332a90b9d)

Change the URL of stockApi parameter to `http://127.0.0.1/` or `http://localhost/` , the request will be blocked for security reason.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/aead0eb5-5a89-4660-818b-3e082b96bbfd)

Use the URL `http://127.1/` to bypass the security block.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/4665d762-ed86-4634-85bb-dbb0c007bfdd)

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/a94072b4-1da7-4ab1-afc8-23c23d116164)
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/19cd4f63-82fb-460f-8740-10e72f039ecb)
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/a29b3d4b-ad9e-4c56-9afe-043a1b611d96)
