# Runs

A single execution of your workflow is called a *run* in Rescale parlance.

## List Runs for a Job

`GET https://platform.rescale.com/api/jobs/{job_id}/runs/`

## Get a Run

`GET https://platform.rescale.com/api/jobs/{job_id}/runs/{run_id}/`

> curl -X GET -H 'Authorization: Token \<token\>'
> https://platform.rescale.com/api/jobs/QTVia/runs/1/files/

> HTTP 200 OK

```

{
  "count": 63,
  "previous": null,
  "results": [
    {
      "typeId": 5,
      "name": "nut",
      "dateUploaded": "2014-11-12T22:56:50.641761Z",
      "relativePath": "airFoil2D/0/nut",
      "encodedEncryptionKey": "5BBRrtu98/BwNNTkPnJtgaHS2VZ0IzUwgQ+fFqc5rhk=",
      "sharedWith": [],
      "decryptedSize": 1278,
      "owner": "demouser@rescale.com",
      "path": "user/user_OvdRk/output/job_QTVia/run1/airFoil2D/0/nut",
      "isUploaded": true,
      "viewInBrowser": true,
      "id": "dmpTse",
      "md5": "c2e31d85a3af9272841a8b00f3c07498"
    },
    {
      "typeId": 5,
      "name": "nuTilda",
      "dateUploaded": "2014-11-12T22:56:50.550979Z",
      "relativePath": "airFoil2D/0/nuTilda",
      "encodedEncryptionKey":
"dQ3xMn6zAZkUx84ClH3ATmKumeaNJfWGna2k/89/V/s=",
      "sharedWith": [],
      "decryptedSize": 1268,
      "owner": "demouser@rescale.com",
      "path":
"user/user_OvdRk/output/job_QTVia/run1/airFoil2D/0/nuTilda",
      "isUploaded": true,
      "viewInBrowser": true,
      "id": "fDhFDe",
      "md5": "24af84107af3a306e117b866b27b9c55"
    },
    {
      "typeId": 5,
      "name": "p",
      "dateUploaded": "2014-11-12T22:56:50.714078Z",
      "relativePath": "airFoil2D/0/p",
      "encodedEncryptionKey":
"ZHE2IT4ADwAJjfJYnYL4oBwp7YJ9cQr02nS3djnCHGA=",
      "sharedWith": [],
      "decryptedSize": 1166,
      "owner": "demouser@rescale.com",
      "path": "user/user_OvdRk/output/job_QTVia/run1/airFoil2D/0/p",
      "isUploaded": true,
      "viewInBrowser": true,
      "id": "sOhFDe",
      "md5": "dfff0408d9e75c8f81dadeec9b248a46"
    },
    {
      "typeId": 5,
      "name": "U",
      "dateUploaded": "2014-11-12T22:56:50.465184Z",
      "relativePath": "airFoil2D/0/U",
      "encodedEncryptionKey":
"NxEzQf+pChx9716FY4cdSb+UIw9ow64BimupkxaExYA=",
      "sharedWith": [],
      "decryptedSize": 1298,
      "owner": "demouser@rescale.com",
      "path": "user/user_OvdRk/output/job_QTVia/run1/airFoil2D/0/U",
      "isUploaded": true,
      "viewInBrowser": true,
      "id": "RapTse",
      "md5": "66aa52fa89123a8f6c3751d935b919d5"
    },
    {
      "typeId": 5,
      "name": "nut",
      "dateUploaded": "2014-11-12T22:56:50.931594Z",
      "relativePath": "airFoil2D/100/nut",
      "encodedEncryptionKey":
"M+X0Sxys9icqpXmdUreDnqg2TmLVL7B7vs68JiJDEU4=",
      "sharedWith": [],
      "decryptedSize": 100195,
      "owner": "demouser@rescale.com",
      "path": "user/user_OvdRk/output/job_QTVia/run1/airFoil2D/100/nut",
      "isUploaded": true,
      "viewInBrowser": true,
      "id": "fmpTse",
      "md5": "84597f0bc96aaefd338109e6ddbe3493"
    },
    {
      "typeId": 5,
      "name": "nuTilda",
      "dateUploaded": "2014-11-12T22:56:50.862457Z",
      "relativePath": "airFoil2D/100/nuTilda",
      "encodedEncryptionKey":
"yg6l0x1NkYkXOPT3TRoxTnXVC3x9C/SaB+tLSX+6M+U=",
      "sharedWith": [],
      "decryptedSize": 99221,
      "owner": "demouser@rescale.com",
      "path":
"user/user_OvdRk/output/job_QTVia/run1/airFoil2D/100/nuTilda",
      "isUploaded": true,
      "viewInBrowser": true,
      "id": "hDhFDe",
      "md5": "489cb134eb1c14f6f5df760d9a421825"
    },
    {
      "typeId": 5,
      "name": "p",
      "dateUploaded": "2014-11-12T22:56:51.005975Z",
      "relativePath": "airFoil2D/100/p",
      "encodedEncryptionKey":
"cwQWYQLRl7+IIU462hGELzwz9iVxpf/CfgYUEQVndB4=",
      "sharedWith": [],
      "decryptedSize": 86615,
      "owner": "demouser@rescale.com",
      "path": "user/user_OvdRk/output/job_QTVia/run1/airFoil2D/100/p",
      "isUploaded": true,
      "viewInBrowser": true,
      "id": "uOhFDe",
      "md5": "fb5df9fdf2fd6de74a0f38998831b252"
    },
    {
      "typeId": 5,
      "name": "phi",
      "dateUploaded": "2014-11-12T22:56:51.079312Z",
      "relativePath": "airFoil2D/100/phi",
      "encodedEncryptionKey":
"5fWxJl5KR7G3oVUYJjjYMzbSveYLAYF6AW8xFDahZtk=",
      "sharedWith": [],
      "decryptedSize": 190707,
      "owner": "demouser@rescale.com",
      "path": "user/user_OvdRk/output/job_QTVia/run1/airFoil2D/100/phi",
      "isUploaded": true,
      "viewInBrowser": true,
      "id": "wMyXse",
      "md5": "2fb30c6d0e3ea1125a361ce069c46a80"
    },
    {
      "typeId": 5,
      "name": "U",
      "dateUploaded": "2014-11-12T22:56:50.787838Z",
      "relativePath": "airFoil2D/100/U",
      "encodedEncryptionKey":
"gHfNzchETji3v69TfeeyhBe0+owGJhNcX7PAzgmJha8=",
      "sharedWith": [],
      "decryptedSize": 298228,
      "owner": "demouser@rescale.com",
      "path": "user/user_OvdRk/output/job_QTVia/run1/airFoil2D/100/U",
      "isUploaded": true,
      "viewInBrowser": true,
      "id": "TapTse",
      "md5": "0cc541d092ceda7e299ecb736c7905ee"
    },
    {
      "typeId": 5,
      "name": "time",
      "dateUploaded": "2014-11-12T22:56:51.222466Z",
      "relativePath": "airFoil2D/100/uniform/time",
      "encodedEncryptionKey":
"F3HkdyuOCnxO6NwIJbv6Zg+xzKTFZKxrc6NvuneB2QE=",
      "sharedWith": [],
      "decryptedSize": 968,
      "owner": "demouser@rescale.com",
      "path":
"user/user_OvdRk/output/job_QTVia/run1/airFoil2D/100/uniform/time",
      "isUploaded": true,
      "viewInBrowser": true,
      "id": "LosKDe",
      "md5": "62ac76eb8aae234370613d7350ac8685"
    }
  ],
  "next":
"https://platform.rescale.com/api/jobs/QTVia/runs/1/files/?page=2"
}
```

This call allows you to fetch the metadata regarding all the files
associated with _run-id 1_. You can then use the _file-id_ to download
each individual file.

Another, endpoint that is helpful in fetching files is, _/api/jobs/<
job-id >/files/_ which will return all the files related to a particular
job, including the output of all the runs.


## Stop a Run

`POST https://platform.rescale.com/api/jobs/{job_id}/runs/{run_id}/stop/`

## Take a Snapshot

`POST https://platform.rescale.com/api/jobs/{job_id}/runs/{run_id}/snapshot/`

## List Output Files

`GET https://platform.rescale.com/api/jobs/{job_id}/runs/{run_id}/files/`

## List Directory Contents

`GET https://platform.rescale.com/api/jobs/{job_id}/runs/{run_id}/directory-contents/`

## Tail File Content

`GET https://platform.rescale.com/api/jobs/{job_id}/runs/{run_id}/tail/{path}/`

