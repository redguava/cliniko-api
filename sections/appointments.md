Appointments
============
* [Get Appointments](#get-appointments "This will return all appointments.")
* [Get Deleted Appointments](#get-deleted-appointments "This will return all deleted appointments ID's only")
* [Get Cancelled Appointments](#get-cancelled-appointments "This will return all cancelled appointments.")
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
      "created_at": "2013-03-27T10:03:57Z",
      "did_not_arrive": false,
      "email_reminder_sent": false,
      "id": 343589,
      "invoice_status": 10,
      "notes": null,
      "online_booking_policy_accepted": null,
      "patient_arrived": false,
      "repeat_rule": {"repeat_type": "Daily", "number_of_repeats": 3, "repeating_interval": 3},
      "sms_reminder_sent": false,
      "treatment_note_status": 90,
      "updated_at": "2013-03-27T10:03:57Z",
      "deleted_at": null,
      "cancellation_time": null,
      "cancellation_note": null,
      "cancellation_reason": null,
      "booking_ip_address": '123.456.78.90',
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
      "invoices": {
        "links": {
          "self": "https://api.cliniko.com/v1/appointments/343589/invoices?page=1"
        }
      },
      "links": {"self": "https://api.cliniko.com/v1/appointments/343589"}
    }
  ],
  "total_entries": 1,
  "links": {"self": "https://api.cliniko.com/v1/appointments?page=1"}
}
```

Get Deleted Appointments
----------------

**Resources**
* ```GET /appointments/deleted``` get all deleted appointments
* ```GET /businesses/:id/appointments/deleted``` get all deleted appointments for a specified business
* ```GET /practitioners/:id/appointments/deleted``` get all deleted appointments for a specified practitioner
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
      "appointment_end": "2013-03-26T14:00:00Z",
      "appointment_start": "2013-03-26T14:00:00Z",
      "created_at": "2013-03-27T10:03:57Z",
      "did_not_arrive": false,
      "email_reminder_sent": false,
      "id": 343589,
      "invoice_status": 10,
      "notes": null,
      "online_booking_policy_accepted": null,
      "patient_arrived": false,
      "repeat_rule": {"repeat_type": "Daily", "number_of_repeats": 3, "repeating_interval": 3},
      "sms_reminder_sent": false,
      "treatment_note_status": 90,
      "updated_at": "2013-03-27T10:03:57Z",
      "deleted_at": "2013-06-05T14:38:48Z",
      "cancellation_time": null,
      "cancellation_note": null,
      "cancellation_reason": null,
      "booking_ip_address": '123.456.78.90',
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
      "invoices": {
        "links": {
          "self": "https://api.cliniko.com/v1/appointments/343589/invoices?page=1"
        }
      },
      "links": {"self": "https://api.cliniko.com/v1/appointments/343589"}
    }
  ],
  "total_entries": 1,
  "links": {"self": "http://api.cliniko.com/v1/businesses/1/appointments/deleted?page=1"}
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
      "appointment_end": "2013-03-26T14:00:00Z",
      "appointment_start": "2013-03-26T14:00:00Z",
      "created_at": "2013-03-27T10:03:57Z",
      "did_not_arrive": false,
      "email_reminder_sent": false,
      "id": 343589,
      "invoice_status": 10,
      "notes": null,
      "online_booking_policy_accepted": null,
      "patient_arrived": false,
      "repeat_rule": {"repeat_type": "Daily", "number_of_repeats": 3, "repeating_interval": 3},
      "sms_reminder_sent": false,
      "treatment_note_status": 90,
      "updated_at": "2013-03-27T10:03:57Z",
      "deleted_at": null,
      "cancellation_time": "2012-05-11T06:21:10Z",
      "cancellation_note": null,
      "cancellation_reason": 10,
      "booking_ip_address": '123.456.78.90',
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
      "invoices": {
        "links": {
          "self": "https://api.cliniko.com/v1/appointments/343589/invoices?page=1"
        }
      },
      "links": {"self": "https://api.cliniko.com/v1/appointments/343589"}
    }
  ],
  "total_entries": 1,
  "links": {"self": "http://api.cliniko.com/v1/businesses/1/appointments/cancelled?page=1"}
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
  "id": 343589,
  "invoice_status": 10,
  "notes": null,
  "online_booking_policy_accepted": null,
  "patient_arrived": false,
  "repeat_rule": {"repeat_type": "Daily", "number_of_repeats": 3, "repeating_interval": 3},
  "sms_reminder_sent": false,
  "treatment_note_status": 90,
  "updated_at": "2013-03-27T10:03:57Z",
  "deleted_at": null,
  "cancellation_time": null,
  "cancellation_note": null,
  "cancellation_reason": null,
  "booking_ip_address": '123.456.78.90',
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
  "invoices": {
    "links": {
      "self": "https://api.cliniko.com/v1/appointments/343589/invoices?page=1"
    }
  },
  "links": {"self": "https://api.cliniko.com/v1/appointments/343589"}
}
```

