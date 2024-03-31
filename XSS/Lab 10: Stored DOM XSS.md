# Stored DOM XSS

## Lab Description

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/405b0a63-d577-4cde-b207-281fdfb1ea81)

## Solution

The website has a DOM XSS stored vulnerability in the comment section of any posts. Post `<><img src=1 onerror=alert(420)>` under any post.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/6105b673-f1e9-46dd-b958-eb5de56ea698)

Whenerver the post which was commented on is loaded the alert pops up.
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/9a7af53c-6327-485a-8ac1-c501cf1e3dde)
