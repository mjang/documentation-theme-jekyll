---
title: Applications, part 2
category: Overview
am_release_version: https://backstage.forgerock.com/docs/am/6.5n
excluded_in_navigation: true
---

Holding page for app types that aren't yet supported (Client Side, Native App)


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
If you have a mobile backend server for your native app, then you can use the web app flow. If the app does not have a secure backend server, then you can use the secure storage API's on the device to store the client credentials. Though this seems secure it's technically not considered a confidential client.

The credentials are not trusted to be kept confidential. With this flow it is recommended to use the PKCE extension. This involves the app generating an arbitrary code and using that when exchanging the the authorization code for a secret. By doing this if the auth code is intercepted then it cannot be used without the arbitrary code.

**Grant Type: Authorization Code with PKCE**

*(Not yet supported)*{: .gray}


---

#### Learn more about OAuth 2.0 Flows

- [https://alexbilbie.com/guide-to-oauth-2-grants/](https://alexbilbie.com/guide-to-oauth-2-grants/)
- [https://medium.com/scalable/an-oauth2-grant-selection-decision-tree-for-securing-rest-apis-d63b5c0c8900](https://medium.com/scalable/an-oauth2-grant-selection-decision-tree-for-securing-rest-apis-d63b5c0c8900)

<br>
[Top](#top){: .float-right}
<br>
