Patients
============
> Patients are the people that book in for appointments.  There isn't much in Cliniko that doesn't revolve around patients.
>
> When you're working with patient information, make sure you abide by the relevant regulations for security and privacy.

* [Get Patients](#get-patients "This will return all patients.")
* [Get Patient](#get-patient "This will return a specified patient.")

Get Patients
----------------

**Resources**
* ```GET /patients``` get all patients

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
      "id": 1,
      "last_name": "Patientman",
      "notes": "",
      "occupation": "",
      "old_reference_id": "",
      "post_code": "3000",
      "referral_source": "",
      "sex": "Male",
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
  "links": {"self": "https://api.cliniko.com/v1/patients"}
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
  "id": 1,
  "last_name": "Patientman",
  "notes": "",
  "occupation": "",
  "old_reference_id": "",
  "post_code": "3000",
  "referral_source": "",
  "sex": "Male",
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
