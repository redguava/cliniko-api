Group Appointments
============
* [Get Group Appointments](#get-group-appointments "This will return all group appointments.")
* [Get Deleted Group Appointments](#get-deleted-group-appointments "This will return all deleted group appointments")
* [Get Group Appointment](#get-group-appointment "This will return a specified group appointment.")
* [Get Conflicts](#get-conflicts "This will return if the specified group appointment has conflicts.")
* [Create Group Appointment](#create-group-appointment "This will create a group appointment.")
* [Update Group Appointment](#update-group-appointment "This will update a group appointment.")
* [Delete Group Appointment](#delete-group-appointment "This will delete a group appointment.")

Get Group Appointments
----------------

**Resources**
* ```GET /group_appointments``` get all group appointments


**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/group_appointments \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "group_appointments": [
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
        "self": "https://api.au1.cliniko.com/v1/group_appointments/1"
      }
    }
  ],
  "total_entries": 202,
  "links": {
    "self": "https://api.au1.cliniko.com/v1/group_appointments?page=1",
    "next": "https://api.au1.cliniko.com/v1/group_appointments?page=2"
  }
}
```

Get Deleted Group Appointments
----------------

**Resources**
* ```GET /group_appointments/deleted``` get all deleted group appointments

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/group_appointments/deleted \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "group_appointments": [
    {
      "id": 1,
      "created_at": "2016-07-11T18:26:36Z",
      "updated_at": "2016-07-12T20:13:42Z",
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
      "deleted_at": "2016-07-12T20:13:42Z",
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
        "self": "https://api.au1.cliniko.com/v1/group_appointments/1"
      }
    }
  ],
  "total_entries": 202,
  "links": {
    "self": "https://api.au1.cliniko.com/v1/group_appointments?page=1",
    "next": "https://api.au1.cliniko.com/v1/group_appointments?page=2"
  }
}
```

Get Group Appointment
------------

**Resources**
* ```GET /group_appointments/:id``` get a specified group appointment

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/group_appointments/1 \
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
    "self": "https://api.au1.cliniko.com/v1/group_appointments/1"
  }
}
```

Get Conflicts
------------

**Resources**
* ```GET /group_appointments/:id/conflicts``` get a specified group appointment's conflicts

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/group_appointments/1/conflicts \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "conflicts" : {
    "exist": true
  }
}
```

Create Group Appointment
----------------
**Resources**
* ```POST /group_appointments``` create a group appointment

**Notes**

If not provided, ends_at is automatically set based upon the duration of the appointment_type and max_attendees is set to the max_attendees of the appointment type.

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/group_appointments \
  -u API_KEY: \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -d '{ "starts_at": "2016-07-13T03:45:00Z", "practitioner_id": "1", "appointment_type_id": "1", "business_id": "1" }' \
  -X POST
```
**Example Response**
```
Headers { Location: https://api.au1.cliniko.com/group_appointments/1 }
```
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
    "self": "https://api.au1.cliniko.com/v1/group_appointments/1"
  }
}

```

Update Group Appointment
----------------
**Resources**
* ```PUT /group_appointments/:id``` update a group appointment

**Notes**

If ends_at is specified and its value is null, it is automatically set based upon the duration of the appointment_type.

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/group_appointments/1 \
  -u API_KEY: \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -d '{ "ends_at": "2016-07-13T04:30:00Z" }' \
  -X PUT
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
  "ends_at": "2016-07-13T04:30:00Z",
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
    "self": "https://api.au1.cliniko.com/v1/group_appointments/1"
  }
}
```

Delete Group Appointment
----------------
**Resources**
* ```DELETE /group_appointments/:id``` delete a group appointment

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/group_appointments/1 \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -X DELETE
```
**Example Response**
A status code of `204 no content` will be returned if successful

Filtering Group Appointments
----------------

For any route that returns a set of group appointments, you can filter them by:
* ```appointment_type_id``` Integer
* ```archived_at``` DateTime
* ```business_id``` Integer
* ```created_at``` DateTime
* ```ends_at``` DateTime
* ```id``` Integer
* ```practitioner_id``` Integer
* ```repeated_from_id``` Integer
* ```starts_at``` DateTime
* ```updated_at``` DateTime

See [Filtering Results](https://github.com/redguava/cliniko-api#filtering-results) for details on how to apply filters.
