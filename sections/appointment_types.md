Appointment Types
============
> The different types of appointments the business offers.

* [Get Appointment Types](#get-appointment-types "This will return all appointment types.")
* [Get Archived Appointment Types](#get-archived-appointment-types "This will return all archived appointment types.")
* [Get Appointment Type](#get-appointment-type "This will return a specified appointment type.")
* [Create Appointment Type](#create-appointment-type "This will create an appointment type.")
* [Update Appointment Type](#update-appointment-type "This will update an appointment type.")
* [Delete Appointment Type](#delete-appointment-type "This will delete an appointment type.")

Get Appointment Types
----------------

**Resources**
* ```GET /appointment_types``` get all appointment types
* ```GET /practitioners/:id/appointment_types``` get all appointment types offered by the specified practitioner

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/appointment_types \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "appointment_types": [
    {
      "category": "Osteopathy",
      "color": "#00FF00",
      "created_at": "2013-03-26T14:00:00Z",
      "duration_in_minutes": 60,
      "id": "514810976034364376",
      "name": "Initial Consultation",
      "description": null,
      "max_attendees": 1,
      "show_in_online_bookings": true,
      "updated_at": "2013-03-26T14:00:00Z",
      "billable_item": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/billable_items/3"
        }
      },
      "product": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/products/7"
        }
      },
      "practitioners": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/appointment_types/514810976034364376/practitioners"
        }
      },
      "treatment_note_template": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/treatment_note_templates/1"
        }
      },
      "links": {"self": "https://api.au1.cliniko.com/v1/appointment_types/514810976034364376"}
    }
  ],
  "total_entries": 1,
  "links": {"self": "https://api.au1.cliniko.com/v1/appointment_types?page=1"}
}
```

Get Archived Appointment Types
----------------

**Resources**
* ```GET /appointment_types/archived``` get all archived appointment types

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/appointment_types/archived \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "appointment_types": [
    {
      "archived_at": "2016-06-28T21:33:26Z",
      "category": "Osteopathy",
      "color": "#00FF00",
      "created_at": "2013-03-26T14:00:00Z",
      "duration_in_minutes": 60,
      "id": "514810976034364376",
      "name": "Initial Consultation",
      "description": null,
      "max_attendees": 1,
      "show_in_online_bookings": true,
      "updated_at": "2013-03-26T14:00:00Z",
      "billable_item": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/billable_items/3"
        }
      },
      "product": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/products/7"
        }
      },
      "practitioners": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/appointment_types/514810976034364376/practitioners"
        }
      },
      "treatment_note_template": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/treatment_note_templates/1"
        }
      },
      "links": {"self": "https://api.au1.cliniko.com/v1/appointment_types/514810976034364376"}
    }
  ],
  "total_entries": 1,
  "links": {"self": "https://api.au1.cliniko.com/v1/appointment_types/archived?page=1"}
}
```

Get Appointment Type
------------

**Resources**
* ```GET /appointment_types/:id``` get a specified appointment type

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/appointment_types/514810976034364376 \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "id": "514810976034364376",
  "category": "Osteopathy",
  "color": "#00FF00",
  "created_at": "2013-03-26T14:00:00Z",
  "duration_in_minutes": 60,
  "name": "Initial Consultation",
  "description": null,
  "max_attendees": 1,
  "show_in_online_bookings": true,
  "updated_at": "2013-03-26T14:00:00Z",
  "billable_item": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/billable_items/3"
    }
  },
  "product": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/products/7"
    }
  },
  "practitioners": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/appointment_types/514810976034364376/practitioners"
    }
  },
  "treatment_note_template": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/treatment_note_templates/1"
    }
  },
  "links": {"self": "https://api.au1.cliniko.com/v1/appointment_types/514810976034364376"}
}
```

Create Appointment Type
----------------
**Resources**
* ```POST /appointment_types``` create an appointment type

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/appointment_types \
  -u API_KEY: \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -d '{ "name": "Initial Consultation", "duration_in_minutes": 5, "color": "#FF0000", "max_attendees": 5 }' \
  -X POST
```

**Example Response**
```
Headers { Location: http://api.cliniko.com/appointment_types/514810976034364376 }
```
```json
{
  "id": "514810976034364376",
  "category": null,
  "color": "#FF0000",
  "created_at": "2013-03-26T14:00:00Z",
  "duration_in_minutes": 5,
  "name": "Initial Consultation",
  "description": null,
  "max_attendees": 5,
  "show_in_online_bookings": null,
  "updated_at": "2013-03-26T14:00:00Z",
  "practitioners": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/appointment_types/514810976034364376/practitioners"
    }
  },
  "links": {"self": "https://api.au1.cliniko.com/v1/appointment_types/514810976034364376"}
}
```

Update Appointment Type
----------------
**Resources**
* ```PUT /appointment_types/:id``` update an appointment type

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/appointment_types/514810976034364376 \
  -u API_KEY: \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -d '{ "name": "updated name" }' \
  -X PUT
```
**Example Response**
```json
{
  "id": "514810976034364376",
  "category": null,
  "color": "#FF0000",
  "created_at": "2013-03-26T14:00:00Z",
  "duration_in_minutes": 5,
  "name": "updated name",
  "description": null,
  "max_attendees": 5,
  "show_in_online_bookings": null,
  "updated_at": "2013-03-26T14:00:00Z",
  "practitioners": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/appointment_types/514810976034364376/practitioners"
    }
  },
  "links": {"self": "https://api.au1.cliniko.com/v1/appointment_types/514810976034364376"}
}
```

Delete Appointment Type
----------------
**Resources**
* ```DELETE /appointment_types/:id``` delete an appointment type

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/appointment_types/514810976034364376 \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -X DELETE
```
**Example Response**
A status code of `204 no content` will be returned if successful

Filtering Appointment Types
----------------

For any route that returns a set of appointment types, you can filter them by:
* ```created_at``` DateTime
* ```id``` String
* ```updated_at``` DateTime

See [Filtering Results](https://github.com/redguava/cliniko-api#filtering-results) for details on how to apply filters.
