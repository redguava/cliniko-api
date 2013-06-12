Appointments
============
* [Get Appointments](#get-appointments "This will return all appointments.")
* [Get Deleted Appointments](#get-appointments "This will return all deleted appointments ids.")
* [Get Cancelled Appointments](#get-appointments "This will return all cancelled appointments.")
* [Get Appointment](#get-appointment "This will return a specified appointment.")
* [Create Appointment](#create-appointment "This will create an appointment.")
* [Update Appointment](#update-appointment "This will update an appointment.")
* [Delete Appointment](#delete-appointment "This will delete an appointment.")

Get Appointments
----------------

**Resources**
* ```GET /appointments``` get all appointments
* ```GET /businesses/:id/appointments``` get all appointments for a specified business
* ```GET /practitioners/:id/appointments``` get all appointments for a specified practitioner
* ```GET /patients/:id/appointments``` get all appointments for a specified patient

**Example Request**
```shell
curl https://api.cliniko.com/v1/appointments \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "appointments": [
    {
      "appointment_end": "2013-03-26T14:00:00Z",
      "appointment_start": "2013-03-26T14:00:00Z",
      "cancellation_note": null,    (REMOVED)
      "cancellation_reason" :null,  (REMOVED)
      "cancellation_time" :null,    (REMOVED)
      "created_at": "2013-03-27T10:03:57Z",
      "did_not_arrive": false,
      "email_reminder_sent": false,
      "id": 343589,
      "notes": null,
      "online_booking_policy_accepted": null,
      "patient_arrived": false,
      "repeat_rule": {"repeat_type": "Daily", "number_of_repeats": 3, "repeating_interval": 3},
      "sms_reminder_sent": false,
      "updated_at": "2013-03-27T10:03:57Z",
      "appointment_repeated_from" : {
        "links": {"self": "https://api.cliniko.com/v1/appointments/2"}
      },
      "appointment_type": {
        "links": {"self": "https://api.cliniko.com/v1/appointment_types/12345"}
      },
      "business": {
        "links": {"self": "https://api.cliniko.com/v1/businesses/45678"}
      },
      "patient": {
        "links": {"self": "https://api.cliniko.com/v1/patients/12345"}
      },
      "practitioner": {
        "links": {"self": "https://api.cliniko.com/v1/practitioners/1"}
      },
      "links": {"self": "https://api.cliniko.com/v1/appointments/343589"}
    }
  ],
  "links": {"self": "https://api.cliniko.com/v1/appointments"}
}
```

Get Deleted Appointments
----------------

**Resources**
* ```GET /appointments/deleted``` get all deleted appointments
* ```GET /businesses/:id/appointments/deleted``` get all deleted for a specified business
* ```GET /practitioners/:id/appointments/deleted``` get all deleted for a specified practitioner
* ```GET /patients/:id/appointments/deleted``` get all deleted appointments for a specified patient

**Example Request**
```shell
curl https://api.cliniko.com/v1/appointments/deleted \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
    "appointments": [
        {
            "id": 8282,
            "deleted_at": "2013-06-05T14:38:48Z"
        }
    ],
    "total_entries": 1,
    "links": {
        "self": "http://api.cliniko.com:3000/v1/businesses/1/appointments/deleted?page=1"
    }
}
```

Get Cancelled Appointments
----------------

**Resources**
* ```GET /appointments/cancelled``` get all cancelled appointments
* ```GET /businesses/:id/appointments/cancelled``` get all cancelled appointments for a specified business
* ```GET /practitioners/:id/appointments/cancelled``` get all cancelled appointments for a specified practitioner
* ```GET /patients/:id/appointments/cancelled``` get all cancelled appointments for a specified patient

**Example Request**
```shell
curl https://api.cliniko.com/v1/appointments/cancelled \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
    "appointments": [
        {
            "cancellation_note": null,
            "cancellation_reason": 10,
            "did_not_arrive": null,
            "email_reminder_sent": false,
            "id": 452,
            "notes": "",
            "online_booking_policy_accepted": null,
            "patient_arrived": false,
            "repeat_rule": {},
            "sms_reminder_sent": false,
            "appointment_end": "2012-05-11T09:15:00Z",
            "appointment_start": "2012-05-11T08:45:00Z",
            "cancellation_time": "2012-05-11T06:21:10Z",
            "created_at": "2012-05-11T04:29:51Z",
            "updated_at": "2012-05-11T06:21:10Z",
            "appointment_type": {
                "links": {
                    "self": "http://api.cliniko.com:3000/v1/appointment_types/21"
                }
            },
            "business": {
                "links": {
                    "self": "http://api.cliniko.com:3000/v1/businesses/11"
                }
            },
            "patient": {
                "links": {
                    "self": "http://api.cliniko.com:3000/v1/patients/130"
                }
            },
            "practitioner": {
                "links": {
                    "self": "http://api.cliniko.com:3000/v1/practitioners/1"
                }
            }
        }
    ],
    "total_entries": 8,
    "links": {
        "next": "http://api.cliniko.com:3000/v1/businesses/1/appointments/cancelled?page=2",
        "self": "http://api.cliniko.com:3000/v1/businesses/1/appointments/cancelled?page=1"
    }
}
```

Get Appointment
------------

**Resources**
* ```GET /appointments/:id``` get a specified appointment

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
  "appointment_end": "2013-03-26T14:00:00Z",
  "appointment_start": "2013-03-26T14:00:00Z",
  "created_at": "2013-03-27T10:03:57Z",
  "did_not_arrive": false,
  "email_reminder_sent": false,
  "id": 1,
  "notes": null,
  "online_booking_policy_accepted": null,
  "patient_arrived": false,
  "repeat_rule": {},
  "sms_reminder_sent": false,
  "updated_at": "2013-03-27T10:03:57Z",
  "appointment_repeated_from" : {
    "links": {"self": "https://api.cliniko.com/v1/appointments/2"}
  },
  "appointment_type": {
    "links": {"self": "https://api.cliniko.com/v1/appointment_types/1"}
  },
  "business": {
    "links": {"self": "https://api.cliniko.com/v1/businesses/1"}
  },
  "patient": {
    "links": {"self": "https://api.cliniko.com/v1/patients/1"}
  },
  "practitioner": {
    "links": {"self": "https://api.cliniko.com/v1/practitioners/1"}
  },
  "links": {"self": "https://api.cliniko.com/v1/appointments/1"}
}
```

Create Appointment
----------------
**Resources**
* ```POST /appointments``` create an appointment

**Example Request**
```shell
curl https://api.cliniko.com/v1/appointments \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -d 'appointment_start=2013-03-26T14:00:00Z&appointment_end=2013-03-26T15:00:00Z&patient_id=1&practitioner_id=1&appointment_type_id=1&business_id=1' \
  -X POST
```
**Example Response**
```
Headers { Location: http://api.cliniko.com/appointments/1 }
```
```json
{
  "appointment_end": "2013-03-26T15:00:00Z",
  "appointment_start": "2013-03-26T14:00:00Z",
  "created_at": "2013-03-27T10:03:57Z",
  "did_not_arrive": false,
  "email_reminder_sent": false,
  "id": 1,
  "notes": null,
  "online_booking_policy_accepted": null,
  "patient_arrived": false,
  "repeat_rule": {},
  "sms_reminder_sent": false,
  "updated_at": "2013-03-27T10:03:57Z",
  "appointment_repeated_from" : {
    "links": {"self": "https://api.cliniko.com/v1/appointments/2"}
  },
  "appointment_type": {
    "links": {"self": "https://api.cliniko.com/v1/appointment_types/1"}
  },
  "business": {
    "links": {"self": "https://api.cliniko.com/v1/businesses/1"}
  },
  "patient": {
    "links": {"self": "https://api.cliniko.com/v1/patients/1"}
  },
  "practitioner": {
    "links": {"self": "https://api.cliniko.com/v1/practitioners/1"}
  },
  "links": {"self": "https://api.cliniko.com/v1/appointments/1"}
}
```

Update Appointment
----------------
**Resources**
* ```PUT /appointments/:id``` update an appointment

**Example Request**
```shell
curl https://api.cliniko.com/v1/appointments/1 \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -d 'appointment_end=2013-03-26T15:00:00Z' \
  -X PUT
```
**Example Response**
```json
{
  "appointment_end": "2013-03-26T15:00:00Z",
  "appointment_start": "2013-03-26T14:00:00Z",
  "created_at": "2013-03-27T10:03:57Z",
  "did_not_arrive": false,
  "email_reminder_sent": false,
  "id": 1,
  "notes": null,
  "online_booking_policy_accepted": null,
  "patient_arrived": false,
  "repeat_rule": {},
  "sms_reminder_sent": false,
  "updated_at": "2013-03-27T10:03:57Z",
  "appointment_repeated_from" : {
    "links": {"self": "https://api.cliniko.com/v1/appointments/2"}
  },
  "appointment_type": {
    "links": {"self": "https://api.cliniko.com/v1/appointment_types/1"}
  },
  "business": {
    "links": {"self": "https://api.cliniko.com/v1/businesses/1"}
  },
  "patient": {
    "links": {"self": "https://api.cliniko.com/v1/patients/1"}
  },
  "practitioner": {
    "links": {"self": "https://api.cliniko.com/v1/practitioners/1"}
  },
  "links": {"self": "https://api.cliniko.com/v1/appointments/1"}
}
```

Delete Appointment
----------------
**Resources**
* ```DELETE /appointments/:id``` delete an appointment

**Example Request**
```shell
curl https://api.cliniko.com/v1/appointments/1 \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -X DELETE
```
**Example Response**  
A status code of `204 no content` will be returned if successful

