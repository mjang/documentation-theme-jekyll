---
title: Node.js SDK
category: SDK's
category-order: 3
order: 1
---


This SDK will show you how to register and authenticate users into an app. The SDK uses the OAuth 2.0 confidential client flow, where an authorization code is exchanged for a token. Check out the section on [app types]({{ site.baseurl }}/overview/app-integration/) to lean more about authorization flows.

> **Node SDK** <br>
> To get started clone the SDK from Github and follow the instructions.<br><br>
> <a href="https://github.com/ForgeCloud/app-sdk" target="_blank" class="btn btn-secondary">{% octicon mark-github" %}Clone from Github</a>
{: .plain-blockquote}

<br>

#### Steps

1. In the ForgeRock cloud console create a web app
1. Enter 'http://localhost:8100/callback' in the uri whitelist field and hit save.
1. Copy and save the client id, secret and uri.
1. On your local machine make sure you have node installed.
1. Clone the SDK from <a href="https://github.com/ForgeCloud/app-sdk" target="_blank">github</a>.
1. From the command line navigate to the app-sdk folder and run `npm i`{: .plain} to install dependencies.
1. In the start.sh file in the root folder enter client id, secret and uri with the information you copied from the app.

    ```
    export HOST=localhost
    export OAUTH_ISSUER=http://openam.fr-saas-{tenantName}.forgeblocks.com/openam/oauth2
    export OAUTH_KEY={CLIENT_ID}
    export OAUTH_SCOPES="openid profile"
    export OAUTH_SECRET={SECRET}
    ```
    {: .language-javascript}

1. Start the app by running `sh start.sh`{: .plain} and hit [http://localhost:8100](http://localhost:8100) in your browser.

In the app you can now test registering, logging in and logging out. To see what the code is doing and how the endpoints are being called look at index.js.

<br><br>
