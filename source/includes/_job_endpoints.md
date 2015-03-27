# Jobs

## List All Jobs

`GET https://platform.rescale.com/api/v2/jobs/`

```shell
curl -H "Authorization: Token <api-token>" https://platform.rescale.com/api/v2/jobs/
```

```python
import requests

requests.get(
  'https://platform.rescale.com/api/v2/jobs/',
  headers={'Authorization': 'Token <api-token>'}
)
```

> Sample Response

```json
{
    "count": 3,
    "next": null,
    "previous": null,
    "results": [
        {
            "analysisNames": [
                "OpenFOAM"
            ],
            "clusterStatusDisplay": {
                "content": "Stopped",
                "labelClass": "",
                "useLabel": false
            },
            "dateInserted": "2015-03-13T23:43:21.223052Z",
            "id": "OsKBd",
            "isVisible": true,
            "jobStatus": {
                "content": "Completed",
                "labelClass": "",
                "useLabel": false
            },
            "name": "the FOAM 2",
            "owner": "mark@rescale.com",
            "sharedWith": [],
            "storage": 8014908
        },
        {
            "analysisNames": [
                "OpenFOAM"
            ],
            "clusterStatusDisplay": {
                "content": "Stopped",
                "labelClass": "",
                "useLabel": false
            },
            "dateInserted": "2015-02-07T01:57:14.332984Z",
            "id": "XZFQV",
            "isVisible": true,
            "jobStatus": {
                "content": "Completed",
                "labelClass": "",
                "useLabel": false
            },
            "name": "the FOAM",
            "owner": "mark@rescale.com",
            "sharedWith": [
                "someoneelse@example.com"
            ],
            "storage": 8014906
        },
        {
            "analysisNames": [
                "Custom User-Defined MPI Software"
            ],
            "clusterStatusDisplay": {
                "content": "",
                "labelClass": "",
                "useLabel": false
            },
            "dateInserted": "2014-10-09T23:00:36.198759Z",
            "id": "kikcT",
            "isVisible": true,
            "jobStatus": {
                "content": "",
                "labelClass": "",
                "useLabel": false
            },
            "name": "MPI Hello",
            "owner": "mark@rescale.com",
            "sharedWith": [],
            "storage": 0
        }
    ]
}
```

This endpoint retrieves all the jobs visible to the authenticated user
(you), whether they are owned by that user or shared with that user.

### Response Properties

Property | Type  | Description
-------- | ------|---------------
clusterStatusDisplay | Object  | Describes the current status of the job's compute clusters
dateInserted | String | The date this job was created
name | String | The name of this job
analysisNames | Array&lt;String&gt; | The names all the analyses being run for the job
jobStatus | Object | Describes the current status of the job
sharedWith | Array&lt;String&gt; | Email addresses of the users this job has been shared with
isVisible | Boolean | Always true if you can retrieve the job
owner | String | The email address of the owner of the job
id | String | A unique identifier for the job
storage | Integer | Number of bytes used for the input and output files of this job

## Get a Specific Job

`GET https://platform.rescale.com/api/v2/jobs/{job_id}/`

```shell
curl -H "Authorization: Token <api-token>" https://platform.rescale.com/api/v2/jobs/aabbcc/
```

```python
```

