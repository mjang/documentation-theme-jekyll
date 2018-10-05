---
title: ForgeRock Identity Gateway 
category: Identity Gateway
excluded_in_navigation: true
category-order: 5
order: 1
---

### About the ForgeRock Identity Gateway
The ForgeRock Identity Gateway (IG) is an API & web application security gateway. By using IG you can abstract security away from your applications and simplify application and API development.

### Advantages

- **Simplicity:** Implement policy enforcement and API security in one place.

- **Consistency:** If you have 100's of apps 100 you can implement security in the gateway instead of the application itself. Any changes to enforcement can be made in the gateway avoiding the need to update code in multiple places. 

- **Legacy Integration:** Onboard applications and legacy APIs that have non-standard authentication methods or older protocols without updating the applications. 

- **Future Proofing:** Protect your applications from new standards and protocols without changing the application or API itself.


### Get Started with IG and ForgeRock Identity Cloud

Set up IG in your local environment by running though the <a href="https://backstage.forgerock.com/docs/ig/6.1/getting-started/#quickstart-install" target="_blank">IG Quick Start Guide</a>


#### Securing an API
In this quick start you will secure an API by using the ForgeRock cloud to authorize access.

1. In the Identity Cloud Admin console navigate to Applications and create a new Service Application.
1. Save the client id and secret.
1. On the server drop in the page: api.js
1. In IG Studio create a route for the path that represents the application you want to protect.
1. In IG Studio enable authorization for the route so IG acts as an OAuth2.0 resource server.
1. In IG Studio configure OAuth2 authorization
    - **Access token resolver:** "OAuth 2.0 introspection endpoint"
    - **Introspection endpoint URI:** https://openam-{TENANT_NAME}.forgeblocks.com/openam/oauth2/introspect`
    - **Client name:** The client ID from the Service App you created in Identity Cloud Admin.
    - **Client secret:** The client secret from the Service App you created in Identity Cloud Admin.
    - **Evaluate scopes:** Statically.
    - **Scopes:** Scopes to be enforced for this route.
1. Deploy the route

#### Test the Route is Protected 

1. Hit to the endpoint "http://ig.example.com:14080/api"
1. Login 


### Secure your Web App
In this quick start you will secure your web app by using the ForgeRock cloud to authorize access.

1. 