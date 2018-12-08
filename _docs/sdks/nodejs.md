---
title: Node.js SDK
category: SDKs
category-order: 4
order: 1
---


This SDK will show you how to register and authenticate users into an app. The SDK uses the OAuth 2.0 confidential client type, where an authorization code is exchanged for a token. Check out the section on [app types]({{ site.baseurl }}/overview/app-integration/) to lean more about authorization flows.

---

## Before you begin
You can skip this section if you have node and git already installed.


#### 1. Install Node & Node Package Manager (npm)
We’ll need to make sure we have a working Node.js development environment along with npm. Npm is installed when you install node. Check you have npm by running the following command in you terminal.

`$ npm -v`{: .plain}

If you get an error then you need to install node. Please refer to the Node.js website for detailed information: <a href="https://nodejs.org/download/" target="_blank">https://nodejs.org/download/</a>

#### 2. Install Git
If you don’t have Git installed, see these instructions for installing Git <a href="https://help.github.com/articles/set-up-git/" target="_blank">https://help.github.com/articles/set-up-git/</a>

---

## Quick Start

> **Node SDK** <br>
> To get started clone the SDK from Github and follow the instructions.<br><br>
> <a href="https://github.com/ForgeCloud/app-sdk" target="_blank" class="btn btn-secondary">{% octicon mark-github" %}Clone from Github</a>
{: .plain-blockquote}

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

In the app you can now test registering, logging in and logging out.  Passwords
are governed by complexity rules shown in your Web App, at the following URL:
https://ui-{TENANT_NAME}.forgeblocks.com/authentication/password.

<br><br>
