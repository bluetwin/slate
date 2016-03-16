## Authentication

This API support Oauth2 authentication:

### OAuth2

```shell
  curl https://api.avvo.com/api/4/lawyers.json \
      -H "Authorization: Bearer abd90df5f27a7b170cd775abf89d632b350b7c1c9d53e08b340cd9832ce52c2c"

```
```ruby
  require "oauth2"
  callback_url = "https://www.yoursite/oauth2/callback"
  client = OAuth2::Client.new(<client_id>,   <client_secret>, site: "https://api.avvo.com", authorize_url: ”/api/4/oauth2/authorize”, token_url: “/api/4/oauth2/authorize”)
  client.auth_code.authorize_url(redirect_uri: callback_url)
  token = client.auth_code.get_token("authorization_code_value", redirect_uri: callback_url,
                                      headers: {"Authorization" => "Basic some_password"})
  response = token.get('/api/4/lawyers.json', params: { id: 123 })
  response.class.name
  # => OAuth2::Response

```
OAuth2 is recommended when you’re creating an application for others on top of Avvo's platform. This authentication provides a secure and easy to use authentication flow for users.

OAuth2 requests must be authenticated with a valid access token passed as bearer token. To use the bearer token, construct a normal HTTPS request and include an Authorization header with the value of Bearer. Signing is not required.

Read more about [OAuth2 authentication](http://oauth.net/2/).

### Obtaining an Access Token

```ruby
   { grant_type: authorization_code,
      client_id: <client_id>,
      client_secret: <client_secret>
      username: <avvo.com user email>
      password: <avvo.com user password>
      redirect_uri: <redirect_url used for registration>
      code: <auth_code>
    }
```

1. Get permission to access Avvo's API.
2. Follow instructions sent to you about setting up an oauth2 application.
3. Post a call to `https://api.avvo.com/api/4/oauth2/authorize` with your id and secret to obtain an auth code. See code to the right.
4. This generates a link to sign in and an auth_code is sent along with the redirect.
5. Capture the auth_code sent in the redirect.
6. Post to `https://api.stag.avvo.com/api/2/oauth2/authorize` with the fields to the right
7. The response will be the access_token.
8. Add this to the Bearer Authorization header of each request.




