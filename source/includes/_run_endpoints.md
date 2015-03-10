# Runs

A single execution of your workflow is called a *run* in Rescale parlance.

## List Runs for a Job

`GET https://platform.rescale.com/api/jobs/{job_id}/runs/`

```shell
curl -X GET -H 'Authorization: Token \<token\>'
https://platform.rescale.com/api/jobs/XXXXXX/runs/
```

```python
import requests

requests.get(
  'https://platform.rescale.com/api/jobs/XXXXXX/runs/',
  headers={'Authorization': 'Token <api-token>'}
)
```

> Sample Response

```json
{
  "count": 121, 
  "next": "https://platform.rescale.com/api/jobs/XXXXXX/runs/?page=2", 
  "previous": null, 
  "results": [
    {
      "dateCompleted": "2015-02-18T03:09:14.667000Z", 
      "dateStarted": "2015-02-18T03:08:49.117000Z", 
      "displayOrder": 1, 
      "id": "1", 
      "isOptimal": false, 
      "outputFileCount": 66, 
      "outputFileSize": 8018226, 
      "parent": null, 
      "type": 3, 
      "variables": [
        {
          "displayValue": "20", 
          "isRelative": false, 
          "name": "x_velocity", 
          "value": 20.0
        }, 
        {
          "displayValue": "3", 
          "isRelative": false, 
          "name": "y_velocity", 
          "value": 3.0
        }, 
        {
          "displayValue": "-0.0187556", 
          "isRelative": false, 
          "name": "Cd", 
          "value": -0.0187556
        }, 
        {
          "displayValue": "0.140742", 
          "isRelative": false, 
          "name": "Cl", 
          "value": 0.140742
        }
      ]
    }, 
    {
      "dateCompleted": "2015-02-18T03:07:13.049000Z", 
      "dateStarted": "2015-02-18T03:06:46.477000Z", 
      "displayOrder": 2, 
      "id": "2", 
      "isOptimal": false, 
      "outputFileCount": 72, 
      "outputFileSize": 8805863, 
      "parent": null, 
      "type": 3, 
      "variables": [
        {
          "displayValue": "20", 
          "isRelative": false, 
          "name": "x_velocity", 
          "value": 20.0
        }, 
        {
          "displayValue": "3.5", 
          "isRelative": false, 
          "name": "y_velocity", 
          "value": 3.5
        }, 
        {
          "displayValue": "-0.0248332", 
          "isRelative": false, 
          "name": "Cd", 
          "value": -0.0248332
        }, 
        {
          "displayValue": "0.157982", 
          "isRelative": false, 
          "name": "Cl", 
          "value": 0.157982
        }
      ]
    }
  ]
}
```

This call allows you to retrieve the first page of runs associated with
_job-id_.


### Response Properties

