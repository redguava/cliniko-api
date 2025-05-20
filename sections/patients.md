# Patients

> Patients are the people that book in for appointments. There isn't much in
> Cliniko that doesn't revolve around patients.
>
> When you're working with patient information, make sure you abide by the
> relevant regulations for security and privacy.
>
> A couple of fields in the patient record deserve special consideration:
>
> - **accepted_privacy_policy** stores the patient's consent to the business'
> own privacy policy. Values can be `null` (no response), `true` (accepted) or
> `false` (rejected). Please consider how this may affect you storing
> information on this patient.
>
> - **time_zone** will contain a valid IANA time zone identifier if the
>   patient's time zone has been set, or `null` if it hasn't. It can be set via
>   the API, in which case it accepts IANA time zone identifiers.
>

- [Get Patients](#get-patients 'This will return all patients.')
- [Get Deleted Patients](#get-deleted-patients 'This will return all deleted patients.')
- [Get Archived Patients](#get-archived-patients 'This will return all archived patients.')
- [Get Patient](#get-patient 'This will return a specified patient.')
- [Create Patient](#create-patient 'This will create a patient.')
- [Update Patient](#update-patient 'This will update a patient.')
- [Archive Patient](#archive-patient 'This will archive a patient.')
- [Unarchive Patient](#unarchive-patient 'This will unarchive a patient.')

## Get Patients

**Resources**

- `GET /patients` get all patients

**Example Request**

```shell
curl https://api.au1.cliniko.com/v1/patients \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**

```json
{
  "patients": [
    {
      "accepted_privacy_policy": true,
      "accepted_email_marketing": true,
      "accepted_sms_marketing": false,
      "address_1": "1 Smith Street",
      "address_2": "",
      "address_3": "",
      "archived_at": "",
      "city": "Melbourne",
      "country": "Australia",
      "created_at": "2013-03-26T14:00:00Z",
      "custom_fields": {
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
                    "token": "d656a93c-a0b6-43ea-ab50-06fd1a00ea44",
                    "selected": true
                  }
                ]
              },
              {
                "name": "Policy number" ,
                "type": "text",
                "token": "fdb9c8a0-2984-4d96-8dc1-fbe703a8afdb",
                "value": "ABC-12345"
              }
            ]
          }
        ]
      },
      "dva_card_number": "",
      "date_of_birth": "2001-05-26",
      "deleted_at": "",
      "email": "peter@example.com",
      "emergency_contact": "",
      "first_name": "Peter",
      "invoice_default_to": "Super Insurance",
      "invoice_email": "super.insurance@example.com",
      "invoice_extra_information": "Insurance #123456\r\nClaim #123456",
      "gender": "Male",
      "gender_identity": "Transgender",
      "id": 1,
      "last_name": "Patientman",
      "medicare": "",
      "medicare_reference_number": "",
      "notes": "",
      "appointment_notes": "",
      "occupation": "",
      "old_reference_id": "",
      "patient_phone_numbers": [],
      "post_code": "3000",
      "preferred_first_name": "Pete",
      "pronouns": null,
      "receives_confirmation_emails": true,
      "referral_source": "",
      "reminder_type": "SMS & Email",
      "sex": "Female to Male",
      "state": "Victoria",
      "title": "Mr",
      "time_zone": "Australia/Melbourne",
      "updated_at": "2013-03-26T14:00:00Z",
      "concession_type": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/concession_types/123"
        }
      },
      "referring_doctor": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/contacts/123"
        }
      },
      "patient_phone_numbers": [
        {
          "phone_type": "Mobile",
          "number": "61444444444"
        },
        {
          "phone_type": "Home",
          "number": "61399999999"
        }
      ],
      "medical_alerts": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/patients/1/medical_alerts?page=1"
        }
      },
      "invoices": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/patients/1/invoices?page=1"
        }
      },
      "appointments": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/patients/1/appointments?page=1"
        }
      },
      "links": { "self": "https://api.au1.cliniko.com/v1/patients/1" }
    }
  ],
  "total_entries": 1,
  "links": { "self": "https://api.au1.cliniko.com/v1/patients?page=1" }
}
```

## Get Deleted Patients

**Resources**

- `GET /patients/deleted` get all deleted patients

**Example Request**

```shell
curl https://api.au1.cliniko.com/v1/patients/deleted \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**

