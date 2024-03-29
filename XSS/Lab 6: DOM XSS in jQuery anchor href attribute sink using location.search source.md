# Lab: DOM XSS in jQuery anchor href attribute sink using location.search source

## Lab Description

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/91400c06-4ecc-495e-b932-3c39008a6261)

## Solution

The page has a DOM XSS vulnerability in submit feedback function. Give some random value in th `returnPath` and we can see it appears in the `href`.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/303ff8e6-8da1-44e6-959a-7872f225ea69)

Now enter `javascript:alert(document.cookie)` as the `returnPath` and it cause an alert when the `back` button is clicked.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/d1584360-f090-427f-a61d-3402fb90942f)
