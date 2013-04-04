Businesses (COMING SOON)
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
curl https://api.cliniko.com/v1/businesses \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "businesses": [
    {
      "business_name": "Healthy Times",
      "address_1": "20 Smith Street",
      "address_2": null,
      "city": "Smithytown",
      "state": "Victoria",
      "post_code" : "3000",
      "country": "Australia",
      "business_registration_name": "ABN",
      "business_registration_value": "1111111111",
      "id": 1,
      "created_at": "2013-03-26T14:00:00Z",
      "updated_at": "2013-03-26T14:00:00Z",
      "website_address": "http://www.healthytimes.com",
      "contact_information": "Phone: 99999 99999",
      "show_in_online_bookings": true,
      "links": {"self": "https://api.cliniko.com/v1/businesses/1"}
    }
  ],
  "links": {"self": "https://api.cliniko.com/v1/businesses"}
}
```

Get Business
------------

**Resources**
* ```GET /business/:id``` get a specified business

**Example Request**
```shell
curl https://api.cliniko.com/v1/business/1 \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "business_name": "Healthy Times",
  "address_1": "20 Smith Street",
  "address_2": null,
  "city": "Smithytown",
  "state": "Victoria",
  "post_code" : "3000",
  "country": "Australia",
  "business_registration_name": "ABN",
  "business_registration_value": "1111111111",
  "id": 1,
  "created_at": "2013-03-26T14:00:00Z",
  "updated_at": "2013-03-26T14:00:00Z",
  "website_address": "http://www.healthytimes.com",
  "contact_information": "Phone: 99999 99999",
  "show_in_online_bookings": true,
  "links": {"self": "https://api.cliniko.com/v1/businesses/1"}
}
```