Property | Type  | Description
-------- | ------|---------------
count | Integer | The total number of runs in the job
next | String | The URL that will return the next page of results.  
previous | String | The URL that will return the previous page of results
results | Array&lt;Object&gt; | An array of [Run objects](#get-a-run)


## Get a Run

`GET https://platform.rescale.com/api/jobs/{job_id}/runs/{run_id}/`

```shell
curl -X GET -H 'Authorization: Token \<token\>'
https://platform.rescale.com/api/jobs/XXXXXX/runs/1/
```

```python
import requests

requests.get(
  'https://platform.rescale.com/api/jobs/XXXXXX/runs/1/',
  headers={'Authorization': 'Token <api-token>'}
)
```

> Sample Response

```json
{
  "dateCompleted": "2015-02-18T03:09:14.667000Z", 
  "dateStarted": "2015-02-18T03:08:49.117000Z", 
  "displayOrder": 1, 
  "id": "1", 
  "isOptimal": false, 
  "outputFileCount": 66, 
  "outputFileSize": 8018226, 
  "parent": null, 
  "type": 3, 
  "variables": [
    {
      "displayValue": "20", 
      "isRelative": false, 
      "name": "x_velocity", 
      "value": 20.0
    }, 
    {
      "displayValue": "3", 
      "isRelative": false, 
      "name": "y_velocity", 
      "value": 3.0
    }, 
    {
      "displayValue": "-0.0187556", 
      "isRelative": false, 
      "name": "Cd", 
      "value": -0.0187556
    }, 
    {
      "displayValue": "0.140742", 
      "isRelative": false, 
      "name": "Cl", 
      "value": 0.140742
    }
  ]
}
```

### Response Properties

Property | Type  | Description
-------- | ------|---------------
dateCompleted | String | The ISO8601 encoded date of when the run finished.
dateInserted | String | The ISO8601 encoded date of when the run started.
displayOrder | Integer | Used for sorting a collection of runs into their canonical order.
id | String | The unique identifier of the run within a job.
isOptimal | Boolean | True if the optimizer or analysis code has designated this as a run of interest.
outputFileCount | Integer | The number of output files associated with this run
outputFileSize | Integer | The total size in bytes of all output files associated with this run
parent | String | The identifier of the parent run. 
type | Integer | 1 = Optimization, 2 = Iteration, 3 = Case
variables | List&lt;Variable&gt; | See below

#### Variable Properties
Property | Type  | Description
-------- | ----- |---------------
displayValue | String | The value that will be inserted into the template 
isRelative | Boolean | True if the variable values are relative to a default value entered into the template placeholder.
name | String | The variable name 
value | Float | The floating point representation of the variable value 

This call allows you to retrieve details for a single run within a job.

## Stop a Run

`POST https://platform.rescale.com/api/jobs/{job_id}/runs/{run_id}/stop/`

```shell
curl -X POST -H 'Authorization: Token \<token\>'
https://platform.rescale.com/api/jobs/XXXXX/runs/1/stop/
```

```python
import requests

requests.post(
  'https://platform.rescale.com/api/jobs/XXXXX/runs/1/stop/',
  headers={'Authorization': 'Token <api-token>'}
)
```

> Sample Response

```json
{}
```

Stops an in-progress run. The workflow processes will be killed and any
available output files will be uploaded to Rescale Cloud Storage. 

## Take a Snapshot

`POST https://platform.rescale.com/api/jobs/{job_id}/runs/{run_id}/snapshot/`

```shell
curl -X POST -H 'Authorization: Token \<token\>'
https://platform.rescale.com/api/jobs/XXXXX/runs/1/snapshot/
```

```python
import requests

requests.post(
  'https://platform.rescale.com/api/jobs/XXXXX/runs/1/snapshot/',
  headers={'Authorization': 'Token <api-token>'}
)
```

> Sample Response

```json
{
  "data": "", 
  "exitcode": 0, 
  "lastSnapshotID": "gQLna", 
  "reason": "Generating snapshot."
}
```

### Response Properties

Property | Type  | Description
-------- | ------|---------------
data | String | TODO
exitcode | Integer | The exit code from the snapshot utility. 0 indicates success.
lastSnapshotID | String | The file ID of the previously taken snapshot.
reason | String | TODO

Snapshots only apply to runs that are currently in-progress. A snapshot is an
archive of all files that currently exist in the working directory. After the
archive is created, it is uploaded to Rescale Cloud Storage and is made
available as a run output file.

## List Output Files

`GET https://platform.rescale.com/api/jobs/{job_id}/runs/{run_id}/files/`

```shell
curl -X GET -H 'Authorization: Token \<token\>'
https://platform.rescale.com/api/jobs/XXXXX/runs/1/files/
```

```python
import requests

requests.get(
  'https://platform.rescale.com/api/jobs/XXXXX/runs/1/files/',
  headers={'Authorization': 'Token <api-token>'}
)
```

> Sample Response

```json

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
      "path": "user/user_OvdRk/output/job_XXXXX/run1/airFoil2D/0/nut",
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
      "encodedEncryptionKey": "dQ3xMn6zAZkUx84ClH3ATmKumeaNJfWGna2k/89/V/s=",
      "sharedWith": [],
      "decryptedSize": 1268,
      "owner": "demouser@rescale.com",
      "path": "user/user_OvdRk/output/job_XXXXX/run1/airFoil2D/0/nuTilda",
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
      "encodedEncryptionKey": "ZHE2IT4ADwAJjfJYnYL4oBwp7YJ9cQr02nS3djnCHGA=",
      "sharedWith": [],
      "decryptedSize": 1166,
      "owner": "demouser@rescale.com",
      "path": "user/user_OvdRk/output/job_XXXXX/run1/airFoil2D/0/p",
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
      "encodedEncryptionKey": "NxEzQf+pChx9716FY4cdSb+UIw9ow64BimupkxaExYA=",
      "sharedWith": [],
      "decryptedSize": 1298,
      "owner": "demouser@rescale.com",
      "path": "user/user_OvdRk/output/job_XXXXX/run1/airFoil2D/0/U",
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
      "encodedEncryptionKey": "M+X0Sxys9icqpXmdUreDnqg2TmLVL7B7vs68JiJDEU4=",
      "sharedWith": [],
      "decryptedSize": 100195,
      "owner": "demouser@rescale.com",
      "path": "user/user_OvdRk/output/job_XXXXX/run1/airFoil2D/100/nut",
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
      "encodedEncryptionKey": "yg6l0x1NkYkXOPT3TRoxTnXVC3x9C/SaB+tLSX+6M+U=",
      "sharedWith": [],
      "decryptedSize": 99221,
      "owner": "demouser@rescale.com",
      "path": "user/user_OvdRk/output/job_XXXXX/run1/airFoil2D/100/nuTilda",
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
      "encodedEncryptionKey": "cwQWYQLRl7+IIU462hGELzwz9iVxpf/CfgYUEQVndB4=",
      "sharedWith": [],
      "decryptedSize": 86615,
      "owner": "demouser@rescale.com",
      "path": "user/user_OvdRk/output/job_XXXXX/run1/airFoil2D/100/p",
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
      "encodedEncryptionKey": "5fWxJl5KR7G3oVUYJjjYMzbSveYLAYF6AW8xFDahZtk=",
      "sharedWith": [],
      "decryptedSize": 190707,
      "owner": "demouser@rescale.com",
      "path": "user/user_OvdRk/output/job_XXXXX/run1/airFoil2D/100/phi",
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
      "encodedEncryptionKey": "gHfNzchETji3v69TfeeyhBe0+owGJhNcX7PAzgmJha8=",
      "sharedWith": [],
      "decryptedSize": 298228,
      "owner": "demouser@rescale.com",
      "path": "user/user_OvdRk/output/job_XXXXX/run1/airFoil2D/100/U",
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
      "encodedEncryptionKey": "F3HkdyuOCnxO6NwIJbv6Zg+xzKTFZKxrc6NvuneB2QE=",
      "sharedWith": [],
      "decryptedSize": 968,
      "owner": "demouser@rescale.com",
      "path": "user/user_OvdRk/output/job_XXXXX/run1/airFoil2D/100/uniform/time",
      "isUploaded": true,
      "viewInBrowser": true,
      "id": "LosKDe",
      "md5": "62ac76eb8aae234370613d7350ac8685"
    }
  ],
  "next": "https://platform.rescale.com/api/jobs/XXXXX/runs/1/files/?page=2"
}
```

This call allows you to fetch the metadata regarding all the files
associated with _run-id_. You can then use the _file-id_ to download
each individual file.

Another, endpoint that is helpful in fetching files is, _/api/jobs/<
job-id >/files/_ which will return all the files related to a particular
job, including the output of all the runs.

**Note**: Output files are available only after a run has completed. If you
want to retrieve a list of files for a run that is currently in progress, you
should use the _/api/jobs/< job-id >/runs/< run-id >/directory-contents/_
[endpoint](#list-directory-contents).

## List Directory Contents

`GET https://platform.rescale.com/api/jobs/{job_id}/runs/{run_id}/directory-contents/`

```shell
curl -X GET -H 'Authorization: Token \<token\>'
https://platform.rescale.com/api/jobs/XXXXX/runs/1/directory-contents/
```

```python
import requests

requests.get(
  'https://platform.rescale.com/api/jobs/XXXXX/runs/1/directory-contents/',
  headers={'Authorization': 'Token <api-token>'}
)
```

> Sample Response

```json
[
  {
    "path": "airFoil2D/0/U", 
    "resource": "/api/jobs/XXXXX/runs/1/tail/airFoil2D/0/U"
  }, 
  {
    "path": "airFoil2D/0/nuTilda", 
    "resource": "/api/jobs/XXXXX/runs/1/tail/airFoil2D/0/nuTilda"
  }, 
  {
    "path": "airFoil2D/0/nut", 
    "resource": "/api/jobs/XXXXX/runs/1/tail/airFoil2D/0/nut"
  }
]
```

### Response Properties

Property | Type  | Description
-------- | ----- |---------------
path | String | The relative path to a file in the run's working directory
resource | String | The API url that can be used to retrieve the file's contents

This call returns a list of files from the specified run's working directory.

**Note**: This endpoint only applies to runs that are currently in-progress.
After a run completes, all files in the working directory are uploaded to
Rescale Cloud Storage and are made available as output files. Use the
_/api/jobs/< job-id >/runs/< run-id >/files/_ [endpoint](#list-output-files) to retrieve them. 

## Tail File Content

`GET https://platform.rescale.com/api/jobs/{job_id}/runs/{run_id}/tail/{path}/`

| Field        | Default | Required | Description  |
| ------------ | --------| -------- | ------------ |
| lines | None | No | The number of lines to retrieve from the specified file. If omitted, the raw binary contents of the file will be returned in the response.

```shell
curl -v -X GET -H 'Authorization: Token \<token\>'
http://platform.rescale.com/api/jobs/XXXXX/runs/1/tail/airFoil2D/0/U?lines=100
```

```python
import requests

requests.get(
  'http://platform.rescale.com/api/jobs/XXXXX/runs/1/tail/airFoil2D/0/U',
  headers={'Authorization': 'Token <api-token>'},
  params={'lines': 100}
)
```

> Sample Response

```json
{
  "fileType": "/home/job_fNjea/work/airFoil2D/0/U: ASCII English text", 
  "lines": [
    "/*--------------------------------*- C++ -*----------------------------------*\\", 
    "| =========                 |                                                 |", 
    "| \\\\      /  F ield         | OpenFOAM: The Open Source CFD Toolbox           |", 
    "|  \\\\    /   O peration     | Version:  2.0.1                                 |", 
    "|   \\\\  /    A nd           | Web:      www.OpenFOAM.com                      |", 
    "|    \\\\/     M anipulation  |                                                 |", 
    "\\*---------------------------------------------------------------------------*/", 
    "FoamFile", 
    "{", 
    "    version     2.0;", 
    "    format      ascii;", 
    "    class       volVectorField;", 
    "    object      U;", 
    "}", 
    "// * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * //", 
    "", 
    "dimensions      [0 1 -1 0 0 0 0];", 
    "", 
    "internalField   uniform (25.75 3.62 0);", 
    "", 
    "boundaryField", 
    "{", 
    "    inlet", 
    "    {", 
    "        type            freestream;", 
    "        freestreamValue uniform (25.75 3.62 0);", 
    "    }", 
    "", 
    "    outlet", 
    "    {", 
    "        type            freestream;", 
    "        freestreamValue uniform (25.75 3.62 0);", 
    "    }", 
    "", 
    "    wall", 
    "    {", 
    "        type            fixedValue;", 
    "        value           uniform (0 0 0);", 
    "    }", 
    "", 
    "    frontAndBack", 
    "    {", 
    "        type            empty;", 
    "    }", 
    "}", 
    "", 
    "// ************************************************************************* //"
  ]
}
```

### Response Properties

Property | Type  | Description
-------- | ------|---------------
fileType | String | The file type as determined by the *NIX file command.
lines | Array&lt;String&gt; | An array containing the last N lines of the requested file where N is the value of the lines querystring argument.

This method can be used to retrieve the last N lines within a file or to stream
back the entire file to the caller.

The _path_ argument of the url corresponds to the _path_ property returned in
the [List Output Files endpoint](#list-output-files).

**Note**: This endpoint only applies to runs that are currently in-progress.
After a run has completed, the _/api/files/< file-id >/contents/_
[endpoint](#download-a-file) can be used to download the output file.
