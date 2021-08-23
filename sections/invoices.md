Invoices
============
* [Get Invoices](#get-invoices "This will return all invoices.")
* [Get Deleted Invoices](#get-deleted-invoices "This will return all deleted invoices.")
* [Get Invoice](#get-invoice "This will return a specified invoice.")

Get Invoices
----------------

**Resources**
* ```GET /invoices``` get all invoices
* ```GET /appointments/:id/invoices``` get all invoices for a specified appointment
* ```GET /practitioners/:id/invoices``` get all invoices for a specified practitioner
* ```GET /patients/:id/invoices``` get all invoices for a specified patient

**Filtering**

You can filter the returned results by these fields:
* ```issue_date``` (Date) with ```>=``` ```>``` ```<=``` ```<``` ```=```
* ```number``` (Integer) with ```>=``` ```>``` ```<=``` ```<``` ```=```
* ```status``` (Integer) with ```>=``` ```>``` ```<=``` ```<``` ```=```

See [Filtering Results](https://github.com/redguava/cliniko-api#filtering-results) for details on how to apply filters.


**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/invoices \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "invoices": [
    {
      "id": 108,
      "issue_date": "2015-04-02",
      "total_amount": "50.0",
      "tax_amount": "0.0",
      "net_amount": "50.0",
      "notes": "",
      "status": 10,
      "invoice_to": "Mrs. Bernice Mayer\r\n4069 Willms Plains\r\nApt. 604\r\nStiedemannhaven  KY  51148-8134\r\nBosnia and Herzegovina",
      "patient_extra_information": "",
      "number": 104,
      "discounted_amount": "0.0",
      "status_description": "Open",
      "created_at": "2015-04-02T13:17:50Z",
      "updated_at": "2015-04-02T13:17:50Z",
      "deleted_at": null,
      "closed_at": null,
      "appointment": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/appointments/70644"
        }
      },
      "business": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/businesses/26"
        }
      },
      "practitioner": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/practitioners/26"
        }
      },
      "patient": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/patients/1593"
        }
      },
      "links": {
        "self": "https://api.au1.cliniko.com/v1/invoices/108"
      }
    }
  ],
  "total_entries": 1,
  "links": {
    "self": "https://api.au1.cliniko.com/v1/invoices?page=1"
  }
}
```

Get Deleted Invoices
----------------

**Resources**
* ```GET /invoices/deleted``` get all deleted invoices
* ```GET /appointments/:id/invoices/deleted``` get all deleted invoices for a specified appointment
* ```GET /practitioners/:id/invoices/deleted``` get all deleted invoices for a specified practitioner
* ```GET /patients/:id/invoices/deleted``` get all deleted invoices for a specified patient

**Filtering**

You can filter the returned results by these fields:
* ```issue_date``` (Date) with ```>=``` ```>``` ```<=``` ```<``` ```=```
* ```number``` (Integer) with ```>=``` ```>``` ```<=``` ```<``` ```=```
* ```status``` (Integer) with ```>=``` ```>``` ```<=``` ```<``` ```=```

See [Filtering Results](https://github.com/redguava/cliniko-api#filtering-results) for details on how to apply filters.

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/invoices/deleted \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "invoices": [
    {
      "id": 108,
      "issue_date": "2015-04-02",
      "total_amount": "50.0",
      "tax_amount": "0.0",
      "net_amount": "50.0",
      "notes": "",
      "status": 10,
      "invoice_to": "Mrs. Bernice Mayer\r\n4069 Willms Plains\r\nApt. 604\r\nStiedemannhaven  KY  51148-8134\r\nBosnia and Herzegovina",
      "patient_extra_information": "",
      "number": 104,
      "discounted_amount": "0.0",
      "status_description": "Open",
      "created_at": "2015-04-02T13:17:50Z",
      "updated_at": "2015-04-02T13:17:50Z",
      "deleted_at": "2015-04-05T15:45:23Z",
      "closed_at": null,
      "appointment": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/appointments/70644"
        }
      },
      "business": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/businesses/26"
        }
      },
      "practitioner": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/practitioners/26"
        }
      },
      "patient": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/patients/1593"
        }
      },
      "links": {
        "self": "https://api.au1.cliniko.com/v1/invoices/108"
      }
    }
  ],
  "total_entries": 1,
  "links": {
    "self": "https://api.au1.cliniko.com/v1/appointments/70644/invoices/deleted?page=1"
  }
}
```


Get Invoice
------------

**Resources**
* ```GET /invoices/:id``` get a specified invoice

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/invoices/3 \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "id": 3,
  "issue_date": "2014-12-11",
  "total_amount": "2367.18",
  "tax_amount": "0.0",
  "net_amount": "2367.18",
  "notes": null,
  "status": 20,
  "invoice_to": null,
  "patient_extra_information": null,
  "number": 1,
  "discounted_amount": "0.0",
  "status_description": "Paid",
  "created_at": "2014-12-18T10:47:05Z",
  "updated_at": "2014-12-18T10:47:08Z",
  "deleted_at": null,
  "closed_at": "2014-12-18T10:47:08Z",
  "business": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/businesses/26"
    }
  },
  "patient": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/patients/380"
    }
  },
  "links": {
    "self": "https://api.au1.cliniko.com/v1/invoices/3"
  }
}
```

Filtering Invoices
----------------

For any route that returns a set of invoices, you can filter them by:
* ```appointment_id``` Integer
* ```business_id``` Integer
* ```created_at``` DateTime
* ```id``` Integer
* ```issue_date``` Date
* ```number``` Integer
* ```patient_id``` Integer
* ```practitioner_id``` Integer
* ```status``` Integer
* ```updated_at``` DateTime

Invoices support the following _integer_ statuses and may be used when filtering by `status`:

| Status | Description   |
|------- | ------------- |
| `10`   | Open          |
| `20`   | Paid          |
| `30`   | Closed        |
| `40`   | Open (credit) |

See [Filtering Results](https://github.com/redguava/cliniko-api#filtering-results) for details on how to apply filters.
