---
title: Tokens 
category: Overview
order: 3
---

There are several tokens in play when you make calls against the ForgeRock authorization server and it is important to understand what they do. 

There are 3 tokens in play...

- **id_token:** contains information about a user.
- **access_token:** used by an application to access an api.
- **refresh_token:** used to obtain a new access_token when the access_token has expired.

Here's an [example call](#call) with all the tokens in play.

### Id Token

This token contains information about the user and is returned in the form of JWT that conforms to the OIDC specification. OIDC defines a set of standard claims about users that can be returned in an **id_token** or in the response from **/userinfo** endpoint.

When you make the call you pass in the scopes that you are asking for access to about the user and in return you get claims containing information about that user. 

#### Scopes

 - **openid** (required) Informs the Authorization Server that the Client is making an OpenID Connect request and requests that the ID Token associated with the authentication session be returned. 

 - **profile** asks for name, family_name, given_name, middle_name, nickname, picture and updated_at.

 - **email** asks for  email and email_verified.

 - **address** asks for address claim.

 - **phone** asks for phone_number.


### Access Token
The access token determines what APIs you are authorized to have access to. The token is in the form of a JWT. As part of the request to the authorization server you pass in the API scopes you would like to access. 

For example passing in the scope **'api.forgecloud.com:user.read'** to the server asks for a JWT to be minted with permission to read from the ForgeRock user endpoint.


### Refresh Token
The refresh token is a special kind of access token that is only available when you use the web app client. The refresh token allows you to ask the authorization for another access_token without bothering the user once it has expired. 

To get a new access token using a refresh token you make a POST to the /access_token endpoint, passing in your client_id, client_secret, grant_type of “refresh_token”, and the refresh_token itself. A new access token and a new refresh token will be returned.

<a name="call"></a>
### Example Call

Here is an example of a call using the web app client type where you are passed back all the tokens.


