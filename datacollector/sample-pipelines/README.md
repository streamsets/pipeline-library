![StreamSets Logo](../../images/Full%20Color%20Transparent.png)

<h1><p align="center">Data Collector: Sample Pipelines</p></h1>

This folder contains pipeline templates and samples for StreamSets Data Collector.

The following templates/samples are currently available:
| Name            | Description     |
| --------------- | --------------- |
| [Citi Bike real-time system data (Basic)](./pipelines/Citi%20Bike%20real-time%20system%20data%20(Basic)) | Reads from Rest API with unstructured and hierarchical data and convert to relational format |
| [Date Conversions](./pipelines/Date%20Conversions) | Convert dates from string to various datetime formats and timezones using Field Type Converter and Expression Evaluator processors |
| [Drift Synchronization for Hive](./pipelines/Drift%20Synchronization%20for%20Hive) | Drift Synchronization from MySQL to the Cloudera distribution of Apache Hive and Apache Impala |
| [Hadoop FS to ADLS Gen2](./pipelines/HDFS%20to%20ADLS%20Gen2) | Load data from Hadoop FS to ADLS Gen 2 by performing some transformations |
| [ML - TensorFlow Binary Classification](./pipelines/ML%20-%20TensorFlow%20Binary%20Classification) |  Load a pre-trained TensorFlow model to classify cancer condition as either benign or malignant |
| [MySQL CDC to Delta Lake](./pipelines/MySQL%20CDC%20to%20Delta%20Lake) | Reads MySQL change data capture (CDC) data and writes to Databricks Delta Lake |
| [MySQL CDC to S3 to Snowflake](./pipelines/MySQL%20CDC%20to%20S3%20to%20Snowflake) | Reads MySQL change data capture (CDC) data, writes to S3 then reads from S3 and writes to Snowflake |
| [MySQL CDC to Snowflake](./pipelines/MySQL%20CDC%20to%20Snowflake) | Reads MySQL change data capture (CDC) data and writes to Snowflake |
| [MySQL Schema Replication to Azure Synapse SQL](./pipelines/MySQL%20Schema%20replication%20to%20Azure%20Synapse%20SQL)| Bulk load data from MySQL into Azure Synapse SQL |
| [MySQL Schema replication to Delta Lake](./pipelines/MySQL%20Schema%20replication%20to%20Delta%20Lake) | Bulk load data from MySQL into Databricks Delta Lake |
| [MySQL binlog to DeltaLake](./pipelines/MySQL%20binlog%20to%20DeltaLake) | Reads MySQL binlog changed data and writes to Databricks Delta Lake |
| [NYC Taxi Ride Payment Type (Basic)](./pipelines/NYC%20Taxi%20Ride%20Payment%20Type%20(Basic)) | Reads data from a directory, process it, route it, mask sensitive data and write into another file system with a different data format |
| [NYC Taxi Ride Payment Type (with Jython)](./pipelines/NYC%20Taxi%20Ride%20Payment%20Type%20(with%20Jython)) | Reads data from a directory, process it using Jython, route it, mask sensitive data and write into another file system with a different data format | 
| [Oracle 19c Bulk Ingest and CDC to Databricks Delta Lake](./pipelines/Oracle%2019c%20Bulk%20Ingest%20and%20CDC%20to%20Databricks%20Delta%20Lake) | Bulk ingest data from Oracle 19c and process Change Data Capture (CDC) into Databricks Delta Lake |
| [Oracle CDC to Delta Lake](./pipelines/Oracle%20CDC%20to%20Delta%20Lake) | Reads change data capture (CDC) data Oracle and writes to Databricks Delta Lake |
| [Oracle CDC to Snowflake](./pipelines/Oracle%20CDC%20to%20Snowflake) | Reads change data capture (CDC) data Oracle and writes to Snowflake |
| [Parse Twitter Data to JSON](./pipelines/Parse%20Twitter%20Data%20to%20JSON) | Parse raw Twitter data and store curated data in JSON format |
| [Parse Web Logs to JSON and Avro](./pipelines/Parse%20Web%20Logs%20to%20JSON%20and%20Avro) | Parse raw web logs ingested in Common Log Format and store curated data in JSON and Avro formats |
| [PostgreSQL CDC to Delta Lake](./pipelines/PostgreSQL%20CDC%20to%20Delta%20Lake) | Reads change data capture (CDC) data from PostgreSQL and writes to Databricks Delta Lake |
| [PostgreSQL CDC to Snowflake](./pipelines/PostgreSQL%20CDC%20to%20Snowflake) | Reads change data capture (CDC) data from PostgreSQL and writes to Snowflake |
| [SQLServer CDC to Delta Lake](./pipelines/SQLServer%20CDC%20to%20Delta%20Lake) | Reads change data capture (CDC) data from SQL Server and writes to Databricks Delta Lake |
| [SQLServer CDC to Snowflake](./pipelines/SQLServer%20CDC%20to%20Snowflake) | Reads change data capture (CDC) data from SQL Server and writes to Snowflake |
| [Salesforce CDC to Delta Lake](./pipelines/Salesforce%20CDC%20to%20Delta%20Lake) | Reads change data capture (CDC) data from Salesforce and writes to Databricks Delta Lake |
| [Salesforce CDC to Snowflake](./pipelines/Salesforce%20CDC%20to%20Snowflake) | Reads change data capture (CDC) data from Salesforce and writes to Snowflake |
| [Salesforce to Delta Lake](./pipelines/Salesforce%20to%20Delta%20Lake) | Bulk load data from Salesforce accounts into Databricks Delta Lake |
| [Working with XML (Basic)](./pipelines/Working%20with%20XML%20(Basic)) | Read and process XML data in Data Collector
| [aws-marketplace-reports](./pipelines/aws-marketplace-reports) | Bulk load data from Salesforce accounts into Databricks Delta Lake |

# Help

For any queries, questions, comments related to these pipelines reach out on any of these channels:

[Chat on Slack](https://streamsetters-slack.herokuapp.com/)

[User Group](https://groups.google.com/a/streamsets.com/d/forum/sdc-user)

[Ask StreamSets](https://ask.streamsets.com/questions/)
