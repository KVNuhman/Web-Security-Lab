# Multi-step process with no access control on one step

## Lab Description

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/1251a165-89ab-410f-95fa-725b2d5608cb)

## Solution

Log in as administrator using the given username and password and try to upgrade the user carlos as admin.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/1f21d470-80a9-43b1-a4fa-eac8e1fe1564)

We are now promted to verify if we are sure about the upgrade.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/a0ee003b-fee1-4e99-8044-5ced485ff87c)

In burp proxy in HTTP History, identify the both requests and send them to Repeater.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/edfa5501-b06e-4a12-a337-d5fef81360a4)

Log in as the normal user `wiener:peter` and get the session cookie.
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/8b8fa9a1-2630-484c-adab-edcef3d4f6be)
kgU7G0fVUh9HwDIJsa4RzuY3VQXW1KyG

Use the above obtained cookie and place it in the above request and change the name from carlos to wiener. Since there is no access control is the second step, the lab is solved successfully.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/ed8223b8-08fd-4ffa-a676-58a0a8510615)
