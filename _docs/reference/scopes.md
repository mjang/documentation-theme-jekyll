---
title: Scopes
category: Reference
category-order: 5
order: 3
datatable: true
---

With scopes, you can set access rights for web apps, to limit their abilities and risks. For example, if an app developer wants to configure an app that allows users to manage their own accounts. To that end, you can include scopes that support:

* Password reset
* Attribute management (such as for phone numbers and addresses)

Alternatively, to set up a service app that can upload multiple users, you can set up scopes that support access to the user database.

Implementation can get complex, depending on authorization requirements.

_**Note:** Before you can configure scopes, you must enable the **Client Credentials** grant type in the advanced settings for your app.._

In support of these requirements, ForgeRock includes custom scopes as defined here. The scopes that you may use depend on the endpoint:

 - **/apps**: For all applications.

 Scopes   | Web App          | Service App
 -------- | -----------------|------------
 apps.create <br> apps.read <br> apps.update <br> apps.delete <br> apps.refresh-secret | **Allowed**: All <br> **Default**: None | **Allowed**: All <br> **Default**: apps.read

 - **/email-templates**: Templates for new users, password reset, and account verification.

 Scopes   | Web App          | Service App
 -------- | -----------------|------------
 email-template.read <br> email-template.update    | **Allowed**: All <br> **Default**: None  | **Allowed**: All <br> **Default**: email-template.read  

 - **/email-templates/send-test**: For sending test emails.

 Scopes   | Web App          | Service App
 -------- | -----------------|------------
 email-template.read  | **Allowed**: All <br> **Default**: None  | **Allowed**: All <br> **Default**: email-template.read  

 - **/hosted-page**: For configuring hosted pages with **GET** and **PUT**.

 Scopes   | Web App          | Service App
 -------- | -----------------|------------
 hosted-page-config.read <br> hosted-page-config.update    | **Allowed**: All <br> **Default**: None  | **Allowed**: All <br> **Default**: None

 - **/me**: For the current logged in user.

 Scopes   | Web App          | Service App
 -------- | -----------------|------------
 me.read <br> me.update    | **Allowed**: All <br> **Default** All | N/A

 - **/me/update-password**: Password updates for the current logged in user.

 Scopes   | Web App          | Service App
 -------- | -----------------|------------
 me.password    | **Allowed**: All <br> **Default** All | N/A

- **/password-policy**: Global password policy configuration.

Scopes   | Web App          | Service App
-------- | -----------------|------------
password-policy.read <br> password-policy.update    | **Allowed**: All <br> **Default**: password-policy.read  | **Allowed**: All <br> **Default**: password-policy.read  

- **/users**: User management.

Scopes   | Web App          | Service App
-------- | -----------------|------------
user.create <br> user.read <br> user.update <br> user.delete    | **Allowed**: All <br> **Default** user.create <br> user.read | **Allowed**: All <br> **Default** user.create <br> user.read <br> user.update

- **/users/reset-password**: Password recovery.

Scopes   | Web App          | Service App
-------- | -----------------|------------
user.reset-password   | **Allowed**: All <br> **Default** All | **Allowed**: All <br> **Default** All

- **/users/recover-username**: Username recovery.

Scopes   | Web App          | Service App
-------- | -----------------|------------
user.recover-username   | **Allowed**: All <br> **Default** All | **Allowed**: All <br> **Default** All
