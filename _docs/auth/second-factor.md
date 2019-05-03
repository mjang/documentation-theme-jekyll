---
title: Second Factor Authentication
category: Authentication
category-order: 3
order: 3
auth_option: 'SecondFactor'
---

Second factor authentication requires users to confirm their identities through a different method. Users still supply usernames *and* passwords, before this option sends the user a confirmation code through SMS or Email. 

Users then must enter that confirmation code before the process signs them into the app.

The following diagram depicts the sign-in flow:

{% plantuml %}
title Second Factor Authentication
autonumber

participant "Web App" as Client
participant "End User" as User
participant "FRaaS Express Edition" as Provider

User->Client: Sign in to the Web App with a password

Client->Provider: Confirm authentication

Provider->User: Present choice for code delivery (email or SMS)

User->Client: Specify choice for code delivery

Client->User: Sends code through client-selected option 

User->Client: User includes the provided code

Provider->Client: Authenticates user

{% endplantuml %}

To incorporate second factor authentication, add the following code snippet to your app:

```
{% include authCodeSample.html %}
```
{% include authCodeTable.html %} 

> Second factor authentication also has risks, such as when passwords are compromised, as well as for SMS/email delivery. But the combination of factors reduces the risk to user data.
<br>

If you're familiar with OAuth 2 specifications, the Web App is the _Relying Party_, and FRaaS Express Edition is the _Authorization (or Identity) Server_.

For more information, see the following seciton of the AM Authentication and Single Sign-On Guide: [About Multi-Factor Authentication]({{ site.am_release_version }}/authentication-guide/#about-mfa).
