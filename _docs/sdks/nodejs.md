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
1. Enter `http://localhost:9080/callback`{: .plain} in the 'login redirect whitelist' field.
1. Enter `http://localhost:9080/`{: .plain} in the 'logout redirect whitelist' field.
1. Hit 'save'
1. Copy and save the client id, secret.
1. On your local machine make sure you have node installed.
1. Clone the SDK from <a href="https://github.com/ForgeCloud/app-sdk" target="_blank">github</a>.
1. From the command line navigate to the app-sdk folder and run the following.

    ```
    npm i
    sh start.sh {tenant name} {client id} {secret}
    ```
    {: .language-javascript}

1. Hit [http://localhost:9080](http://localhost:9080) in your browser.

In the app you can now test registering, logging in and logging out. 

<br><br>
