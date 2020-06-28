Billable Items
============
* [Get Billable Items](#get-billable-items "This will return all billable items.")
* [Get Billable Item](#get-billable-item "This will return a specified billable item.")
* [Create Billable Item](#create-billable-item "This will create a billable item.")
* [Update Billable Item](#update-billable-item "This will update a billable item.")
* [Delete Billable Item](#delete-billable-item "This will delete a billable item.")


Get Billable Items
----------------

**Resources**
* ```GET /billable_items``` get all billable items

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/billable_items \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "billable_items": [
    {
      "id": 1,
      "item_code": "0001",
      "item_type": "Service",
      "name": "Initial Consultation",
      "price": "10.0",
      "tax": {
        "links": {"self": "https://api.au1.cliniko.com/v1/taxes/1"}
      },
      "created_at": "2014-03-04T19:11:30Z",
      "updated_at": "2014-03-04T19:11:30Z",
      "links": {"self": "https://api.au1.cliniko.com/v1/billable_items/1"}
    }
  ],
  "total_entries": 1,
  "links": {"self": "https://api.au1.cliniko.com/v1/billable_items?page=1"}
}
```

Get Billable Item
------------

**Resources**
* ```GET /billable_items/:id``` get a specified billable item

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/billable_items/1 \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "id": 1,
  "item_code": "0001",
  "item_type": "Service",
  "name": "Initial Consultation",
  "price": "10.0",
  "tax": {
    "links": {"self": "https://api.au1.cliniko.com/v1/taxes/1"}
  },
  "created_at": "2014-03-04T19:11:30Z",
  "updated_at": "2014-03-04T19:11:30Z",
  "links": {"self": "https://api.au1.cliniko.com/v1/billable_items/1"}
}
```

Create Billable Item
----------------
**Resources**
* ```POST /billable_items``` create a billable item

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/billable_items \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -d '{ "item_code": "0002", "item_type": "Service", "name": "Billable Item 2", "price": 11, "tax_id": 1 }' \
  -X POST
```
**Example Response**
```
Headers { Location: http://api.cliniko.com/billable items/2 }
```
```json
{
  "id": 1,
  "item_code": "0002",
  "item_type": "Service",
  "name": "Billable Item 2",
  "price": "11.0",
  "tax": {
    "links": {"self": "https://api.au1.cliniko.com/v1/taxes/1"}
  },
  "created_at": "2014-03-04T19:11:30Z",
  "updated_at": "2014-03-04T19:11:30Z",
  "links": {"self": "https://api.au1.cliniko.com/v1/billable_items/1"}
}
```

Update Billable Item
----------------
**Resources**
* ```PUT /billable_items/:id``` update a billable item

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/billable_items/1 \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -d '{ "name": "Billable Item 1" }' \
  -X PUT
```
**Example Response**
```json
{
  "id": 1,
  "item_code": "0001",
  "item_type": "Service",
  "name": "Billable Item 1",
  "price": "11.0",
  "tax": {
    "links": {"self": "https://api.au1.cliniko.com/v1/taxes/1"}
  },
  "created_at": "2014-03-04T19:11:30Z",
  "updated_at": "2014-03-04T19:11:30Z",
  "links": {"self": "https://api.au1.cliniko.com/v1/billable_items/1"}
}
```

Delete Billable Item
----------------
**Resources**
* ```DELETE /billable_items/:id``` delete a billable item

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/billable_items/1 \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -X DELETE
```
**Example Response**
A status code of `204 no content` will be returned if successful

Filtering Billable Items
----------------

You can filter billable items by:
* ```created_at``` DateTime
* ```id``` Integer
* ```tax_id``` Integer
* ```updated_at``` DateTime

See [Filtering Results](https://github.com/redguava/cliniko-api#filtering-results) for details on how to apply filters.
