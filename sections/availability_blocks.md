Availability Blocks
============
* [Get Availability Blocks](#get-availability-blocks "This will return all availability blocks.")
* [Get Availability Block](#get-availability-block "This will return a specified availability block.")
* [Create Availability Block](#create-availability-block "This will create an availability block.")

Get Availability Blocks
----------------

**Resources**
* ```GET /availability_blocks``` get all availability blocks

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/availability_blocks \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "availability_blocks": [
    {
      "id": 1,
      "created_at": "2016-08-19T21:19:37Z",
      "updated_at": "2016-08-19T21:19:37Z",
      "repeat_rule": {},
      "starts_at": "2016-08-14T21:15:00Z",
      "ends_at": "2016-08-14T21:45:00Z",
      "business": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/businesses/3"
        }
      },
      "practitioner": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/practitioners/1"
        }
      },
      "links": {
        "self": "https://api.au1.cliniko.com/v1/availability_blocks/1"
      }
    }
  ],
  "total_entries": 1,
  "links": {
    "self": "https://api.au1.cliniko.com/v1/availability_blocks?page=1"
  }
}
```

Get Availability Block
------------

**Resources**
* ```GET /availability_blocks/:id``` get a specified availability block

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/availability_blocks/1 \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "id": 1,
  "created_at": "2016-08-19T21:19:37Z",
  "updated_at": "2016-08-19T21:19:37Z",
  "repeat_rule": {},
  "starts_at": "2016-08-14T21:15:00Z",
  "ends_at": "2016-08-14T21:45:00Z",
  "business": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/businesses/3"
    }
  },
  "practitioner": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/practitioners/1"
    }
  },
  "links": {
    "self": "https://api.au1.cliniko.com/v1/availability_blocks/1"
  }
}
```

Create Availability Block
----------------
**Resources**
* ```POST /availability_blocks``` create an availability block

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/availability_blocks \
  -u API_KEY: \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -d '{ "starts_at": "2015-01-21T04:00:00Z", "ends_at": "2015-01-21T04:30:00Z", "practitioner_id": "1", "business_id": "1" }' \
  -X POST
```
**Example Response**
```
Headers { Location: https://api.au1.cliniko.com/availability_blocks/10 }
```
```json
{
  "id": 10,
  "created_at": "2016-08-19T21:19:37Z",
  "updated_at": "2016-08-19T21:19:37Z",
  "repeat_rule": {},
  "starts_at": "2015-01-21T04:00:00Z",
  "ends_at": "2015-01-21T04:30:00Z",
  "business": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/businesses/1"
    }
  },
  "practitioner": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/practitioners/1"
    }
  },
  "links": {
    "self": "https://api.au1.cliniko.com/v1/availability_blocks/10"
  }
}
```

Filtering Availability Blocks
----------------

For any route that returns a set of appointments, you can filter them by:
* ```business_id``` Integer
* ```created_at``` DateTime
* ```id``` Integer
* ```practitioner_id``` Integer
* ```starts_at``` DateTime
* ```updated_at``` DateTime

See [Filtering Results](https://github.com/redguava/cliniko-api#filtering-results) for details on how to apply filters.