```json
{
    "archiveFilters": [],
    "caseFile": null,
    "expectedRuns": 3,
    "id": "aabbcc",
    "includeNominalRun": false,
    "isLowPriority": true,
    "isTemplateDryRun": false,
    "jobanalyses": [
        {
            "analysis": {
                "code": "openfoam",
                "name": "OpenFOAM",
                "version": "2.3.1-openmpi",
                "versionName": "2.3.1"
            },
            "command": "./airFoil2D_DOE/Allrun",
            "envVars": {},
            "flags": {},
            "hardware": {
                "coreSummary": {
                    "memoryPerNode": 3750,
                    "numberOfNodes": 1.0,
                    "storagePerNode": 4000
                },
                "coreType": "standard-plus",
                "coresPerSlot": 1,
                "slots": 1,
                "walltime": null
            },
            "inputFiles": [
                {
                    "dateUploaded": "2015-03-26T23:08:33.700457Z",
                    "decryptedSize": 655816,
                    "downloadUrl": "https://platform.rescale.com/api/v2/files/duMEdg/contents/",
                    "encodedEncryptionKey": "NYhibURTMAMKNWmWiDuUZxn+oUaRwp8iExaECpU6Dwo=",
                    "id": "duMEdg",
                    "isDeleted": false,
                    "isUploaded": true,
                    "md5": "60c6492014f73ad0c08da866b4ce9160",
                    "name": "airfoid2d_doe.tar.gz",
                    "owner": "mark@rescale.com",
                    "path": "user/user_KBdkT/airfoid2d_doe.tar.gz-12f94e2222a0feafea96d31e634af2c6",
                    "relativePath": "airfoid2d_doe.tar.gz",
                    "sharedWith": [],
                    "typeId": 1,
                    "viewInBrowser": false
                }
            ],
            "postProcessScript": null,
            "postProcessScriptCommand": "",
            "preProcessScript": null,
            "preProcessScriptCommand": "",
            "templateTasks": [
                {
                    "processedFilename": "airFoil2D_DOE/0/U",
                    "templateFile": {
                        "dateUploaded": "2015-03-26T23:09:46.256315Z",
                        "decryptedSize": 1344,
                        "downloadUrl": "https://platform.rescale.com/api/v2/files/qEMEdg/contents/",
                        "encodedEncryptionKey": "olx6Kn7vde1siRKoDqBRTkaT25k1x8P9IYy3PdhmFhk=",
                        "id": "qEMEdg",
                        "isDeleted": false,
                        "isUploaded": true,
                        "md5": "b4ae5cb300c8b3d1410231e8fd474110",
                        "name": "utemplate",
                        "owner": "mark@rescale.com",
                        "path": "user/user_KBdkT/utemplate-2f3c3004f5909acf0b7cc2a56c5be35c",
                        "relativePath": "utemplate",
                        "sharedWith": [],
                        "typeId": 2,
                        "viewInBrowser": true
                    }
                }
            ],
            "useRescaleLicense": false
        }
    ],
    "jobvariables": [
        {
            "displayOrder": 0,
            "name": "Xvelocity",
            "valueGeneratorSettings": {},
            "valueGeneratorType": "",
            "variableType": "Param"
        },
        {
            "displayOrder": 1,
            "name": "Yvelocity",
            "valueGeneratorSettings": {},
            "valueGeneratorType": "",
            "variableType": "Param"
        }
    ],
    "monteCarloIterations": null,
    "name": "Untitled Job",
    "optimizer": null,
    "owner": "mark@rescale.com",
    "paramFile": {
        "dateUploaded": "2015-03-26T23:09:25.532849Z",
        "decryptedSize": 55,
        "downloadUrl": "https://platform.rescale.com/api/v2/files/sWErpg/contents/",
        "encodedEncryptionKey": "6kvS7Y3M6HXFcHos0rLUcEf4hNyupzn8x1j7CUU3qko=",
        "id": "sWErpg",
        "isDeleted": false,
        "isUploaded": true,
        "md5": "9ba0663810a4568dece19b67533e2759",
        "name": "freestreamvalue.csv",
        "owner": "mark@rescale.com",
        "path": "user/user_KBdkT/freestreamvalue.csv-5ebf0b8ddbf834ec2e8e7e727de91c82",
        "relativePath": "freestreamvalue.csv",
        "sharedWith": [],
        "typeId": 3,
        "viewInBrowser": true
    },
    "remoteVizConfig": null,
    "resourceFilters": []
}
```

Retreive the details of a saved job.

### Response Properties

Property | Type  | Description
-------- | ------|---------------
| archiveFilters | Array&lt;String&gt; | Filters on job visibility related to whether it is archived |
| caseFile | Object | File with case variables for DOE job |
| expectedRuns | Integer | Number of runs for a DOE, will be 1 for basic jobs |
| id | String | Job identifier |
| includeNominalRun | Boolean | Whether to include a nominal baseline run for a DOE job |
| isLowPriority | Boolean | Is this a low priority job? |
| isTemplateDryRun | Boolean | Run this job in "dry run" mode to check DOE templates |
| jobanalyses | Array&lt;Object&gt; | List of analyses for the job. Details below |
| jobvariables | Array&lt;Object&gt; | List of job variables for DOE job. Details below |
| monteCarloIterations | Integer | Number of iterations for Monte Carlo optimization job |
| name | String | Name of job |
| optimizer | Object | Job analysis representing optimizer used for optimization jobs |
| owner | String | Email address of job owner |
| paramFile | Object | CSV file with DOE parameters (DOE job only) |
| remoteVizConfig | Object | (deprecated) Configuration for companion remote visualization node |
| resourceFilters | Array&lt;Object&gt; | Filters on file resources |
| jobvariables | None | No |    List of job variables for this job. See details below. |
| jobanalyses | None | Yes |    List of analyses for this job. See details below. |
| resourceFilters | Default filters | No | List of filtering rules for output files. |

