---
title: Rescale API Reference

language_tabs:
  - shell:
      cURL
  - python

toc_footers:
  - <a href='https://rescale.com/signup'>Sign Up for Rescale</a>
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - informational_endpoints
  - job_endpoints
  - run_endpoints
  - file_endpoints
  - task_endpoints
  - examples

search: true
---

# Introduction

Welcome to the Rescale REST API! Using the API you can upload input files, create jobs, and view the status of existing jobs.
This documentation inludes examples using cURL and python. The python examples use [requests](https://docs.python-requests.org/en/latest/) for https.

All request paths must include the trailing slash (e.g. `/api/jobs/` instead of `/api/jobs`)

## Authentication

The Rescale API uses authentication tokens to authentication each request. The API requires all
requests to be authenticated by passing an https header of the form:

`Authorization: Token <api-token>`

<aside class="notice">
  Replace &lt;api-token&gt; with the value of your api token.
</aside>

If you don't have an api key, you can generate one [here](https://platform.rescale.com/user/settings/api-key/).

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

## Pagination

```shell
curl -H "Authorization: Token <api-token>" "https://platform.rescale.com/api/jobs/?page_size=2&page=4"
```

```python
import requests

requests.get(
  'https://platform.rescale.com/api/jobs/',
  params={'page_size': 2, 'page': 4},
  headers={'Authorization': 'Token <api-token>'}
)
```
```json
{
  "count":123,
  "prev":null,
  "results": [

  ],
  "next":"https://platform.rescale.com/api/jobs/?page_size=2&page=5"
}
```

All API requests for lists of objects will return paginated results. The `page`
and `page_size` query parameters can be used to control pagination.



Some info about `page_size` and `page` parameters here