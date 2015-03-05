# Runs

A single execution of your workflow is called a *run* in Rescale parlance.

## List Runs for a Job

`GET https://platform.rescale.com/api/jobs/{job_id}/runs/`

## Get a Run

`GET https://platform.rescale.com/api/jobs/{job_id}/runs/{run_id}/`

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

