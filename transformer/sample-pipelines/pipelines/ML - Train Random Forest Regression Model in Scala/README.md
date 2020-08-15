Train Random Forest Regression Model in Scala
=======================================================================

This StreamSets Transformer pipeline runs on Databricks cluster. It is designed to train a Spark MLlib Random Forest Regression model using Scala processor. The model is trained to predict sales (== number of units sold) based on advertising budgets allocated to TV, Radio and Newspapers media channels.

Prerequisites
---------------------

* [StreamSets Transformer](https://streamsets.com/products/dataops-platform/transformer-etl/) 3.14.0 or higher. You can [deploy Transformer](https://streamsets.com/products/dataops-platform/transformer-etl/download/) on your choice of **cloud provider** or **download** it for local development.
* Access to Databricks cluster

Setup
---------------------

* [Download and import the pipeline](TrainRandomForestRegressionModelScalaDB28582ef8-fecf-4fa8-94d1-1a58d803153d.json) into your instance of Transformer
* [Download the sample dataset](dataset)
* After importing the pipeline into your environment and before running the pipeline, update the following pipeline parameters:

```
[
  {
    "key": "DB_URL",
    "value": ""
  },
  {
    "key": "DB_TOKEN",
    "value": ""
  },
  {
    "key": "DB_CLUSTER_ID",
    "value": ""
  },
  {
    "key": "STAGING",
    "value": ""
  },
  {
    "key": "SOURCE_DATA_LOCATION",
    "value": ""
  }
  {
    "key": "OUTPUT_DATA_LOCATION",
    "value": ""
  }
]
```

These pipeline parameters refer to the Databricks URL, Databricks token, Databricks cluster Id and location of source dataset as well as output file location.

Technical Details
------------------------------

For techincal information and detailed explanation of this use case, read this [blog](https://bit.ly/TrainRFModel).
