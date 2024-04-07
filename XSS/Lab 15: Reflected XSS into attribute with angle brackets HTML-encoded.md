# Lab: Reflected XSS into attribute with angle brackets HTML-encoded

## Lab Description

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/a5241d5b-7cb6-4edd-99f8-592e450835c0)

## Solution

Search for something in the search bar, find the get request in HTTP history and send it to repeater.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/6f4bf071-b2e3-4427-ad38-f9b18365631a)

Anything searched is being reflected inside an `input` tag.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/e59098b9-9ce5-40ee-ba00-6827419a1859)

Search for `"onmouseover="alert(420)` and now whenever the mouse hover over the search bar, it causes an alert.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/ea02008c-4b08-41fc-8c5a-c105e493c6a6)
