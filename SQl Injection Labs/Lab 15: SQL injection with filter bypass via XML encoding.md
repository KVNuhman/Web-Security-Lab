# SQL injection with filter bypass via XML encoding

## Lab Description

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/53e6bf9d-5164-4ac1-a9ef-dcd73030063e)

## Solution

The check stock option in the website use xml. When used in repeater we can see the number of stock can be seen.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/b34485b2-137c-4083-b172-0d222c851a28)

The `storeId` is modified from `1` to `1+1`, the website repsonds with a `820 units` left.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/bd987c57-3197-4ac9-90af-6978b318710b)

When an SQL Injection attack with the payload `1 UNION SELECT NULL` is tried the `WAF(Web Application Firewall)` flags it as an attack and responded by `Attack Detected`.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/d46b0511-0029-49ab-85f8-5940bc7d1e28)

To encode the payload we use Hackvector extensin in Burp which can be installed from the extensions tab.
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/8f554e11-6ac9-4f35-8649-c69a14bd4952)

We can now encode our payload so that the `WAF` wouldn't be able to flag it. Hence the payload becomes `<@hex_entities>1 UNION SELECT NULL<@/hex_entities>`.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/4dfd9271-1782-439a-9e9b-e48f5e8b48fd)

We use burp repeater to see if the encoding worked and by looking at the result, we have successfully bypassed the `WAF` .
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/9131ff8d-c45d-4f45-9b58-1504d72d0e6d)

Since the previous attack was successfull, now we figure out how many rows are being returened by adding another `NULL` in our payload and since it responds with `0 units` we can understand that only one row is being returened.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/bd1c3ce3-4102-4d55-b1d8-30867b95209f)

Since we know only one row is being returned we use the payload `<@hex_entities>1 UNION SELECT username || '~' || passowrd from users<@/hex_entities>` to list all the users and their passowrds in the ursers table.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/10752e26-287a-4ca2-a848-7d46ac35ca9d)

The username `administrator` and passowrd `dtwaafyc8n21ai8lp53n` is used to successfully login into the administrator account.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/38ce2314-5479-4f74-b87f-d502622eb22e)
