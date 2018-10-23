---
title: REST APIs
category: APIs
category-order: 3
order: 1
---


There are two main APIs for the ForgeRock Identity Cloud: the Authentication API and the Management API. We've created Postman collections describing the APIs and allowing you easily make calls to these APIs. To run the calls in Postman [download](https://www.getpostman.com/apps) and open postman, go to the links below, click the 'Run Postman' button in the top right of the screen to open the collection in postman. 

### Authentication API
Allows you to authenticate and authorize users and apps or assign to access the Management API. 
<a href="https://developer-api.forgerock.com/#45dc632b-91f2-4ea5-a9da-d4d9f395cfd5" target="_blank">Explore the Authentication API</a>


### Management API
Allows you to manage users and other objects in the system. To access the management API you need to use the authentication API to get an access token and pass it along with your calls to the management API.  <a href="https://developer-api.forgerock.com/#6af844f9-ecea-422e-8508-b1017b4cb6bc" target="_blank">Explore the Management API</a>

Note: You need to ask for the proper scopes to be able to manage objects via the management API.

```
api.forgecloud.com:user.read 
api.forgecloud.com:user.write
api.forgecloud.com:app.read 
api.forgecloud.com:app.write 
api.forgecloud.com:password-policy.read 
api.forgecloud.com:password-policy.write
```

<br>


