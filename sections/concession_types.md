Concession Types
============
> The different types of appointments the business offers.

* [Get Concession Types](#get-concession-types "This will return all concession types.")
* [Get Concession Type](#get-concession-type "This will return a specified concession type.")

Get Concession Types
----------------

**Resources**
* ```GET /concession_types``` get all concession types

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/concession_types \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "concession_types": [
    {
      "id": 220,
      "name": "Students",
      "created_at": "2014-07-15T01:03:03Z",
      "updated_at": "2014-07-15T01:03:03Z",
      "links": {
        "self": "https://api.au1.cliniko.com/v1/concession_types/220"
      }
    }
  ],
  "total_entries": 1,
  "links": {
    "self": "https://api.au1.cliniko.com/v1/concession_types?page=1"
  }
}
```

Get Concession Type
------------

**Resources**
* ```GET /concession_types/:id``` get a specified concession type

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/concession_types/1 \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "id": 220,
  "name": "Students",
  "created_at": "2014-07-15T01:03:03Z",
  "updated_at": "2014-07-15T01:03:03Z",
  "links": {
    "self": "https://api.au1.cliniko.com/v1/concession_types/220"
  }
}
```

Filtering Concession Types
----------------

For any route that returns a set of concession types, you can filter them by:
* ```created_at``` DateTime
* ```id``` Integer
* ```updated_at``` DateTime

See [Filtering Results](https://github.com/redguava/cliniko-api#filtering-results) for details on how to apply filters.
