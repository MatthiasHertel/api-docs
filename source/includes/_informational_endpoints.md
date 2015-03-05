# Informational Endpoints

The Rescale API provides several top-level endpoints that provide
information about options available in the system as a whole.

## Core Types

`GET https://platform.rescale.com/api/coretypes/`

```shell
curl -H "Authorization: Token <api-token>" https://platform.rescale.com/api/coretypes/
```

```python
import requests

requests.get(
  'https://platform.rescale.com/api/coretypes/',
  headers={'Authorization': 'Token <api-token>'}
)
```

> Sample Response

```json
{
  "count":14,
  "previous":null,
  "results":[
    {
      "hasSsd":true,
      "code":"standard-plus",
      "compute":"3.00",
      "name":"Marble",
      "isDeprecated":false,
      "price":0.1,
      "remoteVizAllowed":true,
      "storage":40,
      "lowPriorityPrice":"0.050",
      "walltimeRequired":false,
      "displayOrder":1,
      "io":"Standard",
      "memory":3750,
      "cores":[
        1,
        2,
        4,
        8
      ],
      "isPrimary":true,
      "processorInfo":"Intel Xeon E5-2670 v2 (Ivy Bridge) - single threaded",
      "storageIo":"2 GB/s read, 1GB/s write",
      "description":"Standard"
    },
    {
      "hasSsd":false,
      "code":"test",
      "compute":"1.00",
      "name":"HPC Test",
      "isDeprecated":false,
      "price":0.25,
      "remoteVizAllowed":false,
      "storage":0,
      "lowPriorityPrice":"0.100",
      "walltimeRequired":false,
      "displayOrder":null,
      "io":"",
      "memory":1500,
      "cores":[
        1
      ],
      "isPrimary":false,
      "processorInfo":"",
      "storageIo":"",
      "description":""
    }
  ],
  "next":"https://platform.rescale.com/api/coretypes?page=2"
}
```

This endpoint lists informations on all core types available in the
Rescale API. The `code` property can be used in subsequent requests to
submit jobs.

### Response Properties

Property | Type  | Description
-------- | ------|---------------
hasSsd | boolean | Indicates whether this core type has SSD drives
code | String | A unique identifier for this core type, used in other requests
compute | String | TODO
name | String | The display name
isDeprecated | boolean | Indicates if this core type is deprecated. If true, it cannot be used to submit jobs
price | Decimal | Price per core hour for on-demand jobs
remoteVizAllowed| boolean | Indicates if this coretype can be used for remote visualization clusters
storage| Integer | The amount of per-core storage in GB
lowPriorityPrice | String | The price per core hour for low priority jobs
walltimeRequired |boolean | Indicates if jobs submitted with this core type must specify a maximum walltime
displayOrder | Integer | An integer for sorting core type displays
io | String | Indicates the amount of IO available on this coretype, e.g.  `10 GB/s`
memory | Integer | The amount of per-core memory in MB
cores | Array&lt;Integer&gt; | The number of cores on instances of this core type, with an entry for each instance size
isPrimary | boolean | Indicates if this is a primary (default) core type
processorInfo | String | Processor Information
storageIo | String | Same as `storage`
description | String | A description of this core type

## Analyses

`GET https://platform.rescale.com/api/analyses/`

```shell
curl -H "Authorization: Token <api-token>" https://platform.rescale.com/api/remote-viz-config/
```

```python
import requests

requests.get(
  'https://platform.rescale.com/api/analyses/',
  headers={'Authorization': 'Token <api-token>'}
)
```

> Sample Response

