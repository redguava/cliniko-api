Bookings
============

The bookings endpoints are convenience endpoints that can return group appointments, individual appointments, and unavailable blocks. The properties of the response objects depends on the type of booking. You can find the specifics of each type on their documentation page: [group appointments](https://github.com/redguava/cliniko-api/blob/master/sections/group_appointments.md), [individual appointments](https://github.com/redguava/cliniko-api/blob/master/sections/individual_appointments.md), [unavailable blocks](https://github.com/redguava/cliniko-api/blob/master/sections/unavailable_blocks.md).

* [Get Bookings](#get-bookings "This will return all bookings.")
* [Get Booking](#get-booking "This will return a specified booking.")

Get Bookings
------------

**Resources**
* ```GET /bookings``` get all bookings

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/bookings \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "bookings": [
    {
      "id": 1011,
      "created_at": "2017-11-29T20:30:07Z",
      "updated_at": "2017-11-29T20:30:07Z",
      "conflicts": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/group_appointments/1011/conflicts"
        }
      },
      "max_attendees": 2,
      "notes": null,
      "patient_ids": [],
      "repeat_rule": {},
      "repeats": null,
      "deleted_at": null,
      "starts_at": "2017-12-06T01:00:00Z",
      "ends_at": "2017-12-06T02:10:00Z",
      "appointment_type": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/appointment_types/5"
        }
      },
      "business": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/businesses/3"
        }
      },
      "practitioner": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/practitioners/1"
        }
      },
      "attendees": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/group_appointments/1011/attendees"
        }
      },
      "links": {
        "self": "https://api.au1.cliniko.com/v1/bookings/1011"
      }
    },
    {
      "id": 1010,
      "created_at": "2017-11-29T20:27:53Z",
      "updated_at": "2017-11-29T20:27:53Z",
      "conflicts": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/unavailable_blocks/1010/conflicts"
        }
      },
      "notes": null,
      "repeat_rule": {},
      "repeats": null,
      "deleted_at": null,
      "starts_at": "2017-12-05T23:00:00Z",
      "ends_at": "2017-12-05T23:30:00Z",
      "business": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/businesses/3"
        }
      },
      "practitioner": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/practitioners/1"
        }
      },
      "links": {
        "self": "https://api.au1.cliniko.com/v1/bookings/1010"
      }
    },
    {
      "id": 1009,
      "created_at": "2017-11-29T15:53:06Z",
      "updated_at": "2017-11-29T18:40:22Z",
      "booking_ip_address": "10.0.0.43",
      "cancellation_note": null,
      "cancellation_reason": null,
      "conflicts": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/individual_appointments/1009/conflicts"
        }
      },
      "did_not_arrive": false,
      "email_reminder_sent": false,
      "invoice_status": null,
      "notes": null,
      "online_booking_policy_accepted": null,
      "patient_arrived": false,
      "patient_name": "Ada Cummerata",
      "repeat_rule": {},
      "repeats": null,
      "sms_reminder_sent": false,
      "treatment_note_status": null,
      "deleted_at": null,
      "starts_at": "2017-12-04T00:30:00Z",
      "ends_at": "2017-12-04T01:00:00Z",
      "cancelled_at": null,
      "appointment_type": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/appointment_types/1"
        }
      },
      "business": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/businesses/3"
        }
      },
      "practitioner": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/practitioners/1"
        }
      },
      "patient": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/patients/773"
        }
      },
      "attendees": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/individual_appointments/1009/attendees"
        }
      },
      "links": {
        "self": "https://api.au1.cliniko.com/v1/bookings/1009"
      }
    }
  ],
  "total_entries": 3,
  "links": {
    "self": "https://api.au1.cliniko.com/v1/bookings?page=1"
  }
}
```

Get Booking
------------

**Resources**
* ```GET /bookings/:id``` get a specified booking

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/bookings/1 \
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
      "self": "https://api.au1.cliniko.com/v1/group_appointments/1/conflicts"
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
      "self": "https://api.au1.cliniko.com/v1/appointment_types/7"
    }
  },
  "business": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/businesses/1"
    }
  },
  "practitioner": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/practitioners/1"
    }
  },
  "attendees": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/group_appointments/1/attendees"
    }
  },
  "links": {
    "self": "https://api.au1.cliniko.com/v1/bookings/1"
  }
}
```

Filtering Bookings
----------------

For any route that returns a set of bookings, you can filter them by:
* ```archived_at``` DateTime
* ```business_id``` Integer
* ```cancelled_at``` DateTime
* ```created_at``` DateTime
* ```ends_at``` DateTime
* ```id``` Integer
* ```patient_ids``` Array of integers
* ```practitioner_id``` Integer
* ```starts_at``` DateTime
* ```updated_at``` DateTime

See [Filtering Results](https://github.com/redguava/cliniko-api#filtering-results) for details on how to apply filters. Specifically, see String filters for filtering on a list (Array) of ```patient_ids```.
