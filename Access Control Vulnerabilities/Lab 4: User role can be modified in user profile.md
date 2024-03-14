# User role can be modified in user profile

## Lab Description

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/adb7996b-2c10-4442-bacf-620d1f985fd9)

## Solution

Go to the my account section of the website and type in some random email id.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/2e1fbb29-33b4-4aa9-af2a-703ce7d80dc6)

In the http history we can see that the update is being send with a `roleid: 1` .
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/6a570888-ff2c-470b-8e74-89171d94f633)

Send this to the repeater and add in `roleid:2` with the email.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/6390d2b5-d211-42cb-b5e7-4e9322536c35)

This change has opened up an admin panel that we can now access.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/660ff328-3378-4d41-ab5f-001b5749abd3)
