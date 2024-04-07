# Lab: Reflected XSS into HTML context with most tags and attributes blocked

## Lab Description

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/59d86b6f-ea58-4d59-a41f-c2f9c8092ca4)

## Solution

Try entering `<img src=1 onerror=print()>` in the search bar and it loads to say Tag not allowed.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/b4a2bca5-164a-44e8-b38f-ee03499be0a2)

Find the Get request in HTTP history and send it to intruder.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/c614c6f6-1036-4b59-b2ef-9493f784bfe8)

Clear the value in search and give `<§§>` for the payload.
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/4e98eda3-6f05-4fdf-ba9b-9c17b466bb63)

Go to the XSS cheat sheet page in port swigger and click on Copy tags to clipboard and paste it as payload in Burp intruder.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/2991eaa5-124d-422c-9d01-5689dcf6c431)

We can see that body tag returns a status code of 200.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/6bce73ad-b802-4693-8ce7-2319f3d5c6bc)

Net click on Copy events to clipboard in XSS cheat sheet and paste in the payloads section of Burp Intruder.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/06b9dddc-f98a-4be6-9921-86d4b6f8176f)

onresize event gives a status code of 200.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/cbeca112-be39-4cc1-a935-393de062676f)

Go to exploit server and enter `<iframe src="https://YOUR-LAB-ID.web-security-academy.net/?search=%22%3E%3Cbody%20onresize=print()%3E" onload=this.style.width='100px'>` in body, click store and Deliver exploit to victim to send the exploit and finish the lab.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/88a7a7b5-3a64-4dfe-859f-4c8c74ae01c1)
