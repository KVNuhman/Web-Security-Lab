# Lab: Reflected XSS into a JavaScript string with angle brackets and double quotes HTML-encoded and single quotes escaped

## Lab Description

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/65212325-a79e-44c1-b71c-08bab8a2573c)

## Solution

Search for something and it is reflected in the script.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/c55d976f-049d-40ff-ab7c-bfbd949d44b7)

Search for something with `'` and in the result it turns to `/`.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/22e346f3-2954-4059-bebc-cb7f0e8b81c9)

When searched for something with `/` present nothing is changed in the result script.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/652662f3-c4d6-4a22-a21b-4b293e2b073e)

Search for `\'-alert(420)//` and it causes the alert finishing the lab.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/f3389f26-1452-4e12-9db0-0b99a838e62d)
