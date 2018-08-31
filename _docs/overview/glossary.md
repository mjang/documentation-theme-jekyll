---
title: Glossary 
category: Getting Started
order: 4
---



#### Team Member	
A user of the ForgeRock administration console.

#### Admin Console	
Tool used by Team Members to manage their ecosystem e.g. setup users, tenants, apps etc.

#### Tenant	
This is a single, isolated instance of a the admin features. It contains apps, users, devices and rules.

#### App User	
A user of the apps created by the Team Member in the ForgeRock console.

#### User Profile	
User information and meta data related to a user.

#### Resource Owner	
The entity that can grant access to a protected resource.

#### Application / Client
A client application requesting access to a protected resource on the resource server on behalf of the Resource Owner.

#### Resource Server	
The server hosting the protected resources that you want to protect using OAuth2 protocol. It responds to requests from clients with access tokens.

#### Authorization Server	
The server that authenticates the Resource Owner, and issues access tokens to apps after getting proper authorization. (ForgeRock)

#### User Agent	
The agent used by the Resource Owner to interact with the Client, for example a browser or a native application.

#### ID Token
This is a token in the form of a JWT that contains information (Claims) about a user and the authentication context. It can be parsed by the client to get information about a user. 

#### Access Token
This is a token minted by the Authorization Server that can be used to access resources and is opaque to the client.

#### Refresh Token
A Refresh Token is a special kind of token issued by the Authorization Server that can be used to obtain a new access token without involving the user. This type of token is only available when you set up a web app.

#### JWT Token (JSON Web Token)
This is a special kind of token that contains whatever the Authorization Server wants to put in it so it can communicate information to the Resource Server. The Resource Server can parse the token and make authorization decisions based on the information packed into the token.  

#### OAuth 2.0
[OAuth 2.0](https://tools.ietf.org/html/rfc6749) is a *delegation* protocol for conveying *authorization* decisions across a network of web-enabled applications and APIs.

#### OAuth Scopes
This is a representation of a set of rights to a protected resource. Scopes are represented by strings in the OAuth protocol. Clients can request scopes to access to a protected resource and the authorization server can allow or deny these.

#### OpenID Connect
[OpenID Connect](http://openid.net/specs/openid-connect-core-1_0.html) is a simple identity layer on top of the OAuth 2.0 protocol. It enables Clients to verify the identity of the End-User based on the authentication performed by an Authorization Server, as well as to obtain basic profile information about the End-User in an interoperable and REST-like manner. It uses Claims to communicate information about the End-User. 




