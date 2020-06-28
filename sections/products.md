Products
============
* [Get Products](#get-products "This will return all products.")
* [Get Product](#get-product "This will return a specified product.")
* [Create Product](#create-product "This will create a product.")
* [Update Product](#update-product "This will update a product.")
* [Delete Product](#delete-product "This will delete a product.")


Get Products
----------------

**Resources**
* ```GET /products``` get all products

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/products \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "products": [
    {
      "id": 1,
      "item_code": "0001",
      "name": "Product",
      "product_supplier_name": "Supplier",
      "cost_price": "3.0",
      "stock_level": 10,
      "notes": "",
      "serial_number": "123456",
      "price_ex_tax": "10.0",
      "tax": {
        "links": {"self": "https://api.au1.cliniko.com/v1/taxes/1"}
      },
      "created_at": "2014-03-04T19:11:30Z",
      "updated_at": "2014-03-04T19:11:30Z",
      "links": {"self": "https://api.au1.cliniko.com/v1/products/1"}
    }
  ],
  "total_entries": 1,
  "links": {"self": "https://api.au1.cliniko.com/v1/products?page=1"}
}
```

Get Product
------------

**Resources**
* ```GET /products/:id``` get a specified product

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/products/1 \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "id": 1,
  "item_code": "0001",
  "name": "Product",
  "product_supplier_name": "Supplier",
  "cost_price": "3.0",
  "stock_level": 10,
  "notes": "",
  "serial_number": "123456",
  "price_ex_tax": "10.0",
  "tax": {
    "links": {"self": "https://api.au1.cliniko.com/v1/taxes/1"}
  },
  "created_at": "2014-03-04T19:11:30Z",
  "updated_at": "2014-03-04T19:11:30Z",
  "links": {"self": "https://api.au1.cliniko.com/v1/products/1"}
}
```

Create Product
----------------
**Resources**
* ```POST /products``` create a product

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/products \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -d '{ "item_code": "0002", "name": "Product 2", "product_supplier_name": "Supplier", "price": 11, "cost_price": 8, "stock_level": 10, "tax_id": 1, "serial_number": "123456" }' \
  -X POST
```
**Example Response**
```
Headers { Location: http://api.cliniko.com/products/2 }
```
```json
{
  "id": 2,
  "item_code": "0002",
  "name": "Product 2",
  "product_supplier_name": "Supplier",
  "cost_price": "8.0",
  "stock_level": 10,
  "notes": "",
  "serial_number": "123456",
  "price_ex_tax": "11.0",
  "tax": {
    "links": {"self": "https://api.au1.cliniko.com/v1/taxes/1"}
  },
  "created_at": "2014-03-11T19:11:30Z",
  "updated_at": "2014-03-11T19:11:30Z",
  "links": {"self": "https://api.au1.cliniko.com/v1/products/2"}
}
```

Update Product
----------------
**Resources**
* ```PUT /products/:id``` update a product

**IMPORTANT:** Stock level cannot be updated with this request. Please use create stock adjustment to modify product stock level.

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/products/1 \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -d '{ "name": "Product 1" }' \
  -X PUT
```
**Example Response**
```json
{
  "id": 1,
  "item_code": "0001",
  "name": "Product 1",
  "product_supplier_name": "Supplier",
  "cost_price": "3.0",
  "stock_level": 10,
  "notes": "",
  "serial_number": "123456",
  "price_ex_tax": "10.0",
  "tax": {
    "links": {"self": "https://api.au1.cliniko.com/v1/taxes/1"}
  },
  "created_at": "2014-03-04T19:11:30Z",
  "updated_at": "2014-03-04T19:11:30Z",
  "links": {"self": "https://api.au1.cliniko.com/v1/products/1"}
}
```

Delete Product
----------------
**Resources**
* ```DELETE /products/:id``` delete a product

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/products/1 \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -X DELETE
```
**Example Response**
A status code of `204 no content` will be returned if successful

Filtering Products
----------------

You can filter products by:
* ```created_at``` DateTime
* ```id``` Integer
* ```name``` String
* ```tax_id``` Integer
* ```updated_at``` DateTime

See [Filtering Results](https://github.com/redguava/cliniko-api#filtering-results) for details on how to apply filters.
