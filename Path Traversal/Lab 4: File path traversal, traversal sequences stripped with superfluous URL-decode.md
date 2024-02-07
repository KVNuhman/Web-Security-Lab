# File path traversal, traversal sequences stripped with superfluous URL-decode

## Lab Description
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/48423f6a-255a-44d7-9e2c-0b1ccfde41b2)

## Solution
Here we do a double url encoding and convert the payload to `%252e%252e%252f%252e%252e%252f%252e%252e%252fetc/passwd`. We modify the filename parameter and we are able to see passwd file in the server.
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/e4f9d69a-24b9-4aea-8ade-bd61fef1dfda)
