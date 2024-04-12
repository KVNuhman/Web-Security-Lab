# Lab: CSRF where token is not tied to user session

## Lab Description

![image](https://github.com/KVNuhman/Cyber-Forensics/assets/46161259/b4aa4ac5-3362-42d3-87cb-7e7274c47779)

## Solution

Login using the given username and password `wiener:peter` which we will assume to be the victim.

![image](https://github.com/KVNuhman/Cyber-Forensics/assets/46161259/13f41f1f-4647-4a4f-baac-0ee4d3195ade)

Give some random email address and click on **update email** and intercept the request. We can see the request is sent with csrf token attached with the email.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/308383c3-2e3f-4a0f-b87e-d4caac1c3c02)

Now log in using the other account `carlos:montoya` which we will assume to be the attackers account. If we inspect the page, there is a hidden input field named csrf with some value attached to it.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/b4915788-78a3-4853-a079-11213ae65679)

Copy the attackers csrf and paste it in the request intercepted from victim. The email has been changed successfully.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/75433aa1-7501-4523-b43d-427367407969)

If we use the same csrf token again, it respond wth an `Invaild csrf token`.
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/aa51bbf1-46ae-444a-820c-ec513d48cba0)

Go to the orginal request, get a new csrf token by reloadig the account page of the attacker and paste it in the request. Generate an HTML template by going into Engagement tool.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/0ab394d0-401a-4cd9-8ae8-c1e7134db908)

Copy the generated template in the body section in the exploit server, change the email value to whatever value you wanna give. Click on **store** and then **Deliver to victim** to solve the lab.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/5787ce3d-becb-4475-b3b5-d2ab55c4b8ff)
