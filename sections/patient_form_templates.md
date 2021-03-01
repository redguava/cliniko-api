Patient Form Templates
============
> Templates that are the starting point for patient forms.

* [Get Patient Form Templates](#get-patient-form-templates "This will return all patient form templates.")
* [Get Patient Form Template](#get-patient-form-template "This will return a specified patient form template.")
* [Create Patient Form Template](#create-patient-form-template "This will create a patient form template.")
* [Update Patient Form Template](#update-patient-form-template "This will update a patient form template.")
* [Archive Patient Form Template](#archive-patient-form-template "This will archive a patient form template.")

Get Patient Form Templates
----------------

**Resources**
* ```GET /patient_form_templates``` get all patient form templates


**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/patient_form_templates \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "patient_form_templates": [
    {
      "id": "507944033264337974",
      "created_at": "2020-12-01T19:54:07Z",
      "updated_at": "2020-12-01T19:56:22Z",
      "content": {
        "sections": [
          {
            "name": "Medical History",
            "questions": [
              {
                "name": "Please describe your medical history.",
                "type": "paragraph",
                "required": true
              }
            ]
          },
          {
            "name": "Current Condition",
            "questions": [
              {
                "name": "Which of the following symptoms do you suffer from?",
                "type": "checkboxes",
                "answers": [
                  {
                    "value": "Fever"
                  },
                  {
                    "value": "Headache"
                  },
                  {
                    "value": "Shortness of breath"
                  },
                  {
                    "value": "Cough"
                  }
                ],
                "required": false
              }
            ]
          }
        ]
      },
      "name": "New Patient Intake",
      "restricted_to_practitioner": false,
      "archived_at": null,
      "links": {
        "self": "https://api.au1.cliniko.com/v1/patient_form_templates/507944033264337974"
      }
    }
  ],
  "links": {
    "self": "https://api.au1.cliniko.com/v1/patient_form_templates?page=1"
  }
}
```

Get Patient Form Template
------------

**Resources**
* ```GET /patient_form_templates/:id``` get a specified patient form template

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/patient_form_templates/1 \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "id": "507944033264337974",
  "created_at": "2020-12-01T19:54:07Z",
  "updated_at": "2020-12-01T19:56:22Z",
  "content": {
    "sections": [
      {
        "name": "Medical History",
        "questions": [
          {
            "name": "Please describe your medical history.",
            "type": "paragraph",
            "required": true
          }
        ]
      },
      {
        "name": "Current Condition",
        "questions": [
          {
            "name": "Which of the following symptoms do you suffer from?",
            "type": "checkboxes",
            "answers": [
              {
                "value": "Fever"
              },
              {
                "value": "Headache"
              },
              {
                "value": "Shortness of breath"
              },
              {
                "value": "Cough"
              }
            ],
            "required": false
          }
        ]
      }
    ]
  },
  "name": "New Patient Intake",
  "restricted_to_practitioner": false,
  "archived_at": null,
  "links": {
    "self": "https://api.au1.cliniko.com/v1/patient_form_templates/507944033264337974"
  }
}
```

Create Patient Form Template
----------------
**Resources**
* ```POST /patient_form_templates``` create a patient form template

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/patient_form_templates \
  -u API_KEY: \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -d '{ "name": "My template", "content": { "sections": [{ "name": "Section 1", "questions": [{ "name": "Question 1", "type": "text" }] }] } }' \
  -X POST
```
**Example Response**
```
Headers { Location: https://api.au1.cliniko.com/v1/patient_form_templates/507944033264337974 }
```
```json
{
  "id": "507944033264337974",
  "created_at": "2020-12-01T21:01:13Z",
  "updated_at": "2020-12-01T21:01:13Z",
  "content": {
    "sections": [
      {
        "name": "Section 1",
        "questions": [
          {
            "name": "Question 1",
            "type": "text"
          }
        ]
      }
    ]
  },
  "name": "My template",
  "restricted_to_practitioner": false,
  "archived_at": null,
  "links": {
    "self": "https://api.au1.cliniko.test:3000/v1/patient_form_templates/507944033264337974"
  }
}
```

Update Patient Form Template
----------------
**Resources**
* ```PUT /patient_form_templates/:id``` update a patient form template

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/patient_form_templates/507944033264337974 \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'Content-Type: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -d '{ "name": "My template", "content": "{\"sections\": [{\"name\": \"Section A\", \"questions\": [{\"name\": \"Question A\", \"type\": \"text\"}]}]}" }' \
  -X PUT
```
**Example Response**
```json
{
  "id": "507944033264337974",
  "created_at": "2020-12-01T21:01:13Z",
  "updated_at": "2020-12-01T21:01:13Z",
  "content": {
    "sections": [
      {
        "name": "Section A",
        "questions": [
          {
            "name": "Question A",
            "type": "text"
          }
        ]
      }
    ]
  },
  "name": "My template",
  "restricted_to_practitioner": false,
  "archived_at": null,
  "links": {
    "self": "https://api.au1.cliniko.test:3000/v1/patient_form_templates/507944033264337974"
  }
}
```

Archive Patient Form Template
----------------
**Resources**
* ```POST /patient_form_templates/:id/archive``` archive a patient form template

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/patient_form_template/507944033264337974/archive \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -X POST
```
**Example Response**
A status code of `204 no content` will be returned if successful

Filtering Patient Form Templates
----------------

For any route that returns a set of patient form templates, you can filter them by:
* ```created_at``` (DateTime)
* ```id``` (Integer)
* ```updated_at``` (DateTime)
* ```archived_at``` (DateTime)

See [Filtering Results](https://github.com/redguava/cliniko-api#filtering-results) for details on how to apply filters.

Patient Form Template Content Schema
----------------
The `content` property of a patient form template is a JSON object. The schema is validated and must conform to the following rules.

**Content Object**

Property | Type | Accepted Values | Notes
------------ | ------------- | ------------- | -------------
sections | array | An array of section objects | Not required. An empty array is not valid. If there are no sections, this property should be omitted and `content` should be set to `null`.

**Section Object**

Property | Type | Accepted Values | Notes
------------ | ------------- | ------------- | -------------
name | string | A string of 255 or fewer characters | Not required. If there is no name, this property should be omitted.
description | string | A string of 10,000 or fewer characters | Not required. If there is no description, this property should be omitted.
questions | array | An array of question objects | Not required. An empty array is not valid. If there are no questions, this property should be omitted.

**Question Object**

Property | Type | Accepted Values | Notes
------------ | ------------- | ------------- | -------------
name | string | A string of 255 or fewer characters | Name is required.
type | string | `text`, `paragraph`, `checkboxes`, `radiobuttons`. `signature` | Type is required.
required | boolean | `true`, `false` | A `null` value is not valid. If question is not required, this property should be either omitted or have a value of `false`.
answers | array | An array of answer objects | Not required. Only accepted for `checkboxes` and `radiobuttons` type questions. An empty array is not valid. If there are no answers, this property should be omitted.

**Answer Object**

Property | Type | Accepted Values | Notes
------------ | ------------- | ------------- | -------------
value | string | A string of 255 or fewer characters or `null` | Not required.
