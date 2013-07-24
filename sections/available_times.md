Available Times
============
> Available Times is array of DateTime objects that result from a search of available time slots using the following mandatory filters:
>
* Appointment Type
* Practitioner
* Business
* [Time Frame](#time-frame)*
>

* [Get Available Times](#get-available-times "This will return all future available times for which meet specified criteria")

Get Available Times
----------------

**Resources**
* ```GET /businesses/:business_id/practitioners/:practitioner_id/appointment_types/:appointment_type_id/available_times?from=DATETIME&to=DATETIME```
get all available times for selected appointment type, practitioner and business within a specified time frame

**Example Request**
```shell
curl https://api.cliniko.com/v1/businesses/45678/practitioners/1/appointment_types/1/available_times?from=2012-05-11T08:00:00Z&to=2012-05-12T10:00:00Z \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "available_times": [
    { "appointment_start" : "2012-05-11T08:45:00Z" },
    { "appointment_start": "2012-05-11T09:45:00Z" }
  ],
  "total_entries": 1,
  "links": {"self": "/businesses/45678/practitioners/1/appointment_types/1/available_times?from=2012-05-11T08:00:00Z&to=2012-05-12T10:00:00Z"}
}

```

Time Frame*
----------------

Using 'from' and 'to' parameters you specify the beginning and end of a time frame.

The time difference between the 'from' and 'to' parameters should not be longer than 7 days.

Time Frame parameters have to be specified in UTC – e.g. 2014-08-30T18:00:00Z