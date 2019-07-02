# User

## Authenticate

```shell
curl --data-binary '{"id":"1", "method":"user.Authenticate", "jsonrpc":"2.0"}'
  -H 'Authorization: Bearer 5dc78bab-4988-4a15-96a2-9eb084fba6f6 client.genrated.jwt.token'
  -H 'content-type:application/json;'
```

> The above command returns JSON structured like this:

```json
{
	"jsonrpc": "2.0",
	"result": {
		"jwt_access_token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJVc2VySUQiOiJiYmJuN2x2YXRhYWcwMjZpdjJtZyIsIk9yZ0lEIjoiZmlsdGVyZWQiLCJHcm91cElEIjoiZmlsdGVyZWQtZ2xvYmFsZmlsdGVyIn0.e7A_2EQLwS3v7dOVTq0I5afjnmSWYfqmBngFOlRsaJI",
		"refresh_token": "wZk2AnHuCuMplJ2P52a3hK0nZ2CfnQEWH1jLR7Nk"
	},
	"id": "json"
}
```

Authenticates the user and generates an access token and a refresh token.

<aside class="notice">
The access token has a validity of 15 minutes; the refresh token has a validity of 7 days.
</aside>

### HTTP Request

`POST https://api.test.filtered.com/v2/jsonrpc/auth`

<aside class="success">
Returns — Access Token Model — structure containing the JWT access token and refresh token
</aside>

### Errors

Error Code | Meaning
---------- | -------
-32603 | Internal Server Error
-32003 | Mandatory JWT Claim missing
-32600 | The JSON sent is not a valid Request object
