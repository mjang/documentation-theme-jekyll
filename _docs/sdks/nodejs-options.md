---
title: Web App, Advanced Settings
category: SDKs
category-order: 4
order: 2
am_release_version: https://backstage.forgerock.com/docs/am/6.5
---

With a web app, you can adjust settings related to token lifetimes
and grant types. For more information on tokens, see the
[Tokens]({{ site.baseurl }}/overview/token-types) page. The signing algorithm
associated with the JWT Token is **HS256**, short for HMAC-SHA256.

To reduce security risks, limit the use of grant types for your applications.
To learn more about the following **Grant Types**, review the following
definitions, which includes links to ForgeRock Access Management documentation:

* Authorization Code: The [Authorization Code Grant]({{ page.am_release_version}}/oauth2-guide/#oauth2-authz)
is a two-step interactive process used when the client, such as a Java
application running on a server, requires access to protected resources.  

* Client Credentials: The [Client Credentials Grant]({{ page.am_release_version}}/oauth2-guide/#oauth2-client-cred)
is used when the client is also the resource owner, and is accessing its own data.  

* Password: The [Resource Owner Password Credentials Grant]({{page.am_release_version}}/oauth2-guide/#oauth2-ropc)
allows the client to use the resource owner's user name and password to get an
access token.

* Refresh Token: As described in [Managing OAuth 2.0 Refresh Tokens]({{page.am_release_version}}/oauth2-guide/index.html#oauth2-refresh-tokens),
you can use a refresh token to get a new access token with the same or narrower
OAuth 2.0 scopes.
