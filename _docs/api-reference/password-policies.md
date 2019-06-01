---
title: Password Policies
category: API Reference
category-order: 7
order: 1
---

ForgeRock allows you to configure a custom password policies in two ways:

- With a REST call, as shown in the [Password Policies](https://developer-api.forgerock.com/#33bc54db-ba8b-473b-bc4f-68d08a748ead) section of our Management APIs.

- Through the Admin Console, under Configure > Password Policy.

### Password Policy Options

The following table describes options associated with the Password Policies REST calls; the options as described in the Admin Console are self-explanatory:


| Property | Password-Related Description  | Requirement
| ------------- |------------- |
| `disallowFirstNamePart`{: .plain} | Prohibits the use of the first name (case insensitive)
| `disallowLastNamePart`{: .plain} | Prohibits the use of the last name (case insensitive)
| `lockoutPasswordAttempts`{: .plain} | Number of bad password attempts allowed before locking an account; to disable, set = 0
| `maxPasswordAge`{: .plain} | Validity period (days); to disable, set=0 | Max <= 24855 
| `minPasswordLength`{: .plain} | Minimum length | Min=8 Max=64 
| `requireEmailVerification`{: .plain} | Whether users must verify new accounts by email
| `requireLowerCaseLetter`{: .plain} | Whether passwords *must* include a lower case letter
| `requireNumber`{: .plain} | Whether passwords *must* include a digit
| `requireSymbol`{: .plain} | Whether passwords *must* include one of the following special characters: `~!@#$%^&*()-_=+[]{}|;:,.<>/?`{: .plain}
| `requireUpperCaseLetter`{: .plain} | Whether passwords *must* include an upper case letter
| `selfServeUnlockDuration`{: .plain} | Time before unlocking an account (minutes) | Min=1 Max=30 

{: .textSmaller}

For example, if you want to change password policy options, use the following REST call. Substitute your `TENANT_NAME` and `ACCESS_TOKEN`. Include desired
settings in the data (*-d*) block of your REST call, as shown here:

```
curl -X PUT \
https://api-TENANT_NAME.forgeblocks.com/v1/password-policy \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer ACCESS_TOKEN' \
-H 'cache-control: no-cache' \
  -d '{
    "disallowFirstNamePart": true,
    "disallowLastNamePart": true,
    "lockoutPasswordAttempts": 5,
    "maxPasswordAge": 0,
    "minPasswordLength": 10,
    "requireEmailVerification": true,
    "requireLowerCaseLetter": true,
    "requireNumber": true,
    "requireSymbol": true,
    "requireUpperCaseLetter": true,
    "selfServeUnlockDuration": 10
}'
```
_**Note:** If you don't include one or more of the properties in the REST call, you'll see an error message to that effect, such as:_
```
{
  "errors": [
    {
      "code": 0,
      "message": "\"lockoutPasswordAttempts\" is required"
    }
  ]
}
``` 
---
