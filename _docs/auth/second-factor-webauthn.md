---
title: Second Factor With Web Authentication
category: Authentication
category-order: 3
order: 4
auth_option: 'SecondFactorWebAuthn'
---

Second factor authentication requires users to confirm their identities through a different method. Users still supply usernames *and* passwords, before this option sends the user a confirmation code through SMS or Email. 

In this process, web authentication adds an alternative to the SMS/Email confirmation code, an *authenticator*. As noted in the following section, [Passwordless with WebAuthN]({{ site.baseurl }}/auth/passwordless/):

An authenticator is a device that can:

- Set up a private/public key pair
- Confirm consent by a user, locally

Users then must enter that confirmation code before the system signs them into the app.

The following diagram depicts the sign-in flow, before an authenticator is registered:

{% plantuml %}
title Second Factor With Web Authentication (before registering an Authenticator)
autonumber

participant "Web App" as Client
participant "End User" as User
participant "FRaaS Express Edition" as Provider
participant "Authenticator" as Authenticator

User->Client: Sign in to the Web App with a username/password

Client->Provider: Present credentials

Provider->User: Present choice for second factor authentication/ncode delivery through email or SMS/authenticator

User->Client: Choose SMS or email

User->Authenticator: Confirm identity through authenticator

Authenticator->Authenticator: Generate a public/private key pair

Authenticator->Provider: Authenticator sends a public key to the Web App

Provider->Provider: Stores a public key, with the user identity, for the authenticator

Provider->Client: Signs in user

{% endplantuml %}

{% include note.html content="If the user chooses SMS/Email for a second factor, as depicted in step 4, the process defaults to a standard second factor authentication process." %}

Now that FRaaS Express Edition has a public key credential for the authennticator, future logins use the authenticator as a second factor, as depicted here:

{% plantuml %}

title Second Factor Web Authentication (After Authenticator Registration)
autonumber
  
participant "Web App" as Client
participant "End User" as User
participant "FRaaS Express Edition" as Provider
participant "Authenticator" as Authenticator

User->Client: Sign in to the Web App with a username/password
  
Client->Provider: Present username/password

Provider->Provider: Finds public key credential, identifies authenticator

Provider->User: Request verification through authenticator

User->Authenticator: User confirms identity through authenticator

Authenticator->Provider: Authenticator confirms user identity, sends authentication token

Provider->Client: Provider verifies token with the public key, completes the login process

{% endplantuml %}

To incorporate second factor with web authentication, add the following code snippet to your app.

```
{% include authCodeSample.html %}
```
{% include authCodeTable.html %} 

> Second factor authentication also has risks, such as when passwords are compromised, as well as for SMS/email delivery. But the combination of factors reduces the risk to user data.
<br>

If you're familiar with OpenID Connect (OIDC) specifications, the Web App is the _Relying Party_, and the ForgeRock Identity Cloud is the _Authorization Server_.

For more information, see the following seciton of the AM Authentication and Single Sign-On Guide: [About Multi-Factor Authentication]({{ site.am_release_version }}/authentication-guide/#about-mfa).
