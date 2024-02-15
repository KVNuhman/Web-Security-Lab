# Visible error-based SQL injection

## Lab Description

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/e70d3e86-de1c-4e8b-b47a-7408df7995fe)

## Solution

First we will try to generate an error by adding `'` to the tracking ID which is successful. This lets us see the sql query that is happeing in the backend which is
`SELECT * FROM tracking WHERE id = 'TJv9sI9SgdDuX4B5''`.
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/d0898285-aad0-4f43-a685-f7885ee5cf82)

Now we will use the CAST fucntion to see now the server reacts, so we add `' AND CAST((SELECT 1) AS int)--` in the trackingId.
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/f15e9992-155d-4c49-a66b-3185c1421b7a)

In the earlier step we got an error saying AND must be type boolean so me modify the command to `' AND 1=CAST((SELECT 1) AS int)--`.
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/b760024d-eb3a-4437-bbf7-09e72efba029)

We modify the statement again by `' AND 1=CAST((SELECT username FROM users) AS int)--`. This enables us to fetch a `user` from the `users` table.
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/da5fd64c-076d-4cfd-9c81-68463435f903)

In the earlier step when we tried to fetch a `user` an error was generated and on close inspection we can see the statement is truncated. So we modify the statement again as `TrackingId=' AND 1=CAST((SELECT username FROM users) AS int)--`.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/aab12495-258a-43be-aa53-59f8f4b1f7f3)

Above we tried to fetch all the users so now we will limit it to one by modifying the satement using `LIMIT 1`. This generates and error but we are able to see that the first user is `administrator`.
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/45e28f8d-8c9f-4598-a1e8-8136db8dd895)

We use the same command as above but this time we try to fetch the password and in the error message the password is visible which is `w45s460ukqri2m1cj617`.
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/37a61d95-f5a9-4c85-a021-8ed20b677e88)

By using the username as `administrator` and password as `w45s460ukqri2m1cj617` we are able to login.
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/73976873-82eb-442a-8c87-0c48226812fc)
