# Files

All file related operations are listed here.

## List all Files

`GET https://platform.rescale.com/api/files/`

```shell
curl -X GET -H 'Authorization: Token \<token\>'
https://platform.rescale.com/api/files/
```

```python
import requests

requests.get(
  'https://platform.rescale.com/api/files/',
  headers={'Authorization': 'Token <api-token>'}
)
```

> Sample Response

```json
{
    "count": 365,
    "previous": null,
    "results": [
        {
            "typeId": 1,
            "name": "Crash_input.pc.gz",
            "dateUploaded": "2015-03-12T17:56:20.925043-07:00",
            "relativePath": "Crash_input.pc.gz",
            "encodedEncryptionKey": "LkkPk2L2mwuc4OibUs3kJe2RIQrzXbfdWXp9xJhoX0s=",
            "downloadUrl": "https://platform.rescale.com/api/files/WvNKdb/contents/",
            "sharedWith": [],
            "decryptedSize": 56425931,
            "owner": "demouser@rescale.com",
            "path": "user/user_OvdRk/Crash_input.pc.gz-0a87694a180172023d8a37f0c8aac965",
            "isUploaded": true,
            "viewInBrowser": false,
            "id": "WvNKdb",
            "isDeleted": false,
            "md5": "a3bc423552cf5457b2fcf4fad87e451d"
        },
        {
            "typeId": 5,
            "name": "fsi.in",
            "dateUploaded": "2015-01-27T11:06:57.418023-08:00",
            "relativePath": "fsi.in",
            "encodedEncryptionKey": "MQfYDI0UttkgN+N2K71N0/nodyTZi/GjNY1z/Jnmh88=",
            "downloadUrl": "https://platform.rescale.com/api/files/oHyEm/contents/",
            "sharedWith": [
                "shareduser@rescale.com"
            ],
            "decryptedSize": 2744,
            "owner": "demouser@rescale.com",
            "path": "user/user_OvdRk/output/job_RJFSc/run1/fsi.in",
            "isUploaded": true,
            "viewInBrowser": true,
            "id": "oHyEm",
            "isDeleted": false,
            "md5": "2deba2076c80c89e96749e58a26c0d99"
        },
        {
            "typeId": 5,
            "name": "post.echo",
            "dateUploaded": "2015-01-27T11:06:57.310163-08:00",
            "relativePath": "post.echo",
            "encodedEncryptionKey": "wmB+YNh2IDdZURd79NJjOiAnAGxl8mzPVlwS8kLPGnc=",
            "downloadUrl": "https://platform.rescale.com/api/files/ZeFSa/contents/",
            "sharedWith": [
                "shareduser@rescale.com"
            ],
            "decryptedSize": 248,
            "owner": "demouser@rescale.com",
            "path": "user/user_OvdRk/output/job_RJFSc/run1/post.echo",
            "isUploaded": true,
            "viewInBrowser": true,
            "id": "ZeFSa",
            "isDeleted": false,
            "md5": "6796616b942ff5eaa5b68041871b4a0b"
        },
        {
            "typeId": 5,
            "name": "therm.dat",
            "dateUploaded": "2015-01-27T11:06:57.205175-08:00",
            "relativePath": "therm.dat",
            "encodedEncryptionKey": "eQ2twVf8T8J+/lwK7FQNa2Q2PROzlTj2DIyeUPTnuW8=",
            "downloadUrl": "https://platform.rescale.com/api/files/XgpAm/contents/",
            "sharedWith": [
                "shareduser@rescale.com"
            ],
            "decryptedSize": 201624,
            "owner": "demouser@rescale.com",
            "path": "user/user_OvdRk/output/job_RJFSc/run1/therm.dat",
            "isUploaded": true,
            "viewInBrowser": true,
            "id": "XgpAm",
            "isDeleted": false,
            "md5": "d133bafb80e2ebd460efd6cf13f0c42b"
        },
        {
            "typeId": 5,
            "name": "inputs.in",
            "dateUploaded": "2015-01-27T11:06:57.103260-08:00",
            "relativePath": "inputs.in",
            "encodedEncryptionKey": "4FY1kB/Ejq9r3n+Jz1um7yS+F/rXskAzlnDWFABr1HM=",
            "downloadUrl": "https://platform.rescale.com/api/files/JEvOa/contents/",
            "sharedWith": [
                "shareduser@rescale.com"
            ],
            "decryptedSize": 13959,
            "owner": "demouser@rescale.com",
            "path": "user/user_OvdRk/output/job_RJFSc/run1/inputs.in",
            "isUploaded": true,
            "viewInBrowser": true,
            "id": "JEvOa",
            "isDeleted": false,
            "md5": "a5d397df07e6b435d5d1f26eb9ebd4b2"
        },
        {
            "typeId": 5,
            "name": "process_output.log",
            "dateUploaded": "2015-01-27T11:06:57.006959-08:00",
            "relativePath": "process_output.log",
            "encodedEncryptionKey": "haLrcqy/ePGyy7mJjr1J2ApBRQlEaH1UKvB49tNaflE=",
            "downloadUrl": "https://platform.rescale.com/api/files/LWoAm/contents/",
            "sharedWith": [
                "shareduser@rescale.com"
            ],
            "decryptedSize": 1262,
            "owner": "demouser@rescale.com",
            "path": "user/user_OvdRk/output/job_RJFSc/run1/process_output.log",
            "isUploaded": true,
            "viewInBrowser": true,
            "id": "LWoAm",
            "isDeleted": false,
            "md5": "7f2b5ba96aa67cb067193b2e44cbd91d"
        },
        {
            "typeId": 5,
            "name": "post.in",
            "dateUploaded": "2015-01-27T11:06:56.901907-08:00",
            "relativePath": "post.in",
            "encodedEncryptionKey": "TRHGVF0LrDgJ+x6x/hzwYKG34ITfGWTvlhs2a/n1FP0=",
            "downloadUrl": "https://platform.rescale.com/api/files/wuvOa/contents/",
            "sharedWith": [
                "shareduser@rescale.com"
            ],
            "decryptedSize": 593,
            "owner": "demouser@rescale.com",
            "path": "user/user_OvdRk/output/job_RJFSc/run1/post.in",
            "isUploaded": true,
            "viewInBrowser": true,
            "id": "wuvOa",
            "isDeleted": false,
            "md5": "4fdf0c787bd84d4b4b6bf7bf35df1690"
        },
        {
            "typeId": 5,
            "name": "restart0001.rst",
            "dateUploaded": "2015-01-27T11:06:56.801151-08:00",
            "relativePath": "restart0001.rst",
            "encodedEncryptionKey": "iHom7vaSMIVItK0RX1s+gLb6z+vxMn3MwKMLSjvkeCY=",
            "downloadUrl": "https://platform.rescale.com/api/files/VgpAm/contents/",
            "sharedWith": [
                "shareduser@rescale.com"
            ],
            "decryptedSize": 625449464,
            "owner": "demouser@rescale.com",
            "path": "user/user_OvdRk/output/job_RJFSc/run1/restart0001.rst",
            "isUploaded": true,
            "viewInBrowser": false,
            "id": "VgpAm",
            "isDeleted": false,
            "md5": "61a8a7e517ee579d329f7ce56b865e97"
        },
        {
            "typeId": 5,
            "name": "dynamic.out",
            "dateUploaded": "2015-01-27T11:06:56.703897-08:00",
            "relativePath": "dynamic.out",
            "encodedEncryptionKey": "213UMp+Rp2+d6wPzDCxge4X9pV9sIAYft+6WgdAq29M=",
            "downloadUrl": "https://platform.rescale.com/api/files/GEvOa/contents/",
            "sharedWith": [
                "shareduser@rescale.com"
            ],
            "decryptedSize": 14226,
            "owner": "demouser@rescale.com",
            "path": "user/user_OvdRk/output/job_RJFSc/run1/dynamic.out",
            "isUploaded": true,
            "viewInBrowser": true,
            "id": "GEvOa",
            "isDeleted": false,
            "md5": "82116340362aba67bb0c3b58d4ced65f"
        },
        {
            "typeId": 5,
            "name": "equiv_ratio_bin.out",
            "dateUploaded": "2015-01-27T11:06:56.602278-08:00",
            "relativePath": "equiv_ratio_bin.out",
            "encodedEncryptionKey": "hJ2qEY9k5PiVXyAlxHZt4/Qwv3xXWygKefer9Kn23wE=",
            "downloadUrl": "https://platform.rescale.com/api/files/JWoAm/contents/",
            "sharedWith": [
                "shareduser@rescale.com"
            ],
            "decryptedSize": 37210,
            "owner": "demouser@rescale.com",
            "path": "user/user_OvdRk/output/job_RJFSc/run1/equiv_ratio_bin.out",
            "isUploaded": true,
            "viewInBrowser": true,
            "id": "JWoAm",
            "isDeleted": false,
            "md5": "1a2a0b8b3879726b9035cdd1b9308fd9"
        }
    ],
    "next": "https://platform.rescale.com/api/files/?page=2"
}
```

