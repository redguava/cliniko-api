Practitioner Reference Numbers
============
* [Get Practitioner Reference Numbers](#get-practitioner-reference-numbers "This will return all practitioner reference numbers.")
* [Get Practitioner Reference Number](#get-practitioner-reference-number "This will return a specified practitioner reference number.")
* [Create Practitioner Reference Number](#create-practitioner-reference-number "This will create a practitioner reference number.")
* [Update Practitioner Reference Number](#update-practitioner-reference-number "This will update a practitioner reference number.")
* [Delete Practitioner Reference Number](#delete-practitioner-reference-number "This will delete a practitioner reference number.")

Get Practitioner Reference Numbers
----------------

**Resources**
* ```GET practitioners/:practitioner_id/practitioner_reference_numbers``` get all practitioner reference numbers for a specified practitioner.

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/practitioners/1/practitioner_reference_numbers \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "practitioner_reference_numbers": [
    {
      "id": 1,
      "name": "Provider #",
      "reference_number": "123123AB",
      "created_at": "2013-03-26T14:00:00Z",
      "updated_at": "2013-03-26T14:00:00Z",
      "business": {
        "links": {"self": "http://api.cliniko.dev:3000/v1/businesses/1"}
      },
      "practitioner": {
        "links": {"self": "http://api.cliniko.dev:3000/v1/practitioners/1"}
      },
      "links": {"self": "https://api.au1.cliniko.com/v1/practitioner_reference_numbers/1"}
    }
  ],
  "total_entries": 1,
  "links": {"self": "https://api.au1.cliniko.com/v1/practitioners/1/practitioner_reference_numbers?page=1"}
}
```

Get Practitioner Reference Number
------------

**Resources**
* ```GET /practitioner_reference_numbers/:id``` get a specified practitioner reference number.

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/practitioner_reference_numbers/1 \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "created_at": "2013-03-26T14:00:00Z",
  "id": 1,
  "name": "Provider #",
  "reference_number": "123123AB",
  "updated_at": "2013-03-26T14:00:00Z",
  "business": {
    "links": {"self": "http://api.cliniko.dev:3000/v1/businesses/1"}
  },
  "practitioner": {
    "links": {"self": "http://api.cliniko.dev:3000/v1/practitioners/1"}
  },
  "links": {"self": "https://api.au1.cliniko.com/v1/practitioner_reference_numbers/1"}
}
```

Create Practitioner Reference Number
----------------

**Resources**
* ```POST /practitioner_reference_numbers``` create a practitioner reference number

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/practitioner_reference_numbers \
  -u API_KEY: \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -d '{ "name": "Provider #", "reference_number": "123123CD", "practitioner_id": 1, "business_id": 1 }' \
  -X POST
```
**Example Response**
```
Headers { Location: http://api.cliniko.com/practitioner_reference_numbers/2 }
```
```json
{
  "created_at": "2013-03-26T14:00:00Z",
  "id": 2,
  "name": "Provider #",
  "reference_number": "123123CD",
  "updated_at": "2013-03-26T14:00:00Z",
  "business": {
    "links": {"self": "http://api.cliniko.dev:3000/v1/businesses/1"}
  },
  "practitioner": {
    "links": {"self": "http://api.cliniko.dev:3000/v1/practitioners/1"}
  },
  "links": {"self": "https://api.au1.cliniko.com/v1/practitioner_reference_numbers/2"}
}
```

Update Practitioner Reference Number
----------------

**Resources**
* ```PUT /practitioner_reference_numbers/:id``` update a practitioner reference number

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/practitioner_reference_numbers/2 \
  -u API_KEY: \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -d '{ "name": "update name" }' \
  -X PUT
```
**Example Response**
```json
{
  "created_at": "2013-03-26T14:00:00Z",
  "id": 2,
  "name": "update name",
  "reference_number": "123123CD",
  "updated_at": "2013-03-26T14:00:00Z",
  "business": {
    "links": {"self": "http://api.cliniko.dev:3000/v1/businesses/1"}
  },
  "practitioner": {
    "links": {"self": "http://api.cliniko.dev:3000/v1/practitioners/1"}
  },
  "links": {"self": "https://api.au1.cliniko.com/v1/practitioner_reference_numbers/2"}
}
```

Delete Practitioner Reference Number
----------------

**Resources**
* ```DELETE /practitioner_reference_numbers/:id``` delete specified practitioner reference number

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/practitioner_reference_numbers/1 \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -X DELETE
```
**Example Response**
A status code of `204 no content` will be returned if successful

Filtering Practitioner Reference Numbers
----------------

You can filter practitioner reference numbers by:
* ```business_id``` Integer
* ```created_at``` DateTime
* ```id``` Integer
* ```practitioner_id``` Integer
* ```updated_at``` DateTime

See [Filtering Results](https://github.com/redguava/cliniko-api#filtering-results) for details on how to apply filters.
