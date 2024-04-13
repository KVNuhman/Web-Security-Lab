# Lab: Blind SQL injection with time delays

## Lab Description

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/815f06f6-c21e-4311-9631-60641f17c1db)

## Solution

Go to home and you can see the request has a tracking id.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/34b62db6-81ad-4775-beab-02ee12976bd1)

Modify the TrackingId cookie, changing it to: `TrackingId=x'||pg_sleep(10)--` to cause the delay and solve the lab.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/7f2f175b-caef-4d9c-9f48-82b894d5a953)