This call allows you to retrieve the first page of files owned by the
current user.


### Response Properties

Property | Type  | Description
-------- | ------|---------------
count | Integer | The total number of files owned by the current user.
next | String | The URL that will return the next page of results.  
previous | String | The URL that will return the previous page of results
results | Array&lt;Object&gt; | An array of [File objects](#get-metadata-of-a-file)

## Upload a File

`PUT/POST https://platform.rescale.com/api/files/contents/`

```shell
curl -X POST -H 'Content-Type:multipart/form-data' 
-H 'Authorization: Token \<token\>' 
-F 'file=@file_to_upload.txt' 
https://platform.rescale.com/api/files/contents/
```

```python
import requests

# Simple input file upload

requests.post(
  'https://platform.rescale.com/api/files/contents/',
  headers={'Authorization': 'Token \<token\>'},
  files={'file': open('file_to_upload.txt', 'rb')}
)


# Upload with new file name and different file type

type_id = 1  # file type
new_name = 'new_file.txt'  #  new file name

requests.post(
  'https://platform.rescale.com/api/files/contents/',
  headers={'Authorization': 'Token \<token\>'},
  files={'file': (new_name, open('file_to_upload.txt', 'rb'), {'type_id': type_id})}
)
```

> Sample Response

```json
{
    "typeId": 1,
    "name": "testInput.txt",
    "dateUploaded": "2015-03-16T19:43:21.679246Z",
    "relativePath": "testInput.txt",
    "encodedEncryptionKey": "j/nYgAlnGIywZHyDwwzv+FxYVIlmKveMkY7qxAOuRhY=",
    "downloadUrl": "https://platform.rescale.com/api/files/iCdseg/contents/",
    "sharedWith":[],
    "decryptedSize":22,
    "owner": "demouser@rescale.com",
    "path": "user/user_OvdRk/testInput-e034314d-2c8e-432a-9c28-079bfbd8bcdd.txt",
    "isUploaded":true,
    "viewInBrowser":true,
    "id": "iCdseg",
    "isDeleted":false,
    "md5": "cf78c029dc496e9c789db1463a4a84de"
}
```

This call allows you to upload a file from local file system to
Rescale platform.


### Response Properties

Same as [Get Metadata of a File](#get-metadata-of-a-file)


## Delete a File

`DELETE https://platform.rescale.com/api/files/{file_id}/`

```shell
curl -X DELETE -H 'Authorization: Token \<token\>' 
https://platform.rescale.com/api/files/{file_id}/
```

```python
import requests

requests.delete(
  'https://platform.rescale.com/api/files/{file_id}/',
  headers={'Authorization': 'Token \<token\>'}
)
```

> Sample Response

Response has no content if delete is successful.

This call allows you to delete a file from Rescale platform.

### Response Properties

N/A

## Download a File

`GET https://platform.rescale.com/api/files/{file_id}/contents/`

```shell
curl -X GET -H 'Authorization: Token \<token\>' 
-o 'download_file.txt' https://platform.rescale.com/api/files/{file_id}/contents/
```

```python
import requests

response = requests.get(
  'https://platform.rescale.com/api/files/{file_id}/',
  headers={'Authorization': 'Token \<token\>'}
)

with open('file_to_download', 'wb') as fd:
    for chunk in response.iter_content(chunk_size):
        fd.write(chunk)
```

> Sample Response

The response of the content is the content of the file.

### Response Properties

N/A


This call allows you to download a file from Rescale platform.

## Get Plaintext Content of a File

`GET https://platform.rescale.com/api/files/{file_id}/lines/`

```shell
curl -X GET -H 'Authorization: Token \<token\>'
https://platform.rescale.com/api/files/{file_id}/lines/
```

```python
import requests

requests.get(
  'https://platform.rescale.com/api/files/{file_id}/lines',
  headers={'Authorization': 'Token <api-token>'}
)
```

> Sample Response

```json
{
    "lines": [
        "This is line 1.\n",
        "This is line 2.\n",
        "This is line 3.\n",
        "This is line 4.\n",
        "This is line 5.\n"]
}
```

### Response Properties

Property | Type  | Description
-------- | ------|---------------
lines | List&lt;String&gt; | A list of strings of the file.


This call allows you to retrieve the file contents in lines for a
plain text file.

## Get Metadata of a File

`GET https://platform.rescale.com/api/files/{file_id}/`

```shell
curl -X GET -H 'Authorization: Token \<token\>'
https://platform.rescale.com/api/files/{file_id}/
```

```python
import requests

requests.get(
  'https://platform.rescale.com/api/files/{file_id}/',
  headers={'Authorization': 'Token <api-token>'}
)
```

> Sample Response

```json
{
    "typeId": 1, 
    "name": "Crash_input.pc.gz", 
    "dateUploaded": "2015-03-12T17:56:20.925043-07:00", 
    "relativePath": "Crash_input.pc.gz", 
    "encodedEncryptionKey": "LkkPk2L2mwuc4OibUs3kJe2RIQrzXbfdWXp9xJhoX0s=", 
    "downloadUrl": "https://platform.rescale.com/api/files/WvNKdb/contents/", 
    "sharedWith": [], 
    "decryptedSize": 56425931, 
    "owner": "demouser@rescale.com", 
    "path": "user/user_OvdRk/Crash_input.pc.gz-0a87694a180172023d8a37f0c8aac965", 
    "isUploaded": true, 
    "viewInBrowser": false, 
    "id": "WvNKdb", 
    "isDeleted": false, 
    "md5": "a3bc423552cf5457b2fcf4fad87e451d"
}
```

### Response Properties

Property | Type  | Description
-------- | ------|---------------
typeId | Integer | 1 = inpute file, 2 = template file, 3 = parameter file, 4 = script file, 5 = output file, 7 = design variable file, 8 = case file, 9 = optimizer file, 10 = temporary file
name | String | The name of the file.
dateUploaded | String | The ISO8601 encoded date of when the file is uploaded.
relativePath | String | For output files (typeId = 5), the relative path is the path relative to the root output folder(user/{user_id}/output/{job_id}/{run_id}/{relative_path}).
encodedEncryptionKey | String | The key used to encrypt the files.
downloadUrl | String | The download URL of the file.
sharedWith | List&lt;String&gt; | A list of users of the file shared with.
decryptedSize | Integer | The decrypted file size in byte.
owner | String | The owner of the file.
path | String | The absolute path of the file being stored.
isUploaded | Boolean | If the file is already uploaded.
viewInBrowser | Boolean | If the file can be viewed in browser.
id | String | The unique identifier of the file.
isDelelted | Boolean | If the file is already deleted.
md5 | String | The md5 hash of the file.


This call allows you to retrieve details for a single file.

## Update Metadata of a File

`PATCH https://platform.rescale.com/api/files/{file_id}/`

```shell
curl -X PATCH -H 'Content-Type: application/json'
-H 'Authorization: Token \<token\>' --data 
'{
    "typeId": 4,
    "name": "new_script.txt",
    "dateUploaded": "2015-03-17T00:24:39.531384Z",
    "relativePath": "new_script.txt",
    "encodedEncryptionKey": "83TFwNf5QxFaCOmluBQBnJ/L0yAC/2Z9MPs2pKZuUi4=",
    "downloadUrl": "https://platform.rescale.com/api/files/dNEXtf/contents/",
    "sharedWith": [],
    "decryptedSize": 112,
    "owner": "demouser@rescale.com",
    "path": "user/user_OvdRk/testLines-9425c8a5-08a6-4249-939a-2f060a4d0f25.txt",
    "isUploaded": true,
    "viewInBrowser": true,
    "id": "dNEXtf",
    "isDeleted": false,
    "md5": "4d479b49d26318068d3e23aa9d81e9ee"
}'
https://platform.rescale.com/api/files/{file_id}/
```

```python
import requests

requests.patch(
  'https://platform.rescale.com/api/files/{file_id}/',
  {
    "typeId": 4,
    "name": "new_script.txt",
    "dateUploaded": "2015-03-17T00:24:39.531384Z",
    "relativePath": "new_script.txt",
    "encodedEncryptionKey": "83TFwNf5QxFaCOmluBQBnJ/L0yAC/2Z9MPs2pKZuUi4=",
    "downloadUrl": "https://platform.rescale.com/api/files/dNEXtf/contents/",
    "sharedWith": [],
    "decryptedSize": 112,
    "owner": "demouser@rescale.com",
    "path": "user/user_OvdRk/testLines-9425c8a5-08a6-4249-939a-2f060a4d0f25.txt",
    "isUploaded": true,
    "viewInBrowser": true,
    "id": "dNEXtf",
    "isDeleted": false,
    "md5": "4d479b49d26318068d3e23aa9d81e9ee"
  },
  headers={'Authorization': 'Token <api-token>'}
)
```

> Sample Response

```json
{
    "typeId": 4,
    "name": "new_script.txt",
    "dateUploaded": "2015-03-17T00:24:39.531384Z",
    "relativePath": "new_script.txt",
    "encodedEncryptionKey": "83TFwNf5QxFaCOmluBQBnJ/L0yAC/2Z9MPs2pKZuUi4=",
    "downloadUrl": "https://platform.rescale.com/api/files/dNEXtf/contents/",
    "sharedWith": [],
    "decryptedSize": 112,
    "owner": "demouser@rescale.com",
    "path": "user/user_OvdRk/testLines-9425c8a5-08a6-4249-939a-2f060a4d0f25.txt",
    "isUploaded": true,
    "viewInBrowser": true,
    "id": "dNEXtf",
    "isDeleted": false,
    "md5": "4d479b49d26318068d3e23aa9d81e9ee"
}
```

### Response Properties

Same as [Get Metadata of a File](#get-metadata-of-a-file)


This call allows you to update meta data of an exiting file.
