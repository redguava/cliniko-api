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
```

Get Treatment Note
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
