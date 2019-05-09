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


[comment]: <> (Doc issue: https://trello.com/c/x06tXuL2 , also: You can then set up access to a ForgeRock cloud console. To set one up, follow [link to TBD procedure])

---

## Quick Start

In the web app you can now test self-registration, logins, and logouts. Passwords
are governed by complexity rules shown in your web app, at the following URL:
https://ui-{TENANT_NAME}.forgeblocks.com/authentication/password.

1. Navigate to your ForgeRock cloud console, at `https://ui-{TENANT_NAME}.forgeblocks.com`{: .plain}.
2. Select Applications > New Application.
3. In the New Application window, select Web.
4. Enter a unique name for your application.
5. In the **Login Redirect URL Whitelist** field, enter `http://localhost:9080/callback, http://localhost:9080/callback/non-hosted`{: .plain}.
6. In the **Logout Redirect URL Whitelist** field, enter `http://localhost:9080/`{: .plain}.
* If desired, you can modify token lifetime options and grant types, as discussed in
[Advanced Settings](#advanced.settings).
7. Select **Create Application**.
8. In the **Client Credentials** section, review and save the **Client ID** and the **Client Secret**.
9. Navigate to the directory where you saved the **ForgeRock Client Application SDK**
repository.
10. Run the following commands, using the **Tenant Name**, **Client ID**, and the
**Client Secret** created earlier:<br>
 $ ``` npm i ```{: .plain}  
 $ ``` sh start.sh {Tenant Name} {Client ID} {Client Secret} ```{: .plain}
11. Open a browser and havigate to [http://localhost:9080](http://localhost:9080).
Your browser redirects that URL to your cloud console URL at `https://ui-{tenantName}.forgeblocks.com`{: .plain}
12. You can now register and authenticate users locally in the web app that you just created.

<a name="advanced.settings"></a>
## Advanced Settings

With a web app, you can adjust settings related to token lifetimes
and grant types. For more information on tokens, see the
[Tokens]({{ site.baseurl }}/overview/token-types) page. The signing algorithm associated with the JWT Token is **HS256**, short for HMAC-SHA256.

To reduce security risks, limit the use of grant types for your applications. To learn more about the following **Grant Types**, review the following definitions, which includes links to ForgeRock Access Management documentation:

* Authorization Code: The [Authorization Code Grant]({{ site.am_release_version}}/oauth2-guide/#oauth2-authz) is a two-step interactive process used when the client, such as a Java application running on a server, requires access to protected resources.  

* Client Credentials: The [Client Credentials Grant]({{ site.am_release_version}}/oauth2-guide/#oauth2-client-cred)
is used when the client is also the resource owner, and is accessing its own data.  

* Password: The [Resource Owner Password Credentials Grant]({{site.am_release_version}}/oauth2-guide/#oauth2-ropc)
allows the client to use the resource owner's user name and password to get an access token.

* Refresh Token: As described in [Managing OAuth 2.0 Refresh Tokens]({{site.am_release_version}}/oauth2-guide/index.html#oauth2-refresh-tokens),
you can use a refresh token to get a new access token with the same or narrower OAuth 2.0 scopes.

## Technical Notes

This SDK uses the OAuth 2.0 confidential client type, where an
authorization code is exchanged for a token. To learn more about authentication
flows, see the following section on [Creating a Web App]({{ site.baseurl }}/quickstarts/web-app/).