```json
{
  "patients": [
    {
      "deleted_at": "2013-06-05T14:38:48Z",
      "links": { "self": "https://api.au1.cliniko.com/v1/patients/1" }
    }
  ],
  "total_entries": 1,
  "links": { "self": "https://api.au1.cliniko.com/v1/patients/deleted?page=1" }
}
```

## Get Archived Patients

**Resources**

- `GET /patients/archived` get all archived patients

**Example Request**

```shell
curl https://api.au1.cliniko.com/v1/patients/archived \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**

```json
{
  "patients": [
    {
      "accepted_privacy_policy": true,
      "accepted_email_marketing": true,
      "accepted_sms_marketing": false,
      "address_1": "1 Smith Street",
      "address_2": "",
      "address_3": "",
      "archived_at": "2013-06-05T14:37:18Z",
      "city": "Melbourne",
      "country": "Australia",
      "created_at": "2013-03-26T14:00:00Z",
      "custom_fields": null,
      "date_of_birth": "2001-05-26",
      "deleted_at": "",
      "dva_card_number": "",
      "email": "peter@example.com",
      "emergency_contact": "",
      "first_name": "Peter",
      "invoice_default_to": "Super Insurance",
      "invoice_email": "super.insurance@example.com",
      "invoice_extra_information": "Insurance #123456\r\nClaim #123456",
      "gender": "Male",
      "gender_identity": "Transgender",
      "id": 1,
      "last_name": "Patientman",
      "medicare": "",
      "medicare_reference_number": "",
      "merged_at": "2013-06-05T14:37:18Z",
      "merged_with_patient": {
        "links": {
          "self": "https://api.au1.cliniko.test/v1/patients/1001"
        }
      },
      "notes": "",
      "appointment_notes": "",
      "occupation": "",
      "old_reference_id": "",
      "patient_phone_numbers": [],
      "post_code": "3000",
      "preferred_first_name": "Pete",
      "pronouns": null,
      "receives_confirmation_emails": true,
      "referral_source": "",
      "reminder_type": "SMS",
      "sex": "Female to Male",
      "state": "Victoria",
      "title": "Mr",
      "time_zone": "Australia/Melbourne",
      "updated_at": "2013-03-26T14:00:00Z",
      "concession_type": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/concession_types/123"
        }
      },
      "referring_doctor": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/contacts/123"
        }
      },
      "patient_phone_numbers": [
        {
          "phone_type": "Mobile",
          "number": "61444444444"
        },
        {
          "phone_type": "Home",
          "number": "61399999999"
        }
      ],
      "medical_alerts": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/patients/1/medical_alerts?page=1"
        }
      },
      "invoices": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/patients/1/invoices?page=1"
        }
      },
      "appointments": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/patients/1/appointments?page=1"
        }
      },
      "links": { "self": "https://api.au1.cliniko.com/v1/patients/1" }
    }
  ],
  "total_entries": 1,
  "links": { "self": "https://api.au1.cliniko.com/v1/patients/archived?page=1" }
}
```

## Get Patient

**Resources**

- `GET /patients/:id` get a specified patient

**Example Request**

```shell
curl https://api.au1.cliniko.com/v1/patients/1 \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**

