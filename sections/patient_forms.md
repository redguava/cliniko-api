Patient Forms
============

* [Get Patient Forms](#get-patient-form "This will return all patient forms.")
* [Get Patient Form](#get-patient-form "This will return a specified patient form.")
* [Create Patient Form](#create-patient-form "This will create a patient form.")
* [Update Patient Form](#update-patient-form "This will update a patient form.")
* [Archive Patient Form](#archive-patient-form "This will archive a patient form.")

Get Patient Forms
----------------

**Resources**
* ```GET /patient_forms``` get all patient forms


**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/patient_forms \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "patient_forms": [
    {
      "id": "564393784322819470",
      "created_at": "2020-12-05T16:50:29Z",
      "updated_at": "2020-12-05T16:50:40Z",
      "name": "New Patient Intake",
      "restricted_to_practitioner": true,
      "url": "https://account-subdomain.cliniko.com/f/?0QbE1ZP7gp-asV2uQmf7HZb4ne6hfwoz2",
      "completed_at": "2020-12-05T16:50:40Z",
      "content": {
        "sections": [
          {
            "name": "Medical History",
            "questions": [
              {
                "name": "Please describe your medical history.",
                "type": "paragraph",
                "required": true,
                "answer": "The answer"
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
                    "value": "Headache",
                    "selected": true
                  },
                  {
                    "value": "Shortness of breath"
                  },
                  {
                    "value": "Cough",
                    "selected": true
                  }
                ],
                "required": false
              }
            ]
          },
          {
            "name": "Privacy Policy",
            "questions": [
              {
                "name": "I accept the above privacy policy",
                "type": "signature",
                "signature_id": "565805660088829113"
              }
            ],
            "description": "<div>We promise to keep your personal information private.</div>"
          }
        ]
      },
      "signatures": [
       {
         "links": {
           "self": "http://api.au1.cliniko.com/v1/patient_forms/564393784322819470/signatures/565805660088829113"
         }
       }
     ],
      "attendee": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/attendees/543342507652548177"
        }
      },
      "booking": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/bookings/543342507031791275"
        }
      },
      "patient": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/patients/479516700664923158"
        }
      },
      "links": {
        "self": "https://api.au1.cliniko.com/v1/patient_forms/564393784322819470"
      }
    }
  ],
  "links": {
    "self": "https://api.au1.cliniko.com/v1/patient_forms?page=1"
  }
}
```

Get Patient Form
------------

**Resources**
* ```GET /patient_forms/:id``` get a specified patient form

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/patient_forms/564393784322819470 \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "id": "564393784322819470",
  "created_at": "2020-12-05T16:50:29Z",
  "updated_at": "2020-12-05T16:50:40Z",
  "name": "New Patient Intake",
  "restricted_to_practitioner": true,
  "url": "https://account-subdomain.cliniko.com/f/?0QbE1ZP7gp-asV2uQmf7HZb4ne6hfwoz2",
  "completed_at": "2020-12-05T16:50:40Z",
  "content": {
    "sections": [
      {
        "name": "Medical History",
        "questions": [
          {
            "name": "Please describe your medical history.",
            "type": "paragraph",
            "required": true,
            "answer": "The answer"
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
                "value": "Headache",
                "selected": true
              },
              {
                "value": "Shortness of breath"
              },
              {
                "value": "Cough",
                "selected": true
              }
            ],
            "required": false
          }
        ]
      },
      {
        "name": "Privacy Policy",
        "questions": [
          {
            "name": "I accept the above privacy policy",
            "type": "signature",
            "signature_id": "565805660088829113"
          }
        ],
        "description": "<div>We promise to keep your personal information private.</div>"
      }
    ]
  },
  "signatures": [
   {
     "links": {
       "self": "http://api.au1.cliniko.com/v1/patient_forms/564393784322819470/signatures/565805660088829113"
     }
   }
 ],
  "attendee": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/attendees/543342507652548177"
    }
  },
  "booking": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/bookings/543342507031791275"
    }
  },
  "patient": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/patients/479516700664923158"
    }
  },
  "links": {
    "self": "https://api.au1.cliniko.com/v1/patient_forms/564393784322819470"
  }
}
```

Create Patient Form
----------------
> When creating a patient form with a `patient_form_template_id`, the values for `name`, `content`, and `restricted_to_practitioner` will be pulled from the template. However, you may provide any of those values to override the template, or even provide all of your own values and exclude the `patient_form_template_id` altogether.

**Resources**
* ```POST /patient_forms``` create a patient form

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/patient_forms \
  -u API_KEY: \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -d '{ "patient_id": "479516700664923158", "patient_form_template_id": "507944033264337974" }' \
  -X POST
