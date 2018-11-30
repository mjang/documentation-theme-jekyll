---
title: EA.11.29.2018
type: major
---


**Features**
* Enhanced default user schema.
* Ability to query the [User endpoint]({{ site.baseurl }}/apis/apis-filtering/).

**Fixes**
* BUG #893: Cannot register a new user via the SDK.
 
**Known Issues**
* BUG #1021: Id Token and /userInfo endpoint not returning all user data.
* BUG #694: When setting up an application all grant types are allowed regardless of grant type boxes checked.
* BUG #1004: Cannot PATCH user via the API. Workaround: use a PUT.
* BUG #905: Hosted page not Styled upon first use. Workaround: hit the 'Save' button in the hosted page section.