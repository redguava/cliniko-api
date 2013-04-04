Appointment Types (COMING SOON)
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
      "id": 1,
      "name": "Initial Consultation",
      "duration_in_minutes": 60,
      "color": "#00FF00",
      "category": "Osteopathy",
      "show_in_online_bookings": true,
      "created_at": "2013-03-26T14:00:00Z",
      "updated_at": "2013-03-26T14:00:00Z",
      "links": {"self": "https://api.cliniko.com/v1/appointment_types/1"}
    }
  ],
  "links": {"self": "https://api.cliniko.com/v1/appointment_types"}
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
  "name": "Initial Consultation",
  "duration_in_minutes": 60,
  "color": "#00FF00",
  "category": "Osteopathy",
  "show_in_online_bookings": true,
  "created_at": "2013-03-26T14:00:00Z",
  "updated_at": "2013-03-26T14:00:00Z",
  "links": {"self": "https://api.cliniko.com/v1/appointment_types/1"}
}
```
