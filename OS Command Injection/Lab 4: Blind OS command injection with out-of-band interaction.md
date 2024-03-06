# Blind OS command injection with out-of-band interaction

## Lab Description

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/8757fbd8-b6f8-4f64-a17c-1c9dc091ad47)

## Solution

The vulnerability is in the feedback form of the website. So we first input some values, submit it and intercept the request using burp interceptor.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/f501d905-75b8-447e-96b9-4266ad99bccc)

We can insert payload in the email field by using the `insert Collaborator payload` option.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/dd890397-1f40-48ae-aad1-4c2870b8ce4d)

After inserting the payload moodify it by adding an `nslookup` in the start and using `&` to add this with out previous email input. The entered payload can be url encoded by selecting it and clicking `CTRL + U`. We can see the server responds with `200 OK`.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/582d0944-2549-4712-8014-6734d23efdc1)

Now if we go to collaborator we can see an nslookup was made and the deatils will be shown which successfully completes the lab.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/bfdd32b5-6423-4c64-9aab-7690a08d27be)
