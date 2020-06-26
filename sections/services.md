Services
============

* [Get Services](#get-services "This returns all services.")

Get Services
----------------

**Resources**
* ```GET /services``` Get all services.
* ```GET /businesses/:id/services``` Get all services of the specified business.

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/services \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "services": [
    {
      "practitioners": [
        {
          "links": {
            "self": "https://api.au1.cliniko.com/v1/practitioners/1"
          }
        },
        {
          "links": {
            "self": "https://api.au1.cliniko.com/v1/practitioners/2"
          }
        }
      ],
      "appointment_type": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/appointment_types/456"
        }
      },
      "business": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/businesses/123"
        }
      }
    }
  ],
  "total_entries": 1,
  "links": {
    "self": "https://api.au1.cliniko.com/v1/services?page=1"
  }
}
```
