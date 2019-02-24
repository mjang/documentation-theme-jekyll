---
title: Scopes
category: Reference
category-order: 5
order: 3
datatable: true
---

With scopes, you can set access rights for web apps, to limit their abilities and risks. For example, if an app developer wants to configure an app that allows users to manage their own accounts. To that end, you can include scopes that support:

* Password reset
* User profile management (such as for phone numbers and addresses)

Alternatively, to set up a service app that can upload multiple users, you can set up scopes that support access to the user database.

Implementation can get complex, depending on authorization requirements.

_**Note:** Before you can configure scopes, you must enable the **Client Credentials** grant type in the advanced settings for your app.._

In support of these requirements, ForgeRock includes custom scopes as defined here. The scopes that you may use depend on the endpoint. The scopes are shown in the following format: `(entity|task).(action)`{: .plain}.

 - **/apps**: For all applications.

    - apps.create
    - apps.read
    - apps.update
    - apps.delete
    - apps.refresh-secret  
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

    - me.password  
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
