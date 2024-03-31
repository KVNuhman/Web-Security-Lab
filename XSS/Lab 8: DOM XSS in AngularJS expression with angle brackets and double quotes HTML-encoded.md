# Lab: DOM XSS in AngularJS expression with angle brackets and double quotes HTML-encoded

## Lab Description

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/77a4e024-5f32-49e1-bab7-ecc0600ebc9e)

## Solution

The page has a vulnerability in the search section, search for some random string.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/4b792cd0-8d25-4143-88e9-8a48af6ccb59)

The searched word appear in inside the `ng-app` directive.
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/ee57e13d-2a73-4fe1-95bb-a03cd072cb0c)

Enter `{{$on.constructor('alert(420)')()}}` in the search box to cause the alert to happen and solve the lab.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/1dd151c5-e212-4af4-933a-a4be4265a897)