```
**Example Response**
```
Headers { Location: https://api.au1.cliniko.com/v1/patient_forms/564393784322819470 }
```
```json
{
  "id": "564393784322819470",
  "created_at": "2020-12-05T16:50:29Z",
  "updated_at": "2020-12-05T16:50:40Z",
  "name": "New Patient Intake",
  "restricted_to_practitioner": true,
  "url": "https://account-subdomain.cliniko.com/f/?0QbE1ZP7gp-asV2uQmf7HZb4ne6hfwoz2",
  "completed_at": null,
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
      },
      {
        "name": "Privacy Policy",
        "questions": [
          {
            "name": "I accept the above privacy policy",
            "type": "signature"
          }
        ],
        "description": "<div>We promise to keep your personal information private.</div>"
      }
    ]
  },
  "signatures": null,
  "patient": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/patients/479516700664923158"
    }
  },
  "links": {
    "self": "https://api.au1.cliniko.com/v1/patient_forms/564393784322819470"
  }
}
```

Update Patient Form
----------------
**Resources**
* ```PUT /patient_forms/:id``` update a patient form

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/patient_forms/564393784322819470 \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'Content-Type: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -d '{ "completed": true, "content": "{\"sections\": [{\"name\": \"Medical History\",\"questions\": [{\"name\": \"Please describe your medical history.\",\"type\": \"paragraph\",\"required\": true,\"answer\": \"The answer\"}]},{\"name\": \"Current Condition\",\"questions\": [{\"name\": \"Which of the following symptoms do you suffer from?\",\"type\": \"checkboxes\",\"answers\": [{\"value\": \"Fever\"},{\"value\": \"Headache\",\"selected\": true},{\"value\": \"Shortness of breath\"},{\"value\": \"Cough\",\"selected\": true}],\"required\": false}]},{\"name\": \"Privacy Policy\",\"questions\": [{\"name\": \"I accept the above privacy policy\",\"type\": \"signature\",\"signature\": \"data:image/svg+xml;base64,PHN2ZyBvbmxvYWQ...\"}],\"description\": \"<div>We promise to keep your personal information private.</div>\"}]}" }' \
  -X PUT
```
**Example Response**
```json
{
  "id": "564393784322819470",
  "created_at": "2020-12-05T16:50:29Z",
  "updated_at": "2020-12-05T16:50:40Z",
  "name": "New Patient Intake",
  "restricted_to_practitioner": true,
  "url": "https://account-subdomain.cliniko.com/f/?0QbE1ZP7gp-asV2uQmf7HZb4ne6hfwoz2",
  "completed_at": "2020-12-05T16:50:40Z",
  "content": {
    "sections": [
      {
        "name": "Medical History",
        "questions": [
          {
            "name": "Please describe your medical history.",
            "type": "paragraph",
            "required": true,
            "answer": "The answer"
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
                "value": "Headache",
                "selected": true
              },
              {
                "value": "Shortness of breath"
              },
              {
                "value": "Cough",
                "selected": true
              }
            ],
            "required": false
          }
        ]
      },
      {
        "name": "Privacy Policy",
        "questions": [
          {
            "name": "I accept the above privacy policy",
            "type": "signature",
            "signature_id": "565805660088829113"
          }
        ],
        "description": "<div>We promise to keep your personal information private.</div>"
      }
    ]
  },
  "signatures": [
   {
     "links": {
       "self": "http://api.au1.cliniko.com/v1/patient_forms/564393784322819470/signatures/565805660088829113"
     }
   }
 ],
  "patient": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/patients/479516700664923158"
    }
  },
  "links": {
    "self": "https://api.au1.cliniko.com/v1/patient_forms/564393784322819470"
  }
}
```

Archive Patient Form
----------------
**Resources**
* ```POST /patient_forms/:id/archive``` archive a patient form

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/patient_forms/564393784322819470/archive \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -X POST
```
**Example Response**
A status code of `204 no content` will be returned if successful

Filtering Patient Forms
----------------

For any route that returns a set of patient forms, you can filter them by:
* ```archived_at``` (DateTime)
* ```completed_at``` (DateTime)
* ```created_at``` (DateTime)
* ```id``` (Integer)
* ```patient_id``` (Integer)
* ```updated_at``` (DateTime)

See [Filtering Results](https://github.com/redguava/cliniko-api#filtering-results) for details on how to apply filters.

Patient Form Content Schema
----------------
The `content` property of a patient form is a JSON object. The schema is validated and must conform to the following rules.

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
answer | string | A of 255 or fewer characters | Only accepted for `text` and `paragraph` type. This will be required if the `required` property is `true`, and the patient form has been completed.
answers | array | An array of answer objects | Only accepted for `checkboxes` and `radiobuttons` type questions. An empty array is not valid. If there are no answers, this property should be omitted. At least one answer must be `selected` if the `required` property is `true` and the patient form has been completed.
signature | string | A [data URI](https://en.wikipedia.org/wiki/Data_URI_scheme) representing an SVG image, with a maximum dimension of 500x500px. | Only accepted for `signature` type questions. The image will be saved as a `Signature` resource, and this property will be replaced by a `signature_id` property in the response. This property or the `signature_id` property will be required if the `required` property is `true`, and the patient form has been completed.
signature_id | integer | An id of a previously submitted `signature` | Only accepted for `signature` type questions. This property or the `signature` property will be required if the `required` property is `true`, and the patient form has been completed.

**Answer Object**

Property | Type | Accepted Values | Notes
------------ | ------------- | ------------- | -------------
value | string | A string of 255 or fewer characters or `null` | Not required.
selected | boolean | true | Not required. Only accepts `true`. If the answer is not selected, this property should be omitted. For `radiobuttons` type questions, only one answer can be selected.

Permitted HTML in paragraph answers
----------------
Basic HTML is supported in answers to paragraph questions. We sanitize these answers to ensure the HTML is safe and our editor can support the formatting. Currently, only `div` and `br` tags are supported. Characters like `\n`, `\r`, and `\t` will be stripped out. The angle bracket characters (`<`, and `>`) should be sent as html encodings (ex: `<` should be sent as `&lt;`). Content inside unescaped angle brackets could be indentified as unsupported HTML and will be stripped.