```json
{
  "count":88,
  "previous":null,
  "results":[
    {
      "industries":[
        {
          "name":"Aerospace",
          "icon":null
        },
        {
          "name":"Automotive",
          "icon":null
        }
      ],
      "code":"abaqus",
      "description":"<p><b>Abaqus FEA</b> is a software suite for finite element analysis and computer-aided engineering.  The Abaqus product suite consists of four core software products.  <i>Abaqus/CAE</i>, <i>Abaqus/CFD</i>, <i>Abaqus/Standard</i>, and <i>Abaqus/Explicit</i>.</p><p><i>Abaqus CAE</i> is a software application used for both pre-processing and visualizing finite element analysis results.  <i>Abaqus/CFD</i> provides computational fluid dynamics capabilities, while <i>Abaqus/Standard</i> and <i>Abaqus/Explicit</i> are finite element analyzers that employ implicit and explicit integration schemes, respectively.</p>",
      "versions":[
        {
          "eula":null,
          "allowedCoreTypes":[
            "gpu-kepler",
            "gpu-tesla",
            "hi-io",
            "hi-mem",
            "hi-mem-hpc",
            "hpc",
            "hpc-3",
            "hpc-plus",
            "lo-mem",
            "standard",
            "standard-plus",
            "test"
          ],
          "stdCommand":"abaqus job=<job> interactive",
          "version":"6.14-1",
          "mpiCommand":"abaqus job=<job> cpus=<mpi-ranks> mp_mode=mpi interactive",
          "versionCode":"6.14.1-pcmpi",
          "smpCommand":"abaqus job=<job> cpus=<smp-ranks> interactive"
        },
        {
          "eula":null,
          "allowedCoreTypes":[
            "gpu-kepler",
            "gpu-tesla",
            "hi-io",
            "hi-mem",
            "hi-mem-hpc",
            "hpc",
            "hpc-3",
            "hpc-plus",
            "lo-mem",
            "standard",
            "standard-plus",
            "test"
          ],
          "stdCommand":"abaqus job=<job> interactive",
          "version":"6.13-5",
          "mpiCommand":"abaqus job=<job> cpus=<mpi-ranks> mp_mode=mpi interactive",
          "versionCode":"6.13.5-ibm",
          "smpCommand":"abaqus job=<job> cpus=<smp-ranks> interactive"
        },
        {
          "eula":null,
          "allowedCoreTypes":[
            "gpu-kepler",
            "gpu-tesla",
            "hi-io",
            "hi-mem",
            "hi-mem-hpc",
            "hpc",
            "hpc-3",
            "hpc-plus",
            "lo-mem",
            "standard",
            "standard-plus",
            "test"
          ],
          "stdCommand":"abaqus job=<job> interactive",
          "version":"6.12-1",
          "mpiCommand":"abaqus job=<job> cpus=<mpi-ranks> mp_mode=mpi interactive",
          "versionCode":"6.12.0-ibm",
          "smpCommand":"abaqus job=<job> cpus=<smp-ranks> interactive"
        },
        {
          "eula":null,
          "allowedCoreTypes":[
            "gpu-kepler",
            "gpu-tesla",
            "hi-io",
            "hi-mem",
            "hi-mem-hpc",
            "hpc",
            "hpc-3",
            "hpc-plus",
            "lo-mem",
            "standard",
            "standard-plus",
            "test"
          ],
          "stdCommand":"abaqus job=<job> interactive",
          "version":"6.12-1-asca",
          "mpiCommand":"abaqus job=<job> cpus=<mpi-ranks> mp_mode=mpi interactive",
          "versionCode":"6.12.0-asca",
          "smpCommand":"abaqus job=<job> cpus=<smp-ranks> interactive"
        }
      ],
      "supportDesks":[
        {
          "code":"rescale",
          "displayName":"Rescale Support",
          "email":"support@example.com"
        }
      ],
      "hasRescaleLicense":true,
      "vendorName":"",
      "pricing":"",
      "hasShortTermLicense":false,
      "licenseSettings":[
        {
          "isServer":true,
          "licenseType":"Flex",
          "helpText":"The address of the FlexNet license server to use. ([port]@hostname)",
          "name":"LM_LICENSE_FILE",
          "label":"License"
        },
        {
          "isServer":true,
          "licenseType":"Flex",
          "helpText":"The address of the Autodesk Simulation Composite Analysis License Server [port]@hostname",
          "name":"ADSKFLEX_LICENSE_FILE",
          "label":"ASCA License Server"
        }
      ],
      "optimizerType":null,
      "thumbnail":"/static/img/analyses_images/abaqus.png",
      "resources":[
        {
          "url":"https://www.rescale.com/resources/software/abaqus/example/",
          "name":"Basic Example"
        }
      ],
      "name":"Abaqus"
    }
  ],
  "next":"https://platform.rescale.com/api/analyses/?page=2"
}
```

This endpoint lists all the analyses available on Rescale.

### Response Properties


Property | Type  | Description
-------- | ------|---------------
industries | Array&lt;Object&gt; | The industries this analysis is used by
code | String | A unique identifier for this analysis
description | String | Describes this analysis
versions | Array&lt;Object&gt; | Describes all of the verions available for this analysis
supportDesks | Array&lt;Object&gt; | Describes all the support desks that can provide support for this analysis
vendorName | String | The name of the analysis vendor
pricing | String | The cost of this analysis
hasShortTermLicense | boolean | Indicates if a short term license can be purchased to run this analysis
licenseSettings | Array&lt;Object&gt; | The required license settings for running this analysis
optimizerType | Object | TODO
thumbnail | String | A path to the image used to represent this analsyis
resources | Array&lt;Object&gt; | Tutorial resources for this analysis
name | String | The name of this analysis

#### Analysis Version Properties

Property | Type  | Description
-------- | ------|---------------

#### License Settings Properties

Property | Type  | Description
-------- | ------|---------------




## Remote Visulization Options

`GET https://platform.rescale.com/api/remote-viz-config/`

This endpoint lists the options for creating a remote visualization
cluster on rescale

```shell
curl -H "Authorization: Token <api-token>" https://platform.rescale.com/api/remote-viz-config/
```

```python
import requests

requests.get(
  'https://platform.rescale.com/api/remote-viz-config/',
  headers={'Authorization': 'Token <api-token>'}
)
```

> Sample Response

```json
{
  "count":4,
  "previous":null,
  "results":[
    {
      "code":"4-cores-hpc-plus",
      "displayName":"4 Cores HPC+",
      "price":0.15,
      "coreTypeCode":"hpc-plus",
      "cores":4,
      "isWindows":false
    },
    {
      "code":"8-cores-gpu-kepler",
      "displayName":"8 Cores GPU Kepler",
      "price":0.12,
      "coreTypeCode":"gpu-kepler",
      "cores":8,
      "isWindows":false
    },
    {
      "code":"2-cores-hpc-plus-windows",
      "displayName":"2 Cores HPC+ Windows",
      "price":0.15,
      "coreTypeCode":"hpc-plus",
      "cores":2,
      "isWindows":true
    },
    {
      "code":"8-cores-gpu-kepler-windows",
      "displayName":"8 Cores GPU Kepler Windows",
      "price":0.12,
      "coreTypeCode":"gpu-kepler",
      "cores":8,
      "isWindows":true
    }
  ],
  "next":null
}
```

### Response Properties


Property | Type  | Description
-------- | ------|---------------
code | String | A unique identifier for this remote visualization option, to be used in other requests
displayName | String | The display name for this configuration
price | Decimal | The price per hour of a remote visualization cluster with this option
coreTypeCode | String | The code of the [core type](#core-types) used by this remote visualization option
cores | Integer | The number of cores on instances created by this remote viusalization option
isWindows | boolean | Indicates if instances are windows machines

