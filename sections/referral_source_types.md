Referral Source Types
============
> Types of referrals for patients.

* [Get Referral Source Types](#get-referral-source-types "This will return all referral source types.")
* [Get Referral Source Type](#get-referral-source-type "This will return a specified referral source type.")

Get Referral Source Types
----------------

**Resources**
* ```GET /referral_source_types``` get all referral source types

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/referral_source_types \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "referral_source_types": [
    {
      "id": 1,
      "created_at": "2016-06-28T21:33:23Z",
      "updated_at": "2016-06-28T21:33:23Z",
      "name": "Client",
      "referrers": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/patients"
        }
      },
      "referrer_type": "Patient",
      "subcategories": null,
      "links": { "self": "https://api.au1.cliniko.com/v1/referral_source_types/1" }
    },
    {
      "id": 2,
      "created_at": "2016-06-28T21:33:23Z",
      "updated_at": "2016-06-28T21:33:23Z",
      "name": "Contact",
      "referrers": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/contacts"
        }
      },
      "referrer_type": "Contact",
      "subcategories": null,
      "links": { "self": "https://api.au1.cliniko.com/v1/referral_source_types/2" }
    },
    {
      "id": 3,
      "created_at": "2016-06-28T21:33:23Z",
      "updated_at": "2016-06-28T21:33:23Z",
      "name": "Other",
      "referrers": null,
      "referrer_type": null,
      "subcategories": null,
      "links": { "self": "https://api.au1.cliniko.com/v1/referral_source_types/3" }
    },
    {
      "id": 10,
      "created_at": "2016-10-26T05:20:52Z",
      "updated_at": "2016-10-27T00:11:24Z",
      "name": "internets",
      "referrers": null,
      "referrer_type": null,
      "subcategories": [
        "the google",
        "myspace",
        "friendster",
        "ask jeeves"
      ],
      "links": { "self": "https://api.au1.cliniko.com/v1/referral_source_types/10" }
    }
  ],
  "total_entries": 4,
  "links": { "self": "https://api.au1.cliniko.com/v1/referral_source_types?page=1" }
}
```

Get Referral Source Type
------------

**Resources**
* ```GET /referral_source_types/:id``` get a specified referral source type

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/referral_source_types/10 \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "id": 10,
  "created_at": "2016-10-26T05:20:52Z",
  "updated_at": "2016-10-27T00:11:24Z",
  "name": "internets",
  "referrers": null,
  "referrer_type": null,
  "subcategories": [
    "the google",
    "myspace",
    "friendster",
    "ask jeeves"
  ],
  "links": { "self": "https://api.au1.cliniko.com/v1/referral_source_types/10" }
}
```

Filtering Referral Source Types
----------------

For any route that returns a set of referral source types, you can filter them by:
* ```created_at``` DateTime
* ```id``` Integer
* ```updated_at``` DateTime

See [Filtering Results](https://github.com/redguava/cliniko-api#filtering-results) for details on how to apply filters.
