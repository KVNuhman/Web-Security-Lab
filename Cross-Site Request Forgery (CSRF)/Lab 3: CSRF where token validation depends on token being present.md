# Lab: CSRF where token validation depends on token being present

## Lab Description

![image](https://github.com/KVNuhman/Cyber-Forensics/assets/46161259/eafbe789-b246-431c-98af-2944470d3b0c)

## Solution

Log in using the given username and passowrd and click on **Update email** with some arbitary value.

![image](https://github.com/KVNuhman/Cyber-Forensics/assets/46161259/c4d20500-a7d5-477c-a5eb-a62ea279fe24)

An email update request has a CSRF token appended along with the email.

![image](https://github.com/KVNuhman/Cyber-Forensics/assets/46161259/1b5296f4-9613-4b19-9047-4db613f53f01)

Remove the csrf token from the request and resend it. It seems that the update request still works without the token present.

![image](https://github.com/KVNuhman/Cyber-Forensics/assets/46161259/5aa8be01-e726-4236-b5d2-eb1e9913a118)

Go to the oiginal request, remove the csr token and generate HTML template by going to **Engagement tool**.

![image](https://github.com/KVNuhman/Cyber-Forensics/assets/46161259/69aafd70-d4e4-45c9-80fb-eef120986359)

Copy the generated HTML template and paste it in the body section of the exploit server. Click on **Store** and then **Deliver to victim** to solve the lab and finish the exploit.

![image](https://github.com/KVNuhman/Cyber-Forensics/assets/46161259/610a3431-665b-4289-8bb9-4176d79e3cee)
