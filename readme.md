The Cliniko API
===============

This is the offical API for Cliniko.  Cliniko is a practice management system for healthcare practitioners.

The Cliniko API is based on REST principles.  This means you can use any HTTP client and any programming language to interact with the API.

JSON will be returned in all responses from the API.

Security
--------

The Cliniko API is served over HTTPS to ensure data security and privacy.  HTTP is not supported.

Ensure that the HTTP client is up-to-date and has the latest TLS, cipher suites and SNI available. It's recommended that the client uses the cipher offered by the Cliniko API. It's _not recommended_ to hard-code TLS versions or ciphers.

From May 1, 2018, requests to the Cliniko API will require TLS 1.2. See the guide on [How do I test my API client?](https://github.com/redguava/cliniko-api/blob/master/guides/testing_api_client_tls.md) for more information.

Base URL & shards
-----------------

All URLs in this documenation will use the following base, where `{shard}` is the Cliniko shard the account resides in.
You can determine which shard to use through the Cliniko API key. API keys have the shard appended to the end, e.g. `MS0xLWl4SzYYYYdtR3V2HNOTAREALKEYwvNHdeW0pd-au2` is in the shard `au2`.
If your API key was generated some time ago and has no shard on it, your shard will be `au1`.

```
https://api.{shard}.cliniko.com/v1
```

> Examples in this guide will typically use `au1` as the shard, unless the example requires otherwise. Please ensure you use **the appropriate** shard for your requests.

## Current regions and their shards

 Region | Shard
--------|--------
 AU | `au1`
 AU | `au2`
 AU | `au3`
 CA | `ca1`
 UK | `uk1`
 EU | `eu1`

It is **strongly** advisable that you validate the shard component:
- being one of these shard values, or
- matches the regex /\w{2}\d{1,2}/i

For more about the introduction of shards, and a code example of API keys with the shard attached may be used, [read the guide.](guides/sharding.md)

Authentication
--------------

The Cliniko API uses HTTP Basic authentication. This is secure, as all requests are via SSL.

Each Cliniko user will have their own API Key(s) - these are used for authentication. The API Key will have the same permissions as the user it belongs to.

You should provide the Cliniko API Key (either with or without the shard suffix) as the basic auth username. There is no need to provide a password. This should be sent in the `Authorization` header. The psuedocode for how the `Authorization` header should be built is:

```
"Basic " + base64_encode(api_key + ":")
```

For example, if your API key is `MxJrZXkiOiI1Njd1amJmZTQ1NyJ9-au2`, then you would generate your Authorization header like so, using the API Key as the username:
```
"Basic " + base64_encode("MxJrZXkiOiI1Njd1amJmZTQ1NyJ9-au2" + ":")
```

resulting in your Authorization header value:
```
Basic TXhKclpYa2lPaUkxTmpkMWFtSm1aVFExTnlKOS1hdTI6
```

To obtain an API key for testing, sign up for a free trial and go to the "My Info" link in the bottom left corner of the navigation within Cliniko. Click the "Manage API keys" button, you can create an API key from that page. If you need your trial extended just let us know.

Identifying your application
--------------

To identify your application, you need to send the `User-Agent` header. In the event of an issue, this allows us to easily track down your requests and contact you. This should be in the form:
```
APP_VENDOR_NAME (APP_VENDOR_EMAIL)
```

**APP_VENDOR_NAME** is the name of your application
**APP_VENDOR_EMAIL** is a contact email address for you or your company

As an example, a valid `User-Agent` value would be something like:
_Really helpful app (devs@helpfulapp.com)_

**If your requests do not include a User-Agent that contains a name and valid contact email, future requests may be automatically blocked.**

Errors
------

Conventional HTTP response codes are used to indicate API errors.

General code rules apply:
* 2xx range indicate success.
* 4xx range indicate an error resulting from the provided information (eg. missing a required parameter)
* 5xx range indicate an error with our Cliniko servers

Making a request
----------------

All URLs start with `https://api.{shard}.cliniko.com/v1`. **SSL only**. The path is prefixed with the API version. If we change the API in backward-incompatible ways, we'll bump the version marker and maintain stable support for the old URLs.

To make a request for all the patients on a specific account in the `au1` shard, you'd append the patients index path to the base url like this: https://api.au1.cliniko.com/v1/patients. In curl, that looks like:

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/appointments \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```
*Note: curl uses the -u flag to pass basic auth credentials (adding a colon after the API key will prevent it from asking for a password).*

**API_KEY** is the API Key provided by the Cliniko user

Make sure to send the `Accept` header with `application/json`.

That's all!

Rate limits
----------------

API requests are rate limited to 200 per minute per user. We recommend you design your app to stagger requests to avoid hitting the rate limit.

Requests exceeding the rate limit will receive a response with a 429 status and an X-RateLimit-Reset header containing the time at which the limit will reset. The time is formatted as a UNIX timestamp of elapsed seconds since the start of the UNIX epoch in the UTC timezone.

Requests that exceed our fair use allocation may be blocked. If you require a higher rate limit, please contact us.

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
  "next": "https://api.au1.cliniko.com/v1/appointments?page=4&per_page=100",
  "self": "https://api.au1.cliniko.com/v1/appointments?page=3&per_page=100",
  "previous": "https://api.au1.cliniko.com/v1/appointments?page=2&per_page=100"
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

`https://api.au1.cliniko.com/v1/appointments?q=appointment_start:>2014-03-04T20:37:17Z`

To apply multiple filters, send multiple filter strings as an array with the `q[]` parameter:

`https://api.au1.cliniko.com/v1/appointments?q[]=appointment_start:>2014-03-04T20:37:17Z&q[]=appointment_start:<2014-04-04T20:37:17Z`

The `q[]` method also works for a single filter string:

`https://api.au1.cliniko.com/v1/appointments?q[]=appointment_start:>2014-03-04T20:37:17Z`


**Example Request (Greater than)**
```shell
curl https://api.au1.cliniko.com/v1/appointments?q=appointment_start:>2014-03-04T20:37:17Z \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Request (Contains)**
```shell
curl https://api.au1.cliniko.com/v1/patients?q=last_name:~son \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Request (Wildcard Search)**
```shell
curl https://api.au1.cliniko.com/v1/patients?q=last_name:~~ja%on% \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Request (Multiple Filters)**
```shell
curl https://api.au1.cliniko.com/v1/patients?q%5B%5D=first_name:~bri&q%5B%5D=last_name:~son \
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
* [Appointments (Individual)](https://github.com/redguava/cliniko-api/blob/master/sections/individual_appointments.md)
* [Appointments (Group)](https://github.com/redguava/cliniko-api/blob/master/sections/group_appointments.md)
* [Attendees](https://github.com/redguava/cliniko-api/blob/master/sections/attendees.md)
* [Available Times](https://github.com/redguava/cliniko-api/blob/master/sections/available_times.md)
* [Billable Items](https://github.com/redguava/cliniko-api/blob/master/sections/billable_items.md)
* [Businesses](https://github.com/redguava/cliniko-api/blob/master/sections/businesses.md)
* [Concession Types](https://github.com/redguava/cliniko-api/blob/master/sections/concession_types.md)
* [Contacts](https://github.com/redguava/cliniko-api/blob/master/sections/contacts.md)
* [Daily Availabilities](https://github.com/redguava/cliniko-api/blob/master/sections/daily_availabilities.md)
* [Files](https://github.com/redguava/cliniko-api/blob/master/sections/patient_attachments.md)
* [Invoices](https://github.com/redguava/cliniko-api/blob/master/sections/invoices.md)
* [Invoice Items](https://github.com/redguava/cliniko-api/blob/master/sections/invoice_items.md)
* [Medical Alerts](https://github.com/redguava/cliniko-api/blob/master/sections/medical_alerts.md)
* [Patients](https://github.com/redguava/cliniko-api/blob/master/sections/patients.md)
* [Patient Form Templates](https://github.com/redguava/cliniko-api/blob/master/sections/patient_form_templates.md)
* [Patient Forms](https://github.com/redguava/cliniko-api/blob/master/sections/patient_forms.md)
* [Practitioners](https://github.com/redguava/cliniko-api/blob/master/sections/practitioners.md)
* [Practitioner Reference Numbers](https://github.com/redguava/cliniko-api/blob/master/sections/practitioner_reference_numbers.md)
* [Products](https://github.com/redguava/cliniko-api/blob/master/sections/products.md)
* [Referral Sources](https://github.com/redguava/cliniko-api/blob/master/sections/referral_sources.md)
* [Referral Source Types](https://github.com/redguava/cliniko-api/blob/master/sections/referral_source_types.md)
* [Services](https://github.com/redguava/cliniko-api/blob/master/sections/services.md)
* [Settings](https://github.com/redguava/cliniko-api/blob/master/sections/settings.md)
* [Stock Adjustments](https://github.com/redguava/cliniko-api/blob/master/sections/stock_adjustments.md)
* [Taxes](https://github.com/redguava/cliniko-api/blob/master/sections/taxes.md)
* [Treatment Note Templates](https://github.com/redguava/cliniko-api/blob/master/sections/treatment_note_templates.md)
* [Treatment Notes](https://github.com/redguava/cliniko-api/blob/master/sections/treatment_notes.md)
* [Users](https://github.com/redguava/cliniko-api/blob/master/sections/users.md)

Custom Patient Button
---------------------

Cliniko offers an additional integration option for applications that handle
patient data. See [this
guide](https://github.com/redguava/cliniko-api/blob/master/guides/custom_patient_page.md)
for more details.

Telehealth links
---------------------

Telehealth in Cliniko includes the generation of appointment Telehealth links. To understand what these are and how to use them, see [this
guide](https://github.com/redguava/cliniko-api/blob/master/guides/telehealth_links.md)
for more details.

Get involved and help make our API better
-----------------------------------------

Please give us feedback on how we can make the API better.

*  Join [Cliniko API Developers Group](https://groups.google.com/a/redguava.com.au/d/forum/cliniko-api) to stay updated with any changes and exchange information with Cliniko API Developers.
*  For feature requests or bugs please use GitHub issues. You can also fork this project and send a pull request with any improvements.

Want to talk to us? Send an email through to support@cliniko.com and we'll make sure it gets to the developers.
