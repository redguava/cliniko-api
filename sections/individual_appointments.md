Individual Appointments
============

* [Get Individual Appointments](#get-individual-appointments "This will return all individual appointments.")
* [Get Deleted Individual Appointments](#get-deleted-individual-appointments "This will return all deleted individual appointments ID's only")
* [Get Cancelled Individual Appointments](#get-cancelled-individual-appointments "This will return all cancelled individual appointments.")
* [Get Individual Appointment](#get-individual-appointment "This will return a specified individual appointment.")
* [Get Conflicts](#get-conflicts "This will return if the specified individual appointment has conflicts.")
* [Create Individual Appointment](#create-individual-appointment "This will create an individual appointment.")
* [Update Individual Appointment](#update-individual-appointment "This will update an individual appointment.")
* [Delete Individual Appointment](#delete-individual-appointment "This will delete an individual appointment.")
* [Cancel Individual Appointment](#cancel-individual-appointment "This will cancel an individual appointment.")

Get Individual Appointments
----------------

**Resources**
* ```GET /individual_appointments``` get all individual appointments


**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/individual_appointments \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "individual_appointments": [
    {
      "id": 1,
      "created_at": "2016-06-28T21:33:26Z",
      "updated_at": "2016-07-22T15:10:08Z",
      "booking_ip_address": null,
      "cancellation_note": null,
      "cancellation_reason": null,
      "cancellation_reason_description": "",
      "conflicts": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/individual_appointments/1/conflicts"
        }
      },
      "did_not_arrive": false,
      "email_reminder_sent": false,
      "invoice_status": null,
      "notes": null,
      "online_booking_policy_accepted": null,
      "patient_arrived": false,
      "patient_name": "Joe Monahan",
      "repeat_rule": {},
      "repeats": null,
      "sms_reminder_sent": false,
      "treatment_note_status": null,
      "deleted_at": null,
      "starts_at": "2016-07-21T03:45:00Z",
      "ends_at": "2016-07-21T04:30:00Z",
      "cancelled_at": null,
      "appointment_type": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/appointment_types/2"
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
      "patient": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/patients/82"
        }
      },
      "attendees": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/individual_appointments/1/attendees"
        }
      },
      "links": {
        "self": "https://api.au1.cliniko.com/v1/individual_appointments/1"
      }
    }
  ],
  "total_entries": 952,
  "links": {
    "self": "https://api.au1.cliniko.com/v1/individual_appointments?page=1",
    "next": "https://api.au1.cliniko.com/v1/individual_appointments?page=2"
  }
}
```

Get Deleted Individual Appointments
----------------

**Resources**
* ```GET /individual_appointments/deleted``` get all deleted individual appointments

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/individual_appointments/deleted \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "individual_appointments": [
    {
      "id": 1,
      "created_at": "2016-06-28T21:33:26Z",
      "updated_at": "2016-07-22T15:10:08Z",
      "booking_ip_address": null,
      "cancellation_note": null,
      "cancellation_reason": null,
      "cancellation_reason_description": "",
      "conflicts": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/individual_appointments/1/conflicts"
        }
      },
      "did_not_arrive": false,
      "email_reminder_sent": false,
      "invoice_status": null,
      "notes": null,
      "online_booking_policy_accepted": null,
      "patient_arrived": false,
      "patient_name": "Joe Monahan",
      "repeat_rule": {},
      "repeats": null,
      "sms_reminder_sent": false,
      "treatment_note_status": null,
      "deleted_at": "2016-07-22T15:10:08Z",
      "starts_at": "2016-07-21T03:45:00Z",
      "ends_at": "2016-07-21T04:30:00Z",
      "cancelled_at": null,
      "appointment_type": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/appointment_types/2"
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
      "patient": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/patients/82"
        }
      },
      "attendees": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/individual_appointments/1/attendees"
        }
      },
      "links": {
        "self": "https://api.au1.cliniko.com/v1/individual_appointments/1"
      }
    }
  ],
  "total_entries": 1,
  "links": {
    "self": "https://api.au1.cliniko.com/v1/individual_appointments/deleted?page=1",
  }
}
```

Get Cancelled Individual Appointments
----------------

**Resources**
* ```GET /individual_appointments/cancelled``` get all cancelled individual appointments

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/individual_appointments/cancelled \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "individual_appointments": [
    {
      "id": 1,
      "created_at": "2016-06-28T21:33:26Z",
      "updated_at": "2016-07-22T15:10:08Z",
      "booking_ip_address": null,
      "cancellation_note": "Last minute cancellation",
      "cancellation_reason": 50,
      "cancellation_reason_description": "Other",
      "conflicts": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/individual_appointments/1/conflicts"
        }
      },
      "did_not_arrive": false,
      "email_reminder_sent": false,
      "invoice_status": null,
      "notes": null,
      "online_booking_policy_accepted": null,
      "patient_arrived": false,
      "patient_name": "Joe Monahan",
      "repeat_rule": {},
      "repeats": null,
      "sms_reminder_sent": false,
      "treatment_note_status": null,
      "deleted_at": null,
      "starts_at": "2016-07-21T03:45:00Z",
      "ends_at": "2016-07-21T04:30:00Z",
      "cancelled_at": "2016-07-22T15:10:08Z",
      "appointment_type": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/appointment_types/2"
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
      "patient": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/patients/82"
        }
      },
      "attendees": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/individual_appointments/1/attendees"
        }
      },
      "links": {
        "self": "https://api.au1.cliniko.com/v1/individual_appointments/1"
      }
    }
  ],
  "total_entries": 952,
  "links": {
    "self": "https://api.au1.cliniko.com/v1/individual_appointments?page=1",
    "next": "https://api.au1.cliniko.com/v1/individual_appointments?page=2"
  }
}
```

Get Individual Appointment
------------

**Resources**
* ```GET /individual_appointments/:id``` get a specified individual appointment

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/individual_appointments/1 \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "id": 1,
  "created_at": "2016-06-28T21:33:26Z",
  "updated_at": "2016-07-22T15:10:08Z",
  "booking_ip_address": null,
  "cancellation_note": null,
  "cancellation_reason": null,
  "cancellation_reason_description": "",
  "conflicts": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/individual_appointments/1/conflicts"
    }
  },
  "did_not_arrive": false,
  "email_reminder_sent": false,
  "invoice_status": null,
  "notes": null,
  "online_booking_policy_accepted": null,
  "patient_arrived": false,
  "patient_name": "Joe Monahan",
  "repeat_rule": {},
  "repeats": null,
  "sms_reminder_sent": false,
  "treatment_note_status": null,
  "deleted_at": null,
  "starts_at": "2016-07-21T03:45:00Z",
  "ends_at": "2016-07-21T04:30:00Z",
  "cancelled_at": null,
  "appointment_type": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/appointment_types/2"
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
  "patient": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/patients/82"
    }
  },
  "attendees": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/individual_appointments/1/attendees"
    }
  },
  "links": {
    "self": "https://api.au1.cliniko.com/v1/individual_appointments/1"
  }
}
```

