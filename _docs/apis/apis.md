---
title: APIs
category: REST APIs
category-order: 3
order: 1
---


There are two APIs for the ForgeRock Identity Cloud - the **Authentication API** and the **Management API**.

We've created Postman collections describing the APIs. If you've already installed Postman ([download here](https://www.getpostman.com/apps)), navigate to our page with [Postman APIs](https://documenter.getpostman.com/view/2758124/Rzn8Pgwy#intro). Select the 'Run Postman' button in the top right of the screen. This should open our collection in your instance of Postman.

_**Note:** You can also download our Postman collections from our [SaaS-Postman](https://github.com/ForgeCloud/SaaS-Postman) repository._

### Understanding the Environment

The REST calls associated with our APIs require information that you may not have readily available. Before running the REST calls in our Postman collections, prepare the following information:

* `client_id`{: .plain}: The Client ID of your App.
* `client_secret`{: .plain}: The Client Secret of your App.
* The base64-encoded value of `client_id:client_secret`{: .plain}, which you can find with the following command:
{% include base64_encode.html %}

You can then include that base64-encoded value in REST calls that require it. In the following excerpt, you'd substitute that value for the `BASE_64_ENCODED_STRING`{: .plain}:

`--header "Authorization: Basic BASE_64_ENCODED_STRING"`{: .plain}

As the Client ID and Client Secret varies by app, the base64-encoded value of `client_id:client_secret`{: .plain} will also vary.

You'll also need to keep track of the following properties:

* `access_token`{: .plain}: Every app and account that you work with gets different access tokens.
* `id`{: .plain}: Every user gets a unique ID.
* `id_token`{: .plain}: To end the session for a specific user, you'll need that user's ID Token.

You can then include the value of that *access_token* in REST calls that require it, as suggested by the following excerpt:

`--header "Authorization: Bearer *access_token*"`{: .plain}

_**Note:** When you see a requirement for an access_token, be careful. That property varies by app and account._

### Authentication API
Allows you to authenticate and authorize users and apps or assign to access the Management API.
<a href="https://documenter.getpostman.com/view/2758124/Rzn8Pgwy" target="_blank">Explore the Authentication API</a>


### Management API
Allows you to manage users and other objects in the system. To access the management API, use the authentication API to get an access token. You can then include that access token for your calls to the management API.  <a href="https://documenter.getpostman.com/view/2758124/Rzn8Pgwy#54d694b2-9982-4d8a-b2c7-0a99315b1eb7" target="_blank">Explore the Management API</a>.

You can also filter users with the management API. Check out the user endpoint [filtering parameters]({{ site.baseurl }}/apis/apis-filtering/).

_**Note:** When using the Authentication API, use appropriate scopes. The access token you get will have the right permissions for the management API._

```
api.forgecloud.com:user.read
api.forgecloud.com:user.write
api.forgecloud.com:app.read
api.forgecloud.com:app.write
api.forgecloud.com:password-policy.read
api.forgecloud.com:password-policy.write
```

<br>
