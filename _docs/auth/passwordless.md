---
title: Passwordless With Web Authentication
category: Authentication
category-order: 3
order: 2
auth_option: 'PasswordlessWebAuthn'
---

Passwordless authentication (also known as Passwordless With WebAuthn) allows users to verify their identities without passwords. Our implementation requires users to enter their passwords once. On future sign-ins, such users can verify their identities through an _authenticator_.

When you sign in to a WebAuthn-enabled app, the next step challenges you to verify your identity through a device. Examples of that device could be a PC, a mobile phone, or a tablet. Your device then uses an authenticator such as a fingerprint reader, facial recognition software, or a hardware key to verify your identity. Authenticators are certified through the [FIDO Alliance](https://fidoalliance.org/certification/fido-certified-products/).

An _authenticator_ is a device that can:
* Set up a private/public key pair
* Confirm consent by a user, locally
 
The authentication flow varies slightly, depending on whether an *authenticator* has been configured. The first diagram depicts a flow that includes authenticator registration.

Once the authenticator verifies your identity, WebAuthn creates an authentication token. WebAuthn creates a new token every time you sign in. The following diagrams depict the flow upon user registration, and then on subsequent sign-ins:

{% plantuml %}
title Passwordless With WebAuthn Flow (First Sign-in)
autonumber

participant "Web App" as Client
participant "End User\n(Browser)" as User
participant "FRaaS Express Edition" as Provider
participant "Authenticator" as Authenticator

User->Client: Sign in to the Web App with a username/password

Client->Provider: Present credentials

Provider->User: Request authenticator registration

User->Authenticator: User confirms identity through an authenticator

Authenticator->Authenticator: Generate a private/public key pair

Authenticator->Provider: Authenticator sends a public key to the Web App

Provider->Provider: Stores a public key, with the user identity, for the authenticator

Provider->Client: Signs in the user

{% endplantuml %}

Now that FRaaS Express Edition has a public key credential for the user's authnticator, future sign-ins do not require a password, as depicted here:

{% plantuml %}
title Passwordless With WebAuthn Flow (After Authenticator Registration)
autonumber

participant "Web App" as Client
participant "End User\n(Browser)" as User
participant "FRaaS Express Edition" as Provider
participant "Authenticator" as Authenticator

User->Client: Sign in to the Web App with a username

Client->Provider: Present username

Provider->Provider: Finds public key credential, identifies authenticator

Provider->User: Request verification through authenticator

User->Authenticator: User confirms identity through authenticator

Authenticator->Provider: Authenticator confirms user identity, sends authentication token

Provider->Client: Provider verifies token with the public key, completes the sign-in process

{% endplantuml %}

To incorporate passwordless authentication, add the following code snippet to your app:

```
{% include authCodeSample.html %}
```

{% include authCodeTable.html %}

{% include warning.html content="The options associated with passwordless authentication have risks. For example:<br/> * Biometrics can be fooled via high-quality photos.<br/> * Unsolicited messages could be sent to devices registered to an account." %}
<br>

If you're familiar with OAuth 2 specifications, the Web App is the _Relying Party_, and FRaaS Express Edition is the _Authorization (or Identity) Server_.

For more information on _WebAuthn_, see the following [document](https://www.w3.org/TR/webauthn/) from the World Wide Web Consortium (W3C).
