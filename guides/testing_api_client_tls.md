# How do I test my API client?
You can test your API Client by making a request to https://tls-test.cliniko.com/.
If the request is successful, the tls-test endpoint will return a HTTP status code of 200 and also an “OK” in the response body. Otherwise, your client may throw an error regarding the connection failing.
