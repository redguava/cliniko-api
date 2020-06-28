# Referral Source

> Referral source of a patient

- [Get Referral Sources](#get-referral-sources 'This will return all referral sources.')
- [Get Referral Source](#get-referral-source "This will return a patient's referral source.")
- [Update Referral Source](#update-referral-source "This update a patient's referral source.")

## Get Referral Sources

**Resources**

- `GET /referral_sources` get all referral sources

**Example Request**

```shell
curl https://api.au1.cliniko.com/v1/referral_sources \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**

```json
{
  "referral_sources": [
    {
      "links": {
        "self": "https://api.au1.cliniko.com/v1/patients/123/referral_source"
      },
      "referrer": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/patients/456"
        }
      },
      "referrer_type": "Patient",
      "subcategory": null,
      "notes": "note written about this referral",
      "patient": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/patients/123"
        }
      },
      "referral_source_type": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/referral_source_types/1"
        }
      }
    }
  ],
  "total_entries": 1,
  "links": {
    "self": "https://api.au1.cliniko.com/v1/referral_sources?page=1"
  }
}
```

## Get Referral Source

**Resources**

- `GET /patients/:patient_id/referral_source` get a patient's referral source

Returns `404` if the patient has no referral source.

**Example Request**

```shell
curl https://api.au1.cliniko.com/v1/patients/123/referral_source \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

There are a few possible types of referral sources. Depending on the type, different attributes will have values.

**Example Response (referred by a patient)**

```json
{
  "links": {
    "self": "https://api.au1.cliniko.com/v1/patients/123/referral_source"
  },
  "referrer": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/patients/456"
    }
  },
  "referrer_type": "Patient",
  "subcategory": null,
  "notes": "note written about this referral",
  "patient": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/patients/123"
    }
  },
  "referral_source_type": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/referral_source_types/1"
    }
  }
}
```

**Example Response (referred by a contact)**

```json
{
  "links": {
    "self": "https://api.au1.cliniko.com/v1/patients/123/referral_source"
  },
  "referrer": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/contacts/456"
    }
  },
  "referrer_type": "Contact",
  "subcategory": null,
  "notes": "note written about this referral",
  "patient": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/patients/123"
    }
  },
  "referral_source_type": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/referral_source_types/2"
    }
  }
}
```

**Example Response ("other" referral type)**

```json
{
  "links": {
    "self": "https://api.au1.cliniko.com/v1/patients/123/referral_source"
  },
  "referrer": null,
  "referrer_type": null,
  "subcategory": null,
  "notes": "note written about this referral",
  "patient": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/patients/123"
    }
  },
  "referral_source_type": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/referral_source_types/3"
    }
  }
}
```

**Example Response (custom defined referral type)**

```json
{
  "links": {
    "self": "https://api.au1.cliniko.com/v1/patients/123/referral_source"
  },
  "referrer": null,
  "referrer_type": null,
  "subcategory": "the subcategory name",
  "notes": "note written about this referral",
  "patient": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/patients/123"
    }
  },
  "referral_source_type": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/referral_source_types/4"
    }
  }
}
```

## Update Referral Source

**Resources**

- `PUT /patients/:patient_id/referral_source` update a patient's referral source

**Example Request**

```shell
curl https://api.au1.cliniko.com/v1/patients/123/referral_source \
  -u API_KEY: \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -d '{ "referral_source_type_id": 100, "subcategory": "Custom subcategory", "notes": "Extra note" }' \
  -X PUT
```

There are a few possible types of referral sources. Depending on the type, different attributes will need values.

**Example Request (referred by a patient)**

```json
{
  "notes": "note written about this Patient referral",
  "referrer_id": 456,
  "referral_source_type_id": 1
}
```

**Example Request (referred by a contact)**

```json
{
  "notes": "note written about this Contact referral",
  "referrer_id": 1001,
  "referral_source_type_id": 2
}
```

**Example Request ("other" referral type)**

```json
{
  "notes": "note written about this Other referral",
  "referral_source_type_id": 3
}
```

**Example Request (custom defined referral type)**

```json
{
  "notes": "note written about this Custom referral type referral",
  "referral_source_type_id": 4,
  "subcategory": "The subcategory name"
}
```

> Note that the subcategory text must match one of the existing subcategories for the custom referral source type.
