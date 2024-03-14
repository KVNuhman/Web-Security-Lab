# Method-based access control can be circumvented

## Lab Description

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/7a7d4d86-4e26-4b1e-825d-d251598fd497)

## Solution

First login in using the given administrator username and passowrd.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/a62e45a5-693d-49ce-bfff-0c8751acb966)

Now we will try to upgrade the user `carlos`.
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/43744e83-77ff-472e-8976-2c6e4aa5c75d)

We use the HTTP history to capture the upgrade request and send it to the repeater.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/5a0d204b-7f4c-4a0d-b93e-fe934b7adaeb)

Now we login using the given user account to get the cookie of the user `wiener` .

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/cac5995f-d64a-4ae2-8836-2b77f9dfbb8d)

In the repeater we change the cookie to the one from user `wiener` and send it. We recieve a response which says `Unauthorized` .

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/d10e90e0-4c8d-4cc0-9081-68605ca1a59c)

Now we change the request method to `GET`.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/be4bea75-b34b-47dc-af04-80b5ccc8f998)

By changing the username parameter from `carlos` to `wiener` we are able to upgrade the user `wiener`.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/b196b49c-815f-45a9-abc7-9467ee3c9901)
