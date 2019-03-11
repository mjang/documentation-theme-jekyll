---
title: Management API
category: Quick Starts
category-order: 2
order: 2
---


Use the management API to configure and read information about stored entities like users and apps. We've created [Postman collections]({{ site.baseurl }}/apis/apis) that describe the APIs and allow you to test different REST calls. For this quick start tutorial, we'll use the terminal to run some REST calls with cURL.

### Creating a user

Before you can create a user, you'll need an access token, available through the Authentication API. With that token, you can create users with the Management API through the `users` endpoint.

1. In the Admin console go to Applications > New Application and create a **Web App** or a **Service App**. Give it a name and select Save.

1. Make a copy of the **Client ID** and **Client Secret**.

1. Base64-encode your Client ID and Client Secret. One way to do so is with the following command:

    ```
    echo -n CLIENT_ID:CLIENT_SECRET | base64
    ```
1. In the following REST call, replace:
    - 'BASE_64_ENCODED_STRING'
    - 'YOUR_TENANT_NAME'

Then, run the custom command in your terminal.

    ```
    curl -X POST \
    https://openam-YOUR_TENANT_NAME.forgeblocks.com/oauth2/access_token \
    -H 'Authorization: Basic BASE_64_ENCODED_STRING' \
    -H 'Cache-Control: no-cache' \
    -H 'Content-Type: application/x-www-form-urlencoded' \
    -d 'scope=api.forgecloud.com:user.read api.forgecloud.com:user.write&grant_type=client_credentials'

    ```

The output includes a long value for `access_token`. In several other ForgeRock Identity Cloud REST calls, you'll see the following entry:

```
 --header "Authorization: Bearer "
```

The `access_token` is also known as the bearer token. To run these REST calls, you'd include the value of the `access_token` within the quotes, after `Bearer`.

#### Note the scopes!

The ForgeRock Identity Cloud creates an access token that allows you to read (`user.read`) and update (`user.write`) user information.



1. Use the Management API to create a user using the newly minted access_token. In the following command, substitute your values for:
    - 'ACCESS_TOKEN'
    - 'YOUR_TENANT_NAME'

Then run the command in the terminal.

    ```
    curl -X POST \
    https://api-YOUR_TENANT_NAME.forgeblocks.com/v1/users \
    -H 'Content-Type: application/json' \
    -H 'Authorization: Bearer ACCESS_TOKEN' \
    -H 'cache-control: no-cache' \
    -d '  {
    "externalId": "701985",
    "userName": "bjensen@example.com",
    "accountVerified": true,
    "name": {
      "formatted": "Ms. Barbara J Jensen, III",
      "familyName": "Jensen",
      "givenName": "Barbara",
      "middleName": "Jane",
      "honorificPrefix": "Ms.",
      "honorificSuffix": "III"
    },
    "displayName": "Babs Jensen",
    "nickName": "Babs",
    "profileUrl": "https://login.example.com/bjensen",
    "emails": [
      {
        "value": "bjensen@example.com",
        "type": "work",
        "primary": true,
        "verified": true
      },
      {
        "value": "babs@jensen.org",
        "type": "home",
        "verified": false
      }
    ],
    "addresses": [
      {
        "type": "work",
        "streetAddress": "6925 Hollywood Blvd",
        "locality": "Hollywood",
        "region": "CA",
        "postalCode": "90028",
        "country": "US",
        "formatted": "6925 Hollywood Blvd\nHollywood, CA 90028 USA",
        "primary": true
      },
      {
        "type": "home",
        "streetAddress": "2800 E Observatory Rd",
        "locality": "Los Angeles",
        "region": "CA",
        "postalCode": "90027",
        "country": "US",
        "formatted": "2800 E Observatory Rd\nLos Angeles, CA 90027 USA"
      }
    ],
    "phoneNumbers": [
      {
        "value": "555-555-5555",
        "type": "work"
      },
      {
        "value": "555-555-4444",
        "type": "mobile"
      }
    ],
    "userType": "Customer",
    "title": "Master Carpenter",
    "preferredLanguage": "en-US",
    "locale": "en-US",
    "timezone": "America/Los_Angeles",
    "active": true,
    "password": "Passwordy1!"
  }'
    ```

1. That's it! Review the user entry the UI. Note how the UI doesn't show every user detail. You can use the management API to review, add, or revise data for this or all users.

For the next steps, save the `id` of the new user.

### Next Steps

1. Navigate to the [REST APIs]({{ site.baseurl }}/apis/apis) page. Download the Postman collection.
1. Update the user you just created. Find the `id` returned from the REST call you ran to create the user.
1. Try running REST calls on other `users` endpoints.
1. If you want different access privileges, create a new `access_token` with desired [scopes]({{ site.baseurl }}/reference/scopes). As you're limited to the scopes configured for your app, find your app at https://ui-{{tenantName}}.forgeblocks.com/apps/, and review the appropriate API Scopes tab.
