---
title: Applications
category: Overview
order: 2
am_release_version: https://backstage.forgerock.com/docs/am/6.5
---

The ForgeRock Identity Cloud can help you integrate authentication and authorization into your application. The way you integrate depends on your app and how users interact with it.

The ForgeRock Identity Cloud uses both [OAuth 2.0](https://tools.ietf.org/html/rfc6749)
and [OpenID Connect](http://openid.net/specs/openid-connect-core-1_0.html):

* OAuth 2.0 supports authorized access to protected resources.
* OpenID Connect provides an identity layer on top of OAuth 2.0.

Briefly, with OAuth 2.0, you can set up access to your resources without sharing your account information. With OpenID Connect, a client application can read basic information about a user via REST. For more information, see the
ForgeRock [Access Management OpenID Connect 1.0 Guide]({{ page.am_release_version}}/oauth2-guide/#openid-connect-authorization-code-flow).

[comment]: <> (I'm not sure we even need to define OAuth 2.0 App types, but for completeness, I'm including the link)

OAuth 2.0 works with two different client types, as defined in
[RFC6749](https://tools.ietf.org/html/rfc6749#section-2.1).


<a name="top"></a>
### Oauth 2.0 App Types

[Web App](#web) || [Machine 2 Machine App](#machine2machine)
{: .mini-nav}

[comment]: <> (I'm tempted to break this out into a separate page, maybe under reference)

Each of these apps require different authorization flows, based on their grant types. When you register your app in the ForgeRock admin console we will set the appropriate grant types for you.

_**Note:** We're working on more app types. Watch the **Work In Progress** and **Completed** sections of our [Roadmap]({{ site.baseurl }}/roadmap/roadmap/) for more information._

**Grant Types**

As defined in RFC6749, OAuth 2.0 explicitly defines four grant types:

- [Authorization Code](https://tools.ietf.org/html/rfc6749#section-1.3.1):
Uses an authorization server as an intermediary between the client and resource owner.
- [Implicit](https://tools.ietf.org/html/rfc6749#section-1.3.2).
- [Resource Owner Password Credentials](https://tools.ietf.org/html/rfc6749#section-1.3.3).
- [Client Credentials](https://tools.ietf.org/html/rfc6749#section-1.3.4).

The OAuth 2.0 specification includes an extensibility mechanism for defining more grant types. The ForgeRock Cloud includes the following additional grant type:

- [Refresh Token](https://tools.ietf.org/html/rfc6749#section-1.5).

<a name="web"></a>
### Web App

 A web app runs on a server, for access by resource owners (users). The web app
 makes server-side API calls. Users do not have access to the OAuth 2 client
 secret or access tokens issued by the authorization server.

An example of a web app is an eCommerce site where people authenticate before
they can start shopping.

Authorization flows in a web app include three grant types:

- Authorization Code
- Resource Owner Password Credentials
- Refresh Token

In brief, when the user authorizes access to their data, the authorization server
returns an *authorization code grant*. The client application exchanges this grant
for an access token.

Refresh tokens allow your web app to get a new access token without asking that user to log in again.

For a detailed flow, see the Access Management OpenID Connect 1.0 Guide section
on [OpenID Connect Authorization Code Flow]({{ page.am_release_version}}/#openid-connect-authorization-code-flow).

<p class="center"><br><a href="{{ site.baseurl }}/sdks/nodejs/" class="btn btn-secondary"><i class="material-icons">build</i>How To Create a Web App</a></p>


<a name="machine2machine"></a>
### Service (Machine to Machine) App
A service app interacts with an API without user involvement. The service app
can request access tokens directly from the authorization server.

An example of a service app is a server script that can access images through a REST call.

Authorization flows in a service app include the following grant type:

*   Client Credentials

[comment]: <> (Moved discussion of Client Side and Native Apps to \_drafts directory)

---

#### Learn more about OAuth 2.0 and OpenID Connect Flows

For more information on how the ForgeRock Identity Cloud processes OAuth 2.0
and OpenID Connect flows, see the following Access Management documents:

- [OAuth 2.0 Guide]({{ page.am_release_version}}/oauth2-guide/index.html)
- [OpenID Connect 1.0 Guide]({{ page.am_release_version}}/oidc1-guide/index.html)

<br>
[Top](#top){: .float-right}
<br>
