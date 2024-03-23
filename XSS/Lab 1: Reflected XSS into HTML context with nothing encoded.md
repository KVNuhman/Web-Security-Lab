# Reflected XSS into HTML context with nothing encoded

## Lab Description

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/b9c7f049-889c-4cfc-8211-443545c1d50e)

## Solution

The website has a vulnerability in the search section. Search `<script>alert("This is an alert")</script>` to make the website create an alert.
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/befc14b6-0731-4c42-8ee4-1cfe808626d3)

The XSS is successful as the webiste generates an alert.
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/1c0c7003-586f-4b9b-915b-6181b6e1e312)
