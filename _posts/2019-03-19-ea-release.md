---
title: EA.3.19.2019
type: major
---

**Features**

* Custom [scopes]({{ site.baseurl }}/reference/scopes).
* API Scopes tab in the UI for each app.
* Update whitelist URLs for the [Node.js SDK]({{ site.baseurl }}/sdks/nodejs).
* Dedicated URL for [API Documentation](https://developer-api.forgerock.com).

**Fixes**

* BUG #1100: Forgot Team Member Password not working

**Known Issues**

* BUG #1428: OIDC Scopes Missing from Authentication API. Several REST calls in our Postman collection may be affected.
* BUG #1286: Not all users listed in the UI.
* BUG #1004: Cannot PATCH user via the API. Workaround: use a PUT.
* BUG #905: Hosted page not Styled upon first use. Workaround: hit the ‘Save’ button in the hosted page section.
