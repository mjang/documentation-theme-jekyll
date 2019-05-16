---
title: Applications
tags:
  - getting_started
keywords: "features, capabilities, scalability, multichannel output, dita, hats, comparison, benefits"
last_updated: "July 16, 2016"
summary: "If you're not sure whether Jekyll and this theme will support your requirements, this list provides a semi-comprehensive overview of available features."
published: true
sidebar: mydoc_sidebar
permalink: mydoc_applications.html
folder: mydoc
---

The ForgeRock Identity Cloud can help you integrate authentication and authorization into your application. The way you integrate depends on your app and how users interact with it.

The ForgeRock Identity Cloud uses both [OAuth 2.0](https://tools.ietf.org/html/rfc6749) and [OpenID Connect](http://openid.net/specs/openid-connect-core-1_0.html):

- OAuth 2.0 supports authorized access to protected resources.
- OpenID Connect provides an identity layer on top of OAuth 2.0.

Briefly, with OAuth 2.0, you can set up access to your resources without sharing your account information. With OpenID Connect, a client application can read basic information about a user via REST. For more information, see the ForgeRock [Access Management OpenID Connect 1.0 Guide]().

[comment]: <> (I'm not sure we even need to define OAuth 2.0 App types, but for 
completeness, I'm including the link)

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