Get Conflicts
------------

**Resources**
* ```GET /individual_appointments/:id/conflicts``` get a specified individual appointment's conflicts

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/individual_appointments/1/conflicts \
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

Create Individual Appointment
----------------
**Resources**
* ```POST /individual_appointments``` create an individual appointment

**Notes**

If not provided, the ends_at is automatically set based upon the duration of the appointment_type.

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/individual_appointments \
  -u API_KEY: \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -d '{ "starts_at": "2016-07-21T03:45:00Z", "patient_id": "1", "practitioner_id": "1", "appointment_type_id": "1", "business_id": "1" }' \
  -X POST
```
**Example Response**
```
Headers { Location: https://api.au1.cliniko.com/individual_appointments/1 }
```
```json
{
  "id": 1,
  "created_at": "2016-06-28T21:33:26Z",
  "updated_at": "2016-07-22T15:10:08Z",
  "booking_ip_address": null,
  "cancellation_note": null,
  "cancellation_reason": null,
  "cancellation_reason_description": "",
  "conflicts": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/individual_appointments/1/conflicts"
    }
  },
  "did_not_arrive": false,
  "email_reminder_sent": false,
  "invoice_status": null,
  "notes": null,
  "online_booking_policy_accepted": null,
  "patient_arrived": false,
  "patient_name": "Joe Monahan",
  "repeat_rule": {},
  "repeats": null,
  "sms_reminder_sent": false,
  "treatment_note_status": null,
  "deleted_at": null,
  "starts_at": "2016-07-21T03:45:00Z",
  "ends_at": "2016-07-21T04:30:00Z",
  "cancelled_at": null,
  "appointment_type": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/appointment_types/1"
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
  "patient": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/patients/1"
    }
  },
  "attendees": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/individual_appointments/1/attendees"
    }
  },
  "links": {
    "self": "https://api.au1.cliniko.com/v1/individual_appointments/1"
  }
}
```

Update Individual Appointment
----------------
**Resources**
* ```PUT /individual_appointments/:id``` update an individual appointment

**Notes**

If ends_at is specified and its value is null, it is automatically set based upon the duration of the appointment_type.

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/individual_appointments/1 \
  -u API_KEY: \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -d '{ "ends_at": "2016-07-21T04:45:00Z" }' \
  -X PUT
```
**Example Response**
```json
{
  "id": 1,
  "created_at": "2016-06-28T21:33:26Z",
  "updated_at": "2016-07-22T15:10:08Z",
  "booking_ip_address": null,
  "cancellation_note": null,
  "cancellation_reason": null,
  "cancellation_reason_description": "",
  "conflicts": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/individual_appointments/1/conflicts"
    }
  },
  "did_not_arrive": false,
  "email_reminder_sent": false,
  "invoice_status": null,
  "notes": null,
  "online_booking_policy_accepted": null,
  "patient_arrived": false,
  "patient_name": "Joe Monahan",
  "repeat_rule": {},
  "repeats": null,
  "sms_reminder_sent": false,
  "treatment_note_status": null,
  "deleted_at": null,
  "starts_at": "2016-07-21T03:45:00Z",
  "ends_at": "2016-07-21T04:45:00Z",
  "cancelled_at": null,
  "appointment_type": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/appointment_types/1"
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
  "patient": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/patients/1"
    }
  },
  "attendees": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/individual_appointments/1/attendees"
    }
  },
  "links": {
    "self": "https://api.au1.cliniko.com/v1/individual_appointments/1"
  }
}
```

