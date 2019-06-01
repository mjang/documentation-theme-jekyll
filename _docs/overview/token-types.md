---
title: Tokens
category: Overview
order: 3
---

The ForgeRock authentication server supports *client*-based access, refresh, and ID tokens, based on the OpenID Connect 1.0 (OIDC) and OAuth 2.0 protocols.

[Open ID Connect 1.0](https://openid.net/connect/) is an authentication layer built on [OAuth 2.0](https://tools.ietf.org/html/rfc6749), where the identity provider that runs the resource server also holds the protected resource.

To use SaaS APIs, it's helpful to understand the following tokens:

- **ID token (id_token)**: contains information about a user.
- **Access token (access_token)**: used to access a protected resource.
- **Refresh token (refresh_token)**: used to obtain a new access token after expiration.


### ID Token
An **ID token** contains information (claims) about the user and the authentication context in the form of a JSON Web Token (JWT). OIDC defines a set of standard claims about users, such as *name* and *email* encoded in the token. The OIDC specification includes a list of [Standard Claims](https://openid.net/specs/openid-connect-core-1_0.html#StandardClaims).

An ID token can be parsed for user information.


#### JWT Token (JSON Web Token)
Contains information from the Authorization Server to communicate with the Relying Party, which can make authorization decisions based on information parsed from the token.  


### Access Token
An **access token** is a credential created by the Authorization Server to access protected resources. The credential depends on the [scopes]({{ site.baseurl }}/reference/scopes) that you include. An access token is opaque to the client. For more information, see the Access Management guide on [Managing OAuth 2.0 Refresh Tokens](https://backstage.forgerock.com/docs/am/6.5/oauth2-guide/#oauth2-refresh-tokens).


### Refresh Token
A **refresh token** is a credential used to obtain a new access token. A refresh token is issued to a client by an authorization server, at the same time as an access token, only for web apps. It's used when an access token expires, to acquire a new access token.

To get a new access token, run a POST on the /access_token endpoint with a refresh token. You'll also need your client_id, client_secret, grant_type of “refresh_token”, and the refresh_token itself. A new access token and a new refresh token will be returned.


### Example REST Call

To see how this works, refer to the POST for a Password Grant
on the ```/oauth2/access_token``` endpoint in the
[Authentication API](https://developer-api.forgerock.com/#316c2802-6751-44c8-b8a0-7dca67e33aa5).


### Additional Reading

For more information, see the
[ForgeRock Access Management OpenID Connect 1.0 Guide](https://backstage.forgerock.com/docs/am/6.5/oidc1-guide/#chap-oidc1-introduction).

The tokens described on this page are defined by the following specifications:
- [Open ID Connect 1.0](https://openid.net/connect/)
- [OAuth2](https://tools.ietf.org/html/rfc6749)

For a conversational perspective of OAuth 2.0 and OIDC, see the following blog
posts:
- [The OpenID Connect Neighborhood](https://forum.forgerock.com/2018/09/openid-connect-neighborhood/)
- [The OAuth2 Apartment Building](https://forum.forgerock.com/2018/09/oauth2-apartment-building/)
