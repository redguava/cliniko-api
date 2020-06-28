Daily Availabilities
============
> The regularly scheduled availabilities of a practitioner at a business. Day of week is given in ISO format, starting with 1 for Monday and ending with 7 for Sunday.

* [Get Daily Availabilities](#get-daily-availabilities "This will return a list of daily availabilities.")
* [Get Daily Availability](#get-daily-availability "This will return a specified daily availability.")

Get Daily Availabilities
----------------

**Resources**
* ```GET /daily_availabilities``` get all daily availabilities
* ```GET /businesses/:id/daily_availabilities``` get all daily availabilities of the specified business
* ```GET /practitioners/:id/daily_availabilities``` get all daily availabilities of the specified practitioner

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/businesses/3/daily_availabilities \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "daily_availabilities": [
  {
    "id": 15,
    "created_at": "2016-06-28T21:33:24Z",
    "updated_at": "2016-09-23T17:19:31Z",
    "availabilities": [
      {
        "starts_at": "09:00",
        "ends_at": "13:00"
      },
      {
        "starts_at": "14:00",
        "ends_at": "17:00"
      }
    ],
    "day_of_week": 7,
    "business": {
      "links": {
        "self": "http://api.cliniko.com/v1/businesses/3"
      }
    },
    "practitioner": {
      "links": {
        "self": "http://api.cliniko.com/v1/practitioners/1"
      }
    },
    "links": {
      "self": "http://api.cliniko.com/v1/internal/daily_availabilities/15"
    }
  }
  ],
  "total_entries": 1,
  "links": {
    "self": "http://api.cliniko.com/v1/businesses/3/daily_availabilities?page=1"
  }
}
```

Get Daily Availability
------------

**Resources**
* ```GET /daily_availabilities/:id``` get a specified daily availability

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/daily_availabilities/15 \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "id": 15,
  "created_at": "2016-06-28T21:33:24Z",
  "updated_at": "2016-09-23T17:19:31Z",
  "availabilities": [
    {
      "starts_at": "09:00",
      "ends_at": "13:00"
    },
    {
      "starts_at": "14:00",
      "ends_at": "17:00"
    }
  ],
  "day_of_week": 7,
  "business": {
    "links": {
      "self": "http://api.cliniko.com/v1/businesses/3"
    }
  },
  "practitioner": {
    "links": {
      "self": "http://api.cliniko.com/v1/practitioners/1"
    }
  },
  "links": {
    "self": "http://api.cliniko.com/v1/internal/daily_availabilities/15"
  }
}
```

Filtering Daily Availabilities
----------------

For any route that returns a set of daily availabilities, you can filter them by:
* ```created_at``` DateTime
* ```business_id``` Integer
* ```id``` Integer
* ```practitioner_id``` Integer
* ```updated_at``` DateTime

See [Filtering Results](https://github.com/redguava/cliniko-api#filtering-results) for details on how to apply filters.
