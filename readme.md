The Cliniko API
===============

This is the offical API for Cliniko.  Cliniko is a practice management system for healthcare practitioners.

The Cliniko API is based on REST principles.  This means you can use any HTTP client and any programming language to interact with the API.

JSON will be returned in all responses from the API.

Security
--------

The Cliniko API is served over HTTPS to ensure data security and privacy.  HTTP is not supported.

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

If you just need an API key for testing, sign up for a free trial and go to the "My Info" link in the top right corner within Cliniko.  You can create an API key there.  If you need your trial extended just let us know.

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

Updated Since
---------------

Fetching a list of records that have been updated since a specific time is easy. A parameter called `updated_since` should be passed and only the records that have been updated since this time will be retrieved.

This timestamp has to be in UTC if present – e.g. 2014-08-30T18:00:00Z.

Filtering Results
-----------------

Some resources allow the results to be filtered. This will be documented with the resource if it is available.

**DateTime Filter Operators**
* ```>=``` Greater than or equal to
* ```>``` Greater than
* ```<=``` Less than or equal to
* ```<``` Less than

**String Filter Operators**
* ```=``` Equals
* ```!=``` Not equal to
* ```~``` Contains
* ```~~``` Wildcard search (%)

To filter a resource, add a filter string to the 'q' parameter.

The filter string format is ```[FIELDNAME]:[OPERATOR][VALUE]```

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

**Format Rules**
* ```DateTime``` has to be in UTC if present – e.g. 2014-08-30T18:00:00Z.

**Filtering Tips**
* ```%``` is the wildcard symbol for the **wildcard search** operator. You may need to escape it (%25).
* You can use multiple ```%```'s in a **wildcard search**.
* The **contains** operator is the same as doing ```%value%``` with the **wildcard search**.

API Resources
-----------------

* [Appointments](https://github.com/redguava/cliniko-api/blob/master/sections/appointments.md)
* [Appointment Types](https://github.com/redguava/cliniko-api/blob/master/sections/appointment_types.md)
* [Businesses](https://github.com/redguava/cliniko-api/blob/master/sections/businesses.md)
* [Practitioners](https://github.com/redguava/cliniko-api/blob/master/sections/practitioners.md)
* [Patients](https://github.com/redguava/cliniko-api/blob/master/sections/patients.md)
* [Available Times](https://github.com/redguava/cliniko-api/blob/master/sections/available_times.md)
* [Taxes](https://github.com/redguava/cliniko-api/blob/master/sections/taxes.md)
* [Users](https://github.com/redguava/cliniko-api/blob/master/sections/users.md)

Get involved and help make our API better
-----------------------------------------

Please give us feedback on how we can make the API better.

*  Join [Cliniko API Developers Group](https://groups.google.com/a/redguava.com.au/d/forum/cliniko-api) to stay updated with any changes and exchange information with Cliniko API Developers.
*  For feature requests or bugs please use GitHub issues. You can also fork this project and send a pull request with any improvements.

Want to talk to us? Send an email through to support@cliniko.com and we'll make sure it gets to the developers.
