# Lab: SSRF with whitelist-based input filter

## Lab Description

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/ceb92c0b-b906-4247-918c-65fe8e55fe5c)

## Solution

The page checks stock using a stockApi parameter.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/15ef9d93-b6ab-4f00-ac00-25ab6f6622de)

Change the URL in stockApi to `http://127.0.0.1/` or `http://localhost/` , the request will be blocked saying it must be from `stock.weliketoshop.net`

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/8db8000f-59a8-4e9a-89f3-c7bd2f2e8cbe)

Change the URL to `http://something@stock.weliketoshop.net/` and the request goes through.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/00abe7e9-4f93-4ae2-b2dd-061f227ec4c8)

Append # to something making the URL `http://something@stock.weliketoshop.net/` and the request fails.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/651f46af-a28c-4944-9285-b538aef1fc34)

Send the request again by double encoding # in the above url to make it `%2523` and the request goes through.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/125d6903-5f94-403a-9245-0c1a7e2e451c)

Use the URL `http://localhost:80%2523@stock.weliketoshop.net/admin/` to access the admin panel.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/96394f42-e745-4680-b013-ef635282d69f)

Use the URL `http://localhost:80%2523@stock.weliketoshop.net/admin/delete?username=carlos` to delete user carlos and finish the lab.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/6b037b6f-f55c-4417-821b-1845044c717c)
