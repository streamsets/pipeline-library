![StreamSets Logo](images/Full%20Color%20Transparent.png)

<h1><p align="center">Pipeline Library</p></h1>

This repo contains pipeline templates and samples that will help you get started with common use cases using StreamSets.  The directory structure is broken out by the StreamSets engine (datacollector or transformer).  Within each engine, the directory structure is broken out by origins and destinations.  Many templates and samples will be located in multiple locations so you can easily find them by origin or destination.  For example, MySQL CDC to Databricks Delta Lake is found in both origins/mysql and destinations/databricks-delta-lake.

The following templates/samples are currently available:
| Name            | Description     |
| --------------- | --------------- |
| [MySQL CDC to Delta Lake](datacollector/destinations/databricks-delta-lake/MySQL%20CDC%20to%20Delta%20Lake) | Reads MySQL change data capture (CDC) data and writes to Databricks Delta Lake |
| [MySQL CDC to Snowflake](datacollector/destinations/snowflake/MySQL%20CDC%20to%20Snowflake) | Reads MySQL change data capture (CDC) data and writes to Snowflake |
| [MySQL Schema replication to Delta Lake](datacollector/destinations/databricks-delta-lake/MySQL%20Schema%20replication%20to%20Delta%20Lake) | Bulk load data from MySQL into Databricks Delta Lake |
| [MySQL binlog to DeltaLake](datacollector/destinations/databricks-delta-lake/MySQL%20binlog%20to%20DeltaLake) | Reads MySQL binlog changed data and writes to Databricks Delta Lake |
| [Oracle 19c Bulk Ingest and CDC to Databricks Delta Lake](datacollector/destinations/databricks-delta-lake/Oracle%2019c%20Bulk%20Ingest%20and%20CDC%20to%20Databricks%20Delta%20Lake) | Bulk ingest data from Oracle 19c and process Change Data Capture (CDC) into Databricks Delta Lake |
| [Oracle CDC to Delta Lake](datacollector/destinations/databricks-delta-lake/Oracle%20CDC%20to%20Delta%20Lake) | Reads change data capture (CDC) data Oracle and writes to Databricks Delta Lake |
| [Oracle CDC to Snowflake](datacollector/destinations/snowflake/Oracle%20CDC%20to%20Snowflake) | Reads change data capture (CDC) data Oracle and writes to Snowflake |
| [PostgreSQL CDC to Delta Lake](datacollector/destinations/databricks-delta-lake/PostgreSQL%20CDC%20to%20Delta%20Lake) | Reads change data capture (CDC) data from PostgreSQL and writes to Databricks Delta Lake |
| [PostgreSQL CDC to Snowflake](datacollector/destinations/snowflake/PostgreSQL%20CDC%20to%20Snowflake) | Reads change data capture (CDC) data from PostgreSQL and writes to Snowflake |
| [SQLServer CDC to Delta Lake](datacollector/destinations/databricks-delta-lake/SQLServer%20CDC%20to%20Delta%20Lake) | Reads change data capture (CDC) data from SQL Server and writes to Databricks Delta Lake |
| [SQLServer CDC to Snowflake](datacollector/destinations/snowflake/SQLServer%20CDC%20to%20Snowflake) | Reads change data capture (CDC) data from SQL Server and writes to Snowflake |
| [Salesforce CDC to Delta Lake](datacollector/destinations/databricks-delta-lake/Salesforce%20CDC%20to%20Delta%20Lake) | Reads change data capture (CDC) data from Salesforce and writes to Databricks Delta Lake |
| [Salesforce CDC to Snowflake](datacollector/destinations/snowflake/Salesforce%20CDC%20to%20Snowflake) | Reads change data capture (CDC) data from Salesforce and writes to Snowflake |
| [Salesforce to Delta Lake](datacollector/destinations/databricks-delta-lake/Salesforce%20to%20Delta%20Lake) | Bulk load data from Salesforce accounts into Databricks Delta Lake |



# Help
For any queries, questions, comments related to these pipelines reach out on any of these channels:

[Chat on Slack](https://streamsetters-slack.herokuapp.com/)

[User Group](https://groups.google.com/a/streamsets.com/d/forum/sdc-user)

[Ask StreamSets](https://ask.streamsets.com/questions/)
