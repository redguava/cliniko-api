Treatment Notes
============
> Notes taken about a patient visit.

* [Get Treatment Notes](#get-treatment-notes "This will return all treatment notes.")
* [Get Deleted Treatment Notes](#get-deleted-treatment-notes "This will return all deleted treatment notes.")
* [Get Treatment Note](#get-treatment-note "This will return a specified treatment note.")
* [Create Treatment Note](#create-treatment-note "This will create a treatment note.")
* [Update Treatment Note](#update-treatment-note "This will update a treatment note.")
* [Delete Treatment Note](#delete-treatment-note "This will delete a treatment note.")

Get Treatment Notes
----------------

**Resources**
* ```GET /treatment_notes``` get all treatment notes


**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/treatment_notes \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "treatment_notes": [
    {
      "id": 1,
      "created_at": "2017-06-12T16:56:57Z",
      "updated_at": "2017-06-12T16:56:57Z",
      "content": {
        "sections": [
          {
            "name": "Section 1",
            "questions": [
              {
                "name": "Patient progress report",
                "type": "paragraph",
                "answer": "<div>Answers to paragraph questions support basic HTML!</div>"
              },
              {
                "name": "Assessment",
                "type": "text",
                "answer": "Answers to text questions are single lines and do not support HTML"
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
                  { "value": "Choice 2", "selected": true },
                  { "value": "Choice 3" }
                ]
              },
              {
                "name": "Choose one or more",
                "type": "checkboxes",
                "answers": [
                  { "value": "Choice 1", "selected": true },
                  { "value": "Choice 2", "selected": true },
                  { "value": "Choice 3" }
                ]
              }
            ]
          }
        ]
      },
      "draft": true,
      "title": "Standard Consultation",
      "deleted_at": null,
      "author_name": "Natasha Hermiston",
      "patient": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/patients/123"
        }
      },
      "practitioner": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/practitioners/456"
        }
      },
      "treatment_note_template": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/treatment_note_templates/789"
        }
      },
      "links": {
        "self": "https://api.au1.cliniko.com/v1/treatment_notes/1"
      }
    }
  ],
  "total_entries": 1,
  "links": {
    "self": "https://api.au1.cliniko.com/v1/treatment_notes?page=1"
  }
}
```

Get Deleted Treatment Notes
----------------

**Resources**
* ```GET /treatment_notes/deleted``` get all deleted treatment notes

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/treatment_notes/deleted \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "treatment_notes": [
    {
      "id": 1,
      "created_at": "2017-06-12T16:56:57Z",
      "updated_at": "2017-06-12T16:56:57Z",
      "content": {
        "sections": [
          {
            "name": "Section 1",
            "questions": [
              {
                "name": "Patient progress report",
                "type": "paragraph",
                "answer": "<div>Answers to paragraph questions support basic HTML!</div>"
              },
              {
                "name": "Assessment",
                "type": "text",
                "answer": "Answers to text questions are single lines and do not support HTML"
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
                  { "value": "Choice 2", "selected": true },
                  { "value": "Choice 3" }
                ]
              },
              {
                "name": "Choose one or more",
                "type": "checkboxes",
                "answers": [
                  { "value": "Choice 1", "selected": true },
                  { "value": "Choice 2", "selected": true },
                  { "value": "Choice 3" }
                ]
              }
            ]
          }
        ]
      },
      "draft": true,
      "title": "Standard Consultation",
      "deleted_at": "2017-06-22T13:14:19Z",
      "author_name": "Natasha Hermiston",
      "patient": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/patients/123"
        }
      },
      "practitioner": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/practitioners/456"
        }
      },
      "treatment_note_template": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/treatment_note_templates/789"
        }
      },
      "links": {
        "self": "https://api.au1.cliniko.com/v1/treatment_notes/1"
      }
    }
  ],
  "total_entries": 1,
  "links": {
    "self": "https://api.au1.cliniko.com/v1/treatment_notes/deleted?page=1"
  }
}
```

Get Treatment Note
------------

