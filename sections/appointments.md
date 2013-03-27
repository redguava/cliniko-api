Appointments
========

Get appointments
------------

* `GET /appointments` will return all appointments.

```json
{
  "appointments": [
    {
      "appointment_end": "2013-03-26T14:00:00Z",
      "appointment_start": "2013-03-26T14:00:00Z",
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
      "links": {"self": "https://api.cliniko.com/v1/appointments/343589"},
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
      }
    }
  ],
  "links": {"self": "https://api.cliniko.com/v1/appointments"}
}
```
