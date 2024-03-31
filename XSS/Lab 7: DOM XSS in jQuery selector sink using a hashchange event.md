# DOM XSS in jQuery selector sink using a hashchange event

## Lab Description

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/2faa4ee2-c1f6-4387-8fae-4a7d3129745c)

## Solution

Click `Go to exploit server` to craft the exploit.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/214aa54d-51dc-455d-b965-5868266d5245)

Go to the body section and add the exploit `<iframe src="https://YOUR-LAB-ID.web-security-academy.net/#" onload="this.src+='<img src=x onerror=print()>'"></iframe>`

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/afd2a40f-8005-4a9e-852b-1a5af6d749b8)

When you select a view exploit, then the website loads and causes it to print the page.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/b7c9d546-ef05-4f73-beb7-2dabaace541c)

Select `Deliver exploit to victim` to complete the lab.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/0381b7a2-6ae2-4298-9c3c-a5e130cd4fe3)
