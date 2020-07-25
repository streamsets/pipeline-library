Oracle 19c Bulk Ingest And Change Data Capture To Databricks Delta Lake
=======================================================================

These pipelines demonstrate how to bulk ingest data from Oracle 19c and process Change Data Capture (CDC) into Databricks Delta Lake.

Prerequisites
---------------------

* [StreamSets Data Collector](https://streamsets.com/products/dataops-platform/data-collector/) 3.16.0 or higher. You can [deploy Data Collector on your choice of cloud provider of choice](https://streamsets.com/products/cloud/), or [you can download it for local use](https://streamsets.com/products/dataops-platform/data-collector/download/).
* Access to Databricks cluster with Databricks Runtime 6.3 or higher
* Ensure the [prerequisites](https://streamsets.com/documentation/datacollector/latest/help/index.html?contextID=concept_xnp_y5f_dlb "pre-requisites") for Databricks Delta Lake are satisfied
* Access to Oracle 19c database

Setup
---------------------

* Download the pipelines and import them into your Data Collector or Control Hub
* After importing the pipelines into your environment and before running the pipelines, update pipeline parameters with your Oracle 19c JDBC URL, Databricks cluster JDBC URL, staging information on Databricks Delta Lake destination >> Staging tab and Table/Key columns information on Databricks Delta Lake destination >> Data tab.
* Start your Databricks cluster

Technical Details
---------------------

For techincal info and detailed explanation, refer to this [blog](https://bit.ly/2ZMAWDk).
