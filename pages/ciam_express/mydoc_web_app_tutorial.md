---
title: Create a Secure Web App
tags: [quick_starts, getting_started, security, PKCE]
keywords: second-factor auth, two-factor authentication
summary: "Some web app summary."
sidebar: mydoc_sidebar
permalink: mydoc_web_app_tutorial.html
folder: mydoc
---

In this tutorial, you'll learn how to set up a web app with two-factor authentication. Users request access with usernames, and then verify their identities through a smart phone.


> Prerequesites: 
- Node >= v11.6.0
- NodeJS >= v8.10.0
- Git

Log into the CIAM Express UI, and select *Create an Application*:


{% include image.html file="newApp.png" alt="Options for New Apps" caption="From here, create a web app." %}


## Create a Web App

If you already have a web app, use (something) to find its *client ID*, and skip to [Adding Auth](#web.app.auth).

Select Web. As suggested by the UI, we support Node.js and Java apps. In the screen that appears:

{% include image.html file="createWebApp.png" alt="You can also create a Web App with some link to some REST call at developer-api.forgerock.com" caption="Create a New Web App from the UI." %}

Enter the options most suited to your environment. Our defaults for the following options support redirects to hosted and non-hosted websites.

- Login Redirect URL Whitelist
- Logout Redirect URL Whitelist

> Our default *Advanced Settings* are secure. 

Select *Create Application*.

If you want to run the REST calls in our API documentation, save the client credentials for your new web app:

{% include image.html file="clientCredentials.png" alt="Save the Client ID and Client Secret" caption="Don't share your app's Client Secret" %}

<a name="web.app.auth"></a>
## Adding Auth

With CIAM Express, you can incorporate a "second factor" to improve security. When you insert the following code in your app: 

```js
<!-- Load ForgeRock SDK for JavaScript -->
    <div id="auth-sdk-target"></div>
    <script>(function(d, s, id) {
        var js,
          el = d.getElementsByTagName(s)[0];
        if (d.getElementById(id)) return;
        js = d.createElement(s);
        js.id = id;
        js.src = 'auth-sdk.js#version=v1.0';
        el.parentNode.insertBefore(js, el);
      })(document, 'script', 'auth-sdk');
    </script>
    <script id="auth-sdk-config" type="text/plain">
      {
        "clientId": "CLIENT_ID",
        "flow": "SecondFactorWebAuthn",
        "org": "ORG_NAME",
        "scope": "SCOPE"
      }
    </script>
````

<a href="#" data-toggle="tooltip" data-original-title="{{site.data.glossary.client_id}}">The Client ID</a> identifies your app.

<a href="#" data-toggle="tooltip" data-original-title="{{site.data.glossary.org_name}}">For ORG_NAME</a> substitute the name of your tenant.



Your users can choose to use the following options to verify their identities:

- A device such as a fingerprint reader
- SMS codes from a mobile phone
- Codes sent to an email address

## Adding for test purposes

{% plantuml %}
title Service (M2M) Apps and Client Credentials

autonumber

participant "Client" as Client
participant "CIAM Express" as AuthzServer
participant "Resource Server" as ResourceServer

Client->AuthzServer: Verify identity, request access token

AuthzServer->Client: Verify credentials, return access token

Client->ResourceServer: Request resource with access token

ResourceServer->AuthzServer: Verify valid access token

AuthzServer->ResourceServer: Response

ResourceServer->Client: Return requested resource
{% endplantuml %}

