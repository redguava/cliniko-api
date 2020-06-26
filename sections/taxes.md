Taxes
============
* [Get Taxes](#get-taxes "This will return all taxes.")
* [Get Tax](#get-tax "This will return a specified tax.")
* [Create Tax](#create-tax "This will create a tax.")
* [Update Tax](#update-tax "This will update a tax.")
* [Delete Tax](#delete-tax "This will delete a tax.")

Get Taxes
----------------

**Resources**
* ```GET /taxes``` get all taxes

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/taxes \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "taxes": [
    {
      "id": 1,
      "name": "GST",
      "amount": "10.0",
      "created_at": "2014-01-29T09:54:54Z",
      "updated_at": "2014-01-29T09:54:54Z",
      "links": {"self": "https://api.au1.cliniko.com/v1/taxes/1"}
    }
  ],
  "total_entries": 1,
  "links": {"self": "https://api.au1.cliniko.com/v1/taxes?page=1"}
}
```

Get Tax
------------

**Resources**
* ```GET /taxes/:id``` get a specified tax

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/taxes/1 \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "id": 1,
  "name": "GST",
  "amount": "10.0",
  "created_at": "2014-01-29T09:54:54Z",
  "updated_at": "2014-01-29T09:54:54Z",
  "links": {"self": "https://api.au1.cliniko.com/v1/taxes/1"}
}
```

Create Tax
----------------
**Resources**
* ```POST /taxes``` create a tax

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/taxes \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'Content-Type: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -d '{ "name": "VAT", "amount": 23 }' \
  -X POST
```
**Example Response**
```
Headers { Location: https://api.au1.cliniko.com/taxes/2 }
```
```json
{
  "id": 2,
  "name": "VAT",
  "amount": "23.0",
  "created_at": "2014-03-03T09:54:54Z",
  "updated_at": "2014-03-03T09:54:54Z",
  "links": {"self": "https://api.au1.cliniko.com/v1/taxes/2"}
}
```

Update Tax
----------------
**Resources**
* ```PUT /taxes/:id``` update a tax

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/taxes/2 \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'Content-Type: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -d '{ "amount": 22 }' \
  -X PUT
```
**Example Response**
```json
{
  "id": 2,
  "name": "VAT",
  "amount": "22.0",
  "created_at": "2014-03-03T09:54:54Z",
  "updated_at": "2014-03-03T09:55:24Z",
  "links": {"self": "https://api.au1.cliniko.com/v1/taxes/2"}
}
```

Delete Tax
----------------
**Resources**
* ```DELETE /taxes/:id``` delete a tax

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/taxes/2 \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -X DELETE
```
**Example Response**
A status code of `204 no content` will be returned if successful

Filtering Taxes
----------------

You can filter taxes by:
* ```created_at``` DateTime
* ```id``` Integer
* ```updated_at``` DateTime

See [Filtering Results](https://github.com/redguava/cliniko-api#filtering-results) for details on how to apply filters.
