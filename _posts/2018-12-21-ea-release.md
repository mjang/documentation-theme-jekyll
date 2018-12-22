---
title: EA.12.21.2018
type: major
---

**Features**
* Custom [email templates]({{ site.baseurl }}/overview/email-templates/) triggered on particular events.
* Ability to invite team members to manage the system.
* Recover username API.
* Updated [app sdk]({{ site.baseurl }}/sdks/nodejs/) with in SDK auth_code flow.

**Fixes**
* BUG #1021: Id Token and /userInfo endpoint not returning all user data.
* BUG #694: When setting up an application all grant types are allowed regardless of grant type boxes checked.

 
**Known Issues**
* BUG #1100: Forgot Team Member Password not working
* BUG #1004: Cannot PATCH user via the API. Workaround: use a PUT.
* BUG #905: Hosted page not Styled upon first use. Workaround: hit the 'Save' button in the hosted page section.