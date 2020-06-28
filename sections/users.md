Users
============

* [Get Users](#get-users "This will return all users.")
* [Get User](#get-user "This will return a specified user.")
* [Get Authenticated User](#get-authenticated-user "This will return a specified user.")

Get Users
----------------

**Resources**
* ```GET /users``` get all users

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/users \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "users": [
    {
      "id": 1,
      "title": "",
      "first_name": "John",
      "last_name": "Smith",
      "email": "john@example.com",
      "role": "administrator",
      "time_zone": "Melbourne",
      "user_active": true,
      "created_at": "2014-01-29T09:54:54Z",
      "updated_at": "2014-04-29T00:00:56Z",
      "links": {"self": "https://api.au1.cliniko.com/v1/users/1"}
    }
  ],
  "total_entries": 1,
  "links": {"self": "https://api.au1.cliniko.com/v1/users?page=1"}
}
```

Get User
------------

**Resources**
* ```GET /users/:id``` get a specified user

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/users/1 \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "id": 1,
  "title": "",
  "first_name": "John",
  "last_name": "Smith",
  "email": "john@example.com",
  "role": "administrator",
  "time_zone": "Melbourne",
  "user_active": true,
  "created_at": "2014-01-29T09:54:54Z",
  "updated_at": "2014-04-29T00:00:56Z",
  "links": {"self": "https://api.au1.cliniko.com/v1/users/1"}
}
```


Get Authenticated User
------------

**Resources**
* ```GET /user``` get the user associated to the API key

**Example Request**
```shell
curl https://api.au1.cliniko.com/v1/user \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "id": 1,
  "title": "",
  "first_name": "John",
  "last_name": "Smith",
  "email": "john@example.com",
  "role": "administrator",
  "time_zone": "Melbourne",
  "user_active": true,
  "created_at": "2014-01-29T09:54:54Z",
  "updated_at": "2014-04-29T00:00:56Z",
  "links": {"self": "https://api.au1.cliniko.com/v1/users/1"}
}
```

Filtering Users
----------------

You can filter users by:
* ```created_at``` DateTime
* ```id``` Integer
* ```updated_at``` DateTime

See [Filtering Results](https://github.com/redguava/cliniko-api#filtering-results) for details on how to apply filters.
