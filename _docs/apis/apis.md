---
title: APIs
category: REST APIs
category-order: 3
order: 1
---


There are two APIs for the ForgeRock Identity Cloud - the **Authentication API** and the **Management API**.

We've created Postman collections describing the APIs. If you've already installed Postman ([download here](https://www.getpostman.com/apps)), navigate to our page with [Postman APIs](https://developer-api.forgerock.com). Select the 'Run Postman' button in the top right of the screen. This should open our collection in your instance of Postman.

_**Note:** You can also download our Postman collection and environment from our [SaaS-Postman](https://github.com/ForgeCloud/SaaS-Postman) repository._

_**Warning:** Some of the calls in our Postman collection won't work until you create a web app. You can build your own web app. If you need guidance, start with our sample [Node.js SDK]({{ site.baseurl }}/sdks/nodejs/) app. You can use our sample app as a template, to see how to incorporate this functionality into your app._


### Understanding the Environment

The REST calls associated with our APIs require information that you may not have readily available. Before running the REST calls in our Postman collections, prepare the following information:

* `client_id`{: .plain}: The Client ID of your App.
* `client_secret`{: .plain}: The Client Secret of your App.
* The base64-encoded value of `client_id:client_secret`{: .plain}, which you can find with the following command:
{% include base64_encode.html %}

As the Client ID and Client Secret varies by app, the base64-encoded value of `client_id:client_secret`{: .plain} will also vary. The REST calls that require base64-encoded information include the Client ID and Client Secret under Authorization, as shown here:

> ![]({{ site.baseurl }}/images/base64_basic_auth.png)
{: .plain-blockquote}

Postman then calculates the base64-encoded value of `client_id:client_secret`{: .plain}, and includes it in the target REST call.

You'll also need to keep track of the following properties:

* `access_token`{: .plain}: Every app and account that you work with gets different access tokens.
* `id`{: .plain}: Every user gets a unique ID.
* `id_token`{: .plain}: To end the session for a specific user, you'll need that user's ID Token.

You can then include the value of that *access_token* in REST calls that require it, as suggested by the following excerpt:

`--header "Authorization: Bearer *access_token*"`{: .plain}

_**Note:** When you see a requirement for an access_token, be careful. That property varies by app and account._


### Authentication APIs
Supports authentication of users to access apps. To review available REST calls, see our Postman documentation on
<a href="https://developer-api.forgerock.com/#8eec1175-0ced-4b72-8b1a-ced836167c87" target="_blank">Authentication APIs</a>


### Management API
Allows you to manage users and other objects in the system. To access the management API, use the authentication API to get an access token. You can then include that access token for your calls to the management API.  <a href="https://developer-api.forgerock.com/#316c2802-6751-44c8-b8a0-7dca67e33aa5" target="_blank">Explore the Management API</a>.

You can also filter users with the management API. Check out the user endpoint [filtering parameters]({{ site.baseurl }}/apis/apis-filtering/).

_**Note:** When using the Authentication API, use appropriate [scopes]({{ site.baseurl }}/reference/scopes/). The access token you get will have the right permissions for the management API._

<br>
