# Lab: Blind SSRF with out-of-band detection

## Lab Description

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/60df0e8d-5d82-46d4-a991-4385e3eedfd8)

## Solution

Go to burp collaborator and clik copy to clipboard to get the subdomain.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/612416ca-c8fa-41b6-80fd-dfc01f25abdf)

Go to the webpage and open any prodcut. Find the request in HTTP history of burp and send it to repeater.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/eb5206f5-8429-4ae9-bb8a-f6c1d0148c94)

Insert the collaborator payload in the Referrer header and click send.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/ab0abc44-0ca6-4c25-ab80-35332f02b752)

In burp collaborator we can see some DNS and HTTP interaction that took place and this solves the lab.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/b0fd0a96-93e2-44b5-bc30-a16bfddc1d5d)
