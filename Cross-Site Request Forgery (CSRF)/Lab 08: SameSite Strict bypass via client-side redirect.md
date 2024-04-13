# Lab: SameSite Strict bypass via client-side redirect

## Lab Description

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/801a51ee-9ead-4b18-a2a9-39fe130ae9aa)

## Solution

Log in using the given username and password and make an email change request with some random email.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/e763c63c-7797-4086-a06d-08e0b5d930cd)

Inspecting the `POST` login request from HTTP history, the `SameSite` cookie attribute is set to `strict`.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/25256899-82aa-46bf-ae79-3de26f151315)

Inspecting the `POST` email change request, the `Samesite` cookie attribute is not set to anything.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/43ff85bb-3ac0-464e-a270-c046e8ed3f42)

Click on any blog post and comment something on it.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/509d03c7-01ae-43fd-a585-0532a39c980f)

After posting the comment, we are present with a page showing redirection and then redirected to the blog we commented on.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/e708fee2-cd7e-46ae-b712-b24fead60748)

The above redirection is done by a `js` script .

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/41a16346-c607-4404-84ad-5c6f16deeaa8)

Copy the URL path and your lab url, append both and paste it on a new tab. Change the post id to some random value for example `https://YOUR-LAB-ID.web-security-academy.net//post/comment/confirmation?postId=test`. Here we are using `postId` as `test`. The page first takes us to the reirection page.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/e708fee2-cd7e-46ae-b712-b24fead60748)

The redirection page then leads to a `404 not found` page.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/38a642ae-f5c6-47e9-8ebd-0c7ebcf87a4e)

If we modify the previously used URL to include some path traversal like `/post/comment/confirmation?postId=1/../../my-account`, the page is redirected to the account page in the website.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/45f0d48f-eb04-4bce-81e8-f19af73499d4)

Go to exploit server and paste the followng script:

```Javascript
<script>
    document.location = "https://YOUR-LAB-ID.web-security-academy.net/post/comment/confirmation?postId=../my-account";
</script>
```

Click on **Store** and **Deliver to victim**, and page takes us to logged in users account page.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/c13fc546-5d01-410b-8a13-5b589dc0ac72)

As mentioned above the redirect leads to account page of victim.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/7c95e9b0-47b7-46dc-90ae-66e8d051de64)

The endpoint allows us to change the email address if the request is changed into a `GET` request.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/f85a0de5-cc11-402c-9a21-f8e36b5e19b3)

In the body section enter the following script

```Javascript
<script>
    document.location = "https://YOUR-LAB-ID.web-security-academy.net/post/comment/confirmation?postId=1/../../my-account/change-email?email=tes%40web-security-academy.net%26submit=1";
</script>
```

Change the email to the one you want and Deliver to the victim to finish the lab.
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/665377a7-bf8c-4de0-9f91-c0e135b14c0d)
