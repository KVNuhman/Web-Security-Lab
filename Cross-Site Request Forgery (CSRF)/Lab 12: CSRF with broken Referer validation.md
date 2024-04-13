# Lab: CSRF with broken Referer validation

## Lab Description

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/7c9bcd4e-dc2f-4baa-ad20-dfe7d99e58af)

## Solution

Log in using the given username and password and make an email update request using any email id.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/6da4eda3-e94d-4b40-a661-9211cd562878)

Find the `POST` request in HTTP history and observe that a Referrer header is present.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/88de1a49-fe97-465a-be7b-948fd31262bc)

The request is rejected if the Referrer header is removed.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/4fb34422-dc28-4307-ac77-38cacb2bfeef)

Copy the original domain of your lab instance and append it to the Referer header in the form of a query string. The website seems to accept any Referer header as long as it contains the expected domain somewhere in the string.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/8dbd33c6-795b-43b8-82a6-d744145cfca3)

Generate a CSRF PoC, edit the h`history.pushState()` function includes a query string with your lab instance URL as follows:
`history.pushState("", "", "/?YOUR-LAB-ID.web-security-academy.net")`

> 1. This line calls the **pushState() method** on the history object, which is part of the browser's window object. It **allows you to manipulate the browser's history stack, including the URL**.
> 2. The pushState() method takes three parameters: **state, title, and URL**.
>
> In this case, the first parameter (state) is an empty string, which means **there is no specific state associated with the URL change**.
> The second parameter (title) is also an empty string, which means the **document title remains unchanged**.
> The third parameter (URL) is set to /?0ab3004f04adb0f080c1c16d007f0016.web-security-academy.net.
>
> This **modifies the URL of the current webpage to /?0ab3004f04adb0f080c1c16d007f0016.web-security-academy.net without triggering a page reload**.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/aac2f5a7-c447-4625-8420-15b7060ce787)

Copy the HTML template to the body of exploit server. Add `Referrer-Policy: unsafe-url` header to solve the issue of modern browsers now stripping the query string from the Referer header by default. Now deliver the exploit to victim to Finish the lab.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/28077a0c-7db4-4959-aa62-9ceba5ebacdf)
