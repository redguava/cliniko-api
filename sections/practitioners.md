Practitioners
============
> All practitioners have an associated user account.  Not all users are practitioners (eg. receptionists wouldn't be).
>
> You can only create appointments for practitioners (not for users).

* [Get Practitioners](#get-practitioners "This will return all practitioners.")
* [Get Practitioner](#get-practitioner "This will return a specified practitioner.")
* [Get Inactive Practitioners](#get-inactive-practitioners "This will return all inactive practitioners.")

Get Practitioners
----------------

**Resources**
* ```GET /practitioners``` get all active practitioners
* ```GET /appointment_types/:id/practitioners``` get all active practitioners that offer the specified appointment type
* ```GET /businesses/:id/practitioners``` get all active practitioners for a specified business

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/practitioners \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "practitioners": [
    {
      "created_at": "2013-03-26T14:00:00Z",
      "designation": "Osteopath",
      "description": null,
      "first_name": "Randy",
      "id": "514810972972521916",
      "last_name": "Savage",
      "show_in_online_bookings": true,
      "title": "Mr",
      "label": "Randy Savage",
      "updated_at": "2013-03-26T14:00:00Z",
      "default_appointment_type": {
        "links": {"self": "https://api.au1.cliniko.com/v1/appointment_types/1"}
      },
      "practitioner_reference_numbers": {
        "links": {"self": "https://api.au1.cliniko.com/v1/practitioners/514810972972521916/practitioner_reference_numbers?page=1"}
      },
      "user": {
        "links": {"self": "https://api.au1.cliniko.com/v1/users/1"}
      },
      "appointments": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/practitioners/514810972972521916/appointments?page=1"
        }
      },
      "invoices": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/practitioners/514810972972521916/invoices?page=1"
        }
      },
      "links": {"self": "https://api.au1.cliniko.com/v1/practitioners/514810972972521916"}
    }
  ],
  "total_entries": "514810972972521916",
  "links": {"self": "https://api.au1.cliniko.com/v1/practitioners?page=1"}
}
```

Get Practitioner
------------

**Resources**
* ```GET /practitioners/:id``` get a specified practitioner

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/practitioners/514810972972521916 \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "created_at": "2013-03-26T14:00:00Z",
  "designation": "Osteopath",
  "description": null,
  "first_name": "Randy",
  "id": "514810972972521916",
  "last_name": "Savage",
  "show_in_online_bookings": true,
  "title": "Mr",
  "label": "Randy Savage",
  "updated_at": "2013-03-26T14:00:00Z",
  "default_appointment_type": {
    "links": {"self": "https://api.au1.cliniko.com/v1/appointment_types/1"}
  },
  "practitioner_reference_numbers": {
        "links": {"self": "https://api.au1.cliniko.com/v1/practitioners/514810972972521916/practitioner_reference_numbers?page=1"}
  },
  "user": {
    "links": {"self": "https://api.au1.cliniko.com/v1/users/1"}
  },
  "appointments": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/practitioners/514810972972521916/appointments?page=1"
    }
  },
  "invoices": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/practitioners/514810972972521916/invoices?page=1"
    }
  },
  "links": {"self": "https://api.au1.cliniko.com/v1/practitioners/514810972972521916"}
}
```

Get Inactive Practitioners
----------------

**Resources**
* ```GET /practitioners/inactive``` get all inactive practitioners
* ```GET /appointment_types/:id/practitioners``` get all inactive practitioners that offer the specified appointment type
* ```GET /businesses/:id/practitioners/inactive``` get all inactive practitioners for a specified business

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/practitioners/inactive \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "practitioners": [
    {
      "created_at": "2013-03-27T14:00:00Z",
      "designation": "Osteopath",
      "first_name": "Andy",
      "id": 3,
      "last_name": "Savage",
      "show_in_online_bookings": true,
      "title": "Mr",
      "updated_at": "2013-03-27T14:00:00Z",
      "default_appointment_type": {
        "links": {"self": "https://api.au1.cliniko.com/v1/appointment_types/1"}
      },
      "user": {
        "links": {"self": "https://api.au1.cliniko.com/v1/users/3"}
      },
      "appointments": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/practitioners/514810972972521916/appointments?page=1"
        }
      },
      "invoices": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/practitioners/514810972972521916/invoices?page=1"
        }
      },
      "links": {"self": "https://api.au1.cliniko.com/v1/practitioners/3"}
    }
  ],
  "total_entries": 1,
  "links": {"self": "https://api.au1.cliniko.com/v1/practitioners/inactive?page=1"}
}
```

Filtering Practitioners
----------------

For any route that returns a set of practitioners, you can filter them by:
* ```created_at``` DateTime
* ```id``` String
* ```updated_at``` DateTime
* ```user_id``` Integer

See [Filtering Results](https://github.com/redguava/cliniko-api#filtering-results) for details on how to apply filters.
