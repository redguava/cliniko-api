Patients
============
> Patients are the people that book in for appointments.  There isn't much in Cliniko that doesn't revolve around patients.
>
> When you're working with patient information, make sure you abide by the relevant regulations for security and privacy.

* [Get Patients](#get-patients "This will return all patients.")
* [Get Patient](#get-patient "This will return a specified patient.")
* [Create Patient](#create-patient "This will create a patient.")
* [Update Patient](#update-patient "This will update a patient.")
* [Delete Patient](#delete-patient "This will delete a patient.")

Get Patients
----------------

**Resources**
* ```GET /patients``` get all patients

**Filtering**

You can filter the returned results by these fields:
* ```first_name``` (String) with ```=``` ```!=```
* ```last_name``` (String) with ```=``` ```!=```
* ```email``` (String) with ```=``` ```!=```

See [Filtering Results](https://github.com/redguava/cliniko-api#filtering-results) for details on how to apply filters.

**Example Request**
```shell
curl https://api.cliniko.com/v1/patients \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "patients": [
    {
      "address_1": "1 Smith Street",
      "address_2": "",
      "address_3": "",
      "archived_at": "",
      "city": "Melbourne",
      "country": "Australia",
      "created_at": "2013-03-26T14:00:00Z",
      "date_of_birth": "2001-05-26",
      "email": "peter@example.com",
      "emergency_contact": "",
      "first_name": "Peter",
      "gender": "Male",
      "id": 1,
      "last_name": "Patientman",
      "notes": "",
      "occupation": "",
      "old_reference_id": "",
      "post_code": "3000",
      "referral_source": "",
      "state": "Victoria",
      "title": "Mr",
      "updated_at": "2013-03-26T14:00:00Z",
      "patient_phone_numbers": [
        {
          "phone_type": "Mobile",
          "number": "61444444444"
        },
        {
          "phone_type": "Home",
          "number": "61399999999"
        }
      ],
      "links": {"self": "https://api.cliniko.com/v1/patients/1"}
    }
  ],
  "total_entires": 1,
  "links": {"self": "https://api.cliniko.com/v1/patients?page=1"}
}
```

Get Patient
------------

**Resources**
* ```GET /patients/:id``` get a specified patient

**Example Request**
```shell
curl https://api.cliniko.com/v1/patients/1 \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)'
```

**Example Response**
```json
{
  "address_1": "1 Smith Street",
  "address_2": "",
  "address_3": "",
  "archived_at": "",
  "city": "Melbourne",
  "country": "Australia",
  "created_at": "2013-03-26T14:00:00Z",
  "date_of_birth": "2001-05-26",
  "email": "peter@example.com",
  "emergency_contact": "",
  "first_name": "Peter",
  "gender": "Male",
  "id": 1,
  "last_name": "Patientman",
  "notes": "",
  "occupation": "",
  "old_reference_id": "",
  "post_code": "3000",
  "referral_source": "",
  "state": "Victoria",
  "title": "Mr",
  "updated_at": "2013-03-26T14:00:00Z",
  "patient_phone_numbers": [
    {
      "phone_type": "Mobile",
      "number": "61444444444"
    },
    {
      "phone_type": "Home",
      "number": "61399999999"
    }
  ],
  "links": {"self": "https://api.cliniko.com/v1/patients/1"}
}
```

Create Patient
----------------
**Resources**
* ```POST /patients``` create a patient

**Example Request**
```shell
curl https://api.cliniko.com/v1/patients \
  -u API_KEY: \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -d '{ "first_name": "John", "last_name": "Snow" }' \ 
  -X POST
```
**Example Response**
```
Headers { Location: http://api.cliniko.com/patients/1 }
```
```json
{
  "address_1": "1 Smith Street",
  "address_2": "",
  "address_3": "",
  "archived_at": "",
  "city": "",
  "country": "",
  "created_at": "2013-03-26T14:00:00Z",
  "date_of_birth": "",
  "email": "",
  "emergency_contact": "",
  "first_name": "John",
  "gender": "",
  "id": 1,
  "last_name": "Snow",
  "notes": "",
  "occupation": "",
  "old_reference_id": "",
  "post_code": "",
  "referral_source": "",
  "state": "",
  "title": "",
  "updated_at": "2013-03-26T14:00:00Z",
  "patient_phone_numbers": [],
  "links": {"self": "https://api.cliniko.com/v1/patients/1"}
}
```

Update Patient
----------------
**Resources**
* ```PUT /patients/:id``` update a patient

**Example Request**
```shell
curl https://api.cliniko.com/v1/patients/1 \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'Content-Type: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -d '{ "first_name": "John", "last_name": "Snow" }' \ 
  -X PUT
```
**Example Response**
```json
{
  "address_1": "1 Smith Street",
  "address_2": "",
  "address_3": "",
  "archived_at": "",
  "city": "Melbourne",
  "country": "Australia",
  "created_at": "2013-03-26T14:00:00Z",
  "date_of_birth": "2001-05-26",
  "email": "peter@example.com",
  "emergency_contact": "",
  "first_name": "John",
  "gender": "Male",
  "id": 1,
  "last_name": "Snow",
  "notes": "",
  "occupation": "",
  "old_reference_id": "",
  "post_code": "3000",
  "referral_source": "",
  "state": "Victoria",
  "title": "Mr",
  "updated_at": "2013-03-26T14:00:00Z",
  "patient_phone_numbers": [
    {
      "phone_type": "Mobile",
      "number": "61444444444"
    },
    {
      "phone_type": "Home",
      "number": "61399999999"
    }
  ],
  "links": {"self": "https://api.cliniko.com/v1/patients/1"}
}
```

Delete Patient
----------------
**Resources**
* ```DELETE /patients/:id``` delete a patient

**Example Request**
```shell
curl https://api.cliniko.com/v1/patients/1 \
  -u API_KEY: \
  -H 'Accept: application/json' \
  -H 'User-Agent: APP_VENDOR_NAME (APP_VENDOR_EMAIL)' \
  -X DELETE
```
**Example Response**
A status code of `204 no content` will be returned if successful
