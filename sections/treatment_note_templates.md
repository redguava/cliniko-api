Treatment Note Templates
============
> Templates that are the starting point for treatment notes.

* [Get Treatment Note Templates](#get-treatment-note-templates "This will return all treatment note templates.")
* [Get Deleted Treatment Note Templates](#get-deleted-treatment-note-templates "This will return all deleted treatment note templates.")
* [Get Treatment Note Template](#get-treatment-note-template "This will return a specified treatment note template.")
* [Create Treatment Note Template](#create-treatment-note-template "This will create a treatment note template.")
* [Update Treatment Note Template](#update-treatment-note-template "This will update a treatment note template.")
* [Delete Treatment Note Template](#delete-treatment-note-template "This will delete a treatment note template.")

Get Treatment Note Templates
----------------

**Resources**
* ```GET /treatment_note_templates``` get all treatment note templates


**Example Request**
```shell
curl https://api.cliniko.com/v1/treatment_note_templates \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "treatment_note_templates": [
    {
      "id": 1,
      "created_at": "2017-06-12T16:03:42Z",
      "updated_at": "2017-06-12T16:03:42Z",
      "content": {
        "sections": [
          {
            "name": "Section 1",
            "questions": [
              {
                "name": "Patient progress report",
                "type": "paragraph",
                "answer": "<div>Default answers to paragraph questions support basic HTML!</div>"
              },
              {
                "name": "Assessment",
                "type": "text"
              }
            ]
          },
          {
            "name": "Section 2",
            "questions": [
              {
                "name": "Choose just one",
                "type": "radiobuttons",
                "answers": [
                  { "value": "Choice 1" },
                  { "value": "Choice 2" },
                  { "value": "Choice 3" }
                ]
              },
              {
                "name": "Choose one or more",
                "type": "checkboxes",
                "answers": [
                  { "value": "Choice 1" },
                  { "value": "Choice 2" },
                  { "value": "Choice 3" }
                ]
              }
            ]
          }
        ]
      },
      "name": "Standard Consultation",
      "print_settings": {
        "include_patient_address": true,
        "include_patient_dob": null,
        "include_patient_medicare": null,
        "include_patient_occupation": null,
        "include_patient_reference_number": null,
        "title": null
      },
      "deleted_at": null,
      "links": {
        "self": "https://api.cliniko.com/v1/treatment_note_templates/1"
      }
    }
  ],
  "total_entries": 1,
  "links": {
    "self": "https://api.cliniko.com/v1/treatment_note_templates?page=1"
  }
}
```

Get Deleted Treatment Note Templates
----------------

**Resources**
* ```GET /treatment_note_templates/deleted``` get all deleted treatment note templates

**Example Request**
```shell
curl https://api.cliniko.com/v1/treatment_note_templates/deleted \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "treatment_note_templates": [
    {
      "id": 1,
      "created_at": "2017-06-12T16:03:42Z",
      "updated_at": "2017-06-12T16:03:42Z",
      "content": {
        "sections": [
          {
            "name": "Section 1",
            "questions": [
              {
                "name": "Patient progress report",
                "type": "paragraph",
                "answer": "<div>Default answers to paragraph questions support basic HTML!</div>"
              },
              {
                "name": "Assessment",
                "type": "text"
              }
            ]
          },
          {
            "name": "Section 2",
            "questions": [
              {
                "name": "Choose just one",
                "type": "radiobuttons",
                "answers": [
                  { "value": "Choice 1" },
                  { "value": "Choice 2" },
                  { "value": "Choice 3" }
                ]
              },
              {
                "name": "Choose one or more",
                "type": "checkboxes",
                "answers": [
                  { "value": "Choice 1" },
                  { "value": "Choice 2" },
                  { "value": "Choice 3" }
                ]
              }
            ]
          }
        ]
      },
      "name": "Standard Consultation",
      "print_settings": {
        "include_patient_address": true,
        "include_patient_dob": null,
        "include_patient_medicare": null,
        "include_patient_occupation": null,
        "include_patient_reference_number": null,
        "title": null
      },
      "deleted_at": "2017-06-23T02:10:25Z",
      "links": {
        "self": "https://api.cliniko.com/v1/treatment_note_templates/1"
      }
    }
  ],
  "total_entries": 1,
  "links": {
    "self": "https://api.cliniko.com/v1/treatment_note_templates/deleted?page=1"
  }
}
```

Get Treatment Note Template
------------

**Resources**
* ```GET /treatment_note_templates/:id``` get a specified treatment note template

**Example Request**
```shell
curl https://api.cliniko.com/v1/treatment_note_templates/1 \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "id": 1,
  "created_at": "2017-06-12T16:03:42Z",
  "updated_at": "2017-06-12T16:03:42Z",
  "content": {
    "sections": [
      {
        "name": "Section 1",
        "questions": [
          {
            "name": "Patient progress report",
            "type": "paragraph",
            "answer": "<div>Default answers to paragraph questions support basic HTML!</div>"
          },
          {
            "name": "Assessment",
            "type": "text"
          }
        ]
      },
      {
        "name": "Section 2",
        "questions": [
          {
            "name": "Choose just one",
            "type": "radiobuttons",
            "answers": [
              { "value": "Choice 1" },
              { "value": "Choice 2" },
              { "value": "Choice 3" }
            ]
          },
          {
            "name": "Choose one or more",
            "type": "checkboxes",
            "answers": [
              { "value": "Choice 1" },
              { "value": "Choice 2" },
              { "value": "Choice 3" }
            ]
          }
        ]
      }
    ]
  },
  "name": "Standard Consultation",
  "print_settings": {
    "include_patient_address": true,
    "include_patient_dob": null,
    "include_patient_medicare": null,
    "include_patient_occupation": null,
    "include_patient_reference_number": null,
    "title": null
  },
  "deleted_at": null,
  "links": {
    "self": "https://api.cliniko.com/v1/treatment_note_templates/1"
  }
}
```

Create Treatment Note Template
----------------
**Resources**
* ```POST /treatment_note_templates``` create a treatment note template

**Example Request**
```shell
curl https://api.cliniko.com/v1/treatment_note_templates \
  -u API_KEY: \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -d '{ "name": "My template" }' \
  -X POST
```
**Example Response**
```
Headers { Location: http://api.cliniko.com/treatment_note_templates/1 }
```
```json
{
  "id": 1,
  "created_at": "2017-06-12T16:03:42Z",
  "updated_at": "2017-06-12T16:03:42Z",
  "content": null,
  "name": "My template",
  "print_settings": {
    "include_patient_address": true,
    "include_patient_dob": null,
    "include_patient_medicare": null,
    "include_patient_occupation": null,
    "include_patient_reference_number": null,
    "title": null
  },
  "deleted_at": null,
  "links": {
    "self": "https://api.cliniko.com/v1/treatment_note_templates/1"
  }
}
```

Update Treatment Note Template
----------------
**Resources**
* ```PUT /treatment_note_templates/:id``` update a treatment note template

**Example Request**
```shell
curl https://api.cliniko.com/v1/treatment_note_templates/1 \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'Content-Type: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -d '{ "name": "My template" }' \
  -X PUT
```
**Example Response**
```json
{
  "id": 1,
  "created_at": "2017-06-12T16:03:42Z",
  "updated_at": "2017-06-29T05:32:51Z",
  "content": null,
  "name": "My template",
  "print_settings": {
    "include_patient_address": true,
    "include_patient_dob": null,
    "include_patient_medicare": null,
    "include_patient_occupation": null,
    "include_patient_reference_number": null,
    "title": null
  },
  "deleted_at": null,
  "links": {
    "self": "https://api.cliniko.com/v1/treatment_note_templates/1"
  }
}
```

Delete Treatment Note Template
----------------
**Resources**
* ```DELETE /treatment_note_templates/:id``` delete a treatment note template

**Example Request**
```shell
curl https://api.cliniko.com/v1/treatment_note_templates/1 \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -X DELETE
```
**Example Response**
A status code of `204 no content` will be returned if successful
