# Web shell upload via obfuscated file extension

## Lab Description

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/08ffb1ed-9443-48bb-bff2-3be6038f88b1)

## Solution

Log in using the given username and password `wiener:peter` and upload an avatar jpeg image.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/be22158b-7538-4b1c-8228-52b577285983)

Create an **exploit.php** file to retrieve the secret.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/eb704d28-059f-440f-9bb2-de0f1c102558)

The server doesn't allow uploading **.php** files.
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/3f37bc99-4643-4ad4-80a7-264cc787859b)

Change the file name by adding a null character, change the filename to `exploit.php%00.jpg`. The file is successfully uploaded.
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/cc5094ef-096a-4ce2-9363-758f10dc1640)

The secret can be accessed by going to `files/avatar/exploit.php`.
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/5f4699b7-a69f-4225-b294-5d13f22a74ff)