Delete Individual Appointment
----------------
**Resources**
* ```DELETE /individual_appointments/:id``` delete an individual appointment

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/individual_appointments/1 \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -X DELETE
```
**Example Response**
A status code of `204 no content` will be returned if successful

Cancel Individual Appointment
----------------
**Resources**
* ```PATCH /individual_appointments/:id/cancel``` cancel an individual appointment

**Notes**

The `cancellation_reason` information is mandatory.

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/individual_appointments/1/cancel \
  -u API_KEY: \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -d '{ "cancellation_reason": 50, "cancellation_note": "A note" }' \
  -X PATCH
```

**Example Response**
A status code of `204 no content` will be returned if successful

**Cancellation Reason Codes**
* `10` Feeling better
* `20` Condition worse
* `30` Sick
* `31` COVID-19 related
* `40` Away
* `50` Other
* `60` Work


Filtering Individual Appointments
----------------

For any route that returns a set of individual appointments, you can filter them by:
* ```appointment_type_id``` Integer
* ```archived_at``` DateTime
* ```business_id``` Integer
* ```cancelled_at``` DateTime
* ```created_at``` DateTime
* ```ends_at``` DateTime
* ```id``` Integer
* ```patient_id``` Integer
* ```practitioner_id``` Integer
* ```repeated_from_id``` Integer
* ```starts_at``` DateTime
* ```updated_at``` DateTime

See [Filtering Results](https://github.com/redguava/cliniko-api#filtering-results) for details on how to apply filters.
