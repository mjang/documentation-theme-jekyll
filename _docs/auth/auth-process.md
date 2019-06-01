---
title: Incorporate Auth Into Your App
category: Authentication
category-order: 3
order: 1
auth_option: 'Desired authentication flow'
---


This section shows you how to incorporate our Authentication Services into your Native/SPA (browser-based) apps.

As shown in the Admin Console, we provide the following options for authentication services. Links with more information are included (except for Username and Password authentication). Note the associated value of `flow`, which you can substitute in the code sample shown:

*  Username and Password: `UsernamePassword`{: .plain}
*  [Passwordless with WebAuthN]({{ site.baseurl }}/auth/passwordless/): `PasswordlessWebAuthn`{: .plain}
*  [Second Factor]({{ site.baseurl }}/auth/second-factor/): `SecondFactor`{: .plain}
*  [Second Factor with WebAuthn]({{ site.baseurl }}/auth/second-factor-webauthn/): `SecondFactorWebAuthn`{: .plain}

---

Each of these options includes a JavaScript code sample that you can incorporate into your app:

```
{% include authCodeSample.html %}
```

For the variables in the `auth-sdk-config` code block, substitute as follows:

{% include authCodeTable.html %}

You can incorporate the given `div-id` in your app, as needed.

> Browsers load the source code of Native/SPAs. To keep your apps secure, we recommend that you do not include a *client secret* in Native/SPA apps. 


---
