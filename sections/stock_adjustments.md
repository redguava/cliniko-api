Stock Adjustments
============
* [Get Stock Adjustments](#get-stock-adjustments "This will return all stock adjustments.")
* [Get Stock Adjustment](#get-stock-adjustment "This will return a specified stock adjustment.")
* [Create Stock Adjustment](#create-stock-adjustment "This will create a stock adjustment.")

Get Stock Adjustments
----------------

**Resources**
* ```GET /stock_adjustments``` get all stock adjustments.

**Example Request**
```shell
curl https://api.cliniko.com/v1/stock_adjustments \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "stock_adjustments": [
    {
      "id": 1,
      "quantity": -2,
      "adjustment_type": "Other",
      "comment": null,
      "created_at": "2014-03-17T13:31:51Z",
      "updated_at": "2014-03-17T13:31:51Z",
      "user": {
        "links": {
          "self": "https://api.cliniko.com/v1/users/1"
        }
      },
      "product": {
        "links": {
          "self": "https://api.cliniko.com/v1/products/1"
        }
      },
      "links": {"self": "https://api.cliniko.com/v1/stock_adjustments/1"}
    }
  ],
  "total_entries": 1,
  "links": {"self": "https://api.cliniko.com/v1/stock_adjustments?page=1"}
}
```

Get Stock Adjustment
------------

**Resources**
* ```GET /stock_adjustments/:id``` get a specified stock adjustment

**Example Request**
```shell
curl https://api.cliniko.com/v1/stock_adjustments/1 \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "id": 1,
  "quantity": -2,
  "adjustment_type": "Other",
  "comment": null,
  "created_at": "2014-03-17T13:31:51Z",
  "updated_at": "2014-03-17T13:31:51Z",
  "user": {
    "links": {
      "self": "https://api.cliniko.com/v1/users/1"
    }
  },
  "product": {
    "links": {
      "self": "https://api.cliniko.com/v1/products/1"
    }
  },
  "links": {"self": "https://api.cliniko.com/v1/stock_adjustments/1"}
}
```

Create Stock Adjustment
----------------
**Resources**
* ```POST /stock_adjustments``` create a stock adjustment

**Required Parameters**

 There are tree parameters required:
 * `product_id` indicating an existing product of which stock level you want to modify
 * `quantity` defines a number of products you want to add/remove to/from a stock level
 * `adjustment_type` describes the reason of stock level modification. Following adjustment types are defined in Cliniko:
   * Increase types: `"Stock Purchase", "Returned", "Other"`
   * Decrease types: `"Damaged", "Out of Date", "Item Sold", "Other"`

**IMPORTANT:** Negative value of quantity param is only allowed when decreasing adjustment type has been selected and vice versa. 

**Example Request**
```shell
curl https://api.cliniko.com/v1/stock_adjustments \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'Content-Type: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -d '{ "adjustment_type": "Other", "quantity": 2, "product_id": 1 }' \
  -X POST
```
**Example Response**
```
Headers { Location: https://api.cliniko.com/stock_adjustments/2 }
```
```json
{
  "id": 2,
  "quantity": 2,
  "adjustment_type": "Other",
  "comment": null,
  "created_at": "2014-03-17T13:31:51Z",
  "updated_at": "2014-03-17T13:31:51Z",
  "user": {
    "links": {
      "self": "https://api.cliniko.com/v1/users/1"
    }
  },
  "product": {
    "links": {
      "self": "https://api.cliniko.com/v1/products/1"
    }
  },
  "links": {"self": "https://api.cliniko.com/v1/stock_adjustments/2"}
}
```
