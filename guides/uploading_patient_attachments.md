# How to upload a patient attachment to Cliniko

Cliniko uses Amazon S3 to store and process patient attachments. Files can be
stored in one of several regions, with a given customer account's files always
being stored in the same region.

Amazon supports several algorithms for generating the signatures used in the
process outlined below. The latest version of their signature algorithm is 4,
supported by all regions. This is what Cliniko uses.

The guide below contains instructions on how to upload patient attachments to
Cliniko.

## Get a presigned URL to upload your file to S3

Make a GET request for a presigned URL for the patient that you want to upload a file for.
`https://api.au1.cliniko.com/v1/patients/456/attachment_presigned_post`

The response will then give you the URL and parameters you need to upload the
file:

```json
{
  "url": "https://cliniko-files-example-bucket.s3.amazonaws.com/",
  "fields": {
    "key": "123/patients/456/attachments/temp/s0m3-w31rd-l0c4t10n-1na-t3mpd1r/${filename}",
    "policy": "TH1Sw1llB3aR34LLYl0ngSTR1NG0nlyUNDERST00DbyROBOT5",
    "x-amz-credential": "TH1S1SN0TAR34LACC3SSK3Y",
    "x-amz-signature": "51gn3d+0n3/R0b0t2aN0th3r=",
    "x-amz-algorithm": "AWS4-HMAC-SHA256",
    "x-amz-date": "TIMESTAMP",
    "success_action_status":"201",
    "acl":"private"
  }
}
```

## Upload the file to our s3 bucket

Using the tool of your choice, make a POST request to the given URL with the
file to upload. You must append the given parameters to the request payload
using the given keys and values. Make sure to use the values provided as the
values will vary for each upload and the s3 bucket will differ based on the
location of the Cliniko account.

```
curl https://cliniko-files-example-bucket.s3.amazonaws.com/ \
  -F 'x-amz-credential=TH1S1SN0TAR34LACC3SSK3Y' \
  -F 'key=123/patients/456/attachments/temp/s0m3-w31rd-l0c4t10n-1na-t3mpd1r/${filename}' \
  -F 'policy=TH1Sw1llB3aR34LLYl0ngSTR1NG0nlyUNDERST00DbyROBOT5' \
  -F 'x-amz-signature=51gn3d+0n3/R0b0t2aN0th3r=' \
  -F 'x-amz-algorithm=AWS4-HMAC-SHA256' \
  -F 'x-amz-date=TIMESTAMP' \
  -F 'success_action_status=201' \
  -F 'acl=private' \
  -F 'file=@/home/user/files/test.pdf'
```

Upon success, you will receive a 201 response and an XML response payload from s3 like this:
```xml
<?xml version="1.0" encoding="UTF-8"?>
<PostResponse>
  <Location>https://cliniko-files-example-bucket.s3.amazonaws.com/123%2Fpatients%2F456%2Fattachments%2Ftemp%2Fs0m3-w31rd-l0c4t10n-1na-t3mpd1r%2Fthe-name-of-the-file.txt</Location>
  <Bucket>cliniko-files-example-bucket</Bucket>
  <Key>123/patients/456/attachments/temp/s0m3-w31rd-l0c4t10n-1na-t3mpd1r/the-name-of-the-file.txt</Key>
  <ETag>"4n0th3rD4NGr0b0tID"</ETag>
</PostResponse>
```

## Create a patient attachment record in Cliniko

At this point, your file is in our s3 bucket in a temp directory, but Cliniko
doesn't have a patient attachment record for it. To finish, you must create a
new patient attachment record.

To do so, make a POST request to the patient attachments endpoint, with the
patient ID and s3 temp URL as parameters. The `upload_url` parameter is the
combination of `url` value in the presigned post response + `Key` value in the
s3 XML response.

`https://api.au1.cliniko.com/v1/patient_attachments`
```json
{
  "description": "Custom description for this attachment",
  "patient_id": 382,
  "upload_url": "https://cliniko-files-example-bucket.s3.amazonaws.com/123/patients/456/attachments/temp/s0m3-w31rd-l0c4t10n-1na-t3mpd1r/the-name-of-the-file.txt"
}
```

A successful create will return a 201 and the payload will be the new attachment
record. The format of that response is detailed in the section on the [patient
attachment resource](https://github.com/redguava/cliniko-api/blob/master/sections/patient_attachments.md).

## Cliniko will process the file

At this point the record exists, but Cliniko will not yet have processed the
file. This is indicated by the `processing_completed` attribute being `false`. A
few other attributes like filename will be blank until processing is
finished. The time to process a file depends upon the size of the file and the
amount of other traffic in the queue. When the processing is completed, the file
will no longer exist at the temp location where you uploaded it. You will need
to request the patient attachment record and follow the URL provided there to
access the file again.

## Free trial accounts have limited file space

Please note that free trial accounts have a restricted amount of file
storage. If you attempt to upload beyond those limits, you will receive an
error.
