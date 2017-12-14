# How to upload a patient attachment to Cliniko

## Get a presigned POST to upload your file to s3

Make a request for a presigned POST for the patient that you want to upload a file for.
`http://api.cliniko.com/v1/patients/456/attachment_presigned_post`

The response will give you the URL and parameters that you need to upload the file to s3.
```json
{
  "url": "https://cliniko-files-example-bucket.s3.amazonaws.com/",
  "fields": {
    "AWSAccessKeyId": "TH1S1SN0TAR34LACC3SSK3Y",
    "key": "123/patients/456/attachments/temp/s0m3-w31rd-l0c4t10n-1na-t3mpd1r/${filename}",
    "policy": "TH1Sw1llB3aR34LLYl0ngSTR1NG0nlyUNDERST00DbyROBOT5",
    "signature": "51gn3d+0n3/R0b0t2aN0th3r=",
    "success_action_status":"201",
    "acl":"private"
  }
} 
```

## Upload the file to our s3 bucket

Using the tool of your choice, make a POST request to the given URL with the file to upload. You must append the given parameters to the request payload using the given keys and values. Make sure to use the values provided as the values will vary for each upload and the s3 bucket will differ based on the location of the Cliniko account.

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

At this point, your file is in our s3 bucket in a temp directory, but Cliniko doesn't have a patient attachment record for it. To finish, you must create a new patient attachment record.

To do so, make a POST request to the patient attachments endpoint, with the patient ID and s3 temp URL as parameters. The `upload_url` parameter is the `Location` value in the s3 XML response. Using the value as is from the XML response is important as the s3 filename may have been escaped special characters to make the URL friendly.

`http://api.cliniko.com/v1/patient_attachments`
```json
{
  "patient_id": "382",
  "upload_url": "https://cliniko-files-example-bucket.s3.amazonaws.com/123%2Fpatients%2F456%2Fattachments%2Ftemp%2Fs0m3-w31rd-l0c4t10n-1na-t3mpd1r%2Fthe-name-of-the-file.txt"
}
```

A successful create will return a 201 and the payload will be the new attachment record. The format of that response is detailed in the section on the [patient attachment resource](url here when that page exists).

## Cliniko will process the file

At this point the record exists, but Cliniko will not yet have processed the file. This is indicated by the `processing_completed` attribute being `false`. A few other attributes like filename will be blank until processing is finished. The time to process a file depends upon the size of the file and the amount of other traffic in the queue. When the processing is completed, the file will no longer exist at the temp location where you uploaded it. You will need to request the patient attachment record and follow the URL provided there to access the file again.

## Free trial accounts have limited file space

Please note that free trial accounts are allowed only 10 files that must not total more than 1 MB. If you attempt to upload beyond those limits, you will receive an error.
