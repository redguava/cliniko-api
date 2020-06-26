Invoice Items
===============
* [Get Invoice Items](#get-invoice-items "This will return all invoice items.")
* [Get Deleted Invoice Items](#get-deleted-invoice-items "This will return all deleted invoice items.")
* [Get Invoice Item](#get-invoice-item "This will return a specified invoice item.")

Get Invoice Items
----------------

**Resources**
* ```GET /invoice_items``` get all invoice items
* ```GET /invoices/:id/invoice_items``` get all invoice items for a specified invoice

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/invoice_items \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "invoice_items": [
    {
      "id": 1,
      "created_at": "2015-10-25T05:34:34Z",
      "updated_at": "2015-10-25T05:34:34Z",
      "concession_type_name": "",
      "discount_percentage": "18.1818",
      "discounted_amount": "20.0",
      "is_monetary_discount": true,
      "name": "Initial consultation and treatment",
      "net_price": "81.818",
      "quantity": 1,
      "tax_amount": "10.0",
      "tax_name": "GST",
      "unit_price": "100.0",
      "total_including_tax": "90.0",
      "code": "2020",
      "deleted_at": null,
      "billable_item": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/billable_items/1"
        }
      },
      "invoice": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/invoices/1"
        }
      },
      "links": {
        "self": "https://api.au1.cliniko.com/v1/invoice_items/1"
      }
    }
  ],
  "total_entries": 1,
  "links": {
    "self": "https://api.au1.cliniko.com/v1/invoice_items?page=1"
  }
}
```

Get Deleted Invoice Items
----------------

**Resources**
* ```GET /invoice_items/deleted``` get all deleted invoice items
* ```GET /invoice/:id/invoice_items/deleted``` get all deleted invoice items for a specified invoice

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/invoice_items/deleted \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "invoice_items": [
    {
      "id": 1,
      "created_at": "2015-10-25T05:34:34Z",
      "updated_at": "2015-10-25T05:34:34Z",
      "concession_type_name": "",
      "discount_percentage": "18.1818",
      "discounted_amount": "20.0",
      "is_monetary_discount": true,
      "name": "Initial consultation and treatment",
      "net_price": "81.818",
      "quantity": 1,
      "tax_amount": "10.0",
      "tax_name": "GST",
      "unit_price": "100.0",
      "total_including_tax": "90.0",
      "code": "2020",
      "deleted_at": 2015-10-26T05:34:34Z,
      "billable_item": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/billable_items/1"
        }
      },
      "invoice": {
        "links": {
          "self": "https://api.au1.cliniko.com/v1/invoices/1"
        }
      },
      "links": {
        "self": "https://api.au1.cliniko.com/v1/invoice_items/1"
      }
    }
  ],
  "total_entries": 1,
  "links": {
    "self": "https://api.au1.cliniko.com/v1/invoice_items/deleted?page=1"
  }
}
```


Get Invoice Item
------------

**Resources**
* ```GET /invoice_items/:id``` get a specified invoice item

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/invoice_items/3 \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "id": 1,
  "created_at": "2015-10-25T05:34:34Z",
  "updated_at": "2015-10-25T05:34:34Z",
  "concession_type_name": "",
  "discount_percentage": "18.1818",
  "discounted_amount": "20.0",
  "is_monetary_discount": true,
  "name": "Wooden Pants",
  "net_price": "81.818",
  "quantity": 1,
  "tax_amount": "10.0",
  "tax_name": "GST",
  "unit_price": "100.0",
  "total_including_tax": "90.0",
  "code": "2020",
  "deleted_at": null,
  "product": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/products/1"
    }
  },
  "invoice": {
    "links": {
      "self": "https://api.au1.cliniko.com/v1/invoices/1"
    }
  },
  "links": {
    "self": "https://api.au1.cliniko.com/v1/invoice_items/1"
  }
}
```

Filtering Invoice Items
----------------

For any route that returns a set of invoice items, you can filter them by:
* ```created_at``` DateTime
* ```id``` Integer
* ```invoice_id``` Integer
* ```updated_at``` DateTime

See [Filtering Results](https://github.com/redguava/cliniko-api#filtering-results) for details on how to apply filters.
