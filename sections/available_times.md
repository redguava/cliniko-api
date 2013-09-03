Available Times
============
> Available Times are appointment start times that are currently available for the practitioner based on the parameters provided.

* [Get Available Times](#get-available-times "This will return all available times")

Get Available Times
----------------

**Resources**

Get all available times
``` 
GET /businesses/:business_id/practitioners/:practitioner_id/appointment_types/:appointment_type_id/available_times?from=DATE&to=DATE 
```

**Required Parameters**

There are two parameters required, these form the time frame of available times requested:
* `from` the start date of the time frame (search starts from the beginning of that day in the cliniko account's time zone) 
* `to`   the end date of the time frame (search ends at the end of that day in the cliniko account's time zone)

`from` and `to` cannot be more than 7 days apart (ie. the maximum time period you can request is 7 days) 

`from` and `to` cannot be older than the current date in the cliniko account's time zone.


**Example Request**
```shell
curl https://api.cliniko.com/v1/businesses/1/practitioners/1/ \
appointment_types/1/available_times?from=2013-05-21&to=2013-05-22 \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "available_times": [
    { "appointment_start" : "2013-05-21T08:45:00Z" }
  ],
  "total_entries": 1,
  "links": {"self": "/businesses/1/practitioners/1/appointment_types/1/available_times?from=2013-05-21&to=2013-05-22&page=1"}
}

```

**IMPORTANT EXTRA INFORMATION**

Cliniko users can configure how available times are displayed in our online bookings module.  

This API endpoint that retrieves available times will respect these settings.  The settings are:

* **Maximum number of appointments per day segment**

    Day parts are morning (before Midday), afternoon (Midday to 5pm) and evening (5pm onwards).  

    Possible settings are; 1, 2, 3, 4, 5 or unlimited.
    
* **Minimum advance time required for online bookings**

    This is the minimum amount of time from now that a available time will be shown.

    Possible settings are; Now, 1 Hour, 2 Hours, 4 Hours, Tomorrow or 2 Days.
    
* **Business to be displayed in online bookings**

    Setting to choose which businesses can be displayed in our online bookings module. 
    
    The API will not return available times for businesses not enabled for online bookings.
    
* **Appointment Type to be displayed in online bookings**

    Setting to choose which appointment types can be displayed in our online bookings module. 
    
    The API will not return available times for appointment types not enabled for online bookings.
    
* **Practitioner to be displayed in online bookings**

    Setting to choose which practitioners can be displayed in our online bookings module. 
    
    The API will not return available times for practitioners not enabled for online bookings.
