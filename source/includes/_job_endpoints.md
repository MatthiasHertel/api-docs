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

## List the Output Files for a Job

`GET https://platform.rescale.com/api/jobs/{job_id}/files/`

## Create a Job

`POST https://platform.rescale.com/api/jobs/`

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

