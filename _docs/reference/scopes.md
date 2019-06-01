---
title: Scopes
category: Reference
category-order: 6
order: 3
datatable: true
---

A scope is a set of rights to a protected resource, associated with an access token. Clients can request scopes to access to a protected resource. The authorization server can allow or deny such requests.

With scopes, you can set access rights for web apps, to limit their abilities and risks. For example, if an app developer wants to configure an app that allows users to manage their own accounts. To that end, you can include scopes that support:

* Password reset
* User profile management (such as for phone numbers and addresses)

Alternatively, to set up a service app that can upload multiple users, you can set up scopes that support access to the user database.

Implementation can get complex, depending on authorization requirements.

_**Note:** Before you can configure scopes, you must enable the **Client Credentials** grant type in the advanced settings for your app.._

### OIDC Scopes

Apps can use OpenID Connect (OIDC) scopes to access user information such as *name*, *email*, and *phone_number*. 

OIDC requests **must** include the following scope:

 - **openid**

OIDC requests can also include the following scopes, which are associated with the following *voluntary* claims. 

 - **profile**: *name*, *given_name*, *family_name*, *middle_name*, *nickname*, *profile*, *picture*, *zoneinfo*, *locale*, *updated_at*

 - **email**: *email*, *email_verified*

 - **address**: *address*

 - **phone**: *phone_number*

A *voluntary* claim does not have to be included. For example, if you ask for information about a user without a *middle_name*, the app does not have to return that claim for the user. 

You can manage these scopes from the UI. Log into https://ui-\{\{tenantName}}.forgeblocks.com. Sign in as a team member. Navigate to and select an application. You'll see available and selected scopes under an **API Scopes** tab:

![]({{ site.baseurl }}/images/scopes.png)
{: .plain-blockquote}

### Custom Scopes

ForgeRock also includes custom scopes as defined here. The scopes that you may use depend on the endpoint. The scopes are shown in the following format: `(entity).(action)`{: .plain}.

 - **/apps**: For all applications.

    - apps.create
    - apps.read
    - apps.update
    - apps.delete
<br>

 - **/email-templates**: Templates for new users, password reset, and account verification.

    - email-template.read
    - email-template.update  
<br>

 - **/email-templates/send-test**: For sending test emails.

   - email-template.read  
<br>

 - **/hosted-page**: For configuring hosted pages with **GET** and **PUT**.

   - hosted-page-config.read
   - hosted-page-config.update  
<br>

 - **/me**: For the current logged in user.

   - me.read
   - me.update  
<br>

 - **/me/update-password**: Password updates for the current logged in user.

    - me.update-password  
<br>

- **/password-policy**: Global password policy configuration.

   - password-policy.read
   - password-policy.update  
<br>

- **/users**: User management.

   - user.create
   - user.read
   - user.update
   - user.delete  
<br>

- **/users/reset-password**: Password recovery.

   - user.reset-password  
<br>

- **/users/recover-username**: Username recovery.

   - user.recover-username

### More Information

If you want more information on OIDC Scopes, see:

- [OpenID Connect Specification, Authentication Request](https://openid.net/specs/openid-connect-core-1_0.html#AuthRequest)
- [OpenID Connect Specification on Requesting Claims using Scope Values](https://openid.net/specs/openid-connect-core-1_0.html#ScopeClaims)
