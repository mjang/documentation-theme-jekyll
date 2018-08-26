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

#### Resource Owner	
The entity that can grant access to a protected resource.

#### Application / Client
A client application requesting access to a protected resource on the resource server on behalf of the Resource Owner.

#### Resource Server	
The server hosting the protected resources that you want to protect using OAuth2 protocol. It responds to requests from clients with access tokens.

#### Authorization Server	
The server that authenticates the Resource Owner, and issues access tokens to apps after getting proper authorization. (ForgeRock)

#### Id Token
This is a token in the form of a JWT that contains information about a user. The ID Token is represented as a JSON Web Token (JWT). 

#### Access Token
This is a token that can be used to access resources.

#### Refresh Token
A Refresh Token is a special kind of token that can be used to obtain a new access token. This type of token is only available when you set up a web app.

#### User Agent	
The agent used by the Resource Owner to interact with the Client, for example a browser or a native application.

#### User Profile	
User information and meta data related to a user.

