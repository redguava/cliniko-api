Patient Attachments
============
> Files uploaded to a patient's profile

* [Get Patient Attachments](#get-patient-attachments "This will return all patient attachments.")
* [Get Patient Attachment](#get-patient-attachment "This will return a specified patient attachment.")
* [Create Patient Attachment](#create-patient-attachment "This will create a patient attachment.")
* [Delete Patient Attachment](#delete-patient-attachment "This will delete a patient attachment.")

Get Patient Attachments
----------------

**Resources**
* ```GET patient_attachments``` get all patient attachments
* ```GET patients/:patient_id/patient_attachments``` get all patient attachments for the specified patient

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/patient_attachments \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "patient_attachments": [
    {
      "id": 1,
      "created_at": "2017-12-31T15:32:58Z",
      "updated_at": "2017-12-31T15:32:58Z",
      "content_type": "text/plain",
      "filename": "the-name-of-the-file.txt",
      "size": 14936,
      "content": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/patient_attachments/1/content"
        }
      },
      "description": null,
      "processing_completed": true,
      "patient": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/patients/123"
        }
      },
      "user": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/users/456"
        }
      },
      "links": {
        "self": "https://api.au1.cliniko.com/v1/patient_attachments/1"
      }
    }
  ],
  "total_entries": 1,
  "links": {
    "self": "https://api.au1.cliniko.com/v1/patient_attachments?page=1"
  }
}
```

Get Patient Attachment
------------

**Resources**
* ```GET patient_attachments/:id``` get a specified patient attachment

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/patient_attachments/1 \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "id": 1,
  "created_at": "2017-12-31T15:32:58Z",
  "updated_at": "2017-12-31T15:32:58Z",
  "content_type": "text/plain",
  "filename": "the-name-of-the-file.txt",
  "size": 14936,
  "content": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/patient_attachments/1/content"
    }
  },
  "description": null,
  "processing_completed": true,
  "patient": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/patients/123"
    }
  },
  "user": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/users/456"
    }
  },
  "links": {
    "self": "https://api.au1.cliniko.com/v1/patient_attachments/1"
  }
}
```

Create Patient Attachment
----------------
**Resources**
* ```POST patient_attachments``` create a product

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/patient_attachments \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -d '{ "patient_id": "123", "upload_url": "https://cliniko-files-example-bucket.s3.amazonaws.com/123%2Fpatients%2F456%2Fattachments%2Ftemp%2Fs0m3-w31rd-l0c4t10n-1na-t3mpd1r%2Fthe-name-of-the-file.txt" }' \
  -X POST
```
**Example Response**
```
Headers { Location: https://api.au1.cliniko.com/patient_attachments/1 }
```
```json
{
  "id": 1,
  "created_at": "2017-12-31T15:32:58Z",
  "updated_at": "2017-12-31T15:32:58Z",
  "content_type": null,
  "filename": null,
  "size": null,
  "content": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/patient_attachments/1/content"
    }
  },
  "description": null,
  "processing_completed": false,
  "patient": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/patients/123"
    }
  },
  "user": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/users/456"
    }
  },
  "links": {
    "self": "https://api.au1.cliniko.com/v1/patient_attachments/1"
  }
}
```

Delete Patient Attachment
----------------
**Resources**
* ```DELETE patient_attachments/:id``` delete a product

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/patient_attachments/1 \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -X DELETE
```
**Example Response**
A status code of `204 no content` will be returned if successful

Filtering Patient Attachments
----------------

You can filter patient attachments by:
* ```created_at``` DateTime
* ```content_type``` String
* ```description``` String
* ```filename``` String
* ```id``` Integer
* ```patient_id``` Integer
* ```size``` Integer
* ```user_id``` Integer
* ```updated_at``` DateTime

See [Filtering Results](https://github.com/redguava/cliniko-api#filtering-results) for details on how to apply filters.
