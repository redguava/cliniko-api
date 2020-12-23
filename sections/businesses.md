Businesses
============
> Businesses represent a business or location (eg. a clinic).  Each Cliniko account can have unlimited businesses.
>
> These are typically used for each physical location if there is more than one.  Most Cliniko accounts have just one business.

* [Get Businesses](#get-businesses "This will return all businesses.")
* [Get Business](#get-business "This will return a specified business.")

Get Businesses
----------------

**Resources**
* ```GET /businesses``` get all businesses

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/businesses \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "businesses": [
    {
      "address_1": "20 Smith Street",
      "address_2": null,
      "business_name": "Healthy Times",
      "business_registration_name": "ABN",
      "business_registration_value": "1111111111",
      "city": "Smithytown",
      "contact_information": "Phone: 99999 99999",
      "country": "Australia",
      "country_code": "AU",
      "created_at": "2013-03-26T14:00:00Z",
      "id": "514810976554457178",
      "post_code" : "3000",
      "show_in_online_bookings": true,
      "state": "Victoria",
      "updated_at": "2013-03-26T14:00:00Z",
      "website_address": "http://www.healthytimes.com",
      "practitioners": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/businesses/514810976554457178/practitioners"
        }
      },
      "appointments": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/businesses/514810976554457178/appointments?page=1"
        }
      },
      "links": {"self": "https://api.au1.cliniko.com/v1/businesses/514810976554457178"}
    }
  ],
  "total_entires": 1,
  "links": {"self": "https://api.au1.cliniko.com/v1/businesses?page=1"}
}
```

Get Business
------------

**Resources**
* ```GET /businesses/:id``` get a specified business

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/businesses/514810976554457178 \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "address_1": "20 Smith Street",
  "address_2": null,
  "business_name": "Healthy Times",
  "business_registration_name": "ABN",
  "business_registration_value": "1111111111",
  "city": "Smithytown",
  "contact_information": "Phone: 99999 99999",
  "country": "Australia",
  "country_code": "AU",
  "created_at": "2013-03-26T14:00:00Z",
  "id": "514810976554457178",
  "post_code" : "3000",
  "show_in_online_bookings": true,
  "state": "Victoria",
  "updated_at": "2013-03-26T14:00:00Z",
  "website_address": "http://www.healthytimes.com",
  "practitioners": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/businesses/514810976554457178/practitioners"
    }
  },
  "appointments": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/businesses/514810976554457178/appointments?page=1"
    }
  },
  "links": {"self": "https://api.au1.cliniko.com/v1/businesses/514810976554457178"}
}
```

Filtering Businesses
----------------

You can filter businesses by:
* ```created_at``` DateTime
* ```id``` String
* ```updated_at``` DateTime

See [Filtering Results](https://github.com/redguava/cliniko-api#filtering-results) for details on how to apply filters.
