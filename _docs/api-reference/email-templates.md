---
title: Email Templates 
category: API Reference
category-order: 6
order: 2
---

ForgeRock allows you to design custom emails triggered by user account activity. 

For example, you can set up an account verification email that's sent when a user 
registers for your service or application. That same email can also welcome 
users to your service.

ForgeRock email templates support the use of Markdown, based on the 
[CommonMark](https://spec.commonmark.org/) specification, enhanced by the
[markdown-it](https://github.com/markdown-it/markdown-it) parser. You can test
options on the [markdown-it demo site](https://markdown-it.github.io/). In 
addition, you can:

* Use [variables](#variables) to help personalize messages.
* Skin templates using CSS.


### Available Templates

You can configure the following templates to send email to your users. You can 
access these templates in your app, at the following URL: 
https://ui-{TENANT_NAME}.forgeblocks.com/email.

| Template Name | Description  |
| ------------- |------------- |
| **Forgot&nbsp;Password** | Whenever a user requests a password change. 
| **Recover&nbsp;Username** | For users who need help recovering their usernames. 
| **Registration**  | When a user registers on your service or application.  

{: .textSmaller} 

---

 ***Additional Templates Coming Soon:***
<br>

| Template Name | Description  |  
| ------------- |------------- |
| **Welcome** | When users verify their email addresses. 
| **Password&nbsp;Reset&nbsp;Successful** | Upon successful password reset.    
| **Email&nbsp;Update&nbsp;Successful** | After a user changes the account email address, an email is sent to both the old and new account to verify the change.
| **Account&nbsp;Locked** | When a user is locked out of their account.     
| **Username&nbsp;Recovered** | After a user has recovered their username.    
{: .textSmaller} 


<a name="variables"></a>
#### Variables

[//]: # (Are these handlebars.js variables -- and is that worth mentioning to help them create additional variables?)

You can add variables (with double curly braces **\{\{ variableName \}\}**) to 
the template. The variables will then pull data from entities such as users, 
apps and tenants. The following table includes example variables:



| Variable | Description  | Example |
| ------------- |------------- |------------- |
| \{\{application.name\}\} | Name of application. | *TrakMyExpenses*  
| \{\{user.emails.primary\}\} | Primary email of the user. | *bjensen@example.com*
| \{\{user.preferredLanguage\}\} | Preferred language of the user. |  *en-US*
| \{\{user.name.givenName\}\} | Given name / first name of the user.  | *Barbara*
| \{\{user.name.familyName\}\} | Family name / last name of the user. | *Jensen*
| \{\{user.name.formatted\}\} | User's fully formatted name. | *Ms. Barbara J Jensen, III*
| \{\{user.displayName\}\} | User's display name. | *Babs Jensen*
| \{\{user.userName\}\} | The username. | *bjensen*
| \{\{url\}\} | Generic link for account activity such as registration password reset.
| \{\{url.expiry\}\} | Limit on URL validity, in hours.
| \{\{date\}\} | Date and time of request.
| \{\{organization.name\}\} | Organization name. | *Mega Money Mgr Inc.*
| \{\{tenant.name\}\} | Tenant Name. | *Mega&nbsp;Money&nbsp;Mgr-Dev*
{: .variable .textSmaller} 



<br>

[//]: # (Should this be a common footer for each of our doc pages?)

> See a missing template or have feedback? let us know! [ea.cloud@forgerock.com](mailto:ea.cloud@forgerock.com)


<br>
