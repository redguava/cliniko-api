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
curl https://api.au1.cliniko.com/v1/treatment_note_templates \
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
        "self": "https://api.au1.cliniko.com/v1/treatment_note_templates/1"
      }
    }
  ],
  "total_entries": 1,
  "links": {
    "self": "https://api.au1.cliniko.com/v1/treatment_note_templates?page=1"
  }
}
```

Get Deleted Treatment Note Templates
----------------

**Resources**
* ```GET /treatment_note_templates/deleted``` get all deleted treatment note templates

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/treatment_note_templates/deleted \
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
        "self": "https://api.au1.cliniko.com/v1/treatment_note_templates/1"
      }
    }
  ],
  "total_entries": 1,
  "links": {
    "self": "https://api.au1.cliniko.com/v1/treatment_note_templates/deleted?page=1"
  }
}
```

Get Treatment Note Template
------------

**Resources**
* ```GET /treatment_note_templates/:id``` get a specified treatment note template

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/treatment_note_templates/1 \
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
    "self": "https://api.au1.cliniko.com/v1/treatment_note_templates/1"
  }
}
```

Create Treatment Note Template
----------------
**Resources**
* ```POST /treatment_note_templates``` create a treatment note template

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/treatment_note_templates \
  -u API_KEY: \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -d '{ "name": "My template", "content": "{\"sections\": [{\"name\": \"Section 1\", \"questions\": [{\"name\": \"Question 1\", \"type\": \"text\"}]}]}" }' \
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
    "self": "https://api.au1.cliniko.com/v1/treatment_note_templates/1"
  }
}
```

Update Treatment Note Template
----------------
**Resources**
* ```PUT /treatment_note_templates/:id``` update a treatment note template

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/treatment_note_templates/1 \
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
  "id": 1,
  "created_at": "2017-06-12T16:03:42Z",
  "updated_at": "2017-06-29T05:32:51Z",
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
    "self": "https://api.au1.cliniko.com/v1/treatment_note_templates/1"
  }
}
```

Delete Treatment Note Template
----------------
**Resources**
* ```DELETE /treatment_note_templates/:id``` delete a treatment note template

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/treatment_note_templates/1 \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -X DELETE
```
**Example Response**
A status code of `204 no content` will be returned if successful

Filtering Treatment Note Templates
----------------

For any route that returns a set of treatment note templates, you can filter them by:
* ```created_at``` (DateTime)
* ```id``` (Integer)
* ```updated_at``` (DateTime)

See [Filtering Results](https://github.com/redguava/cliniko-api#filtering-results) for details on how to apply filters.

Treatment Note Template Content Schema
----------------
The `content` property of a treatment note template is a JSON object. The schema is validated and must conform to the following rules.

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
answer | string | A string | Not required. Only accepted for `paragraph` type questions. This will be used as the default answer for treatment notes built from this template. Empty values are not valid. If there is no default answer, this property should be omitted. Accepts basic HTML, see [HTML docs](#permitted-html-in-paragraph-answers "docs for HTML content") for details.
answers | array | An array of answer objects | Not required. Only accepted for `checkboxes` and `radiobuttons` type questions. An empty array is not valid. If there are no answers, this property should be omitted.

**Answer Object**

Property | Type | Accepted Values | Notes
------------ | ------------- | ------------- | -------------
value | string | A string of 255 or fewer characters or `null` | Not required.

Permitted HTML in paragraph answers
----------------
Basic HTML is supported in answers to paragraph questions. We sanitize these answers to ensure the HTML is safe and our editor can support the formatting. Currently, only `div` and `br` tags are supported. We will be opening up support for more tags in the future. Characters like `\n`, `\r`, and `\t` will be stripped out. The angle bracket characters (`<`, and `>`) should be sent as html encodings (ex: `<` should be sent as `&lt;`). Content inside unescaped angle brackets could be indentified as unsupported HTML and will be stripped.
