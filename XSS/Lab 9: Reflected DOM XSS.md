# Reflected DOM XSS

## Lab Description

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/f8dcbd0b-b8e3-44ef-95ff-39a534b52f54)

## Solution

The wbsite has a vulnerabilty in the search section. Enter a random string and the string is reflected in a JSON response called search-results.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/adbdb1fd-e303-4b76-9ae4-edd79fec478b)

In sitemap, go to `searchresult.js` and you can see that the JSON response is used with an eval() function call.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/e3c2be89-5632-4903-9017-cdb2baa879a5)

Enter `\"-alert(1)}//` in the search function to cause the alert and solve the lab.
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/9dc50876-eb47-4482-91e4-5fa6702b4546)
