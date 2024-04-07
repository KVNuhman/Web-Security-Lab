# Lab: Reflected XSS into a JavaScript string with single quote and backslash escaped

## Lab Description

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/edaddbc2-4400-456c-8769-0a1b172bfb85)

## Solution

Search for something and in the result the seached value is reflected in the javascript.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/6e488a6d-a5bd-4777-bb54-aa710777bd6c)

Search for something that has `'` and in the script it gets turned into `/` preventing us from breaking out of the string.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/18b89145-19e7-49f5-b3bb-42a8fd9161e8)

Now search for </script><script>alert(420)</script> to cause an alert to happen solving the lab.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/7bd31d9e-0e8c-4a2b-bdbf-606bafd7efc0)
