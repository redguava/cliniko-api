Communications
============

Response attributes will vary based on communication type and user permission.

* [Get Communications](#get-communications "This will return all communications.")
* [Get Communication](#get-communication "This with return a specified communication.")
* [Create Memo Communication](#create-memo-communication "This will create a memo communication.")
* [Update Memo Communication](#update-memo-communication "This will update a memo communication.")
* [Archive Memo Communication](#archive-memo-communication "This will archive a memo communication.")
* [Filtering Communications](#filtering-communications "This will let you filter the communication query results.")
* [Category Code Mapping](#category-code-mapping "This table lists the valid category codes and their corresponding descriptions.")
* [Permitted Memo Communication Properties](#permitted-memo-communication-properties "These are the permitted properties when creating or updating a memo communication.")

Get Communications
--------------------

**Resources**
* ```GET /communications``` get all communications

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/communications \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
    "communications": [
        {
            "archived_at": null,
            "category": "Appointment Reminder",
            "category_code": 1,
            "content": "Lorem ipsum dolor sit amet consectetuer adipiscing elit sed diam nonummy nibh",
            "content_subject": "Appointment Reminder",
            "created_at": "2022-02-02T03:42:27Z",
            "direction_code": 1,
            "direction_description": "Sent",
            "from": null,
            "id": "1",
            "links": {
                "self": "https://api.au1.cliniko.com/v1/communications/1"
            },
            "patient": {
                "links": {
                    "self": "https://api.au1.cliniko.com/v1/patients/1"
                }
            },
            "to": "russell.boyle@example.net",
            "type": "Email",
            "type_code": 2,
            "updated_at": "2022-02-02T03:42:27Z"
        }
    ],
    "links": {
        "next": "https://api.au1.cliniko.com/v1/communications?page=2&per_page=1",
        "self": "https://api.au1.cliniko.com/v1/communications?page=1&per_page=1"
    },
    "total_entries": 230
}
```

Get Communication
--------------------

**Resources**
* ```GET /communications/:id``` get a specified communication

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/communications/1 \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
    "archived_at": null,
    "category": "Appointment Reminder",
    "category_code": 1,
    "content": "Lorem ipsum dolor sit amet consectetuer adipiscing elit sed diam nonummy nibh",
    "content_subject": "Appointment Reminder",
    "created_at": "2022-02-02T03:42:27Z",
    "direction_code": 1,
    "direction_description": "Sent",
    "from": null,
    "id": "1",
    "links": {
        "self": "https://api.au1.cliniko.com/v1/communications/1"
    },
    "patient": {
        "links": {
            "self": "https://api.au1.cliniko.com/v1/patients/1"
        }
    },
    "to": "russell.boyle@example.net",
    "type": "Email",
    "type_code": 2,
    "updated_at": "2022-02-02T03:42:27Z"
}
```

Create Memo Communication
--------------------

**Resources**
* ```POST /communications``` create a memo communication

> :warning: Creating a memo with SMS or email as communication type **will not** send a communication. A memo just records a communication has taken place.

> :warning: Only memo communications (`category_code`: 12) are supported by `POST /communications` resource.

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/communications \
  -u API_KEY: \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -d '{ "category_code": 12, "confidential": false, "direction_code": 2, "from": "Russell Boyle", "patient_id": "1", "to": "Jay Leno", "type_code": 3, "content": "Test memo" }' \
  -X POST
```

See the [Category Code Mapping](#category-code-mapping "This table lists the valid category codes and their corresponding descriptions.") section below for permitted memo communication properties.

**Example Response**
```json
{
   "archived_at" : null,
   "category" : "Memo",
   "category_code" : 12,
   "confidential" : false,
   "content" : "Test memo",
   "created_at" : "2022-04-26T08:49:45Z",
   "direction_code" : 2,
   "direction_description" : "Received",
   "from" : "Russell Boyle",
   "id" : "1",
   "links" : {
      "self" : "https://api.au1.cliniko.com/v1/communications/1"
   },
   "patient" : {
      "links" : {
         "self" : "https://api.au1.cliniko.com/v1/patients/1"
      }
   },
   "to" : "Jay Leno",
   "type" : "Phone call",
   "type_code" : 3,
   "updated_at" : "2022-04-26T08:49:45Z"
}
```

Update Memo Communication
--------------------

**Resources**
* ```PUT /communications/:id``` update a memo communication

> :warning: Only memo communications (`category_code`: 12) are supported by `PUT /communications/:id` resource.

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/communications/1 \
  -u API_KEY: \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -d '{ "type_code": 2, "content": "Test memo update" }' \
  -X PUT
```

**Example Response**
```json
{
   "archived_at" : null,
   "category" : "Memo",
   "category_code" : 12,
   "confidential" : false,
   "content" : "Test memo update",
   "created_at" : "2022-04-26T08:49:45Z",
   "direction_code" : 2,
   "direction_description" : "Received",
   "from" : "Russell Boyle",
   "id" : "1",
   "links" : {
      "self" : "https://api.au1.cliniko.com/v1/communications/1"
   },
   "patient" : {
      "links" : {
         "self" : "https://api.au1.cliniko.com/v1/patients/1"
      }
   },
   "to" : "Jay Leno",
   "type" : "Email",
   "type_code" : 2,
   "updated_at" : "2022-04-26T09:14:20Z"
}
```
See the [Category Code Mapping](#category-code-mapping "This table lists the valid category codes and their corresponding descriptions.") section below for permitted memo communication properties.

Archive Memo Communication
--------------------

**Resources**
* ```POST /communications/:id/archive``` archive a memo communication

> :warning: Only memo communications (`category_code`: 12) are supported by `POST /communications/:id/archive` resource.

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/communications/1/archive \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -X POST
```

**Example Response**
A status code of 204 no content will be returned if successful

Filtering Communications
--------------------

You can filter communications by:
* ```archived_at/deleted_at``` (DateTime)
* ```category_code```[^1] (Integer)
* ```created_at``` (DateTime)
* ```id``` (BigInt)
* ```patient_id``` (BigInt)
* ```updated_at``` (DateTime)

See [Filtering Results](https://github.com/redguava/cliniko-api#filtering-results) for details on how to apply filters.

## Category Code Mapping
| Category Code | Category                              |
| ------------- | ------------------------------------- |
| 1             | Appointment reminder                  |
| 2             | SMS forwarding                        |
| 3             | Invoice                               |
| 4             | Appointment confirmation email        |
| 5             | Letters                               |
| 6             | Practitioner appointment notification |
| 7             | SMS messages                          |
| 8             | SMS patient reply                     |
| 9             | Account statements                    |
| 10            | Cancelled appointment notification    |
| 11            | Auth code                             |
| 12            | Memos                                 |
| 13            | Practitioner reply                    |
| 14            | Payments                              |
| 15            | Bulk emails                           |
| 16            | Appointment cancellation              |
| 17            | Patient form                          |
| 18            | Upcoming appointments                 |
| 19            | Completed patient form                |

## Permitted Memo Communication Properties
When creating or updating memo communications, the following properties are permitted.

| Name             | Type    | Required?[^2] | Description                                                                                  |
| ---------------- | ------- | ------------- | -------------------------------------------------------------------------------------------- |
| `category_code`  | Integer | **no**        | Defaults to `12` (memo); a `category_code` other than memo's cannot be set                   |
| `confidential`   | Boolean | **yes**       |                                                                                              |
| `content`        | String  | **yes**       |                                                                                              |
| `direction_code` | Integer | **yes**       | Message direction:<br />1 - outbound<br />2 - inbound                                        |
| `from`           | String  | **yes**       | Message source name (i.e. patient name)                                                      |
| `patient_id`     | BigInt  | **yes**       |                                                                                              |
| `to`             | String  | **yes**       | Message recipient name (i.e. practitioner name)                                              |
| `type_code`      | Integer | **yes**       | Communication type:<br />1 - SMS<br />2 - email<br />3 - phone call<br />4 - other           |

[^1]: see Category Code Mapping for the valid category codes
[^2]: required on create
