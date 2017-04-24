The Cliniko API
===============

This is the offical API for Cliniko.  Cliniko is a practice management system for healthcare practitioners.

The Cliniko API is based on REST principles.  This means you can use any HTTP client and any programming language to interact with the API.

JSON will be returned in all responses from the API.

Security
--------

The Cliniko API is served over HTTPS to ensure data security and privacy.  HTTP is not supported.

Ensure that the HTTP client is up-to-date and has the latest TLS, cipher suites and SNI available. It's recommended that the client uses the cipher offered by the Cliniko API. It's _not recommended_ to hard-code TLS versions or ciphers.

Base URL
--------

All URLs in this documenation will use the following base
```
https://api.cliniko.com/v1
```

Authentication
--------------

The Cliniko API uses HTTP Basic authentication. This is secure as all requests are via SSL.

Each Cliniko user will have their own API Key(s), this is used for authentication.  The API Key will have the same permissions as the user it is from.

You should provide the Cliniko API Key as the basic auth username.  There is no need to provide a password.

If you just need an API key for testing, sign up for a free trial and go to the "My Info" link in the bottom left corner of the navigation within Cliniko.  You can create an API key there.  If you need your trial extended just let us know.

Errors
------

Conventional HTTP response codes are used to indicate API errors.

General code rules apply:
* 2xx range indicate success.
* 4xx range indicate an error resulting from the provided information (eg. missing a required parameter)
* 5xx range indicate an error with our Cliniko servers


Making a request
----------------

All URLs start with `https://api.cliniko.com/v1`. **SSL only**. The path is prefixed with the API version. If we change the API in backward-incompatible ways, we'll bump the version marker and maintain stable support for the old URLs.

To make a request for all the appointments on a specific account, you'd append the appointments index path to the base url to form something like https://api.cliniko.com/v1/appointments. In curl, that looks like:

**Example Request**
```shell
curl https://api.cliniko.com/v1/appointments \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```
*Note: curl uses the -u flag to pass basic auth credentials (adding a colon after the API key will prevent it from asking for a password).*

**API_KEY** is the API Key provided by the Cliniko user
**APP_VENDOR_NAME** is the name of your application that integrates with Cliniko
**APP_VENDOR_EMAIL** is a contact email address for your company

That's all!

Data Responses
--------------

We only support JSON for serialization of data.

Dates and Times
---------------

All dates and times are expected to be in UTC.

Pagination
---------------

Requests that return multiple items will be paginated to 50 items by default. You can specify further pages with the `page` parameter. You can also set a custom page size up to 100 with the `per_page` parameter.

All paginated requests will return the total number of entries that exist as total_entries in the response.

The pagination info is included in the links object. It is recommended to follow these links instead of constructing your own URLs.

```
"appointments": {
  ...
},
total_entries: 400,
"links": {
  "next": "https://api.cliniko.com/v1/appointments?page=4&per_page=100",
  "self": "https://api.cliniko.com/v1/appointments?page=3&per_page=100",
  "previous": "https://api.cliniko.com/v1/appointments?page=2&per_page=100"
}
```

The possible pagination links are:

`next`
Shows the URL of the immediate next page of results.

`self`
Shows the URL of the current page of results.

`previous`
Shows the URL of the immediate previous page of results.

