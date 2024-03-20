# Web shell upload via Content-Type restriction bypass

## Lab Description

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/f602ccf6-4c80-4aec-ba81-8c414bb855a2)

## Solution

Log in using the given username and password `wiener:peter` and upload an avatar jpeg image.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/be22158b-7538-4b1c-8228-52b577285983)

In HTTP History we can see the post and get request. Send them to Repeater.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/d6707dc5-da8d-41c9-882d-905fc360ae85)

Create an exploit.php file to retreive the secret.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/eb704d28-059f-440f-9bb2-de0f1c102558)

When we try to upload the file directly, the server restricts prompting to upload jpeg or png files.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/2adc5d5f-d4d3-4d69-aee5-b39c71b4b3d7)

Identify the above post request in HTTP History and send it to Repeater.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/241b63c5-498e-4bd8-ae0e-1115a4893fe7)

Change the **Content Type** to **imgae/jpeg**, this will enable the file to be uploaded successfully.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/55d9bccd-76e8-41b0-b50c-8fed0bcca1cc)

The secret is visible when the avatr section is opened in a new tab. Submit it in the **Submit Solution** section to finish the lab.
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/8c843495-d3de-41d0-a0b0-a4f5fb6d4f10)
