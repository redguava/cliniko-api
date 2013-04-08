The Cliniko API
===============

**The Cliniko API is currently in BETA, so there will still be some changes over the next few weeks**

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

Errors
------

Conventional HTTP response codes are used to indicate API errors.

General code rules apply:
* 2xx range indicate success.
* 4xx range indicate error resulted from the provided information (eg. missing a required parameter)
* 5xx range indicate and error with our Cliniko servers


Making a request
----------------

All URLs start with `https://api.cliniko.com/v1/`. **SSL only**. The path is prefixed with the API version. If we change the API in backward-incompatible ways, we'll bump the version marker and maintain stable support for the old URLs.

To make a request for all the appointments on a specific account, you'd append the appointments index path to the base url to form something like https://api.cliniko.com/api/v1/appointments. In curl, that looks like:

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
  "next": "https://api.cliniko.com/appointments?page=4&per_page=100",
  "self": "https://api.cliniko.com/appointments?page=3&per_page=100",
  "previous": "https://api.cliniko.com/appointments?page=2&per_page=100"
}
```

The possible pagination links are:

`next`
Shows the URL of the immediate next page of results.

`self`
Shows the URL of the current page of results.

`previous`
Shows the URL of the immediate previous page of results.

API Resources
-----------------

* [Appointments](https://github.com/redguava/cliniko-api/blob/master/sections/appointments.md)
* [Appointment Types](https://github.com/redguava/cliniko-api/blob/master/sections/appointment_types.md)
* [Businesses](https://github.com/redguava/cliniko-api/blob/master/sections/businesses.md)
* [Practitioners](https://github.com/redguava/cliniko-api/blob/master/sections/practitioners.md)

Get involved and help make our API better
-----------------------------------------

Please give us feedback on how we can make the API better. For feature requests or bugs please use GitHub issues. You can also fork this project and send a pull request with any improvements.

Want to talk to us? Send an email through to support@cliniko.com and we'll make sure it gets to the developers.
