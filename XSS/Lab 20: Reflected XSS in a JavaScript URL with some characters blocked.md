# Lab: Reflected XSS in a JavaScript URL with some characters blocked

## Lab Description

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/024752c0-a296-40ba-b679-ca974e91b2e2)

## Solution

Append `/post?postId=5&%27},x=x=%3E{throw/**/onerror=alert,1337},toString=x,window%2b%27%27,{x:%27` in the url and a post opens up.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/19678074-5b63-4c50-8fa1-1ece028dfb8e)

Click on **Back to blog** to trigger the alert.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/7c087cf8-43a4-4806-a178-e28238eb5c33)

> The exploit uses exception handling to call the `alert` function with arguments. The `throw` statement is used, separated with a blank comment in order to get round the no spaces restriction. The `alert` function is assigned to the `onerror` exception handler.

> As `throw` is a statement, it cannot be used as an expression. Instead, we need to use arrow functions to create a block so that the `throw` statement can be used. We then need to call this function, so we assign it to the `toString` property of `window` and trigger this by forcing a string conversion on `window`.
