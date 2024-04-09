# Lab: Reflected XSS protected by CSP, with CSP bypass

## Lab Description

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/c3b74c85-b9a7-456b-8f06-5cf2850dc2d4)

## Solution

Search for something in the search bar and it is reflected in the result. Search for `<img src=1 onerror=alert(1)>` but the CSP prevents the script from executing.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/a758ab4e-927b-42f6-a1b4-596ac11319a4)

Append `?search=%3Cscript%3Ealert%281%29%3C%2Fscript%3E&token=;script-src-elem%20%27unsafe-inline%27` to the lab url.

The injection uses the `script-src-elem` directive in CSP. This directive allows you to target just script elements. Using this directive, you can overwrite existing `script-src` rules enabling you to inject `unsafe-inline`, which allows you to use inline scripts.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/ab37a581-a7b7-49bb-90cd-de313082742a)
