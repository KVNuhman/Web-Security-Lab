# User role controlled by request parameter

## Lab Description

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/6589bcd7-51b8-4ba0-b4d8-d394a04dbbbd)

## Solution

First we will login using the provided user id and passowrd `wiener:peter` and intercept the request. We can see that there are two cookes and one of them is `Admin` and it is set to `false`.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/7558565c-6c0d-4d97-9084-a8a5353eb341)

We inspect the page and change the cookie value to `true` by going into `Applications` .

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/0842506d-00bd-48b2-a029-365ad02f941d)

Now we are able to access the admin panel.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/4fe6dffa-72c7-45dc-a9db-e696fc70d0ec)