The pagination links will only be included if they are relevant (eg. there will be no `next` link if you are on the last page.

Filtering Results
-----------------

Some resources allow the results to be filtered. This will be documented with the resource if it is available.

**Date Filter Operators**
* ```=``` Equal to
* ```>=``` Greater than or equal to
* ```>``` Greater than
* ```<=``` Less than or equal to
* ```<``` Less than

Dates must be in YYYY-MM-DD format. The date filter accepts wildcards in this format using `*`. Ex: `****-05-**` will return all patients born in May.

**DateTime Filter Operators**
* ```>=``` Greater than or equal to
* ```>``` Greater than
* ```<=``` Less than or equal to
* ```<``` Less than

**Integer Filter Operators**
* ```=``` Equal to
* ```!=``` Not equal to
* ```>=``` Greater than or equal to
* ```>``` Greater than
* ```<=``` Less than or equal to
* ```<``` Less than

**String Filter Operators**
* ```=``` Equals
* ```!=``` Not equal to
* ```~``` Contains
* ```~~``` Wildcard search (%)


**Filter String Format**

The filter string format is ```[FIELDNAME]:[OPERATOR][VALUE]```

The integer ```=``` operator also accepts a list of integers in the format: ```[FIELDNAME]:=[VALUE],[VALUE],[VALUE],[VALUE]```. For example, ```practitioner_id:=1,2,3```.

**Sending Filter Parameters**

To filter a resource, send a filter string as the `q` parameter:

`https://api.cliniko.com/v1/appointments?q=appointment_start:>2014-03-04T20:37:17Z`

To apply multiple filters, send multiple filter strings as an array with the `q[]` parameter:

`https://api.cliniko.com/v1/appointments?q[]=appointment_start:>2014-03-04T20:37:17Z&q[]=appointment_start:<2014-04-04T20:37:17Z`

The `q[]` method also works for a single filter string:

`https://api.cliniko.com/v1/appointments?q[]=appointment_start:>2014-03-04T20:37:17Z`


**Example Request (Greater than)**
```shell
curl https://api.cliniko.com/v1/appointments?q=appointment_start:>2014-03-04T20:37:17Z \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Request (Contains)**
```shell
curl https://api.cliniko.com/v1/patients?q=last_name:~son \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Request (Wildcard Search)**
```shell
curl https://api.cliniko.com/v1/patients?q=last_name:~~ja%on% \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Request (Multiple Filters)**
```shell
curl https://api.cliniko.com/v1/patients?q%5B%5D=first_name:~bri&q%5B%5D=last_name:~son \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```
In this example, `q[]` is encoded as `q%5B%5D` so this command works properly in a terminal.

**Format Rules**
* ```DateTime``` has to be in UTC if present – e.g. 2014-08-30T18:00:00Z.

**Filtering Tips**
* ```%``` is the wildcard symbol for the **wildcard search** operator. You may need to escape it (%25).
* You can use multiple ```%```'s in a **wildcard search**.
* The **contains** operator is the same as doing ```%value%``` with the **wildcard search**.
* You can get records that have been updated since a certain time by sending a filter for updated_at. Ex: `q=updated_at:>2014-08-30T18:00:00Z`


Ordering
-----------------

By default, API results are ordered in ascending direction by their `created_at` timestamps.

You can specify a custom column to order by sending the `sort` parameter as the column name (eg. `sort=appointment_start`). You can also send multiple columns to sort by (eg. `sort=appointment_start,created_at`).

You can also specify the order direction by sending the `order` parameter set to `desc` or `asc` (eg. `order=desc`). If you need to order a column in the other direction, you can specify the order in the `sort` parameter (eg. `sort=appointment_start,created_at:desc`).

Availability times are not able to be custom ordered, they are always returned chronologically.

API Resources
-----------------

* [Appointment Types](https://github.com/redguava/cliniko-api/blob/master/sections/appointment_types.md)
* [Appointments](https://github.com/redguava/cliniko-api/blob/master/sections/appointments.md)
* [Available Times](https://github.com/redguava/cliniko-api/blob/master/sections/available_times.md)
* [Billable Items](https://github.com/redguava/cliniko-api/blob/master/sections/billable_items.md)
* [Businesses](https://github.com/redguava/cliniko-api/blob/master/sections/businesses.md)
* [Concession Types](https://github.com/redguava/cliniko-api/blob/master/sections/concession_types.md)
* [Contacts](https://github.com/redguava/cliniko-api/blob/master/sections/contacts.md)
* [Daily Availabilities](https://github.com/redguava/cliniko-api/blob/master/sections/daily_availabilities.md)
* [Invoices](https://github.com/redguava/cliniko-api/blob/master/sections/invoices.md)
* [Invoice Items](https://github.com/redguava/cliniko-api/blob/master/sections/invoice_items.md)
* [Medical Alerts](https://github.com/redguava/cliniko-api/blob/master/sections/medical_alerts.md)
* [Patients](https://github.com/redguava/cliniko-api/blob/master/sections/patients.md)
* [Practitioners](https://github.com/redguava/cliniko-api/blob/master/sections/practitioners.md)
* [Practitioner Reference Numbers](https://github.com/redguava/cliniko-api/blob/master/sections/practitioner_reference_numbers.md)
* [Products](https://github.com/redguava/cliniko-api/blob/master/sections/products.md)
* [Referral Sources](https://github.com/redguava/cliniko-api/blob/master/sections/referral_sources.md)
* [Referral Source Types](https://github.com/redguava/cliniko-api/blob/master/sections/referral_source_types.md)
* [Services](https://github.com/redguava/cliniko-api/blob/master/sections/services.md)
* [Settings](https://github.com/redguava/cliniko-api/blob/master/sections/settings.md)
* [Stock Adjustments](https://github.com/redguava/cliniko-api/blob/master/sections/stock_adjustments.md)
* [Taxes](https://github.com/redguava/cliniko-api/blob/master/sections/taxes.md)
* [Users](https://github.com/redguava/cliniko-api/blob/master/sections/users.md)

Get involved and help make our API better
-----------------------------------------

Please give us feedback on how we can make the API better.

*  Join [Cliniko API Developers Group](https://groups.google.com/a/redguava.com.au/d/forum/cliniko-api) to stay updated with any changes and exchange information with Cliniko API Developers.
*  For feature requests or bugs please use GitHub issues. You can also fork this project and send a pull request with any improvements.

Want to talk to us? Send an email through to support@cliniko.com and we'll make sure it gets to the developers.
