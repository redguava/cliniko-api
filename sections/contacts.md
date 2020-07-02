# Contacts

> Third party contacts.

- [Get Contacts](#get-contacts 'This will return all contacts.')
- [Get Contact](#get-contact 'This will return a specified contact.')
- [Create Contact](#create-contact 'This will create a contact.')
- [Update Contact](#update-contact 'This will update a contact.')
- [Delete Contact](#delete-contact 'This will delete a contact.')

## Get Contacts

**Resources**

- `GET /contacts` get all contacts

**Example Request**

```shell
curl https://api.au1.cliniko.com/v1/contacts \
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
      "type": "Doctor",
      "type_code": 1,
      "links": {
        "self": "http://api.cliniko.com/v1/contacts/1"
      }
    }
  ],
  "total_entries": 1,
  "links": {
    "self": "https://api.au1.cliniko.com/v1/contacts?page=1"
  }
}
```

## Get Contact

**Resources**

- `GET /contacts/:id` get a specified contact

**Example Request**

```shell
curl https://api.au1.cliniko.com/v1/contacts/1 \
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
  "doctor_type": null,
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
  "type": "Doctor",
  "type_code": 1,
  "links": {
    "self": "http://api.cliniko.com/v1/contacts/1"
  }
}
```

## Create Contact

When creating a contact, setting the contact's country must be done using the `country_code` parameter.
This is the [ISO 3166-1](https://en.wikipedia.org/wiki/ISO_3166-1#Current_codes) country code.

A contact's `doctor_type` may be the string value `general_practitioner` or `specialist`. To clear the value,
set it to `null`.

**Resources**

- `POST /contacts` create a contact

**Example Request**

```shell
curl https://api.au1.cliniko.com/v1/contacts \
  -u API_KEY: \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -d '{ "first_name": "John", "last_name": "Snow", "country_code": "AU" }' \
  -X POST
```

**Example Response**

```
Headers { Location: http://api.cliniko.com/contacts/1 }
```

```json
{
  "id": 12,
  "created_at": "2018-02-12T17:58:18Z",
  "updated_at": "2018-02-12T17:58:18Z",
  "address_1": "",
  "address_2": "",
  "address_3": "",
  "city": "",
  "company_name": "",
  "country_code": "AU",
  "deleted_at": null,
  "doctor_type": null,
  "email": "",
  "first_name": "John",
  "last_name": "Snow",
  "notes": "",
  "occupation": "",
  "phone_numbers": [],
  "post_code": "",
  "preferred_name": "",
  "provider_number": "",
  "state": "",
  "title": "",
  "country": "Australia",
  "type": "Standard",
  "type_code": 0,
  "links": {
    "self": "https://api.au1.cliniko.com/v1/contacts/12"
  }
}
```

## Update Contact

When updating a contact, changing the contact's country must be done using the `country_code` parameter.
This is the [ISO 3166-1](https://en.wikipedia.org/wiki/ISO_3166-1#Current_codes) country code.

A contact's `doctor_type` may be the string value `general_practitioner` or `specialist`. To clear the value,
set it to `null`.

**Resources**

- `PUT /contacts/:id` update a contact

**Example Request**

```shell
curl https://api.au1.cliniko.com/v1/contacts/1 \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'Content-Type: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -d '{ "first_name": "John", "last_name": "Snow" }' \
  -X PUT
```

**Example Response**

```json
{
  "id": 12,
  "created_at": "2018-02-12T17:58:18Z",
  "updated_at": "2018-02-12T17:59:56Z",
  "address_1": "",
  "address_2": "",
  "address_3": "",
  "city": "",
  "company_name": "",
  "country_code": "AU",
  "deleted_at": null,
  "doctor_type": null,
  "email": "",
  "first_name": "John",
  "last_name": "Snow",
  "notes": "",
  "occupation": "",
  "phone_numbers": [],
  "post_code": "",
  "preferred_name": "",
  "provider_number": "",
  "state": "",
  "title": "",
  "country": "Australia",
  "type": "Standard",
  "type_code": 0,
  "links": {
    "self": "https://api.au1.cliniko.com/v1/contacts/12"
  }
}
```

## Delete Contact

**Resources**

- `DELETE /contacts/:id` delete a contact

**Example Request**

```shell
curl https://api.au1.cliniko.com/v1/contacts/1 \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -X DELETE
```

**Example Response**
A status code of `204 no content` will be returned if successful

## Filtering Contacts

For any route that returns a set contacts, you can filter them by:

- `created_at` DateTime
- `email` String
- `first_name` String
- `id` Integer
- `last_name` String
- `type_code` Integer
- `updated_at` DateTime

See [Filtering Results](https://github.com/redguava/cliniko-api#filtering-results) for details on how to apply filters.