## List Job Output Files

`GET https://platform.rescale.com/api/v2/jobs/{job_id}/files/`


```shell
curl -H "Authorization: Token <api-token>" https://platform.rescale.com/api/v2/jobs/aabbcc/files/
```

```json
{
    "count": 1,
    "next": null,
    "previous": null,
    "results": [
        {
            "dateUploaded": "2015-03-13T23:56:37.184619Z",
            "decryptedSize": 1680,
            "downloadUrl": "https://platform.rescale.com/api/v2/files/xTyjeg/contents/",
            "encodedEncryptionKey": "VkAWWRkKR9xJIDJTdkVK42O/7+Xo3M4LOaGvP6HjHMA=",
            "id": "xTyjeg",
            "isDeleted": false,
            "isUploaded": true,
            "md5": "8632d6580e922bd9f8691cc2d6ea3443",
            "name": "fvSchemes",
            "owner": "mark@rescale.com",
            "path": "user/user_KBdkT/output/job_OsKBd/run1/airFoil2D/system/fvSchemes",
            "relativePath": "airFoil2D/system/fvSchemes",
            "sharedWith": [],
            "typeId": 5,
            "viewInBrowser": true
        }
    ]
}
```

List OUTPUT files for a given job

### Response Properties

Property | Type  | Description
-------- | ------|---------------
| dateUploaded | DateTime | Date file was uploaded to platform by job |
| decryptedSize | Integer | File size in bytes |
| downloadUrl | URL | URL for retrieving file |
| encodedEncryptionKey | String | Key to decrypt file |
| id | String | Id of file |
| isDeleted | Boolean | Whether file has been marked deleted |
| isUploaded | Boolean | Whether file has finished uploading (false means upload is in progress or failed) |
| md5 | String | MD5 string for file contents |
| name | String | Name of file |
| owner | String | Email address of file owner |
| path | String | Path for file in Rescale storage |
| relativePath | String | Path for file relative to job run |
| sharedWith | Array%gt;String&lt; | List of email address the file was shared with |
| typeId | Integer | Type of file (input, output, template, etc.), should be 5=output in this case |
| viewInBrowser | Boolean | Whether the file can be viewed directly in on the Rescale platform |

## Create a Job

`POST https://platform.rescale.com/api/v2/jobs/`

> Basic job, no input files

```shell
curl -H "Authorization: Token <api-token>" -H "Content-Type: application/json" "http://platform-local.rescale.com:8000/api/jobs/" -d '
{
    "name": "Jobbo",
    "jobanalyses": [
        {
            "analysis": {
                "code": "user_included",
                "version": "0"
            },
            "command": "echo \"Hello world\"",
            "hardware": {
                "coreType": "standard-plus",
                "coresPerSlot": 1
            }
        }
    ]
}
'
```

> Response

```json
{
    "archiveFilters": [],
    "caseFile": null,
    "expectedRuns": null,
    "id": "LeeKa",
    "includeNominalRun": false,
    "isLowPriority": false,
    "isTemplateDryRun": false,
    "jobanalyses": [
        {
            "analysis": {
                "code": "user_included",
                "name": "Custom User-Defined Software",
                "version": "0",
                "versionName": ""
            },
            "command": "echo \"Hello world\"",
            "envVars": {},
            "flags": {},
            "hardware": {
                "coreSummary": {
                    "memoryPerNode": 3750,
                    "numberOfNodes": 1.0,
                    "storagePerNode": 4000
                },
                "coreType": "standard-plus",
                "coresPerSlot": 1,
                "slots": 1,
                "walltime": null
            },
            "inputFiles": [],
            "postProcessScript": null,
            "postProcessScriptCommand": "",
            "preProcessScript": null,
            "preProcessScriptCommand": "",
            "templateTasks": [],
            "useRescaleLicense": false
        }
    ],
    "jobvariables": [],
    "monteCarloIterations": null,
    "name": "Jobbo",
    "optimizer": null,
    "owner": "mark@rescale.com",
    "paramFile": null,
    "remoteVizConfig": null,
    "resourceFilters": []
}
```