```json
{
  "accepted_privacy_policy": true,
  "accepted_email_marketing": true,
  "accepted_sms_marketing": false,
  "address_1": "1 Smith Street",
  "address_2": "",
  "address_3": "",
  "archived_at": "",
  "city": "Melbourne",
  "country": "Australia",
  "created_at": "2013-03-26T14:00:00Z",
  "custom_fields": {
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
                "token": "d656a93c-a0b6-43ea-ab50-06fd1a00ea44",
                "selected": true
              }
            ]
          },
          {
            "name": "Policy number" ,
            "type": "text",
            "token": "fdb9c8a0-2984-4d96-8dc1-fbe703a8afdb",
            "value": "ABC-12345"
          }
        ]
      }
    ]
  },
  "date_of_birth": "2001-05-26",
  "deleted_at": "",
  "email": "peter@example.com",
  "emergency_contact": "",
  "first_name": "Peter",
  "invoice_default_to": "Super Insurance",
  "invoice_email": "super.insurance@example.com",
  "invoice_extra_information": "Insurance #123456\r\nClaim #123456",
  "gender": "Male",
  "gender_identity": "Transgender",
  "id": 1,
  "last_name": "Patientman",
  "medicare": "",
  "medicare_reference_number": "",
  "notes": "",
  "appointment_notes": "",
  "occupation": "",
  "old_reference_id": "",
  "patient_phone_numbers": [],
  "post_code": "3000",
  "preferred_first_name": "Pete",
  "pronouns": null,
  "receives_confirmation_emails": true,
  "referral_source": "",
  "reminder_type": "None",
  "sex": "Female to Male",
  "state": "Victoria",
  "title": "Mr",
  "time_zone": "Australia/Melbourne",
  "updated_at": "2013-03-26T14:00:00Z",
  "concession_type": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/concession_types/123"
    }
  },
  "referring_doctor": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/contacts/123"
    }
  },
  "patient_phone_numbers": [
    {
      "phone_type": "Mobile",
      "number": "61444444444"
    },
    {
      "phone_type": "Home",
      "number": "61399999999"
    }
  ],
  "medical_alerts": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/patients/1/medical_alerts?page=1"
    }
  },
  "invoices": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/patients/1/invoices?page=1"
    }
  },
  "appointments": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/patients/1/appointments?page=1"
    }
  },
  "links": { "self": "https://api.au1.cliniko.com/v1/patients/1" }
}
```

## Create Patient

> As of 2018-12-03, `gender` is now deprecated. Instead, the `/patients` API endpoint will now expose and accept the new `gender_identity` and `sex` properties.
> The `/patients` endpoint will continue to return a patient's gender, but you may only use the new properties when _creating_ or _updating_ patients. Note that we are not serving the current value of `gender` in either of the new fields - these need to be updated separately, either through the Cliniko UI, or through the API.
> Find more on why we've made this switch here: [Changes coming to patient gender and sex](https://groups.google.com/a/redguava.com.au/forum/#!topic/cliniko-api/H5fXFk_MH98)

**Validation**

Patient records must have a `first_name` and `last_name`. `email`, if supplied, is validated using the following RegEx in Ruby:
```ruby
/\A[A-Z0-9!#$%&'\*+-\/=?^_`{\|}~]+@[A-Z0-9.-]+\.[A-Z]{2,63}\z/i
```

**Resources**

- `POST /patients` create a patient

**Example Request**

```shell
curl https://api.au1.cliniko.com/v1/patients \
  -u API_KEY: \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -d '{ "first_name": "John", "last_name": "Snow" }' \
  -X POST
