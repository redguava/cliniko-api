Appointments
============
* [Get Appointments](#get-appointments "This will return all appointments.")
* [Get Appointment](#get-appointment "This will return a specified appointment.")

Get Appointments
----------------

**Resources**
* ```GET /appointments``` get all appointments
* **COMING SOON:** ```GET /businesses/:id/appointments``` get all appointments for a specified business 
* **COMING SOON:** ```GET /practitioners/:id/appointments``` get all appointments for a specified practitioner

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
      "cancellation_note": null,
      "cancellation_reason" :null,
      "cancellation_time" :null,
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
  "cancellation_note": null,
  "cancellation_reason" :null,
  "cancellation_time" :null,
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
