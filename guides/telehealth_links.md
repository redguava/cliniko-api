# Telehealth links
On _most_ appointment endpoints (`/bookings`, `/individual_appointments`, `/attendees`), we've added a new property to the response payload: `telehealth_url` (group appointments aren't yet supported).

On the `/appointments` and `/individual_appointments` endpoints, the `telehealth_url` link **is only for the practitioner or an account administrator**. This link is not for patients. In other words, that link will only get an authenticated practitioner/administrator into the Telehealth appointment.

In this example, the link generated is for practitioner or administrator use only. It's a fairly stock-standard URL.
```json
GET /individual_appointments/987654321

{
  "id": "987654321",
  "telehealth_url": "https://subdomain.cliniko.com/appointments/987654321/connect",
  "attendees": {
    "link": "https://api.au1.cliniko.com/v1/individual_appointments/987654321/attendees"
  }
}
```

The patient's link can be found on the `/attendees` endpoint (or nested `/attendees` endpointa). It is also named `telehealth_url`., but it's format is quite different. We needed these to be short(-ish) and unguessable. Please also be careful with this link - the patient link will work for _anyone who has the link_. Patients do not need to be authenticated in Cliniko to attend their Telehealth appointment.
```json
GET /individual_appointments/987654321/attendees

{
  "id": "123456789",
  "telehealth_url": "https://subdomain.cliniko.com/c/yxt65-xdR864MNvao"
}
```

Now here's the trick. Telehealth is only available for an appointment **if the corresponding appointment type has Telehealth switched on**. But, we are sending a populated `telehealth_url` property in **every response**, regardless of the appointment type's Telehealth status. That is, even if the appointment's appointment type is not for Telehealth, you will still get a valid-looking URL in that property. If you follow it however, Cliniko will let you know that no Telehealth session is available for that appointment. We appreciate that this isn't the most straightforward way to do this, but there's a strong technical reason we are including Telehealth links in appointments that are not for Telehealth.

As you can imagine, A LOT of appointments are booked in Cliniko on a daily basis. We run a cache in front of our database that handles the bulk of API requests for appointments, from both external (ie. you) and internal (ie. Cliniko) clients. If we removed or nullified the `telehealth_url` property from appointments each time the appointment type's Telehealth status was changed, we'd have to regularly invalidate and reload that cache. That'd result in continuous spikes in Cliniko's DB load, which has significant flow on effects, both to API clients and users of the web app itself. So we didn't want to do that.

The TL;DR for that is: all appointments _could be_ Telehealth if their appointment type was flagged as such, and this way it means we don't have to run workers to go back over appointment records changing their Telehealth link values when the appointment type is changed.

For API integrators, it just means that if your app is sending out Telehealth links sourced from the Cliniko API, you need to double-check that the appointment type for the appointment also has Telehealth switched on. If it doesn't, you probably don't want to send the Telehealth link.
