---
title: REST API's
category: API's
category-order: 2
order: 1
---


There are two main API's for the ForgeRock Identity Cloud: the Authentication API and the Management API. 

##### Authentication API
This allows you to authenticate users to gain access to your applications or assign to access the Management API. You can use this API if you want to build authentication into your apps without using the hosted login pages. 
[Explore the Authentication API](#)

---

##### Management API
The Management API allows you to manage users and other objects in the system. To call this API you need to create a Machine 2 Machine application under 'applications' and assign it to the API. You can then exchange a client ID and secret for an access token and call the API using the token.
[Explore the Management API](#)



