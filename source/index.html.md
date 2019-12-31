---
title: HYBRID-REST

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - javascript

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:
  - os
  - acl
  - acp
  - ou
  - users
  - admins
  - roles
  - deadlines
  - deadline_category
  - data_security
  - dispose_type
  - public_status
  - security_class
  - status_code

search: true
---

# Introduction

Welcome to the Kittn API! You can use our API to access Kittn API endpoints, which can get information on various cats, kittens, and breeds in our database.

We have language bindings in Shell, Ruby, Python, and JavaScript! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

This example API documentation page was created with [Slate](https://github.com/lord/slate). Feel free to edit it and use it as a base for your own API's documentation.

# Authentification

> To authorize, use this code:

```shell
curl --request POST \
  --url http://127.0.0.1:9002/api/v1/ubit/auth/ \
  --header 'Authorization: Basic {BASE64}}' \
  --data '{"access_token":{MASTER_KEY}}'
```

```javascript
````
> You must replace `{BASE64}` with your username and password in base64 encoded.
>
> Your muste replace `{MASTER_KEY}` with your Master Key.

When making any API request to HYBRID-REST, you will need to include your token that was generated using the master key in a header that looks like the following:

`Authorization: Basic eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MSwiaWF0IjoxNTc3NzAzOTU5fQ.HEI6m7Twef5CKa-UMjhFoBSdIpgfMa4LKWVX-0vWf-I"`

<aside class="notice">
You must replace <code>eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MSwiaWF0IjoxNTc3NzAzOTU5fQ.HEI6m7Twef5CKa-UMjhFoBSdIpgfMa4LKWVX-0vWf-I"</code> with your personal token.
</aside>
