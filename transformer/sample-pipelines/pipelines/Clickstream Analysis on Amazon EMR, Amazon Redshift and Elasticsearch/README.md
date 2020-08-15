Clickstream Analysis on Amazon EMR, Amazon Redshift and Elasticsearch
=======================================================================

This StreamSets Transformer pipeline runs on Apache Spark deployed on an Amazon EMR cluster and it's designed to perform clickstream analysis. It ingests raw clickstream logs from Amazon S3, perform aggregations and store those on Amazon Redshift for analysis and the pipeline also sends raw logs to Elasticsearch for querying and quick visualizations. 

Prerequisites
---------------------

* [StreamSets Transformer](https://streamsets.com/products/dataops-platform/transformer-etl/) 3.14.0 or higher. You can [deploy Transformer](https://streamsets.com/products/dataops-platform/transformer-etl/download/) on your choice of **cloud provider** or **download** it for local development.
* Access to Amazon EMR with Spark cluster 
    * Ensure the [prerequisites](https://streamsets.com/documentation/transformer/latest/help/transformer/Clusters/EMR.html#concept_yjs_gzt_vkb) for Amazon EMR are satisfied
* Access to Amazon S3
* Access to Amazon Redshift cluster

Setup
---------------------

* [Download and import the pipeline](ClickstreamLogsToESRedshiftEMRfe856fed-ca84-4689-88d1-432f6ae8e6cd:iamontheinet.json) into your instance of Transformer
* [Download the sample dataset](Schematic_Log.csv) and upload it to your Amazon S3 bucket
* After importing the pipeline into your environment and before running the pipeline, update the following pipeline parameters:

```
[
  {
    "key": "EMR_STAGING",
    "value": ""
  },
  {
    "key": "EMR_CLUSTER_ID",
    "value": ""
  },
  {
    "key": "AWS_DATA_BUCKET",
    "value": ""
  },
  {
    "key": "ES_URL",
    "value": ""
  },
  {
    "key": "REDSHIFT_ENDPOINT",
    "value": ""
  },
  {
    "key": "AWS_TEMP_BUCKET",
    "value": ""
  },
  {
    "key": "ES_INDEX",
    "value": ""
  },
  {
    "key": "REDSHIFT_USER",
    "value": ""
  },
  {
    "key": "REDSHIFT_SCHEMA",
    "value": ""
  }
]

```

These pipeline parameter are used by various stages in the pipleine, such as, Amazon S3 buckets, Amazon Redshift endpoint and credentials, Elasticsearch URL and index name, etc.

Technical Details & Demo Video
------------------------------

For techincal info, detailed explanation of this use case and to watch demo video, read this [blog](https://bit.ly/EMRRedshiftES).
