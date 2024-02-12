# apigee-federation

https://console.cloud.google.com/apigee/overview?hl=en&project=project-federate-apigee&supportedpurview=project

## Keyless

```sh
curl https://34.96.107.193.nip.io/hello-world           
Hello, Guest!
```

## API key

```sh
curl https://34.96.107.193.nip.io/bs-quote-generato-proxy
{"phrase":"Credibly Maximize Premier E-business"}
```

Once API key is enforced, it can be passed as a query parameter like so: 

```sh
curl 'https://34.96.107.193.nip.io/bs-quote-generato-proxy?apikey=u8weMyBxks01lCOKnDNx2n4i9kYA4784mTeT3nawWKIujzSX'
{"phrase":"Continually Formulate Collaborative Channels"}
```

## OAuth

OAuth credentials

key: `MW6Lb4xkyxmuQneKaQMxqRVnPmKBaCGXgA9x8ZiyY8y7F8W2`

secret: `Dkp9ilQRkPFm7HWZOIuG3wdMAsPqY0umLRbhdR7xTe6Ydvkfs8afxuO0Jkzs8jHs`

```sh
curl https://34.96.107.193.nip.io/hellooauth2            
{"fault":{"faultstring":"Invalid access token","detail":{"errorcode":"oauth.v2.InvalidAccessToken"}}
```
Get an OAuth token:

```sh
curl -X POST -H "Content-Type: application/x-www-form-urlencoded" \
"https://34.96.107.193.nip.io/oauth/client_credential/accesstoken?grant_type=client_credentials" \
-d "client_id=MW6Lb4xkyxmuQneKaQMxqRVnPmKBaCGXgA9x8ZiyY8y7F8W2&client_secret=Dkp9ilQRkPFm7HWZOIuG3wdMAsPqY0umLRbhdR7xTe6Ydvkfs8afxuO0Jkzs8jHs"
{
  "refresh_token_expires_in": "0",
  "api_product_list": "[OAuth_API_product]",
  "api_product_list_json": [
    "OAuth_API_product"
  ],
  "organization_name": "project-federate-apigee",
  "developer.email": "jonathan.michaux@graviteesource.com",
  "token_type": "BearerToken",
  "issued_at": "1707406838904",
  "client_id": "MW6Lb4xkyxmuQneKaQMxqRVnPmKBaCGXgA9x8ZiyY8y7F8W2",
  "access_token": "dh8ZmLYjnZcDKzA7ctQa4F2v6kJW",
  "application_name": "36e2ae6a-f5f7-4b33-be34-9d76e33b92ea",
  "scope": "",
  "expires_in": "3599",
  "refresh_count": "0",
  "status": "approved"
}
```

Call the API with the access token: 

```sh
curl https://34.96.107.193.nip.io/hellooauth2 -H "Authorization: Bearer dh8ZmLYjnZcDKzA7ctQa4F2v6kJW"
{"ip":"88.170.205.78, 34.96.107.193,10.132.15.195, 34.76.14.116, 35.227.194.212"}
```