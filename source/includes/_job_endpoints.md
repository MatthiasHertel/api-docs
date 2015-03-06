# Jobs

## List All Jobs

`GET https://platform.rescale.com/api/jobs/`

```shell
curl -H "Authorization: Token <api-token>" https://platform.rescale.com/api/jobs/
```

```python
import requests

requests.get(
  'https://platform.rescale.com/api/jobs/',
  headers={'Authorization': 'Token <api-token>'}
)
```

> Sample Response

```json
{
  "count":347,
  "previous":null,
  "results":[
    {
      "clusterStatusDisplay":{
        "content":"Stopped",
        "labelClass":"",
        "useLabel":false
      },
      "dateInserted":"2015-03-04T00:41:02.194615Z",
      "name":"Untitled Job",
      "analysisNames":[
        "Custom User-Defined Software"
      ],
      "storage":86,
      "jobStatus":{
        "content":"Completed",
        "labelClass":"",
        "useLabel":false
      },
      "sharedWith":[

      ],
      "isVisible":true,
      "owner":"owner@example.com",
      "id":"FtFSc"
    },
    {
      "clusterStatusDisplay":{
        "content":"Started",
        "labelClass":"label-success",
        "useLabel":true
      },
      "dateInserted":"2015-03-03T03:06:14.902048Z",
      "name":"LS-Dyna (Cloned)",
      "analysisNames":[
        "LS-DYNA"
      ],
      "storage":0,
      "jobStatus":{
        "content":"Executing",
        "labelClass":"label-success",
        "useLabel":true
      },
      "sharedWith":[
        "recipient@example.com"
      ],
      "isVisible":true,
      "owner":"owner@example.com",
      "id":"KDFSc"
    }
  ],
  "next":"https://platform.rescale.com/api/jobs/?page=2"
}
```

This endpoint retrieves all the jobs visible to the authenticated user
(you), whether they are owned by that user or shared with that user.

### Response Properties

Property | Type  | Description
-------- | ------|---------------
clusterStatusDisplay | Object  | Describes the current status of the job's clusters
dateInserted | String | The date this job was created
name | String | The name of this job
analysisNames | Array&lt;String&gt; | The names all the analyses being run for the job
jobStatus | Object | Describes the current status of the job
sharedWith | Array&lt;String&gt; | Email addresses of the users this job has been shared with
isVisible | boolean | TODO: Can this ever be false in the output?!
owner | String | The email address of the owner of the job
id | String | A unique identifier for the job

## Get a Specific Job

`GET https://platform.rescale.com/api/jobs/{job_id}/`

## List Job Output Files

`GET https://platform.rescale.com/api/jobs/{job_id}/files/`

## Create a Job

`POST https://platform.rescale.com/api/jobs/`

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

`POST https://platform.rescale.com/api/jobs/{job_id}/submit/`

## Update a Job

`PUT https://platform.rescale.com/api/jobs/{job_id}`

`PATCH https://platform.rescale.com/api/jobs/{job_id}`


## Delete a Job

`DELETE https://platform.rescale.com/api/jobs/{job_id}/`

## Stop a Job

`POST https://platform.rescale.com/api/jobs/{job_id/stop/`

## Share a Job

`POST https://platform.rescale.com/api/jobs/{job_id/share/`

## Get the Status History of a Job

`GET https://platform.rescale.com/api/jobs/{job_id}/statuses`

`GET https://platform.rescale.com/api/jobs/{job_id}/cluster_statuses/`

