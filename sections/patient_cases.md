Patient Cases
============
* [Get Patient Cases](#get-patient-cases "This will return all patient cases.")
* [Get Patient Case](#get-patient-case "This will return a specified patient case.")
* [Create Patient Case](#create-patient-case "This will create a patient case.")
* [Update Patient Case](#update-patient-case "This will update a patient case.")
* [Archive Patient Case](#archive-patient-case "This will archive a patient case.")


Get Patient Cases
----------------

**Resources**
* ```GET /patient-cases``` get all patient cases

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/patient_cases \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "patient_cases": [
    {
      "id": "566562806174843905",
      "created_at": "2021-02-20T16:59:09Z",
      "updated_at": "2021-07-23T17:47:16Z",
      "max_invoiceable_amount": null,
      "closed": false,
      "include_cancelled_attendees": true,
      "include_dna_attendees": null,
      "issue_date": "2021-02-18",
      "expiry_date": "2022-02-17",
      "name": "Case One",
      "notes": null,
      "max_sessions": 12,
      "referral": false,
      "referral_type": null,
      "attendee_ids": [
        "372482141335848698",
        "529672213901608572",
        "555656064805111313",
        "555655906260419766"
      ],
      "patient": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/patients/372481449527346255"
        }
      },
      "attendees": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/patient_cases/566562806174843905/attendees"
        }
      },
      "bookings": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/patient_cases/566562806174843905/bookings"
        }
      },
      "patient_attachments": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/patient_cases/566562806174843905/patient_attachments"
        }
      },
      "invoices": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/patient_cases/566562806174843905/invoices"
        }
      },
      "links": {
        "self": "https://api.au1.cliniko.com/v1/patient_cases/566562806174843905"
      }
    }
  ],
  "total_entries": 1,
  "links": {"self": "https://api.au1.cliniko.com/v1/patient_cases?page=1"}
}
```

Get Patient Case
------------

**Resources**
* ```GET /patient-cases/:id``` get a specific patient case

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/patient_cases/566562806174843905 \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "id": "566562806174843905",
  "created_at": "2021-02-20T16:59:09Z",
  "updated_at": "2021-07-23T17:47:16Z",
  "max_invoiceable_amount": null,
  "closed": false,
  "include_cancelled_attendees": true,
  "include_dna_attendees": null,
  "issue_date": "2021-02-18",
  "expiry_date": "2022-02-17",
  "name": "Case One",
  "notes": null,
  "max_sessions": 12,
  "referral": false,
  "referral_type": null,
  "attendee_ids": [
    "372482141335848698",
    "529672213901608572",
    "555656064805111313",
    "555655906260419766"
  ],
  "patient": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/patients/372481449527346255"
    }
  },
  "attendees": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/patient_cases/566562806174843905/attendees"
    }
  },
  "bookings": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/patient_cases/566562806174843905/bookings"
    }
  },
  "patient_attachments": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/patient_cases/566562806174843905/patient_attachments"
    }
  },
  "invoices": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/patient_cases/566562806174843905/invoices"
    }
  },
  "links": {
    "self": "https://api.au1.cliniko.com/v1/patient_cases/566562806174843905"
  }
}
```

Create Patient Case
----------------
**Resources**
* ```POST /patient-cases``` create a patient case

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/patient_cases \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -d '{ "name": "Patient Case 2", "patient_id": 372481449527346255 }' \
  -X POST
```
**Example Response**
```
Headers { Location: http://api.cliniko.com/patient-cases/2 }
```
```json
{
  "id": "566562806174843905",
  "created_at": "2021-07-25T18:36:24Z",
  "updated_at": "2021-07-25T18:36:24Z",
  "max_invoiceable_amount": null,
  "closed": false,
  "include_cancelled_attendees": null,
  "include_dna_attendees": null,
  "issue_date": null,
  "expiry_date": null,
  "name": "Patient Case 2",
  "notes": null,
  "max_sessions": null,
  "referral": false,
  "referral_type": null,
  "attendee_ids": [],
  "patient": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/patients/372481449527346255"
    }
  },
  "attendees": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/patient_cases/566562806174843905/attendees"
    }
  },
  "bookings": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/patient_cases/566562806174843905/bookings"
    }
  },
  "patient_attachments": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/patient_cases/566562806174843905/patient_attachments"
    }
  },
  "invoices": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/patient_cases/566562806174843905/invoices"
    }
  },
  "links": {
    "self": "https://api.au1.cliniko.com/v1/patient_cases/566562806174843905"
  }
}
```

Update Patient Case
----------------
**Resources**
* ```PUT /patient-cases/:id``` update a patient case

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/patient_cases/1 \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -d '{ "name": "Patient Case 3" }' \
  -X PUT
```
**Example Response**
```json
{
  "id": "566562806174843905",
  "created_at": "2021-07-25T18:36:24Z",
  "updated_at": "2021-07-25T18:36:24Z",
  "max_invoiceable_amount": null,
  "closed": false,
  "include_cancelled_attendees": null,
  "include_dna_attendees": null,
  "issue_date": null,
  "expiry_date": null,
  "name": "Patient Case 3",
  "notes": null,
  "max_sessions": null,
  "referral": false,
  "referral_type": null,
  "attendee_ids": [],
  "patient": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/patients/372481449527346255"
    }
  },
  "attendees": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/patient_cases/566562806174843905/attendees"
    }
  },
  "bookings": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/patient_cases/566562806174843905/bookings"
    }
  },
  "patient_attachments": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/patient_cases/566562806174843905/patient_attachments"
    }
  },
  "invoices": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/patient_cases/566562806174843905/invoices"
    }
  },
  "links": {
    "self": "https://api.au1.cliniko.com/v1/patient_cases/566562806174843905"
  }
}
```

Archive Patient Case
----------------
**Resources**
* ```POST /patient-cases/:id/archive``` archive a patient case

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/patient_cases/1/archive \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -X POST
```
**Example Response**
A status code of `204 no content` will be returned if successful

Filtering Patient Cases
----------------

You can filter patient cases by:
* ```created_at``` DateTime
* ```expiry_date``` Date
* ```id``` Integer
* ```patient_id``` Integer
* ```updated_at``` DateTime

See [Filtering Results](https://github.com/redguava/cliniko-api#filtering-results) for details on how to apply filters.

## Permitted properties
When creating or updating Patient Cases, the following properties are permitted.

| Name                          | Type          | Required? | Description     |
|------------------------------ | ------------- | --------- | --------------- |
| `attendee_ids`                | Array[BigInt] |           | A list of the attende IDs this case is linked to. |
| `closed`                      | Boolean       |           | |
| `contact_id`                  | BigInt        |           | Contact (doctor only) linked to this case. |
| `expiry_date`                 | Date          |           | |
| `include_cancelled_attendees` | Boolean       |           | |
| `include_dna_attendees`       | Boolean       |           | |
| `issue_date`                  | Date          |           | |
| `max_invoiceable_amount`      | Money         |           | A money amount, up to 2 decimal places. |
| `max_sessions`                | Integer       |           | |
| `name`                        | String        | **yes**   | |
| `notes`                       | String        |           | |
| `patient_attachment_ids`      | Array[BigInt] |           | A list of the patient attachments this case is linked to (note that patient attachments must already exist). |
| `patient_id`                  | BigInt        | **yes**   | Patient linked to this case. |
| `referral`                    | Boolean       |           | |
| `referral_type`               | Enum          |           | One of [`medicare`]. |
