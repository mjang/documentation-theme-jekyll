---
title: Email Templates 
category: Overview
order: 4
excluded_in_navigation: true
excluded_in_search: true
---

ForgeRock allows you to create emails that are automatically sent when triggered by a users activity. 

For example when a user registers for your service or application you can trigger an account verification email. The email can contain a link to verify their account and welcome them to your service. 




### Available Templates

There are a number of templates available out of the box that you can configure and send to your users.


| Template Name | Description  |
| ------------- |------------- |
| **Registration**  | Sent whenever a user signs up for the first time.  
| **Forgot&nbsp;Password** | Sent whenever a user requests a password change. 
| **Recover&nbsp;Username** | Email sent if user wishes to recover username. 

{: .textSmaller} 

---

 ***Coming Soon...***
<br>

| Template Name | Description  |  
| ------------- |------------- |
| **Welcome** | Sent once the user verifies their email address. 
| **Password&nbsp;Reset&nbsp;Successful** | Sent when a user has successfully reset their password.    
| **Email&nbsp;Update&nbsp;Successful** | Sent when a user has successfully changed their email. The email will go to both the old and new account in case the user did not request it.
| **Account&nbsp;Locked** | Sent when a user has been locked out of their account.     
| **Username&nbsp;Recovered** | Sent after a user has recovered their username.    
{: .textSmaller} 


### Configuring Templates

Email templates are written in [markdown]({{ site.baseurl }}/reference/markdown) and can be skinned using CSS. You can also use variables in the template to pull data from various entities in the system like users, apps and tenants.


#### Variables

Variables are formatted using double curly braces **\{\{ variableName \}\}** and can be used in the body of the email or in the form fields.



| Variable | Description  | 
| ------------- |------------- |
| \{\{application.name\}\} | Name of application the user registered from. <br> *Example: TrakMyExpenses*  
| \{\{user.emails.primary\}\} | Primary email of the user. <br> *Example: bjensen@example.com*
| \{\{user.preferredLanguage\}\} | Preferred language of the user.  <br> *Example: en-US*
| \{\{user.name.givenName\}\} | Given name / first name of the user.  <br> *Example: Barbara*
| \{\{user.name.familyName\}\} | Family name / last name of the user.  <br> *Example: Jensen*
| \{\{user.name.formatted\}\} | The users fully formatted name.  <br> *Example: Ms. Barbara J Jensen, III*
| \{\{user.displayName\}\} | The display name of the user.  <br> *Example: Babs Jensen*
| \{\{user.userName\}\} | The users username.  <br> *Example: bjensen*
| \{\{url\}\} | Generic link that will either confirm account registration or reset password within the email.
| \{\{url.expiry\}\} | Time till url link expires in hours.
| \{\{date\}\} | Date and time of request.
| \{\{organization.name\}\} | Organization name.  <br> *Example: Mega Money Mgr Inc.*
| \{\{tenant.name\}\} | Tenant Name.  <br> *Example: Mega&nbsp;Money&nbsp;Mgr-Dev*
{: .variable .textSmaller} 



<br>

> See a missing template or have feedback? let us know! [ea.cloud@forgerock.com](mailto:ea.cloud@forgerock.com)


<br>