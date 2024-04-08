# Lab: Stored XSS into onclick event with angle brackets and double quotes HTML-encoded and single quotes and backslash escaped

## Lab Description

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/8bf9da2c-5fb3-4083-b001-6ba37d1a41a7)

## Solution

To post comment the it asks us to give a website .

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/b6b658f1-4f60-4732-bd09-d9097d5e746b)

The given website given in comment is reflected in the result inside an `onclick` event.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/02f3c37e-08a2-48e9-9db0-334d7265d862)

In the comment give the website as `http://foo?&apos;-alert(420)-&apos;` and when the posts loads, click on the name on the comment to cause the alert and to finish the lab.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/d12a3103-5e60-40f0-ad4f-14e671cd38e2)
