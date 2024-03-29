# Lab: DOM XSS in innerHTML sink using source location.search

## Lab Description

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/b3f9d36f-c1a9-4086-9500-5f9f23093ba0)

## Solution

The webpage has an XSS vulnerability in the search section.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/a7d0c022-4363-4b97-9b95-f37fbed22915)

Entering `<img src=1 onerror=alert(1)>` has cause and XSS vulnerability.
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/a1199683-980d-4703-bbd0-10d07bdd8cd7)
