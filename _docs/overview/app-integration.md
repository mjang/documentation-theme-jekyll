---
title: Getting Started 
category: Overview
order: 2
---

## Adding Authentication to your App

You have several choices when integrating your app into the platform. The method of integration depends on the kind of app you have and how users interact with it.

ForgeRock uses OAuth 2.0 to authorize access to protected resources and OpenID Connect to provide an identity layer on top of the OAuth 2.0 protocol.

OAuth 2.0 Authorization Framework describes a protocol for managing authorization to protected resources for your service.  It does not describe methods for authentication. To get access to a protected resources OAuth 2.0 uses access tokens (JWT)

> Quick Tip<br><br>
> **OAuth 2.0:** Is used for resource access<br>
> **OpenID Connect:** Is used for authenticating users


### Application Types

Which kind of app you have determines what grant flow you should incorporate into your app to provide access to resources. Determining what method to use is based on:

1. If there are people are logging into your app
2. How secure your app is and if it can securely store a token

#### Web Apps

Able to securely store and transmit information on the server side and users are logging into the apps. An example might be an eCommerce site build in node.js where people login to shop. 

**grant_type: authorization_code**

This grant type is most appropriate for server-side web applications. After the resource owner has authorized access to their data, they are redirected back to the web application with an authorization code as a query parameter in the URL. This code must be exchanged for an access token by the client application. This exchange is done server-to-server and requires both the client_id and client_secret, preventing even the resource owner from obtaining the access token. This grant type also allows for long-lived access to an API by using refresh tokens.


#### Native / Mobile Apps


#### Single Page Apps (SPA's)
The code of the application runs completely in the browser. In this case there is no way to secure  security at all.  Token is stored in browser.


#### Machine 2 Machine (Service Apps)
A Machine 2 Machine app represents a program that interacts with an API where there is no user involved. An example might be a server script that would be granted access to consume a ip location API.
