# Remote code execution via polyglot web shell upload

## Lab Description

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/1e31b13d-c936-4dc1-9e86-4f6fc2ca510b)

## Solution

Create an **exploit.php** file to retrieve the secret.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/eb704d28-059f-440f-9bb2-de0f1c102558)

The server doesn't allow upload of **.php** file.
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/b72f552e-b1b4-4739-bfa1-790db85f9820)

Use exiftool to create a polyglot PHP/JPG file that is fundamentally a normal image, but contains your PHP payload in its metadata.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/372dcd50-c9b8-4a22-8716-f65081a2f14d)

The polyglot.php is successfully uploaded.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/098aa7c2-63c9-4c20-9b74-d98c5a4389e5)

The secret key is the one after `START` in the response when you access files/avatar/polyglot.php . Submitting the secret in Submit Solution finishes the lab.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/1717588e-b328-4bc9-9688-b775129191e2)
