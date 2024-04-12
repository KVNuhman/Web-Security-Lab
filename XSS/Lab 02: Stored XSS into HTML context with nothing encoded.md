# Stored XSS into HTML context with nothing encoded

## Lab Description

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/c31cd69c-8c57-4ac4-8467-23bb09216c75)

## Solution

This website has an XSS vulnerability in the comment section. Give the payload in the comment and enter some values for name, email and website.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/0b860d74-422f-4d87-81c5-6349598cd50f)

As we submit the comment we get the pop saying lab is completed.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/d331dcec-6814-45b6-8d39-3f4d9effed28)

If we go to the post we commented on, eveytime the page loads, the alert is shown, hence the Stored XSS is successful.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/1fa34378-4da6-4bff-81fd-dea487d14cc1)
