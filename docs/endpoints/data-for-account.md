---
Data for Account
---

This endpoint represents a single [data](../resources/data.md) associated with a given [account](../resources/account.md).

## Request

```
GET /accounts/{account}/data/{key}
```

### Arguments

| name     | notes                          | description                                                      | example                                                   |
| ------   | -------                        | -----------                                                      | -------                                                   |
| `key`| required, string               | Key name | `user-id`|


## Response

This endpoint responds with a value of the data field for the given account. See [data resource](../resources/data.md) for reference.

### Example Request
::: tabs language

- curl
  ```curl
  curl "https://horizon-testnet.stellar.org/accounts/GA2HGBJIJKI6O4XEM7CZWY5PS6GKSXL6D34ERAJYQSPYA6X6AI7HYW36/data/user-id"
  ```
- JavaScript
  ```js
  var StellarSdk = require('stellar-sdk');
  var server = new StellarSdk.Server('https://horizon-testnet.stellar.org');

  server.accounts()
    .accountId("GAKLBGHNHFQ3BMUYG5KU4BEWO6EYQHZHAXEWC33W34PH2RBHZDSQBD75")
    .call()
    .then(function (account) {
      return account.data({key: 'user-id'})
    })
    .then(function(dataValue) {
      console.log(dataValue)
    })
    .catch(function (err) {
      console.log(err)
    })
  ```
- Try it out
  https://www.stellar.org/laboratory/#explorer?resource=data&endpoint=for_account

:::
### Example Response

```json
{
  "value": "MTAw"
}
```