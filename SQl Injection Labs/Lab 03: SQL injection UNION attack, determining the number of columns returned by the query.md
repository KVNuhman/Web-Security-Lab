# SQL injection UNION attack, determining the number of columns returned by the query

## Lab Description

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/55b7d7b2-4180-4b89-b9fc-a3d84f0c3176)

## Solution

We inject the `UNION SELECT NULL` statement into the category filter and increment the number of times `NUll` is used.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/0bcf6a00-3c40-481a-a148-84ffc28586ad)

When three `NULL` keywords are given the server doesn't throw and error and we can understand the resultset rerurns three columns.
