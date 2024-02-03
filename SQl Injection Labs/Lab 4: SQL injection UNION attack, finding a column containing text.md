# SQL injection UNION attack, finding a column containing text

# Lab Descriptions

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/9ec8c0df-06ad-4253-9b94-a9675dada9d6)

## Solution

First we use the `UNION SELECT NULL` to find the number of columns in the resulset.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/27daec12-beee-4d87-a1b4-8c18467309e7)

We can understand that the resultset has three columns.

Next task is to display the given keyword `TEBwy2`.This can be done by changing the `NULL` into the keyword and when the column which return a string matches with it the keyword is displayed.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/3a87dfdb-d5ab-415a-9a82-e8aedbfa523b)
