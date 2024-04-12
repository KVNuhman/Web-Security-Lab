# Web shell upload via path traversal

## Lab Description

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/31866c0a-a043-4e47-bc98-8b361a4c14a8)

## Solution

Log in using the given username and password `wiener:peter` and upload an avatar jpeg image.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/abf7915e-a6e6-4094-a23d-7750091bbf5a)

Create an **exploit.php** file to retrieve the secret.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/eb704d28-059f-440f-9bb2-de0f1c102558)

Upload the **exploit.php** and we can see the upload is successful.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/0138e248-9acf-4d92-8344-09c33cdcdaf0)

When tried to GET the exploit.php file, rather than executing it, the file's content is shown as plain.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/96777ec9-816d-424a-a580-f50c5ad50794)

Identify the POST request in HTTP History and send it to Repeater.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/a9d1a05b-59e4-4a0c-87ef-998e30458148)

Use path traversal to save the file one directory above by giving the name as, `../exploit.php` . The response shows that the browser strips **../** .

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/7b7d3be3-b96d-41a2-8ecd-aba2d32fc552)

URL encode **../** by changing it to **..%2f** . The browser response shows the upload is successful in the directory we required.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/b7c043e0-b77f-4dde-959d-d8357047b505)

We can see the secret using GET request for file/avatar/../exploit.php

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/59c44f7d-e1f1-437c-a1cb-ce8959093c36)