Create Appointment
----------------
**Resources**
* ```POST /appointments``` create an appointment

**Notes**

If not provided, the appointment_end is automatically set based upon the duration of the appointment_type.

**Example Request**
```shell
curl https://api.cliniko.com/v1/appointments \
  -u API_KEY: \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -d '{ "appointment_start": "2015-01-21T04:00:00Z", "patient_id": "1", "practitioner_id": "1", "appointment_type_id": "1", "business_id": "1" }' \
  -X POST
```
**Example Response**
```
Headers { Location: http://api.cliniko.com/appointments/1 }
```
```json
{
  "appointment_end": "2013-03-26T14:00:00Z",
  "appointment_start": "2013-03-26T14:00:00Z",
  "created_at": "2013-03-27T10:03:57Z",
  "did_not_arrive": false,
  "email_reminder_sent": false,
  "id": 343589,
  "invoice_status": 10,
  "notes": null,
  "online_booking_policy_accepted": null,
  "patient_arrived": false,
  "repeat_rule": {"repeat_type": "Daily", "number_of_repeats": 3, "repeating_interval": 3},
  "sms_reminder_sent": false,
  "treatment_note_status": 90,
  "updated_at": "2013-03-27T10:03:57Z",
  "deleted_at": null,
  "cancellation_time": null,
  "cancellation_note": null,
  "cancellation_reason": null,
  "booking_ip_address": '123.456.78.90',
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
  "invoices": {
    "links": {
      "self": "https://api.cliniko.com/v1/appointments/343589/invoices?page=1"
    }
  },
  "links": {"self": "https://api.cliniko.com/v1/appointments/343589"}
}
```

Update Appointment
----------------
**Resources**
* ```PUT /appointments/:id``` update an appointment

**Notes**

If not provided, the appointment_end is automatically set based upon the duration of the appointment_type.

**Example Request**
```shell
curl https://api.cliniko.com/v1/appointments/1 \
  -u API_KEY: \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -d '{ "appointment_end": "2015-01-21T05:00:00Z" }' \
  -X PUT
```
**Example Response**
```json
{
  "appointment_end": "2013-03-26T14:00:00Z",
  "appointment_start": "2013-03-26T14:00:00Z",
  "created_at": "2013-03-27T10:03:57Z",
  "did_not_arrive": false,
  "email_reminder_sent": false,
  "id": 343589,
  "invoice_status": 10,
  "notes": null,
  "online_booking_policy_accepted": null,
  "patient_arrived": false,
  "repeat_rule": {"repeat_type": "Daily", "number_of_repeats": 3, "repeating_interval": 3},
  "sms_reminder_sent": false,
  "treatment_note_status": 90,
  "updated_at": "2013-03-27T10:03:57Z",
  "deleted_at": null,
  "cancellation_time": null,
  "cancellation_note": null,
  "cancellation_reason": null,
  "booking_ip_address": '123.456.78.90',
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
  "invoices": {
    "links": {
      "self": "https://api.cliniko.com/v1/appointments/343589/invoices?page=1"
    }
  },
  "links": {"self": "https://api.cliniko.com/v1/appointments/343589"}
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

Filtering Appointments
----------------

For any route that returns a set of appointments, you can filter them by:
* ```appointment_start``` DateTime
* ```appointment_type_id``` Integer
* ```business_id``` Integer
* ```id``` Integer
* ```patient_id``` Integer
* ```practitioner_id``` Integer
* ```updated_at``` DateTime

See [Filtering Results](https://github.com/redguava/cliniko-api#filtering-results) for details on how to apply filters.
