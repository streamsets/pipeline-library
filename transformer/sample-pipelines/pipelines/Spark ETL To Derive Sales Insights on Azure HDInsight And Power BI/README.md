Spark ETL To Derive Sales Insights on Azure HDInsight And Power BI
==================================================================

This StreamSets Transformer pipeline runs on Apache Spark for Azure HDInsight cluster to extract raw data and transform it (cleanse and curate) before storing it in multiple destinations for efficient downstream analysis. The pipeline also uses technologies like Azure Data Lake Storage (ADLS) Gen2 and Azure SQL database, and the curated data is queried and visualized in Power BI.

Prerequisites
---------------------

* [StreamSets Transformer](https://streamsets.com/products/dataops-platform/transformer-etl/) 3.14.0 or higher. You can [deploy Transformer](https://streamsets.com/products/dataops-platform/transformer-etl/download/) on your choice of **cloud provider** or **download** it for local development.
* Access to Apache Spark for Azure HDInsight cluster 
* Access to ADLS Gen2 storage
* Access to Azure SQL database

Setup
---------------------

* [Download and import the pipeline](https://github.com/iamontheinet/pipeline-library/blob/master/transformer/sample-pipelines/pipelines/SalesInsightsOnAzureSQLHDInsight37efd28a-9c98-494b-85bd-c6fd8a85af10.json) into your instance of Transformer
* [Download the sample sales dataset](https://github.com/iamontheinet/pipeline-library/blob/master/transformer/sample-pipelines/pipelines/dataset/) and upload it to your ADLS Gen2 storage
* After importing the pipeline into your environment and before running the pipeline, update the following pipeline parameters:

```
[
  {
    "key": "HD_LIVY_ENDPOINT",
    "value": ""
  },
  {
    "key": "HD_STAGING",
    "value": ""
  },
  {
    "key": "HD_USER",
    "value": ""
  },
  {
    "key": "HD_PASSWORD",
    "value": ""
  },
  {
    "key": "ADLS_STORAGE_ACCOUNT",
    "value": ""
  },
  {
    "key": "ADLS_FILESYSTEM_CONTAINER",
    "value": ""
  },
  {
    "key": "ADLS_SHARED_KEY",
    "value": ""
  },
  {
    "key": "AZURE_SQL_URL",
    "value": ""
  },
  {
    "key": "ADLS_GEN2_SOURCE_PATH",
    "value": ""
  },
  {
    "key": "AZURE_SQL_DB",
    "value": ""
  },
  {
    "key": "AZURE_SQL_DB_USER",
    "value": ""
  },
  {
    "key": "AZURE_SQL_DB_PWD",
    "value": ""
  },
  {
    "key": "AZURE_SQL_DB_TABLE",
    "value": ""
  },
  {
    "key": "ADLS_GEN2_DESTINATION_PATH",
    "value": ""
  },
  {
    "key": "ADLS_GEN2_DESTINATION_PARTITION",
    "value": ""
  }
]

```

These pipeline parameter are used by various stages in the pipleine, such as, HDInsight cluster details, ADLS Gen2 information for loading raw/source data and also to store clean data, Azure SQL database and credentials for storing curated data, etc.

Technical Details
------------------------------

For techincal information, detailed explanation of this use case and to see how the curated data in Azure SQL is analyzed in Power BI, read this [blog](https://bit.ly/SparkETLonHDInsight).

