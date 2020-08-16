TensorFlow Binary Classification Of Breast Cancer Condition
=======================================================================

This StreamSets Data Collector pipeline is designed to load a pre-trained TensorFlow model to classify cancer condition as either *benign* or *malignant*.

Prerequisites
---------------------

* [StreamSets Data Collector](https://streamsets.com/products/dataops-platform/data-collector/). You can [deploy Data Collector](https://streamsets.com/products/dataops-platform/data-collector/download/) on your choice of cloud provider or you can download it for local development.

Setup
---------------------

* [Download and import the pipeline](TensorFlowBreastCancerBinaryclassificationc6bb44b7-bf28-4b3a-8c8f-e419625b3096.json) into your instance of Data Colelctor
* [Download the sample dataset](dataset)
* [Download the TensorFlow model](model)
* After importing the pipeline into your environment and before running the pipeline, update the following pipeline parameters:

```
[
  {
    "key": "INPUT_DATA_LOCATION",
    "value": ""
  },
  {
    "key": "INPUT_DATA_FILE",
    "value": ""
  },
  {
    "key": "KAFKA_TOPIC_BENIGN",
    "value": ""
  },
  {
    "key": "KAFKA_TOPIC_MALIGNANT",
    "value": ""
  },
  {
    "key": "KAFKA_BROKER_URI",
    "value": ""
  },
  {
    "key": "TF_MODEL_LOCATION",
    "value": ""
  }
]
```

These pipeline parameters refer to the locations of source dataset, the TensorFlow model, Kafka topics as well as Kafka broker URI.

Technical Details
------------------------------

For techincal information and detailed explanation of this use case, read this [blog](https://bit.ly/TFInSDC).
