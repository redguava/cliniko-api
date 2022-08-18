# Settings

- [Get Settings](#get-settings 'This returns all settings.')
- [Get Public Settings](#get-public-settings 'This returns settings that are viewable by any user.')

## Get Settings

**Resources**

- `GET /settings` Get all settings. This route is only accessible to users with a role that can view settings.

**Example Request**

```shell
curl https://api.us1.cliniko.com/v1/settings \
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
    "id": 123,
    "name": "Bins, Boehm and Baumbach",
    "country": "United States",
    "time_zone": "Eastern Time (US & Canada)",
    "currency_symbol": "$",
    "subdomain": "example",
    "email_from": "admin@example.com",
    "admin": {
      "email": "admin@example.com",
      "first_name": "Tim",
      "last_name": "Decker"
    }
  },
  "calendar": {
    "start_hour": 0,
    "end_hour": 24,
    "timeslot_height_in_pixels": 15,
    "timeslot_size_in_minutes": 15,
    "show_current_time_indicator": true,
    "multiple_appointments_gap": false
  },
  "online_bookings": {
    "adroll": {
      "advertiser_id": "XXXXXY",
      "pixel_id": "YYYYYYX"
    },
    "calendar_info": "pick a time!",
    "enabled": true,
    "google_analytics": {
      "tracking_id": "UA-XXXXXXX-Y"
    },
    "logo_url": null,
    "max_appointments_per_day_segment": 5,
    "min_hours_advance_required_to_book": 2,
    "min_hours_notice_for_patient_cancellation": 0,
    "notify_practitioner_by_email": true,
    "notify_practitioner_by_sms": true,
    "policy": "be cool",
    "practitioner_order": [1, 2, 3],
    "require_patient_address": false,
    "show_appointment_duration": true,
    "show_prices": false
  },
  "patient_custom_fields_definition": {
    "sections": [
      {
        "name": "Insurance coverage",
        "token": "ef4c43ec-105d-489c-88cc-0f3c5f67dc70",
        "fields": [
          {
            "name": "Provider",
            "type": "radiobuttons",
            "other": {
              "enabled": true
            },
            "token": "b16839e0-26a4-48d6-83d6-36658e357c81",
            "options": [
              {
                "name": "Great Insurance",
                "token": "944e2fe0-6730-42fd-b9a2-519f35ceb46a"
              },
              {
                "name": "Super Insurance",
                "token": "d656a93c-a0b6-43ea-ab50-06fd1a00ea44"
              }
            ]
          },
          {
            "name": "Policy number" ,
            "type": "text",
            "token": "fdb9c8a0-2984-4d96-8dc1-fbe703a8afdb"
          }
        ]
      }
    ]
  },
  "reminders": {
    "default_reminder_type": "SMS & Email"
  },
  "links": {
    "self": "https://api.us1.cliniko.com/v1/settings/public"
  }
}
```

## Get Public Settings

**Resources**

- `GET /settings/public` Get only public settings. This route is accessible to any authenticated user.

**Example Request**

```shell
curl https://api.us1.cliniko.com/v1/settings/public \
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
    "id": 123,
    "name": "Bins, Boehm and Baumbach",
    "country": "United States",
    "time_zone": "Eastern Time (US & Canada)",
    "currency_symbol": "$",
    "subdomain": "example"
  },
  "calendar": {
    "start_hour": 0,
    "end_hour": 24,
    "timeslot_height_in_pixels": 15,
    "timeslot_size_in_minutes": 15,
    "show_current_time_indicator": true,
    "multiple_appointments_gap": false
  },
  "online_bookings": {
    "calendar_info": "pick a time!",
    "enabled": true,
    "logo_url": null,
    "max_appointments_per_day_segment": 5,
    "min_hours_advance_required_to_book": 2,
    "min_hours_notice_for_patient_cancellation": 0,
    "notify_practitioner_by_email": true,
    "notify_practitioner_by_sms": true,
    "policy": "be cool",
    "practitioner_order": [1, 2, 3],
    "require_patient_address": false,
    "show_appointment_duration": true,
    "show_prices": false
  },
  "patient_custom_fields_definition": {
    "sections": [
      {
        "name": "Insurance coverage",
        "token": "ef4c43ec-105d-489c-88cc-0f3c5f67dc70",
        "fields": [
          {
            "name": "Provider",
            "type": "radiobuttons",
            "other": {
              "enabled": true
            },
            "token": "b16839e0-26a4-48d6-83d6-36658e357c81",
            "options": [
              {
                "name": "Great Insurance",
                "token": "944e2fe0-6730-42fd-b9a2-519f35ceb46a"
              },
              {
                "name": "Super Insurance",
                "token": "d656a93c-a0b6-43ea-ab50-06fd1a00ea44"
              }
            ]
          },
          {
            "name": "Policy number" ,
            "type": "text",
            "token": "fdb9c8a0-2984-4d96-8dc1-fbe703a8afdb"
          }
        ]
      }
    ]
  },
  "reminders": {
    "default_reminder_type": "SMS & Email"
  },
  "links": {
    "self": "https://api.us1.cliniko.com/v1/settings/public"
  }
}
```
