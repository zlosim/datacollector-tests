<!---
  Licensed under the Apache License, Version 2.0 (the "License");
  you may not use this file except in compliance with the License.
  You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

  Unless required by applicable law or agreed to in writing, software
  distributed under the License is distributed on an "AS IS" BASIS,
  WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
  See the License for the specific language governing permissions and
  limitations under the License. See accompanying LICENSE file.
--->

[StreamSets](http://streamsets.com)
=================

This project hosts tests for StreamSets Data Collector.

Documentation
-----------
For full documentation, including installation, quickstart examples of tests and API documentation, please see [Docs](https://jenkins.streamsets.net/job/testframework-Docs-Build/Test_Framework_Docs/).

Folder structure for tests
----------------------

```
datacollector-tests
├── Dockerfile
├── LICENSE
├── README.md
├── pipeline
│   ├── pipelines
│   │   ├── multitable_jdbc_to_hive_replication.json
│   │   └── pipeline_1.json
│   ├── test_jdbc_multitable_consumer.py
│   └── test_pipelines.py
├── stage
│   ├── test_cdh_stages.py
│   └── test_jdbc_stages.py
└── upgrade
    ├── pipelines
    │   ├── sdc_1.1.0
    │   │   ├── AmazonS3_trash
    │   │   │   └── sdc_1.1.0_pipeline_AmazonS3_trash.json
    │   │   ├── Dev_Data_Trash
    │   │       └── sdc_1.1.0_pipeline_Dev_Data_Trash.json
    │   ├── sdc_2.1.0.0
    │   │   ├── AmazonS3_Trash
    │   │   │   └── sdc_2.1.0.0_pipeline_AmazonS3_Trash.json
    │   │   ├── DevDataGenerator_Trash
    │   │       └── sdc_2.1.0.0_pipeline_DevDataGenerator_Trash.json
    │   └── sdc_2.2.0.0
    │       ├── AmazonS3_Trash
    │           └── sdc_2.2.0.0_pipeline_AmazonS3_Trash.json
    └── test_pipelines_upgrade.py
```

+ **pipeline/** - This folder contains Python modules to test StreamSets Data Collector (SDC).
            These tests cater to end-to-end scenarios for pipelines already created in SDC.
            e.g. single or multithreaded pipelines.

+ **pipeline/pipelines/** - This folder contains JSON files defining the pipelines which are required by tests in folder /pipeline.
            To generate these JSON files, pipelines under test are created using SDC and exported as JSON files.

+ **stage/** - This folder contains Python modules to test a stage in SDC.
            The tests generate the pipeline under test using pipeline templates and stage definitions from SDC.

+ **upgrade/** - This folder contains Python modules to test SDC pipeline upgrades.

+ **upgrade/pipelines/** - This folder contains JSON files defining the pipelines which are required by tests in folder /upgrade.
            To generate these JSON files, pipelines under test are created using SDC and exported as JSON files.

Contributing code
-----------
We welcome contributors! We are working on adding contents to this area.
