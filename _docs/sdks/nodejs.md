---
title: Web App (Node.js SDK)
category: SDKs
category-order: 4
order: 1
---


This page shows you how to register and authenticate users in a web app, using 
the Node.js SDK. 

---

## Before you begin
Before running a web app locally, install the following software:

* [NodeJS](https://nodejs.org/en/download/)
* [npm](https://www.npmjs.com/get-npm)
* [git](https://help.github.com/articles/set-up-git/)

Next, clone the [**ForgeRock Client Application SDK**](https://github.com/ForgeCloud/app-sdk).

You can then set up access to a ForgeRock cloud console. To set one up, follow [link to TBD procedure]

[comment]: <> (Doc issue: https://trello.com/c/x06tXuL2)

---

## Quick Start

In the app you can now test self-registration, logins and logouts.  Passwords
are governed by complexity rules shown in your Web App, at the following URL:
https://ui-{TENANT_NAME}.forgeblocks.com/authentication/password.

1. Navigate to your ForgeRock cloud console, at `https://ui-{TENANT_NAME}.forgeblocks.com`{: .plain}.
2. Select Applications > New Application.
3. In the New Application window, select Web.
4. Enter a unique name for your application.
5. In the **Login Redirect URL Whitelist** field, enter `http://localhost:9080/callback, http://localhost:9080/callback/non-hosted`{: .plain}.
6. In the **Logout Redirect URL Whitelist** field, enter `http://localhost:9080/`{: .plain}.
* If desired, you can modify token lifetime options and grant types, as discussed in 
[Web App, Advanced Settings]({{ site.baseurl }}/sdks/nodejs-options).
7. Select **Create Application**. 
8. In the **Client Credentials** section, review and save the **Client ID** and the **Client Secret**.
9. Navigate to the directory where you saved the **ForgeRock Client Application SDK** 
repository.
10. Run the following commands, using the **Tenant Name**, **Client ID**, and the 
**Client Secret** created earlier:<br>
 $ ``` sudo npm i ```{: .plain}  
 $ ``` sudo sh start.sh {Tenant Name} {Client ID} {Client Secret} ```{: .plain} 
11. Open a browser and havigate to [http://localhost:9080](http://localhost:9080).
Your browser redirects that URL to your cloud console URL at `https://ui-{tenantName}.forgeblocks.com`{: .plain}
12. You can now register and authenticate users locally in the web app that you just created.


## Technical Notes

This SDK uses the OAuth 2.0 confidential client type, where an 
authorization code is exchanged for a token. To learn more about authentication 
flows, see the following section on [Creating a Web App]({{ site.baseurl }}/quickstarts/web-app/).
