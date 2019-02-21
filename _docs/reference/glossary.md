---
title: Glossary
category: Reference
category-order: 5
order: 1
---

For a description of token types, see the [Tokens]({{ site.baseurl }}/overview/token-types) page.


#### Admin Console
Tool used by Team Members to manage their ecosystem(s). For example, Team Mambers
 can use the Admin Console to set up users, tenants, apps, and more.

#### App User
A regular user, created by a the Team Member, possibly through the ForgeRock
 console.

#### Application / Client
A client application that requests access to a protected resource on the resource server on behalf of the Resource Owner.

#### Authorization Server
The server that authenticates the Resource Owner, and issues access tokens to apps.

#### OAuth 2.0
[OAuth 2.0](https://tools.ietf.org/html/rfc6749) is a *delegation* protocol for conveying *authorization* decisions across a network of web-enabled applications and APIs.

#### OpenID Connect (OIDC)
[OpenID Connect](http://openid.net/specs/openid-connect-core-1_0.html) is an authentication layer on top of the OAuth 2.0 protocol.
Clients can use OIDC to verify the identity of an end-user based on the actions of an authorization server. It can also obtain basic
profile information about end-users in an interoperable and REST-like manner.

#### Resource Owner
An entity that can grant access to a protected resource.

#### Resource Server
A host for protected resources using OAuth 2.0. A Resource Server responds to requests
 from clients with access tokens.

#### SAML
SAML (Security Assertion Markup Language) is not supported by the ForgeRock Identity Cloud.

#### Scope
A scope is a set of (OAuth 2.0) rights to a protected resource, associated with an access token. Clients can request scopes for access to a protected resource. The Authorization Server can allow or deny such requests. For more information on the scopes that you can configure for the ForgeRock Identity Cloud, see the following page: [Scopes]({{ site.baseurl }}/reference/scopes).

#### Team Member
A ForgeRock administration console user.

#### Tenant
A single, isolated instance of the Admin Console. A Tenant contains apps,
 users, devices and rules.

#### User Profile
User information and metadata.

#### User Agent
The agent used by the Resource Owner to interact with the Client, such as a browser or a native application.
