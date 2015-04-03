Settings
============

* [Get Settings](#get-settings "This returns all settings.")
* [Get Public Settings](#get-public-settings "This returns settings that are viewable by any user.")

Get Settings
----------------

**Resources**
* ```GET /settings``` Get all settings. This route is only accessible to users with a role that can view settings.

**Example Request**
```shell
curl https://api.cliniko.com/v1/settings \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "terminology": {
    "patient": "client"
  },
  "account": {
    "name": "Bins, Boehm and Baumbach",
    "country": "United States",
    "time_zone": "Eastern Time (US & Canada)"
  },
  "calendar": {
    "timeslot_size_in_minutes": 15
  },
  "online_bookings": {
    "enabled": true,
    "policy": "be cool",
    "calendar_info": "pick a time!"
  }
}
```

Get Public Settings
------------

**Resources**
* ```GET /settings/public``` Get only public settings. This route is accessible to any authenticated user.

**Example Request**
```shell
curl https://api.cliniko.com/v1/settings/public \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "terminology": {
    "patient": "client"
  },
  "account": {
    "name": "Bins, Boehm and Baumbach",
    "country": "United States",
    "time_zone": "Eastern Time (US & Canada)"
  },
  "calendar": {
    "timeslot_size_in_minutes": 15
  }
}
```
