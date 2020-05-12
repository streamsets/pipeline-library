MySQL CDC to Delta Lake
==============================

This pipeline demonstrates how to read change data capture (CDC) data from a MySQL database and replicate the changes to Delta Lake table(s) on Databricks.

For more information, see [Loading Data into Databricks Delta Lake](https://streamsets.com/documentation/datacollector/latest/help/index.html?contextID=concept_a5b_wvk_ckb) in [StreamSets Data Collector documentation](https://streamsets.com/documentation/datacollector/latest/help/).

Prerequisites
-------------

* [StreamSets Data Collector](https://streamsets.com/products/dataops-platform/data-collector/) 3.15.0 or higher. You can [run Data Collector on your cloud provider of choice](https://streamsets.com/products/cloud/), or [download it for local use](https://streamsets.com/products/dataops-platform/data-collector/download/).
* Ensure the [pre-requisites](https://streamsets.com/documentation/datacollector/latest/help/index.html?contextID=concept_xnp_y5f_dlb "pre-requisites") for Databricks Delta Lake are complete
* [MySQL Server](https://www.mysql.com/) with Binary log enabled
* [MySQL Connector/J](https://dev.mysql.com/downloads/connector/j/) JDBC Driver

Setup
-----

* [Download the pipeline](MySQL%20CDC%20(Binary%20Log%20to%20DeltaLake.json) and import it into Data Collector or Control Hub
* Configure all the pipeline parameters for your MySQL Database and Databricks connections
* If necessary, update the MySQL binlog origin to replicate only specific tables
* By default, the Databricks Delta Lake destination is configured to auto create each table that is replicated from MySQL and write the data in DBFS. If you'd like, update the configurations in the destination per your needs.
* Configure Databricks Delta Lake destination to add a key column for each Delta Lake table being replicated. This is required for ensure the Merge command is run with the right conditional logic for Inserts, Updates and Deletes.
* Start your Databricks cluster.

Running the Pipeline
--------------------

Start the pipeline. It takes a couple of seconds to create a connection to Databricks. Once the connection is established, you should see records replicated from MySQL and sent to Delta Lake. Insert, update and delete records in MySQL to see how they are being replicated in Delta Lake.

![Pipeline running](MySQL%20CDC%20to%20Delta%20Lake.png)

