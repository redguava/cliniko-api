Practitioner Reference Numbers
============
* [Get Practitioner Reference Numbers](#get-practitioner-reference-numbers "This will return all practitioner reference numbers.")
* [Get Practitioner Reference Number](#get-practitioner-reference-number "This will return a specified practitioner reference number.")

Get Practitioner Reference Numbers
----------------

**Resources**
* ```GET /practitioner_reference_numbers``` get all practitioner reference numbers.

**Example Request**
```shell
curl https://api.cliniko.com/v1/practitioner_reference_numbers \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "practitioner_reference_numbers": [
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
      "links": {"self": "https://api.cliniko.com/v1/practitioner_reference_numbers/1"}
    }
  ],
  "total_entries": 1,
  "links": {"self": "https://api.cliniko.com/v1/practitioner_reference_numbers?page=1"}
}
```

Get Practitioner Reference Number
------------

**Resources**
* ```GET /practitioner_reference_numbers/:id``` get a specified practitioner reference number.

**Example Request**
```shell
curl https://api.cliniko.com/v1/practitioner_reference_numbers/1 \
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
  "links": {"self": "https://api.cliniko.com/v1/practitioner_reference_numbers/1"}
}
```
