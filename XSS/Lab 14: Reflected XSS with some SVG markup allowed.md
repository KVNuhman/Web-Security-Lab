# Lab: Reflected XSS with some SVG markup allowed

## Lab Description

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/db355e3a-539c-4540-9337-86a380621443)

## Solution

Try searching `<img src=1 onerror=alert(420)>` and on loading the page will say **Tag is not allowed**.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/ccb9707f-dd5b-4d15-b089-dbd7c81340c6)

Find the get request in HTTP History and send it to burp intruder.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/08765a72-3ba3-46b1-a0f0-7bf298305b2d)

Clear the search field and add `<§§>`.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/050db5de-1cd4-4da0-b5d2-969388772a99)

Go to XSS cheat sheat and click on **Copy tag to clipboard** and paste in the payload section. We can see `<svg>`, `<animatetransform>`, `<title>` and `<image>` reuturns status code 200.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/96981291-f0e3-48a2-b031-fba2816a9778)

Now change the search to `<svg><animatetransform%20§§=1>` and paste the content from **Copy events** in XSS cheat sheet to payload section.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/5fe893d6-f36b-4588-9d41-bd2b4d7d72b9)

In the result `onbegin` returns status code 200.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/bf555a5a-0ed8-44f5-85f4-3c9c69f623bd)

Append `/?search=%22%3E%3Csvg%3E%3Canimatetransform%20onbegin=alert(1)%3E` to the url and hit enter to finish the lab.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/54f944de-cdd3-491d-9245-163e24208697)
