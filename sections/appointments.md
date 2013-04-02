Appointments
============
* [Get Appointments](#get-appointments "This will return all appointments.")
* [Get Appointment](#get-appointment "This will return a specified appointment.")

Get Appointments
----------------

This will return all appointments.

**Resource**
```
GET /appointments
```

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
      "repeat_rule": {},
      "sms_reminder_sent": false,
      "updated_at": "2013-03-27T10:03:57Z",
      "patient": {
        "id": 12345,
        "title": "Mr",
        "first_name": "Hulk",
        "last_name": "Hogan",
        "links": {"self": "https://api.cliniko.com/v1/patients/12345"}
      },
      "appointment_type": {
        "id": 12345,
        "name": "Initial Consultation",
        "color": "#00FF00",
        "category": "Osteopathy",
        "links": {"self": "https://api.cliniko.com/v1/appointment_types/12345"}
      },
      "business": {
        "id": 45678,
        "business_name": "Melbourne Osteopathy",
        "links": {"self": "https://api.cliniko.com/v1/businesses/45678"}
      },
      "practitioner": {
        "id": 1,
        "title": "Mr",
        "first_name": "Randy",
        "last_name": "Savage",
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

This will return the specified appointment.

**Resource**
```
GET /appointments/:id
```

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
  "patient": {
    "id": 1,
    "title": "Mr",
    "first_name": "Hulk",
    "last_name": "Hogan",
    "links": {"self": "https://api.cliniko.com/v1/patients/1"}
  },
  "appointment_type": {
    "id": 1,
    "name": "Initial Consultation",
    "color": "#00FF00",
    "category": "Osteopathy",
    "links": {"self": "https://api.cliniko.com/v1/appointment_types/1"}
  },
  "business": {
    "id": 1,
    "business_name": "Melbourne Osteopathy",
    "links": {"self": "https://api.cliniko.com/v1/businesses/1"}
  },
  "practitioner": {
    "id": 1,
    "title": "Mr",
    "first_name": "Randy",
    "last_name": "Savage",
    "links": {"self": "https://api.cliniko.com/v1/practitioners/1"}
  },
  "links": {"self": "https://api.cliniko.com/v1/appointments/1"}
}
```
