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

Errors
------

Conventional HTTP response codes are used to indicate API errors.

General code rules apply:
* 2xx range indicate success.
* 4xx range indicate error resulted from the provided information (eg. missing a required parameter)
* 5xx range indicate and error with our Cliniko servers


Making a request
----------------

Todo

Data Responses
--------------

We only support JSON for serialization of data. 

Use HTTP caching
----------------

Todo

Rate limiting
-------------

You can perform up to 500 requests per minute for the same account. If you exceed this limit, you'll get a error response for subsequent requests.


API Resources
-----------------

None Yet

Get involved and help make our API better
-----------------------------------------

Please give us feedback on how we can make the API better. For feature requests or bugs please use GitHub issues. You can also fork this project and send a pull request with any improvements.

Want to talk to us? Send an email through to support@cliniko.com and we'll make sure it gets to the developers.