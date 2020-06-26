Unavailable Blocks
============
* [Get Unavailable Blocks](#get-unavailable-blocks "This will return all unavailable blocks.")
* [Get Deleted Unavailable Blocks](#get-deleted-unavailable-blocks "This will return all deleted unavailable blocks")
* [Get Unavailable Block](#get-unavailable-block "This will return a specified unavailable block.")
* [Get Conflicts](#get-conflicts "This will return if the specified unavailable block has conflicts.")
* [Create Unavailable Block](#create-unavailable-block "This will create an unavailable block.")
* [Update Unavailable Block](#update-unavailable-block "This will update an unavailable block.")
* [Delete Unavailable Block](#delete-unavailable-block "This will delete an unavailable block.")

Get Unavailable Blocks
----------------

**Resources**
* ```GET /unavailable_blocks``` get all unavailable blocks


**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/unavailable_blocks \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "unavailable_blocks": [
    {
      "id": 1,
      "created_at": "2016-07-11T18:28:11Z",
      "updated_at": "2016-07-15T00:04:35Z",
      "conflicts": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/unavailable_blocks/1/conflicts"
        }
      },
      "notes": null,
      "repeat_rule": {},
      "repeats": null,
      "deleted_at": null,
      "starts_at": "2016-07-13T06:30:00Z",
      "ends_at": "2016-07-13T07:00:00Z",
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
        "self": "https://api.au1.cliniko.com/v1/unavailable_blocks/1"
      }
    }
  ],
  "total_entries": 20,
  "links": {
    "self": "https://api.au1.cliniko.com/v1/unavailable_blocks?page=1",
  }
}
```

Get Deleted Unavailable Blocks
----------------

**Resources**
* ```GET /unavailable_blocks/deleted``` get all deleted unavailable blocks

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/unavailable_blocks/deleted \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "unavailable_blocks": [
    {
      "id": 1,
      "created_at": "2016-07-11T18:28:11Z",
      "updated_at": "2016-07-15T00:04:35Z",
      "conflicts": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/unavailable_blocks/1/conflicts"
        }
      },
      "notes": null,
      "repeat_rule": {},
      "repeats": null,
      "deleted_at": "2016-07-15T00:04:35Z",
      "starts_at": "2016-07-13T06:30:00Z",
      "ends_at": "2016-07-13T07:00:00Z",
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
        "self": "https://api.au1.cliniko.com/v1/unavailable_blocks/1"
      }
    }
  ],
  "total_entries": 20,
  "links": {
    "self": "https://api.au1.cliniko.com/v1/unavailable_blocks?page=1",
  }
}
```

Get Unavailable Block
------------

**Resources**
* ```GET /unavailable_blocks/:id``` get a specified unavailable block

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/unavailable_blocks/1 \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "id": 1,
  "created_at": "2016-07-11T18:28:11Z",
  "updated_at": "2016-07-15T00:04:35Z",
  "conflicts": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/unavailable_blocks/1/conflicts"
    }
  },
  "notes": null,
  "repeat_rule": {},
  "repeats": null,
  "deleted_at": null,
  "starts_at": "2016-07-13T06:30:00Z",
  "ends_at": "2016-07-13T07:00:00Z",
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
    "self": "https://api.au1.cliniko.com/v1/unavailable_blocks/1"
  }
}
```

Get Conflicts
------------

**Resources**
* ```GET /unavailable_blocks/:id/conflicts``` get a specified unavailable block's conflicts

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/unavailable_blocks/1/conflicts \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "conflicts" : {
    "exist": true
  }
}
```

Create Unavailable Block
----------------
**Resources**
* ```POST /unavailable_blocks``` create an unavailable block

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/unavailable_blocks \
  -u API_KEY: \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -d '{ "starts_at": "2016-07-13T03:45:00Z", "practitioner_id": "1", "business_id": "1" }' \
  -X POST
```
**Example Response**
```
Headers { Location: https://api.au1.cliniko.com/unavailable_blocks/1 }
```
```json
{
  "id": 1,
  "created_at": "2016-07-11T18:28:11Z",
  "updated_at": "2016-07-15T00:04:35Z",
  "conflicts": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/unavailable_blocks/1/conflicts"
    }
  },
  "notes": null,
  "repeat_rule": {},
  "repeats": null,
  "deleted_at": null,
  "starts_at": "2016-07-13T06:30:00Z",
  "ends_at": "2016-07-13T07:00:00Z",
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
    "self": "https://api.au1.cliniko.com/v1/unavailable_blocks/1"
  }
}
```

Update Unavailable Block
----------------
**Resources**
* ```PUT /unavailable_blocks/:id``` update an unavailable block

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/unavailable_blocks/1 \
  -u API_KEY: \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -d '{ "ends_at": "2016-07-13T07:30:00Z" }' \
  -X PUT
```
**Example Response**
```json
{
  "id": 1,
  "created_at": "2016-07-11T18:28:11Z",
  "updated_at": "2016-07-15T00:04:35Z",
  "conflicts": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/unavailable_blocks/1/conflicts"
    }
  },
  "notes": null,
  "repeat_rule": {},
  "repeats": null,
  "deleted_at": null,
  "starts_at": "2016-07-13T06:30:00Z",
  "ends_at": "2016-07-13T07:30:00Z",
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
    "self": "https://api.au1.cliniko.com/v1/unavailable_blocks/1"
  }
}
```

Delete Unavailable Block
----------------
**Resources**
* ```DELETE /unavailable_blocks/:id``` delete an unavailable block

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/unavailable_blocks/1 \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -X DELETE
```
**Example Response**
A status code of `204 no content` will be returned if successful

Filtering Unavailable Blocks
----------------

For any route that returns a set of unavailable blocks, you can filter them by:
* ```archived_at``` DateTime
* ```business_id``` Integer
* ```created_at``` DateTime
* ```ends_at``` DateTime
* ```id``` Integer
* ```practitioner_id``` Integer
* ```repeated_from_id``` Integer
* ```starts_at``` DateTime
* ```updated_at``` DateTime

See [Filtering Results](https://github.com/redguava/cliniko-api#filtering-results) for details on how to apply filters.
