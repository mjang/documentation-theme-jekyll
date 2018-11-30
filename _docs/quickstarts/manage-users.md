---
title: Management API
category: Quick Starts
category-order: 2
order: 2
---



The management API allows you to configure and read information about stored entities like users and apps. We've created [postman collections]({{ site.baseurl }}/apis/apis) describing the APIs and allowing you easily test calls. For this quick start we'll just use the terminal and run some CURL commands. 

### Creating a user

To create a user first we need to get a token that authorizes us to update the user, then we'll use this token to call the user endpoint and create the user.

1. In the Admin console go to Applications > New Application and create a 'Service App'. Give it a name and click 'Save'.

1. Copy the "client id" and "secret".

1. In your terminal base64 encode the client id and secret by running the command below.

    ```
    echo -n CLIENT_ID:SECRET | base64
    ```
1. Copy the command below
    - Replace 'BASE_64_ENCODED_STRING' 
    - Replace 'YOUR_TENANT_NAME' 

    Then run the command in the terminal.

    ```
    curl -X POST \
    https://openam-YOUR_TENANT_NAME.forgeblocks.com/openam/oauth2/access_token \
    -H 'Authorization: Basic BASE_64_ENCODED_STRING' \
    -H 'Cache-Control: no-cache' \
    -H 'Content-Type: application/x-www-form-urlencoded' \
    -d 'scope=api.forgecloud.com:user.read api.forgecloud.com:user.write&grant_type=client_credentials'
        
    ```

   #### Note the scopes!
    We are telling the authorization server to mint a token that will allow us to read and update users.

1. Now we can call the Management API to create a user using the access_token we just got. Copy the command below.
    - Replace 'ACCESS_TOKEN'
    - Replace 'YOUR_TENANT_NAME' 

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

1. That's it! check out the user in the UI to see what's there. We don't show all of the possible user fields in the UI, only the primary ones. You can use the management API to add additional data to the user.

### Where to go from here

1. Head over to the [API]({{ site.baseurl }}/apis/apis) section and download the calls into postman. 
1. Try updating the user you just created using the id returned from the create user call.
1. Try updating other endpoints in the system. Don't forget to ask for the right scopes when you call the authorization endpoint to get the token. The token is minted based on the scopes you've asked for.

```
api.forgecloud.com:user.read 
api.forgecloud.com:user.write
api.forgecloud.com:app.read 
api.forgecloud.com:app.write 
api.forgecloud.com:password-policy.read 
api.forgecloud.com:password-policy.write
```



