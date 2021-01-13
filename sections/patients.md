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
- [Delete Patient](#delete-patient 'This will delete a patient.')
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
      "accepted_sms_marketing": false,
      "address_1": "1 Smith Street",
      "address_2": "",
      "address_3": "",
      "archived_at": "",
      "city": "Melbourne",
      "country": "Australia",
      "created_at": "2013-03-26T14:00:00Z",
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
      "post_code": "3000",
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
      "accepted_sms_marketing": false,
      "address_1": "1 Smith Street",
      "address_2": "",
      "address_3": "",
      "archived_at": "2013-06-05T14:37:18Z",
      "city": "Melbourne",
      "country": "Australia",
      "created_at": "2013-03-26T14:00:00Z",
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
      "post_code": "3000",
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
- `GET /patients/:id,id,id...` get multiple specified patients 

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
  "accepted_sms_marketing": false,
  "address_1": "1 Smith Street",
  "address_2": "",
  "address_3": "",
  "archived_at": "",
  "city": "Melbourne",
  "country": "Australia",
  "created_at": "2013-03-26T14:00:00Z",
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
  "post_code": "3000",
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
  "accepted_sms_marketing": false,
  "address_1": "1 Smith Street",
  "address_2": "",
  "address_3": "",
  "archived_at": "",
  "city": "",
  "country": "",
  "created_at": "2013-03-26T14:00:00Z",
  "date_of_birth": "",
  "deleted_at": "",
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
  "post_code": "",
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
  "accepted_sms_marketing": false,
  "address_1": "1 Smith Street",
  "address_2": "",
  "address_3": "",
  "archived_at": "",
  "city": "Melbourne",
  "country": "Australia",
  "created_at": "2013-03-26T14:00:00Z",
  "date_of_birth": "2001-05-26",
  "deleted_at": "",
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
  "post_code": "3000",
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
  "accepted_sms_marketing": false,
  "address_1": "1 Smith Street",
  "address_2": "",
  "address_3": "",
  "archived_at": "",
  "city": "Melbourne",
  "country": "Australia",
  "created_at": "2013-03-26T14:00:00Z",
  "date_of_birth": "2001-05-26",
  "deleted_at": "",
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
  "post_code": "3000",
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
