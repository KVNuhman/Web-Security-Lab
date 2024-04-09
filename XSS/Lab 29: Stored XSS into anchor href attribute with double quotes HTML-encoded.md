# Lab: Stored XSS into anchor href attribute with double quotes HTML-encoded

## Lab Description

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/2ee7db97-575a-4cce-a644-a7440a72f20e)

## Solution

Enter some arbitary values in the comment section and post it.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/1270d738-e1e3-48dc-bfb0-da142d9a103b)

The website entered is being reflected inside an `href` tag.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/eeaccb5e-6ba2-484d-b79d-0497516b69d3)

Give some arbitary values again, intercept the request and chnage the website to `javascript:alert(1)` to cause the XSS vulnerability.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/8e4e1329-f004-4981-b6e8-a8857957e31e)

Whenever someon clicks on the username of the post we added, it causes the alert to occur.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/6648d868-caca-465d-8e7a-15c8c3fabd41)