Creates and saves a job, DOES NOT start job, see submit below.

### Job level fields

| Field        | Default | Required | Description  |
| ------------- |:-------------:|:--- | ----- |
| name    | None | Yes | Human friendly name for this job. |
| paramFile     | None | No |   File with parameter variables. |
| caseFile | None | No |    File with case variables. |
| jobvariables | None | No |    List of job variables for this job. See details below. |
| jobanalyses | None | Yes |    List of analyses for this job. See details below. |
| resourceFilters | Default filters | No | List of filtering rules for output files. |
| isTemplateDryRun | False | No | Run this job in "dry run" mode. |
| includeNominalRun | False | No | Include the run with nominal variables. |
| monteCarloIterations | None | No | Number of iterations in case the variables use a monteCarlo generator type.|

### JobVariables

A job may contain one or more variables. You might find this field
useful in setting up a classic Design of Experiments job with Rescale
platform.

| Field        | Default | Required | Description  |
| ------------- |:-------------:|:--- | ----- |
| name | None | Yes | Name for the the variable. |
| variableType | None | Yes | Options are: 'Param', 'Design', 'Output', 'Case', 'Constraint' & 'Objective'|
| displayOrder | None | Yes | Order in which the variables appear in the Rescale UI |
| variableGeneratorType | None | Yes | Options are: 'Normal', 'Uniform', 'Linspace', 'FixedRange', 'Triangular' & 'LogNormal' |
| valueGeneratorSettings | None | Yes | JSON blob describing the generator |

### JobAnalyses

A job needs at least one analysis. You can use [analyses](#analyses) endpoint
to get a list of current Analyses available on the Rescale platform and
the sample JSON schema for a particular analysis, which could help you
in constructing your JSON blob.

| Field        | Default | Required | Description  |
| ------------- |:-------------:|:--- | ----- |
| analysis | None | Yes | Analysis to use. This field is a JSON blob with schema {"code", "version"}. A GET call to _/api/analyses/_ end point should get you the code for software package you want. "version" is an optional parameter. |
| command | None | Yes | Command to run this analysis with. |
| useMpi | False | No | Whether you want to spin up an mpi cluster. |
| envVars | Empty dict | No | Dictionary of environment variables for this analysis. |
| hardware | None | Yes | Hardware settings for this analysis. Takes a JSON blob with schema {"coreType", "coresPerSlot"}. |
| inputFiles | None | No | List of input files for this analysis. |
| useRescaleLicense | False | No | If the analysis has an option for using a Rescale provided license, set this field to True. |
| templateTasks | None | No | The template file for this analysis. |
| preProcessScript | None | No | Pre-processing script for this analysis. |
| preProcessScriptCommand | None | No | Command to kick off the pre-processing script. |
| postProcessScript | None | No | Post-processing script for this analysis. |
| postProcessScriptCommand | None | No | Command to kick off the post-processing script. |


## Submit a Saved Job

`POST https://platform.rescale.com/api/v2/jobs/{job_id}/submit/`

```shell
curl -H "Authorization: Token <api-token>" https://platform.rescale.com/api/v2/jobs/LeeKa/submit/ -X POST
```

Submits a saved job to run.  No data returned.

## Update a Job

`PUT https://platform.rescale.com/api/v2/jobs/{job_id}`

`PATCH https://platform.rescale.com/api/v2/jobs/{job_id}`

```shell
curl -H "Authorization: Token e95aca40caabf137e71ba11469d7aa304dea4386"  -H "Content-Type:application/json" "https://platform.rescale.com/api/v2/jobs/LeeKa/" -X PATCH -d '
{
    "name": "Jobster"
}
'
```

> Response

```json
{
    "id": "LeeKa",
    "isLowPriority": false,
    "name": "Jobster"
}
```


## Delete a Job

`DELETE https://platform.rescale.com/api/v2/jobs/{job_id}/`

## Stop a Job

`POST https://platform.rescale.com/api/v2/jobs/{job_id/stop/`

## Share a Job

`POST https://platform.rescale.com/api/v2/jobs/{job_id/share/`

## Get the Status History of a Job

`GET https://platform.rescale.com/api/v2/jobs/{job_id}/statuses`

`GET https://platform.rescale.com/api/v2/jobs/{job_id}/cluster_statuses/`

