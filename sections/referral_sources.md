Referral Source
============
> Referral source of a patient

* [Get Referral Source](#get-referral-source "This will return a patient's referral source.")

Get Referral Source
------------

**Resources**
* ```GET /patients/:patient_id/referral_source``` get a patient's referral source

**Example Request**
```shell
curl https://api.cliniko.com/v1/patients/123/referral_source \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

There are a few possible types of referral sources. Depending on the type, different attributes will have values.

**Example Response (referred by a patient)**
```json
{
  "links": {
    "self": "https://api.cliniko.com/v1/patients/123/referral_source"
  },
  "referrer": {
    "links": {
      "self": "https://api.cliniko.com/v1/patients/456"
    }
  },
  "referrer_type": "Patient",
  "subcategory": null,
  "notes": "note written about this referral",
  "referral_source_type": {
    "links": {
      "self": "https://api.cliniko.com/v1/referral_source_types/1"
    }
  }
}
```

**Example Response (referred by a contact)**
```json
{
  "links": {
    "self": "https://api.cliniko.com/v1/patients/123/referral_source"
  },
  "referrer": {
    "links": {
      "self": "https://api.cliniko.com/v1/contacts/456"
    }
  },
  "referrer_type": "Contact",
  "subcategory": null,
  "notes": "note written about this referral",
  "referral_source_type": {
    "links": {
      "self": "https://api.cliniko.com/v1/referral_source_types/2"
    }
  }
}
```

**Example Response ("other" referral type)**
```json
{
  "links": {
    "self": "https://api.cliniko.com/v1/patients/123/referral_source"
  },
  "referrer": null,
  "referrer_type": null,
  "subcategory": null,
  "notes": "note written about this referral",
  "referral_source_type": {
    "links": {
      "self": "https://api.cliniko.com/v1/referral_source_types/3"
    }
  }
}
```

**Example Response (custom defined referral type)**
```json
{
  "links": {
    "self": "https://api.cliniko.com/v1/patients/123/referral_source"
  },
  "referrer": null,
  "referrer_type": null,
  "subcategory": "the subcategory name",
  "notes": "note written about this referral",
  "referral_source_type": {
    "links": {
      "self": "https://api.cliniko.com/v1/referral_source_types/4"
    }
  }
}
```
