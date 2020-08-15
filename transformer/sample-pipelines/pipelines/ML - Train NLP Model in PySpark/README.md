Train Natural Language Processing Model using PySpark
=======================================================================

This StreamSets Transformer pipeline runs on Databricks cluster. It is designed to train a Spark MLlib Logistic Regression model for Natural Language Processing (NLP) using PySpark processor. The model is trained to classify given tweet as a *positive* or *negative* sentiment.

Prerequisites
---------------------

* [StreamSets Transformer](https://streamsets.com/products/dataops-platform/transformer-etl/) 3.14.0 or higher. You can [deploy Transformer](https://streamsets.com/products/dataops-platform/transformer-etl/download/) on your choice of **cloud provider** or **download** it for local development.
* Access to Databricks cluster 
    * Ensure the PySpark [prerequisites](https://streamsets.com/documentation/transformer/latest/help/transformer/Processors/PySpark.html#concept_ok3_bd2_qkb) are satisfied

Setup
---------------------

* [Download and import the pipeline](TrainNLPModelPySparkDB787ba4f1-dcb1-4d53-ab61-d80569daac14.json) into your instance of Transformer
* [Download the sample datasets](dataset)
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
    "key": "POSITIVE_TWEETS_LOCATION",
    "value": ""
  },
  {
    "key": "NEGATIVE_TWEETS_LOCATION",
    "value": ""
  },
  {
    "key": "OUTPUT_FILE_LOCATION",
    "value": ""
  }
]
```

These pipeline parameters refer to the Databricks URL, Databricks token, Databricks cluster Id and locations for source datasets as well as output file location.

Technical Details
------------------------------

For techincal information and detailed explanation of this use case, read this [blog](https://bit.ly/TrainNLPModel).
