Contacts
============
> Third party contacts.

* [Get Contacts](#get-contacts "This will return all contacts.")
* [Get Contact](#get-contact "This will return a specified contact.")

Get Contacts
----------------

**Resources**
* ```GET /contacts``` get all contacts

**Example Request**
```shell
curl https://api.cliniko.com/v1/contacts \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "contacts": [
    {
      "id": 1,
      "created_at": "2016-07-25T18:52:09Z",
      "updated_at": "2016-10-28T23:43:31Z",
      "address_1": "691 Candelario Crossroad",
      "address_2": "Apt. 735",
      "address_3": "",
      "city": "Lake Haliebury",
      "company_name": "",
      "deleted_at": null,
      "email": "geovany@example.net",
      "first_name": "Darrell",
      "last_name": "Bode",
      "notes": "",
      "occupation": "",
      "phone_numbers": [
        {
          "number": "0987654321",
          "phone_type": "Mobile"
        },
        {
          "number": "1234567890",
          "phone_type": "Home"
        }
      ],
      "post_code": "34623",
      "preferred_name": "",
      "provider_number": "",
      "state": "MN",
      "title": "Mr.",
      "country": "Estonia",
      "contact_type": "Doctor",
      "links": {
        "self": "http://local.cliniko.dev:3000/v1/contacts/1"
      }
    }
  ],
  "total_entries": 1,
  "links": {
    "self": "https://api.cliniko.com/v1/contacts?page=1"
  }
}
```

Get Contact
------------

**Resources**
* ```GET /contacts/:id``` get a specified contact

**Example Request**
```shell
curl https://api.cliniko.com/v1/contacts/1 \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "id": 1,
  "created_at": "2016-07-25T18:52:09Z",
  "updated_at": "2016-10-28T23:43:31Z",
  "address_1": "691 Candelario Crossroad",
  "address_2": "Apt. 735",
  "address_3": "",
  "city": "Lake Haliebury",
  "company_name": "",
  "deleted_at": null,
  "email": "geovany@example.net",
  "first_name": "Darrell",
  "last_name": "Bode",
  "notes": "",
  "occupation": "",
  "phone_numbers": [
    {
      "number": "0987654321",
      "phone_type": "Mobile"
    },
    {
      "number": "1234567890",
      "phone_type": "Home"
    }
  ],
  "post_code": "34623",
  "preferred_name": "",
  "provider_number": "",
  "state": "MN",
  "title": "Mr.",
  "country": "Estonia",
  "contact_type": "Doctor",
  "links": {
    "self": "http://local.cliniko.dev:3000/v1/contacts/1"
  }
}
```

Filtering Contacts
----------------

For any route that returns a set contacts, you can filter them by:
* ```created_at``` DateTime
* ```id``` Integer
* ```updated_at``` DateTime

See [Filtering Results](https://github.com/redguava/cliniko-api#filtering-results) for details on how to apply filters.
