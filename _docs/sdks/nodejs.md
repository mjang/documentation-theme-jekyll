---
title: Node.js SDK
category: SDK's
category-order: 3
order: 1
---


> **Sample App** <br>
> To get started pull the sample app from Github and follow the instructions in the github repo. <br><br>
> <a href="https://github.com/ForgeCloud/app-sdk" class="btn btn-secondary">{% octicon mark-github" %}Clone from Github</a>
{: .plain-blockquote}

<br/>

#### Running the Sample App  
The node sample app will use the OAuth 2.0 confidential client flow (web app). An Authorization Code is exchanged for a token. Your app must be able to securely store and transmit information. Check out the section on [client types](#) to lean more about which authorization flow to use.

#### Steps

1. Make sure you have node installed
1. Clone the repo from github
1. From the command line navigate to the *app-sdk* folder and run *npm i* to install dependencies
1. In the ForgeRock cloud console create a web app and copy the client id, secret and uri
1. In the *start.sh* file in the root folder set the following variables with the information you copied from the app.

```
export HOST=localhost
export OAUTH_ISSUER=http://openam.fr-saas-{tenantName}.forgeblocks.com/openam/oauth2
export OAUTH_KEY={CLIENT ID}
export OAUTH_SCOPES="openid profile"
export OAUTH_SECRET={SECRET}
```
{: .language-javascript}

To start the app run the following command

```
sh start.sh
```

<br><br><br><br>
