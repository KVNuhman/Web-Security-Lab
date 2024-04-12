# URL-based access control can be circumvented

## Lab Description

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/ba2fa4ad-8da6-4f51-b9fd-5e887385d3f7)

## Solution

The website has an admin panel and when we try to access it, it shows `'Access Denied'` .

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/38e1b821-2843-4949-a070-825327776b9b)

We edit the `Get` request by only giving `/` in the request and by appending an HTTP header `X-Original-URL: /invalid` . This gives us a `not found` response.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/111a3b92-1409-459c-817e-3164efcb739d)

Now by changing `/invalid` to `/admin` we are able to access the admin panel.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/c309544c-014d-446b-94da-905643e91b83)

Specify the header as `/admin/delete` and parameter as `?username=carlos` to delete user carlos.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/56bb65bd-a5c3-4974-b6d8-39e7d318a5e4)