**Resources**
* ```GET /treatment_notes/:id``` get a specified treatment note

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/treatment_notes/1 \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "id": 1,
  "created_at": "2017-06-12T16:56:57Z",
  "updated_at": "2017-06-12T16:56:57Z",
  "content": {
    "sections": [
      {
        "name": "Section 1",
        "questions": [
          {
            "name": "Patient progress report",
            "type": "paragraph",
            "answer": "<div>Answers to paragraph questions support basic HTML!</div>"
          },
          {
            "name": "Assessment",
            "type": "text",
            "answer": "Answers to text questions are single lines and do not support HTML"
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
              { "value": "Choice 2", "selected": true },
              { "value": "Choice 3" }
            ]
          },
          {
            "name": "Choose one or more",
            "type": "checkboxes",
            "answers": [
              { "value": "Choice 1", "selected": true },
              { "value": "Choice 2", "selected": true },
              { "value": "Choice 3" }
            ]
          }
        ]
      }
    ]
  },
  "draft": true,
  "title": "Standard Consultation",
  "deleted_at": null,
  "author_name": "Natasha Hermiston",
  "patient": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/patients/123"
    }
  },
  "practitioner": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/practitioners/456"
    }
  },
  "treatment_note_template": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/treatment_note_templates/789"
    }
  },
  "links": {
    "self": "https://api.au1.cliniko.com/v1/treatment_notes/1"
  }
}
```

Create Treatment Note
----------------
When creating treatment notes, the treatment note _author_ will be the practitioner linked to the API key you're using.
> Only users that are also practitioners may create treatment notes.

In addition, you may link a treatment note to an appointment by adding the `booking_id` parameter - this should contain the `id` of a valid [individual](https://github.com/redguava/cliniko-api/blob/master/sections/individual_appointments.md) or [group appointment](https://github.com/redguava/cliniko-api/blob/master/sections/group_appointments.md).

**Resources**
* ```POST /treatment_notes``` create a treatment note

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/treatment_notes \
  -u API_KEY: \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -d '{ "draft": true, "patient_id": 123, "booking_id": 987, "treatment_note_template_id": 789, "content": {"sections": [{"name": "Section 1", "questions": [{"name": "Question 1", "type": "text", "answer": "The answer is 42"}]}]} }' \
  -X POST
```
**Example Response**
```
Headers { Location: http://api.cliniko.com/treatment_notes/1 }
```
```json
{
  "id": 1,
  "created_at": "2017-06-12T16:56:57Z",
  "updated_at": "2017-06-12T16:56:57Z",
  "content": {
    "sections": [
      {
        "name": "Section 1",
        "questions": [
          {
            "name": "Question 1",
            "type": "text",
            "answer": "The answer is not 42"
          }
        ]
      }
    ]
  },
  "draft": true,
  "title": "Standard Consultation",
  "deleted_at": null,
  "author_name": "Natasha Hermiston",
  "patient": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/patients/123"
    }
  },
  "booking": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/bookings/987"
    }
  },
  "practitioner": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/practitioners/456"
    }
  },
  "treatment_note_template": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/treatment_note_templates/789"
    }
  },
  "links": {
    "self": "https://api.au1.cliniko.com/v1/treatment_notes/1"
  }
}
```

Update Treatment Note
----------------
**Resources**
* ```PUT /treatment_notes/:id``` update a treatment note

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/treatment_notes/1 \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'Content-Type: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -d '{ "draft": false, "content": {"sections": [{"name": "Section 1", "questions": [{"name": "Question 1", "type": "text", "answer": "The answer is not 42"}]}]} }' \
  -X PUT
```
**Example Response**
```json
{
  "id": 1,
  "created_at": "2017-06-12T16:56:57Z",
  "updated_at": "2017-06-12T16:56:57Z",
  "content": {
    "sections": [
      {
        "name": "Section 1",
        "questions": [
          {
            "name": "Question 1",
            "type": "text",
            "answer": "The answer is not 42"
          }
        ]
      }
    ]
  },
  "draft": false,
  "title": "Standard Consultation",
  "deleted_at": null,
  "author_name": "Natasha Hermiston",
  "patient": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/patients/123"
    }
  },
  "practitioner": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/practitioners/456"
    }
  },
  "treatment_note_template": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/treatment_note_templates/789"
    }
  },
  "links": {
    "self": "https://api.au1.cliniko.com/v1/treatment_notes/1"
  }
}
```

Delete Treatment Note
----------------
**Resources**
* ```DELETE /treatment_notes/:id``` delete a treatment note

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/treatment_notes/1 \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -X DELETE
```
**Example Response**
A status code of `204 no content` will be returned if successful

Filtering Treatment Notes
----------------

For any route that returns a set of treatment notes, you can filter them by:
* ```created_at``` (DateTime)
* ```id``` (Integer)
* ```patient_id``` (Integer)
* ```practitioner_id``` (Integer)
* ```treatment_note_template_id``` (Integer)
* ```updated_at``` (DateTime)

See [Filtering Results](https://github.com/redguava/cliniko-api#filtering-results) for details on how to apply filters.

Treatment Note Content Schema
----------------
The `content` property of a treatment note is a JSON object. The schema is validated and must conform to the following rules.

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
type | string | `text`, `paragraph`, `checkboxes`, `radiobuttons` | Type is required.
answer | string | A string | Not required. Only accepted for `text` and `paragraph` type questions. Empty values are not valid. If there is no answer, this property should be omitted. Accepts basic HTML, see [HTML docs](#permitted-html-in-paragraph-answers "docs for HTML content") for details.
answers | array | An array of answer objects | Not required. Only accepted for `checkboxes` and `radiobuttons` type questions. An empty array is not valid. If there are no answers, this property should be omitted.

**Answer Object**

Property | Type | Accepted Values | Notes
------------ | ------------- | ------------- | -------------
value | string | A string of 255 or fewer characters or `null` | Not required.
selected | boolean | true | Not required. Only accepts `true`. If the answer is not selected, this property should be omitted. For `radiobuttons` type questions, only one answer can be selected.

Permitted HTML in paragraph answers
----------------
Basic HTML is supported in answers to paragraph questions. We sanitize these answers to ensure the HTML is safe and our editor can support the formatting. Currently, only `div` and `br` tags are supported. We will be opening up support for more tags in the future. Characters like `\n`, `\r`, and `\t` will be stripped out. The angle bracket characters (`<`, and `>`) should be sent as html encodings (ex: `<` should be sent as `&lt;`). Content inside unescaped angle brackets could be indentified as unsupported HTML and will be stripped.
