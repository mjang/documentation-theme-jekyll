---
title: APIs
category: REST APIs
category-order: 3
order: 1
---


There are two main APIs for the ForgeRock Identity Cloud - the **Authentication API** and the **Management API**. 

We've created Postman collections describing the APIs. To run the calls in Postman [download](https://www.getpostman.com/apps) and open postman, go to the links below and click the 'Run Postman' button in the top right of the screen to open the collection in postman. 

### Authentication API
Allows you to authenticate and authorize users and apps or assign to access the Management API. 
<a href="https://documenter.getpostman.com/view/2758124/Rzn8Pgwy" target="_blank">Explore the Authentication API</a>


### Management API
Allows you to manage users and other objects in the system. To access the management API you need to use the authentication API to get an access token and pass it along with your calls to the management API.  <a href="https://documenter.getpostman.com/view/2758124/Rzn8Pgwy#54d694b2-9982-4d8a-b2c7-0a99315b1eb7" target="_blank">Explore the Management API</a>. 

There are also ways to filter users via the management API. Check out the user endpoint [filtering parameters]({{ site.baseurl }}/apis/apis-filtering/).

_**Note:** You need to ask for the proper scopes when you call the Authentication API to get a token so you have the right permissions on the objects in the management API._

```
api.forgecloud.com:user.read 
api.forgecloud.com:user.write
api.forgecloud.com:app.read 
api.forgecloud.com:app.write 
api.forgecloud.com:password-policy.read 
api.forgecloud.com:password-policy.write
```

<br>


