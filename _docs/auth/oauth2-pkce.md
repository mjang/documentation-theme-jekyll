---
title: Keeping Your Apps Secure with PKCE
category: Authentication
category-order: 3
order: 5
---

In OAuth 2.0, the authorization server authenticates the end user. It also confirms, with the end user, that your client app is allowed to access the user's resources. On confirmation, the authorization server returns an authorization code to your client app. The authorization code is used to get an access token. Your client, app, as the *bearer*, can use the token to access to the user's resources. 

Your client app cannot protect this exchange from other applications running in the browser. These apps may be native or single-page applications (SPAs).

You'll find native apps installed on devices such as smart phones. You'll find single-page applications (SPAs) running on browsers (which is why they're often called "browser-based apps"). In these cases, the source code is available on the browser or the device. Since these public-facing apps cannot maintain the confidentiality of a client secret, we take a different approach.

Proof Key for Code Exchange (PKCE) mitigates the risks of an OAuth 2.0 attack. Otherwise, a malicious application running in the same browser as the your public client app could take advantage by getting the authorization code first.

PKCE also mitigates the risks when apps do not use a client secret. With PKCE, your app, with the help of our code, generates a *code_verifier* (nonce). When your users make a request, your app creates a *hash* of that code_verifier as a *code_challenge*. The ForgeRock Identity Cloud, as an Authorization Server, saves that hash value. 

After the hash is confirmed as valid, your app subsequently exchanges its authorization code grant for an access token. Your app then uses that token to grant access to desired resources.

The following diagram depicts the authorization code grant flow:

{% plantuml %}
title Authentication on Browser-based Apps With PKCE 
autonumber

participant "Web App" as Client
participant "End User\n(Browser)" as User
participant "FRaaS Express Edition" as Provider
participant "Resource Server" as Resource

Client->Client: Generate code verifier; create hash as a code challenge

Client->User: Send code challenge and code verifier

User->Provider: Authenticate and send code challenge hash

Provider->Provider: Store code challenge
group Authenticate user
  Provider->User: Request credentials
  User->Provider: Supply credentials
end

Provider->User: Return authorization code

User->Client: Pass authorization code

Client->Provider: Send authorization code, code verifier; request access token

Provider->Client: Confirm matching hash, return access token

Client->Resource: Request resource with access token

{% endplantuml %}


If you're familiar with OpenID Connect (OIDC) specifications, the Web App is the _Relying Party_, and the ForgeRock Identity Cloud is the _Authorization Server_.

For more information on PKCE standards see the following IETF document: [ Proof Key for Code Exchange by OAuth Public Clients](https://tools.ietf.org/html/rfc7636).
 
For more information on how ForgeRock implements PKCE for native and SPA apps, see the following section of our Access Management documentation: [Authorization Code Grant With PKCE]({{ site.am_release_version }}/oauth2-guide/#oauth2-authz-pkce) 
