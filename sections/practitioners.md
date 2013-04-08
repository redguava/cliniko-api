Practitioners (COMING SOON)
============
> All practitioners have an associated user account.  Not all users are practitioners (eg. receptionists wouldn't be).
>
> You can only create appointments for practitioners (not for users).

* [Get Practitioners](#get-practitioners "This will return all practitioners.")
* [Get Practitioner](#get-practitioner "This will return a specified practitioner.")

Get Practitioners
----------------

**Resources**
* ```GET /practitioners``` get all practitioners

**Example Request**
```shell
curl https://api.cliniko.com/v1/practitioners \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "practitioners": [
    {
      "title": "Mr",
      "first_name": "Randy",
      "last_name": "Savage",
      "designation": "Osteopath",
      "show_in_online_bookings": true,
      "id": 1,
      "created_at": "2013-03-26T14:00:00Z",
      "updated_at": "2013-03-26T14:00:00Z",
      "default_appointment_type": {
        "links": {"self": "https://api.cliniko.com/v1/appointment_types/1"}
      },
      "links": {"self": "https://api.cliniko.com/v1/practitioners/1"}
    }
  ],
  "links": {"self": "https://api.cliniko.com/v1/practitioners"}
}
```

Get Practitioner
------------

**Resources**
* ```GET /practitioners/:id``` get a specified practitioner

**Example Request**
```shell
curl https://api.cliniko.com/v1/practitioners/1 \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "title": "Mr",
  "first_name": "Randy",
  "last_name": "Savage",
  "designation": "Osteopath",
  "show_in_online_bookings": true,
  "id": 1,
  "created_at": "2013-03-26T14:00:00Z",
  "updated_at": "2013-03-26T14:00:00Z",
  "default_appointment_type": {
    "links": {"self": "https://api.cliniko.com/v1/appointment_types/1"}
  },
  "links": {"self": "https://api.cliniko.com/v1/practitioners/1"}
}
```
