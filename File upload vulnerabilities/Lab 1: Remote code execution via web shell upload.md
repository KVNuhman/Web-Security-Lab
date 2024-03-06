# Remote code execution via web shell upload

## Lab Description

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/df780eb0-4e05-479c-a972-8370256a47b7)

## Solution

Login to the account using the username and password given. In the avatar upload section choose an image and upload.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/599b4d49-98f2-411e-b88a-ad6d4b75f2e1)

A conformation for successful upload is shown.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/73f5779c-28f6-4fee-a367-57b8e6b28b90)

In Proxy inside the HTTPHistory filter the section by selecting images in under Filter by MIME type.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/760650f0-2625-435c-90ab-c52a76c587ad)

The selected section shows the image we previously uploaded and it was shown using a `GET` request.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/805abfd4-44b9-4fca-9932-28c077c44db8)

Create a malicious php file called `exploit.php` with content being `<? php echo file_get_contents('/home/carlos/secret')>`. It enables us to read and display contents of file `secret` . Now upload it to server the same way the avatar picture was uploaded.
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/298ab66c-5211-44be-be14-7ad27143c00e)

The file has been uploaded successfully. In the response section we can see the content of the file secret `GLtDfJ0iNkBkS38O6gjfmxuFvQyGVroV` .
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/8bca5f8f-be6b-4e5b-ba6c-98b238de43db)

Entering the secret in the submit solution alert box finishes the lab.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/73550f8c-9a23-4908-a235-1ddcbb9cb02d)
