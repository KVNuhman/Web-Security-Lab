# Lab: Reflected XSS into a template literal with angle brackets, single, double quotes, backslash and backticks Unicode-escaped

## Lab Description

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/c521781f-1223-4cbd-a27a-0d426f44166d)

## Solution

Search for something in the search bar and the search value is reflected as a Javascript template string.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/37c26c87-5b97-40d7-a0e3-e25b3c1ed79d)

Search for `${alert(420)}` to break out of the template string to cause an alert.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/95444655-d55f-46f8-9616-0a1d93675157)
