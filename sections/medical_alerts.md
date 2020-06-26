Medical Alerts
============
* [Get Medical Alerts](#get-medical-alerts "This will return all medical alerts.")
* [Get Deleted Medical Alerts](#get-deleted-medical-alerts "This will return all deleted medical alerts")
* [Get Medical Alert](#get-medical-alert "This will return a specified medical alert.")
* [Create Medical Alert](#create-medical-alert "This will create a medical alert.")
* [Update Medical Alert](#update-medical-alert "This will update a medical alert.")
* [Delete Medical Alert](#delete-medical-alert "This will delete a medical alert.")

Get Medical Alerts
----------------

**Resources**
* ```GET /medical_alerts``` get all medical alerts
* ```GET /patients/:id/medical_alerts``` get all medical alerts for a specified patient

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/medical_alerts \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "medical_alerts": [
    {
      "created_at": "2013-03-27T10:03:57Z",
      "id": 343589,
      "name": "a medical alert",
      "updated_at": "2013-03-27T10:03:57Z",
      "deleted_at": null,
      "patient": {
        "links": {"self": "https://api.au1.cliniko.com/v1/patients/12345"}
      },
      "links": {"self": "https://api.au1.cliniko.com/v1/medical_alerts/343589"}
    }
  ],
  "total_entries": 1,
  "links": {"self": "https://api.au1.cliniko.com/v1/medical_alerts?page=1"}
}
```

Get Deleted Medical Alerts
----------------

**Resources**
* ```GET /medical_alerts/deleted``` get all deleted medical alerts
* ```GET /patients/:id/medical_alerts/deleted``` get all deleted medical alerts for a specified patient

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/medical_alerts/deleted \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "medical_alerts": [
    {
      "created_at": "2013-03-27T10:03:57Z",
      "id": 343589,
      "name": "a medical alert",
      "updated_at": "2013-03-27T10:03:57Z",
      "deleted_at": "2013-06-05T14:38:48Z",
      "patient": {
        "links": {"self": "https://api.au1.cliniko.com/v1/patients/12345"}
      },
      "links": {"self": "https://api.au1.cliniko.com/v1/medical_alerts/343589"}
    }
  ],
  "total_entries": 1,
  "links": {"self": "https://api.au1.cliniko.com/v1/medical_alerts/deleted?page=1"}
}
```

Get Medical Alert
------------

**Resources**
* ```GET /medical_alerts/:id``` get a specified medical alert

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/medical_alerts/1 \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "created_at": "2013-03-27T10:03:57Z",
  "id": 1,
  "name": "a medical alert",
  "updated_at": "2013-03-27T10:03:57Z",
  "deleted_at": null,
  "patient": {
    "links": {"self": "https://api.au1.cliniko.com/v1/patients/12345"}
  },
  "links": {"self": "https://api.au1.cliniko.com/v1/medical_alerts/1"}
}
```

Create Medical Alert
----------------
**Resources**
* ```POST /medical_alerts``` create a medical alert

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/medical_alerts \
  -u API_KEY: \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -d '{ "name": "a medical alert", "patient_id": "12345" }' \
  -X POST
```
**Example Response**
```
Headers { Location: http://api.cliniko.com/medical_alerts/1 }
```
```json
{
  "created_at": "2013-03-27T10:03:57Z",
  "id": 1,
  "name": "a medical alert",
  "updated_at": "2013-03-27T10:03:57Z",
  "deleted_at": null,
  "patient": {
    "links": {"self": "https://api.au1.cliniko.com/v1/patients/12345"}
  },
  "links": {"self": "https://api.au1.cliniko.com/v1/medical_alerts/1"}
}
```

Update Medical Alert
----------------
**Resources**
* ```PUT /medical_alerts/:id``` update a medical alert

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/medical_alerts/1 \
  -u API_KEY: \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -d '{ "name": "update medical alert name" }' \
  -X PUT
```
**Example Response**
```json
{
  "created_at": "2013-03-27T10:03:57Z",
  "id": 1,
  "name": "updated medical alert name",
  "updated_at": "2013-03-27T10:03:57Z",
  "deleted_at": null,
  "patient": {
    "links": {"self": "https://api.au1.cliniko.com/v1/patients/12345"}
  },
  "links": {"self": "https://api.au1.cliniko.com/v1/medical_alerts/1"}
}
```

Delete Medical Alert
----------------
**Resources**
* ```DELETE /medical_alerts/:id``` delete an medical alert

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/medical_alerts/1 \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -X DELETE
```
**Example Response**
A status code of `204 no content` will be returned if successful

Filtering Medical Alerts
----------------

For any route that returns a set of medical alerts, you can filter them by:
* ```created_at``` DateTime
* ```id``` Integer
* ```patient_id``` Integer
* ```updated_at``` DateTime

See [Filtering Results](https://github.com/redguava/cliniko-api#filtering-results) for details on how to apply filters.
