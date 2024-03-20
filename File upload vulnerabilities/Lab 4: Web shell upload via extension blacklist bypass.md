# Web shell upload via extension blacklist bypass

## Lab Description

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/d96fa2e6-ec8f-482f-858a-7aa0008b49b2)

## Solution

Log in using the given username and password `wiener:peter` and upload an avatar jpeg image.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/48bd70e4-f1fe-4217-ae40-9b642b505efc)

Create an **exploit.php** file to retrieve the secret.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/eb704d28-059f-440f-9bb2-de0f1c102558)

Upload the **exploit.php** as avatar, the server restricts us to upload a .php file.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/a736fe51-670c-4331-a122-3dc838e1a63b)

Identify the POST request in HTTP Histroy and send it to bup Repeater.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/a42ebae4-512c-45f1-ae15-e140f8e0cc11)

We have to make some changes to the request:

- Change the value of the **filename parameter** to `.htaccess`.
- Change the value of the **Content-Type** header to `text/plain`.
- Replace the contents of the file (your PHP payload) with the following Apache directive:
  `AddType application/x-httpd-php .l33t`

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/b59bca5a-cf16-48de-9c46-230eef9678b6)

Now go back to the original POST request and change **filename** from `exploit.php` to `exploit.l33t` .
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/a059c86a-6616-428d-b6ce-51cb9a8b28d4)

Now when the avatar is being accessed the secret is shown. Submitting it in the Submit Solution section finishes the lab.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/26590df9-f4bf-465f-b8cb-e62b179a50de)
