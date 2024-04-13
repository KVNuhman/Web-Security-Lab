# Lab: CSRF where Referer validation depends on header being present

## Lab Description

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/96fafa13-6eae-43ae-9ffc-f77fb9a2350b)

## Solution

Log in using the given username and password and make an email update request using any email id.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/38bf8067-f3f2-4f57-b02d-969bb986b21b)

Find the `POST` request in HTTP history and send it to repeater. Observe that the request has a `Referer header` present.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/16846b39-421a-414f-bbbb-7cbf09509854)

The page will reject the email update if the referer header is removed or not present in the request.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/91b5d75a-ba29-486f-a377-cd6977973e79)

Generate a CSRF PoC using engagement tools and add `<meta name="referrer" content="no-referrer">` to it by placing it in a head tag.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/7482874b-7fca-4ba2-ba08-33e9b45003ae)

Copy the PoC into the body section of exploit server. Click on Store and then deliver to victim to finish the lab.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/669c0b54-d6cb-46e0-be8f-1927f9280a6b)