```
curl -X POST \
https://openam-YOUR_TENANT_NAME.forgeblocks.com/openam/oauth2/access_token \
-H 'Authorization: Basic BASE_64_ENCODED_STRING' \
-H 'Cache-Control: no-cache' \
-H 'Content-Type: application/x-www-form-urlencoded' \
-d 'grant_type=password&username=bjensen&password=Password1234!&scope=openid profile api.forgecloud.com:user.read'   

```
```
    {
        "access_token": "eyJ0eXAiOiJKV1QiLCJ6aXAiOiJOT05FIiwiYWxnIjoiSFMyNTYifQ.eyJzdWIiOiJiamVuc2VuIiwiY3RzIjoiT0FVVEgyX1NUQVRFTEVTU19HUkFOVCIsImF1dGhfbGV2ZWwiOjAsImF1ZGl0VHJhY2tpbmdJZCI6ImZkMjQ3ZjE1LTk4NGQtNDgzOC05YjMyLTU2ODYyODkwNmU5ZS0xMTE1NDI2IiwiaXNzIjoiaHR0cHM6Ly9vcGVuYW0ta2F0ZTUwMmUuZm9yZ2VibG9ja3MuY29tL29wZW5hbS9vYXV0aDIiLCJ0b2tlbk5hbWUiOiJhY2Nlc3NfdG9rZW4iLCJ0b2tlbl90eXBlIjoiQmVhcmVyIiwiYXV0aEdyYW50SWQiOiJZM09uUHBKMkpZaEF0cWkyWUZzVGhHYUdLMGsiLCJhdWQiOiJiNGFlMDVkMmZiODQ4ZDRhM2Y0NzI3ZTg1NGQyYmNkYiIsIm5iZiI6MTUzODE0NDUwMiwiZ3JhbnRfdHlwZSI6InBhc3N3b3JkIiwic2NvcGUiOlsiYWRkcmVzcyIsIm9wZW5pZCIsImFwaS5mb3JnZWNsb3VkLmNvbTp1c2VyLndyaXRlIiwicHJvZmlsZSIsImFwaS5mb3JnZWNsb3VkLmNvbTp1sc2VyLnJlYWQiLCJwaG9uZSJdLCJhdXRoX3RpbWUiOjE1MzgxNDQ1MDIsInJlYWxtIjoiLyIsImV4cCI6MTUzODE0ODEwMiwiaWF0IjoxNTM4MTQ0NTAyLCJleHBpcmVzX2luIjozNjAwLCJqdGkiOiI0c0U3OWFaMDNZeWd3SDlHSU13QVI5VTM2bDQifQ.RDMd0k6gjJ1tDHiFkAj8l19EgAQYejMK_Y03rfOwFfw",
        "refresh_token": "eyJ0eXAiOiJKV1QiLCJ6aXAiOiJOT05FIiwiYWxnIjoiSFMyNTYifQ.eyJzdWIiOiJiamVuc2VuIiwiY3RzIjoiT0FVVEgyX1NUQVRFTEVTU19HUkFOVCIsImF1dGhfbGV2ZWwiOjAsImF1ZGl0VHJhY2tpbmdJZCI6ImZkMjQ3ZjE1LTk4NGQtNDgzOC05YjMyLTU2ODYyODkwNmU5ZS0xMTE1NDI1IiwiaXNzIjoiaHR0cHM6Ly9vcGVuYW0ta2F0ZTUwMmUuZm9yZ2VibG9ja3MuY29tL29wZW5hbS9vYXV0aDIiLCJ0b2tlbk5hbWUiOiJyZWZyZXNoX3Rva2VuIiwidG9rZW5fdHlwZSI6IkJlYXJlciIsImF1dGhHcmFudElkIjoiWTNPblBwSjJKWWhBdHFpMllGc1RoR2FHSzBrIiwiYXVkIjoiYjRhZTA1ZDJmYjg0OGQ0YTNmNDcyN2U4NTRkMmJjZGIiLCJuYmYiOjE1MzgxNDQ1MDIsImdyYW50X3R5cGUiOiJwYXNzd29yZCIsInNjb3BlIjpbImFkZHJlc3MiLCJvcGVuaWQiLCJhcGkuZm9yZ2VjbG91ZC5jb206dXNlci53cml0ZSIsInByb2ZpbGUiLCJhcGkuZm9yZ2VjbGs91ZC5jb206dXNlci5yZWFkIiwicGhvbmUiXSwiYXV0aF90aW1lIjoxNTM4MTQ0NTAyLCJyZWFsbSI6Ii8iLCJleHAiOjE1Mzg3NDkzMDIsImlhdCI6MTUzODE0NDUwMiwiZXhwaXJlc19pbiI6NjA0ODAwLCJqdGkiOiJmVzc1MHZsem9lcVc0T1Nkb1ZRcTdUVkwxaGsifQ.u-V5wLpPkkvPnYo1GqWGfMGWBL-SBfzVAiXt5ENmCok",
        "scope": "openid profile api.forgecloud.com:user.read",
        "id_token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJhdF9oYXNoIjoiNExhTm42ZDJwd0RpWXVUZVlIU2d2USIsInN1YiI6ImJqZW5zZW4iLCJmb3JtYXR0ZWQiOnsiYWRkcmVzcyI6IjIwMSBNaXNzaW9uIFN0cmVldCJ9LCJhdWRpdFRyYWNraW5nSWQiOiJmZDI0N2YxNS05ODRkLTQ4MzgtOWIzMi01Njg2Mjg5MDZlOWUtMTExNTQyNyIsImlzcyI6Imh0dHBzOi8vb3BlbmFtLWthdGU1MDJlLmZvcmdlYmxvY2tzLmNvbS9vcGVuYW0vb2F1dGgyIiwidG9rZW5OYW1lIjosiaWRfdG9rZW4iLCJnaXZlbl9uYW1lIjoiQmFicyIsImF1ZCI6ImI0YWUwNWQyZmI4NDhkNGEzZjQ3MjdlODU0ZDJiY2RiIiwiYXpwIjoiYjRhZTA1ZDJmYjg0OGQ0YTNmNDcyN2U4NTRkMmJjZGIiLCJhdXRoX3RpbWUiOjE1MzgxNDQ1MDIsIm5hbWUiOiJCYWJzIEplbnNlbiIsInBob25lX251bWJlciI6IjQxNS01NTUtNTU1NSIsInJlYWxtIjoiLyIsImV4cCI6MTUzODsE0ODEwMiwidG9rZW5UeXBlIjoiSldUVG9rZW4iLCJmYW1pbHlfbmFtZSI6IkplbnNlbiIsImlhdCI6MTUzODE0NDUwMiwiZm9yZ2Vyb2NrIjp7InNpZyI6Imc0XkZmJi9jaDktfStbNFF6V3UjekolIyomNUQqelV1Nk9bOC1VWXYifX0.WY1UHRfs0J98Kno2QbxgDq57n6dscUPWeLH5lHSLLUA",
        "token_type": "Bearer",
        "expires_in": 3599
    }
```
{: .wrap-text}


