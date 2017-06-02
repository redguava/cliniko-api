Bookings
============

The bookings endpoint is a convenience endpoint that can return group and individual appointments. The properties of the response objects depends on the type of booking. You can find the specifics of each type on their documentation page: [group appointments](https://github.com/redguava/cliniko-api/blob/master/sections/group_appointments.md), [individual appointments](https://github.com/redguava/cliniko-api/blob/master/sections/individual_appointments.md).

* [Get Booking](#get-booking "This will return a specified booking.")

Get Booking
------------

**Resources**
* ```GET /bookings/:id``` get a specified booking

**Example Request**
```shell
curl https://api.cliniko.com/v1/appointments/1 \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "id": 1,
  "created_at": "2016-07-11T18:26:36Z",
  "updated_at": "2016-07-11T18:26:43Z",
  "conflicts": {
    "links": {
      "self": "https://api.cliniko.com/v1/group_appointments/1/conflicts"
    }
  },
  "max_attendees": 13,
  "notes": null,
  "patient_ids": [48],
  "repeat_rule": {},
  "repeats": null,
  "deleted_at": null,
  "starts_at": "2016-07-13T03:45:00Z",
  "ends_at": "2016-07-13T04:15:00Z",
  "appointment_type": {
    "links": {
      "self": "https://api.cliniko.com/v1/appointment_types/7"
    }
  },
  "business": {
    "links": {
      "self": "https://api.cliniko.com/v1/businesses/1"
    }
  },
  "practitioner": {
    "links": {
      "self": "https://api.cliniko.com/v1/practitioners/1"
    }
  },
  "attendees": {
    "links": {
      "self": "https://api.cliniko.com/v1/group_appointments/1/attendees"
    }
  },
  "links": {
    "self": "https://api.cliniko.com/v1/group_appointments/1"
  }
}
```
