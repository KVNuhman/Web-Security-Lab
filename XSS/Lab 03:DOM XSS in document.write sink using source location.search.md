# DOM XSS in document.write sink using source location.search

## Lab Description

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/fa88b051-bb6a-4433-b8a7-a2b259110360)

## Solution

The webiste has a vulnerability in the search section. The item searched is being entered in the **img** element.
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/74585015-c968-411f-aef3-390baf234352)

Use `"><svg onload=alert(1)>` to create an alert to cause XSS.
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/07a613b7-19a4-4c2c-9877-a96ad654e8d5)
