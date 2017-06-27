Treatment Notes
============
> Notes taken about a patient visit.

* [Get Treatment Notes](#get-treatment-notes "This will return all treatment notes.")
* [Get Deleted Treatment Notes](#get-deleted-treatment-notes "This will return all deleted treatment notes.")
* [Get Treatment Note](#get-treatment-note "This will return a specified treatment note.")
* [Create Treatment Note](#create-treatment-note "This will create a treatment note.")
* [Update Treatment Note](#update-treatment-note "This will update a treatment note.")
* [Delete Patient](#delete-treatment-note "This will delete a treatment note.")

Get Treatment Notes
----------------

**Resources**
* ```GET /treatment_notes``` get all treatment notes


**Example Request**
```shell
curl https://api.cliniko.com/v1/treatment_notes \
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
          "self": "https://api.cliniko.com/v1/patients/123"
        }
      },
      "practitioner": {
        "links": {
          "self": "https://api.cliniko.com/v1/practitioners/456"
        }
      },
      "treatment_note_template": {
        "links": {
          "self": "https://api.cliniko.com/v1/treatment_note_templates/789"
        }
      },
      "links": {
        "self": "https://api.cliniko.com/v1/treatment_notes/1"
      }
    }
  ],
  "total_entries": 1,
  "links": {
    "self": "https://api.cliniko.com/v1/treatment_notes?page=1"
  }
}
```

Get Deleted Treatment Notes
----------------

**Resources**
* ```GET /treatment_notes/deleted``` get all deleted treatment notes

**Example Request**
```shell
curl https://api.cliniko.com/v1/treatment_notes/deleted \
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
          "self": "https://api.cliniko.com/v1/patients/123"
        }
      },
      "practitioner": {
        "links": {
          "self": "https://api.cliniko.com/v1/practitioners/456"
        }
      },
      "treatment_note_template": {
        "links": {
          "self": "https://api.cliniko.com/v1/treatment_note_templates/789"
        }
      },
      "links": {
        "self": "https://api.cliniko.com/v1/treatment_notes/1"
      }
    }
  ],
  "total_entries": 1,
  "links": {
    "self": "https://api.cliniko.com/v1/treatment_notes/deleted?page=1"
  }
}
```

Get Treatment Note
------------

**Resources**
* ```GET /treatment_notes/:id``` get a specified treatment note

**Example Request**
```shell
curl https://api.cliniko.com/v1/treatment_notes/1 \
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
      "self": "https://api.cliniko.com/v1/patients/123"
    }
  },
  "practitioner": {
    "links": {
      "self": "https://api.cliniko.com/v1/practitioners/456"
    }
  },
  "treatment_note_template": {
    "links": {
      "self": "https://api.cliniko.com/v1/treatment_note_templates/789"
    }
  },
  "links": {
    "self": "https://api.cliniko.com/v1/treatment_notes/1"
  }
}
```

Create Treatment Note
----------------
**Resources**
* ```POST /treatment_notes``` create a treatment note

**Example Request**
```shell
curl https://api.cliniko.com/v1/treatment_notes \
  -u API_KEY: \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -d '{ "draft": true, "patient_id": 123, "practitioner_id": 456, "treatment_note_template_id": 789 }' \
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
  "content": null,
  "draft": true,
  "title": "Standard Consultation",
  "deleted_at": null,
  "author_name": "Natasha Hermiston",
  "patient": {
    "links": {
      "self": "https://api.cliniko.com/v1/patients/123"
    }
  },
  "practitioner": {
    "links": {
      "self": "https://api.cliniko.com/v1/practitioners/456"
    }
  },
  "treatment_note_template": {
    "links": {
      "self": "https://api.cliniko.com/v1/treatment_note_templates/789"
    }
  },
  "links": {
    "self": "https://api.cliniko.com/v1/treatment_notes/1"
  }
}
```

Update Treatment Note
----------------
**Resources**
* ```PUT /treatment_notes/:id``` update a treatment note

**Example Request**
```shell
curl https://api.cliniko.com/v1/treatment_notes/1 \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'Content-Type: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -d '{ "draft": false }' \
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
  "draft": false,
  "title": "Standard Consultation",
  "deleted_at": null,
  "author_name": "Natasha Hermiston",
  "patient": {
    "links": {
      "self": "https://api.cliniko.com/v1/patients/123"
    }
  },
  "practitioner": {
    "links": {
      "self": "https://api.cliniko.com/v1/practitioners/456"
    }
  },
  "treatment_note_template": {
    "links": {
      "self": "https://api.cliniko.com/v1/treatment_note_templates/789"
    }
  },
  "links": {
    "self": "https://api.cliniko.com/v1/treatment_notes/1"
  }
}
```

Delete Treatment Note
----------------
**Resources**
* ```DELETE /treatment_notes/:id``` delete a treatment note

**Example Request**
```shell
curl https://api.cliniko.com/v1/treatment_notes/1 \
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
