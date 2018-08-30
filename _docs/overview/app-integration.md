---
title: Applications 
category: Getting Started
order: 2
---

How you integrate authentication and authorization into your application depends on the kind of app you have and how users interact with it. 

ForgeRock uses OAuth 2.0 to authorize access to protected resources and OpenID Connect to provide an identity layer on top of the OAuth 2.0 protocol. The [OAuth 2.0 specification](https://tools.ietf.org/html/rfc6749) is an authorization framework describing how a client application can acquire an access token which can be used to authenticate a request to an API endpoint.  It does not describe methods for authentication. To get access to a protected resources OAuth 2.0 uses access tokens ([JWT's](http://jwt.io)).


<a name="top"></a>
### OAuth 2.0 App Types

[Web App](#web) || [Machine 2 Machine App](#machine2machine) || [Client Side App](#clientside) || [Native App](#native)
{: .mini-nav}

#### In a Nutshell....

To access protected resources a client app registers itself with the resource server and gets a client id and secret.
The app then accesses protected resources by:
1. Authorizing the resource owner (usually a person).
1. Obtaining an access token from the authorization server.
1. Finally accessing the protected resource using the token passed back by the authorization server.

In the ForgeRock admin you need to register your application and get a client id and secret in order to obtain an access token.  In general there are two types of applications.


| 1. Confidential  | 2. Public  |
| ------------- | ------------- | 
| Able to hold credentials (such as a client ID and secret) in a secure way without exposing them to unauthorized parties. This means that the developer will need a trusted backend server to store the secret(s). E.g. A server side web app where code runs on the server. | Cannot hold credentials securely. E.g. a client side single page app where all the code runs in the browser. | 

Each type of application requires different authorization flows that are implemented by setting grant types on the application. When you register your app in the ForgeRock admin console we will automatically set the appropriate grant types for the type of application you have selected.

**Grant Types**

- Client Credentials Grant
- Authorization Code Grant
- Implicit Grant *(not yet supported)*{: .gray}
- Resource Owner Password Credentials Grant *(not yet supported)*{: .gray}
- Refresh Token Grant

<a name="web"></a>
### Web App

This is probably the most common type of application. A web application runs on a server and is accessed by a resource owner (user). The application makes API calls on the server-side. The user has no access to the OAuth client secret or any access tokens issued by the authorization server. WebApp will need to send the End User to FR to kick off this flow.

An example of this type of app might be an eCommerce site built in node.js where people login to shop for goods. 

**Authorization Flows: Authorization Code, Refresh**


1. Resource owner authorizes access to their data
2. Resource owner is redirected back to the web application with an authorization code as a query parameter in the URL. 
3. This code is exchanged for an access token by the client application.

With this type of app you can use the **Refresh** token grant to obtain a new access token without involving the user. To do this the app would make an additional call to obtain a new token when the authorization server responds with an invalid token error.

<p class="center"><br><a href="{{ site.baseurl }}/sdks/nodejs/" class="btn btn-secondary"><i class="material-icons">build</i> GET STARTED</a></p>


> **Auth Code Flow**
> ![]({{ site.baseurl }}/images/auth_code_flow.png)
{: .plain-blockquote}

[Top](#top){: .float-right}


<a name="machine2machine"></a>
### Machine 2 Machine App
A Machine 2 Machine app represents a program that interacts with an API where there is no user involved. The app is acting on behalf of *ITSELF* and not a user. The app can ask for an access token directly without involving a user in the process at all.

An example might be a server script that is granted access to an API providing images.

**Authorization Flows: Client Credentials** 

1. The application makes an authorization request to the authorization server by providing the client credentials
2. The authorization server responds with an access token & access token expiration time

> **Client Credentials Flow**
> ![]({{ site.baseurl }}/images/client_creds_flow.png)
{: .plain-blockquote}

[Top](#top){: .float-right}


<a name="clientside"></a>
### Client Side App
The code of this app type runs completely in the browser. If you can avoid using this type of application for authorizing access to resources then you should as there is no way to secure the token. 

**Authorization Flows: Implicit Grant** 

1. The resource owner grants access to the application
2. A new access token is minted and passed back to the application using a #hash fragment in the URL. 
3. The application can immediately extract the access token from the hash fragment (using JavaScript) and make API requests. 

Note: You cannot use refresh tokens for long-lived access with this app type.


*(Not yet supported)*{: .gray}


[Top](#top){: .float-right}



<a name="native"></a>
### Native App
This app very similar to the client-side application as the credentials are not trusted to be kept confidential. With this flow it is recommended to use the PKCE extension. This involves the app generating an arbitrary code and using that when exchanging the the authorization code for a secret. By doing this if the auth code is intercepted then it cannot be used without the arbitrary code.

**Grant Type: Authorization Code with PKCE** 

*(Not yet supported)*{: .gray}


---

#### Learn more about OAuth 2.0 Flows

- [https://aaronparecki.com/oauth-2-simplified/](https://aaronparecki.com/oauth-2-simplified/)
- [https://alexbilbie.com/guide-to-oauth-2-grants/](https://alexbilbie.com/guide-to-oauth-2-grants/)
- [https://medium.com/scalable/an-oauth2-grant-selection-decision-tree-for-securing-rest-apis-d63b5c0c8900](https://medium.com/scalable/an-oauth2-grant-selection-decision-tree-for-securing-rest-apis-d63b5c0c8900)

<br>
[Top](#top){: .float-right}
<br>