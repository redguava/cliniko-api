Appointments
========

Get appointments
------------

* `GET /appointments` will return all appointments.

```json
[
  {
    "appointment_end": "2013-03-26T14:00:00+11:00",
    "appointment_start": "2013-03-26T14:00:00+11:00",
    "cancellation_reason" :null,
    "cancellation_time" :null,
    "created_at": "2013-03-27T10:03:57+11:00",
    "did_not_arrive": false,
    "email_reminder_sent": false,
    "id": 343589,
    "notes": null,
    "online_booking_policy_accepted": null,
    "patient_arrived": false,
    "repeat_rule": {},
    "sms_reminder_sent": false,
    "updated_at": "2013-03-27T10:03:57+11:00",
    "links": {"self": "http://api.cliniko.com/v1/appointments/343589"}
  }
]
```
