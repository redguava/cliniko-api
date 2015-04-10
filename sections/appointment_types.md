Appointment Types
============
> The different types of appointments the business offers.

* [Get Appointment Types](#get-appointment-types "This will return all appointment types.")
* [Get Appointment Type](#get-appointment-type "This will return a specified appointment type.")

Get Appointment Types
----------------

**Resources**
* ```GET /appointment_types``` get all appointment types

**Example Request**
```shell
curl https://api.cliniko.com/v1/appointment_types \
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
      "id": 1,
      "name": "Initial Consultation",
      "show_in_online_bookings": true,
      "updated_at": "2013-03-26T14:00:00Z",
      "links": {"self": "https://api.cliniko.com/v1/appointment_types/1"}
    }
  ],
  "total_entries": 1,
  "links": {"self": "https://api.cliniko.com/v1/appointment_types?page=1"}
}
```

Get Appointment Type
------------

**Resources**
* ```GET /appointment_types/:id``` get a specified appointment type

**Example Request**
```shell
curl https://api.cliniko.com/v1/appointment_types/1 \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "id": 1,
  "category": "Osteopathy",
  "color": "#00FF00",
  "created_at": "2013-03-26T14:00:00Z",
  "duration_in_minutes": 60,
  "name": "Initial Consultation",
  "show_in_online_bookings": true,
  "updated_at": "2013-03-26T14:00:00Z",
  "links": {"self": "https://api.cliniko.com/v1/appointment_types/1"}
}
```

Filtering Appointment Types
----------------

For any route that returns a set of appointment types, you can filter them by:
* ```id``` Integer
* ```updated_at``` DateTime

See [Filtering Results](https://github.com/redguava/cliniko-api#filtering-results) for details on how to apply filters.