```

**Example Response**

```
Headers { Location: http://api.cliniko.com/patients/1 }
```

```json
{
  "accepted_privacy_policy": true,
  "accepted_email_marketing": true,
  "accepted_sms_marketing": false,
  "address_1": "1 Smith Street",
  "address_2": "",
  "address_3": "",
  "archived_at": "",
  "city": "",
  "country": "",
  "created_at": "2013-03-26T14:00:00Z",
  "custom_fields": null,
  "date_of_birth": "",
  "deleted_at": "",
  "dva_card_number": "",
  "email": "",
  "emergency_contact": "",
  "first_name": "John",
  "invoice_default_to": "",
  "invoice_email": "",
  "invoice_extra_information": "",
  "gender": "Male",
  "gender_identity": "Transgender",
  "id": 1,
  "last_name": "Snow",
  "medicare": "",
  "medicare_reference_number": "",
  "notes": "",
  "appointment_notes": "",
  "occupation": "",
  "old_reference_id": "",
  "patient_phone_numbers": [],
  "post_code": "",
  "preferred_first_name": null,
  "pronouns": null,
  "receives_confirmation_emails": true,
  "referral_source": "",
  "reminder_type": "SMS & Email",
  "sex": "Female to Male",
  "state": "",
  "title": "",
  "time_zone": null,
  "updated_at": "2013-03-26T14:00:00Z",
  "patient_phone_numbers": [],
  "medical_alerts": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/patients/1/medical_alerts?page=1"
    }
  },
  "invoices": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/patients/1/invoices?page=1"
    }
  },
  "appointments": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/patients/1/appointments?page=1"
    }
  },
  "links": { "self": "https://api.au1.cliniko.com/v1/patients/1" }
}
```

## Update Patient

> As of 2018-12-03, `gender` is now deprecated. Instead, the `/patients` API endpoint will now expose and accept the new `gender_identity` and `sex` properties.
> The `/patients` endpoint will continue to return a patient's gender, but you may only use the new properties when _creating_ or _updating_ patients. Note that we are not serving the current value of `gender` in either of the new fields - these need to be updated separately, either through the Cliniko UI, or through the API.
> Find more on why we've made this switch here: [Changes coming to patient gender and sex](https://groups.google.com/a/redguava.com.au/forum/#!topic/cliniko-api/H5fXFk_MH98)

**Validation**

Patient records must have a `first_name` and `last_name`. `email`, if supplied, is validated using the following RegEx in Ruby:
```ruby
/\A[A-Z0-9!#$%&'\*+-\/=?^_`{\|}~]+@[A-Z0-9.-]+\.[A-Z]{2,63}\z/i
```

**Resources**

- `PUT /patients/:id` update a patient

**Example Request**

```shell
curl https://api.au1.cliniko.com/v1/patients/1 \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'Content-Type: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -d '{ "first_name": "John", "last_name": "Snow", "appointment_notes": "Go for fist bumps over handshakes." }' \
  -X PUT
```

**Example Response**

```json
{
  "accepted_privacy_policy": true,
  "accepted_email_marketing": true,
  "accepted_sms_marketing": false,
  "address_1": "1 Smith Street",
  "address_2": "",
  "address_3": "",
  "archived_at": "",
  "city": "Melbourne",
  "country": "Australia",
  "created_at": "2013-03-26T14:00:00Z",
  "custom_fields": null,
  "date_of_birth": "2001-05-26",
  "deleted_at": "",
  "dva_card_number": "",  
  "email": "peter@example.com",
  "emergency_contact": "",
  "first_name": "John",
  "invoice_default_to": "Super Insurance",
  "invoice_email": "super.insurance@example.com",
  "invoice_extra_information": "Insurance #123456\r\nClaim #123456",
  "gender": "Male",
  "gender_identity": "Transgender",
  "id": 1,
  "last_name": "Snow",
  "medicare": "",
  "medicare_reference_number": "",
  "notes": "",
  "appointment_notes": "Go for fist bumps over handshakes.",
  "occupation": "",
  "old_reference_id": "",
  "patient_phone_numbers": [],
  "post_code": "3000",
  "preferred_first_name": null,
  "pronouns": null,
  "receives_confirmation_emails": true,
  "referral_source": "",
  "reminder_type": "SMS & Email",
  "sex": "Female to Male",
  "state": "Victoria",
  "title": "Mr",
  "time_zone": "Australia/Melbourne",
  "updated_at": "2013-03-26T14:00:00Z",
  "patient_phone_numbers": [
    {
      "phone_type": "Mobile",
      "number": "61444444444"
    },
    {
      "phone_type": "Home",
      "number": "61399999999"
    }
  ],
  "medical_alerts": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/patients/1/medical_alerts?page=1"
    }
  },
  "invoices": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/patients/1/invoices?page=1"
    }
  },
  "appointments": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/patients/1/appointments?page=1"
    }
  },
  "links": { "self": "https://api.au1.cliniko.com/v1/patients/1" }
}
```

## Archive Patient

**Resources**

- `POST /patients/:id/archive` archive a patient

**Example Request**

```shell
curl https://api.au1.cliniko.com/v1/patients/1/archive \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -X POST
```

**Example Response**
A status code of `204 no content` will be returned if successful

## Unarchive Patient

**Resources**

- `POST /patients/:id/unarchive` unarchive a patient

**Example Request**

```shell
curl https://api.au1.cliniko.com/v1/patients/1/unarchive \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -X POST
```

**Example Response**

```json
{
  "accepted_privacy_policy": true,
  "accepted_email_marketing": true,
  "accepted_sms_marketing": false,
  "address_1": "1 Smith Street",
  "address_2": "",
  "address_3": "",
  "archived_at": "",
  "city": "Melbourne",
  "country": "Australia",
  "created_at": "2013-03-26T14:00:00Z",
  "custom_fields": null,
  "date_of_birth": "2001-05-26",
  "deleted_at": "",
  "dva_card_number": "",  
  "email": "peter@example.com",
  "emergency_contact": "",
  "first_name": "John",
  "invoice_default_to": "Super Insurance",
  "invoice_email": "super.insurance@example.com",
  "invoice_extra_information": "Insurance #123456\r\nClaim #123456",
  "gender": "Male",
  "gender_identity": "Transgender",
  "id": 1,
  "last_name": "Snow",
  "notes": "",
  "appointment_notes": "",
  "medicare": "",
  "medicare_reference_number": "",
  "occupation": "",
  "old_reference_id": "",
  "patient_phone_numbers": [],
  "post_code": "3000",
  "preferred_first_name": null,
  "pronouns": null,
  "receives_confirmation_emails": true,
  "referral_source": "",
  "reminder_type": "SMS & Email",
  "sex": "Female to Male",
  "state": "Victoria",
  "title": "Mr",
  "time_zone": "Australia/Melbourne",
  "updated_at": "2013-03-26T14:00:00Z",
  "patient_phone_numbers": [
    {
      "phone_type": "Mobile",
      "number": "61444444444"
    },
    {
      "phone_type": "Home",
      "number": "61399999999"
    }
  ],
  "medical_alerts": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/patients/1/medical_alerts?page=1"
    }
  },
  "invoices": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/patients/1/invoices?page=1"
    }
  },
  "appointments": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/patients/1/appointments?page=1"
    }
  },
  "links": { "self": "https://api.au1.cliniko.com/v1/patients/1" }
}
```

## Filtering Patients

For any route that returns a set of patients, you can filter them by:

- `created_at` (DateTime)
- `date_of_birth` (Date)
- `email` (String)
- `first_name` (String)
- `id` (Integer)
- `last_name` (String)
- `old_reference_id` (String)
- `updated_at` (DateTime)

See [Filtering Results](https://github.com/redguava/cliniko-api#filtering-results) for details on how to apply filters.

## Patient Custom Fields Schema

The `custom_fields` property of a patient is a JSON object. The schema is validated and must conform to the following rules. The data provided must also conform to the definition specified in the `patient_custom_fields_definition` attribute on the [Settings](https://github.com/redguava/cliniko-api/blob/master/sections/settings.md) resource. This means that only sections, fields, and options that are defined in the account's settings will be accepted.

**Custom Fields Object**

Property | Type | Accepted Values | Notes
------------ | ------------- | ------------- | -------------
sections | array | An array of section objects | Not required.

**Section Object**

Property | Type | Accepted Values | Notes
------------ | ------------- | ------------- | -------------
name | string | A string of 255 or fewer characters | Disregarded when creating/updating.
token | string | A UUID string | Required, and must match the token of a defined section in the account's custom patient fields settings.
archived | boolean | `true` or `false` | Disregarded when creating/updating.
fields | array | An array of field objects | Not required.

**Field Object**

Property | Type | Accepted Values | Notes
------------ | ------------- | ------------- | -------------
name | string | A string of 255 or fewer characters | Disregarded when creating/updating.
type | string | `text`, `paragraph`, `checkboxes`, `radiobuttons`, `date` | Disregarded when creating/updating.
token | string | A UUID string | Required, and must match the token of a defined field in the account's custom patient fields settings.
archived | boolean | `true` or `false` | Disregarded when creating/updating.
value | string | A string | Not required. Only accepted for `text`, `paragraph` and `date` type questions. Empty values are not valid. If there is no value, the field should be omitted entirely. When provided for a `date` type question, the accepted format is `YYYY-MM-DD`.
options | array | An array of option objects | Not required. Only accepted for `checkboxes` and `radiobuttons` type questions.
other | object | An other object | Not required. Only accepted for `checkboxes` and `radiobuttons` type questions.

**Option Object**

Property | Type | Accepted Values | Notes
------------ | ------------- | ------------- | -------------
name | string | A string of 255 or fewer characters | Disregarded when creating/updating.
token | string | A UUID string | Required, and must match the token of a defined option in the account's custom patient fields settings.
archived | boolean | `true` or `false` | Disregarded when creating/updating.
selected | boolean | true | Not required. For `radiobuttons` type questions, a maximum of one answer can be selected, unless `other` is `selected` on the question, in which case no answers must be selected.

**Other Object**

Property | Type | Accepted Values | Notes
------------ | ------------- | ------------- | -------------
enabled | boolean | `true` or `false` | Disregarded when creating/updating.
archived | boolean | `true` or `false` | Disregarded when creating/updating.
selected | boolean | `true` or `false` | Not required. Only accepted if `enabled` is `true`
value | string | A string of 255 or fewer characters | Not required. Only accepted if `selected` is `true`
