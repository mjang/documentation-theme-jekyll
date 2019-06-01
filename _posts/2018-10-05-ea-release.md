---
title: EA.10.05.2018
type: major
---


**Features**

* Simplify '/users/update-password' endpoint.
* Provide startIndex and count on endpoints. Example: /users?startIndex=0&count=2
* Added a '/me/update-password' endpoint.


**Fixes**
* Prevent tenant creation from failing when an email or tenant name collision occurs.
* Changed '/user' endpoint to '/users'. 
* Changed '/user/me' endpoint to '/me'.
* Changed POST, PUT '/apps' to /apps/{id}'.
 

**Known Issues**
* Team Members sharing password policy with App Users.
* Team Members mixed in with App users.
* Setting Team Member password at tenant create does not include all special characters.
* When setting up an application it allows all grant types regardless of grant type boxes checked.


