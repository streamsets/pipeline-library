![StreamSets Logo](images/Full%20Color%20Transparent.png)

<h1><p align="center">Oracle CDC to Databricks Delta Lake</p></h1>

# Oracle CDC to Databricks Delta Lake

**Important:** *These instructions assume you have access to StreamSets Data Collector (v3.15+) and have performed all the prerequisites for Oracle and Databricks Delta Lake*

- For help installing [StreamSets Data Collector](https://streamsets.com/products/dataops-platform/data-collector/), see [StreamSets Data Collector Installation](https://streamsets.com/documentation/datacollector/latest/help/datacollector/UserGuide/Installation/Install_title.html).
- For help with Oracle CDC Client prerequisites, see [Oracle CDC Client](https://streamsets.com/documentation/datacollector/latest/help/datacollector/UserGuide/Origins/OracleCDC.html).
- For help with Databricks Delta Lake prerequisites, see [Databricks Delta Lake](https://streamsets.com/documentation/datacollector/latest/help/datacollector/UserGuide/Destinations/DeltaLake.html).

For more information, see [Loading Data into Databricks Delta Lake](https://streamsets.com/documentation/datacollector/latest/help/index.html?contextID=concept_a5b_wvk_ckb) in [StreamSets Data Collector documentation](https://streamsets.com/documentation/datacollector/latest/help/).

Here is a link to a short video on using this pipeline template: [Video Link](https://www.youtube.com/channel/UC_4K-__dngOCEmoZs7PVZAg)

## OVERVIEW

This pipeline demonstrates how to read change data capture (CDC) data from an Oracle database and replicate the changes to Databricks Delta Lake.

**Disclaimer:** *This pipeline is meant to serve as a template for performing Oracle CDC to Databricks Delta Lake.  Some of the parameters, tables and fields may be different for your environment and may need additional customizations.  Please consult the StreamSets documentation (linked below) for full information on configuration of each stage used below.  For example, this pipeline has a single table defined with keys.  If you want to handle multiple tables, you will need to add them to the Delta Lake destination --> Data tab.*


## USING THE TEMPLATE

NOTE: [Templates](https://streamsets.com/documentation/controlhub/latest/onpremhelp/controlhub/UserGuide/Pipelines/PipelineTemplates.html) are supported in [StreamSets Control Hub](https://streamsets.com/products/dataops-platform/control-hub/). If you do not have Control Hub, you can import the template pipeline in Data Collector but will need to do that each time you want to use the template.

## PIPELINE

![Pipeline](images/pipeline.png "Oracle CDC to Databricks Delta Lake")

## DOCUMENTATION

[Oracle CDC Client](https://streamsets.com/documentation/datacollector/latest/help/datacollector/UserGuide/Origins/OracleCDC.html)

[Expression Evaluator](https://streamsets.com/documentation/controlhub/latest/help/datacollector/UserGuide/Processors/Expression.html)

[Delta Lake Destination](https://streamsets.com/documentation/controlhub/latest/onpremhelp/datacollector/UserGuide/Destinations/DeltaLake.html)

## STEP-BY-STEP

### Step 1: Download the pipeline

[Click Here](./OracleCDC_to_DeltaLake.zip?raw=true) to download the pipeline and save it to your drive.

### Step 2: Import the pipeline

Click the down arrow next to the "Create New Pipeline" and select "Import Pipeline From Archive".

![Step 2](images/OracletoDBDeltaLake_step2.png "Import the Pipeline")

Click "Browse" and locate the pipeline file you just downloaded, click "OK", then click "Import"

![Step 2a](images/OracletoDBDeltaLake_step2a.png "Import the Pipeline")

### Step 3: Configure the parameters

Click on the pipeline you just imported to open it and click on the "Parameters" tab and fill in the appropriate information for your environment.

**Important:** *The pipeline template uses the most common default settings for things like the region, staging location, etc. All of these are configurable and if you need to change those, you can opt to not use the built-in parameters and choose the appropriate settings yourself. Please refer to the documentation listed in this document for all the available options.*

![Step 3](images/OracletoDBDeltaLake_step3.png "Configure the parameters")

The following parameters are set up for this pipeline:
<table>
  <tr>
                                    <td><code>oracle_schema</code></td>
                                    <td class="entry cellrowborder" headers="d442874e2435 ">Schema to use. You can enter a schema name or use <a class="xref" href="https://docs.oracle.com/database/121/SQLRF/conditions007.htm#SQLRF00501" target="_blank">SQL LIKE syntax</a> to
                                        specify a set of schemas.<p class="p">The origin submits the schema
                                            name in all caps by default. To use a lower or
                                            mixed-case name, select the Case-Sensitive Names
                                            property.</p>
</td>
                                </tr>
  <tr>
                                    <td><code>oracle_table_name_pattern</a></td>
                                    <td class="entry cellrowborder" headers="d442874e2435 ">Table name pattern that specifies the tables to track.
                                        You can enter a table name or use <a class="xref" href="https://docs.oracle.com/database/121/SQLRF/conditions007.htm#SQLRF00501" target="_blank">SQL LIKE syntax</a> to
                                        specify a set of tables. The origin submits table names in
                                        all caps by default. To use lower or mixed-case names,
                                        select the Case-Sensitive Names property.</td>
                                </tr>
  <tr>
   <td><code>oracle_CDC_connection_string</code>
   </td>
   <td class="entry cellrowborder" headers="d442874e2818 ">Connection string used to connect to the database.
                                            <div class="note note"><span class="notetitle">Note:</span> If you include the JDBC credentials in the
                                            connection string, use the user account created for the
                                            origin. Common user accounts for Oracle 12c, 18c, or 19c
                                            multitenant databases start with <code class="ph codeph">c##</code>.
                                            </div>
</td>
  </tr>
  <tr>
   <td><code>oracle_username</code>
   </td>
   <td class="entry cellrowborder" headers="d442874e2925 ">User name for the JDBC connection. Use the user account
                                        created for the origin. Common user accounts for Oracle 12c,
                                        18c, or 19c multitenant databases start with
                                            <code class="ph codeph">c##</code>.<p class="p">For more information, see <a class="xref" href="[OracleCDC.html#concept_jnz_bd2_3y](https://streamsets.com/documentation/datacollector/latest/help/datacollector/UserGuide/Origins/OracleCDC.html#concept_jnz_bd2_3y)">Task 3. Create a User Account</a>.</p>
</td>
  </tr>
  <tr>
   <td><code>oracle_password</code>
   </td>
   <td class="entry cellrowborder" headers="d436212e853 ">MySQL password.<div class="note tip"><span class="tiptitle">Tip:</span> <span class="ph" id="task_qbt_kyh_xx__d15e6239">To
                        secure sensitive information such as user names and passwords, you can use
                              <a class="xref" title="Similar to runtime properties, runtime resources are values that you define in a file local to the Data Collector and call from within a pipeline. But with runtime resources, you can restrict the permissions for the files to secure information." href="https://streamsets.com/documentation/datacollector/latest/help/datacollector/UserGuide/Pipeline_Configuration/RuntimeValues.html#concept_bs4_5nm_2s">runtime resources</a> or <span class="ph"><a class="xref" href="https://streamsets.com/documentation/datacollector/latest/help/datacollector/UserGuide/Configuration/CredentialStores.html#concept_bt1_bpj_r1b">credential stores.</a></span></span></div>
</td>
  </tr>
  <tr>
   <td><code>deltalake_jdbc_url</code>
   </td>
   <td class="entry cellrowborder" headers="d108933e1968 ">JDBC URL used to connect to the Databricks cluster.<p class="p">For example:
                                                <code class="ph codeph">jdbc:spark://dbc-7g9hba4d-a123.cloud.databricks.com:443/default;transportMode=http</code>
                                            <code class="ph codeph">:ssl=1;httpPath=sql/protocolv1/o/89266567230988377/1123-1001003-abc1;AuthMech=3;UID=token;</code></p>
<div class="note tip"><span class="tiptitle">Tip:</span> In Databricks, you can locate the
                                            JDBC URL for your cluster on the
                                                <span class="keyword wintitle">JDBC/ODBC</span> tab in the cluster
                                            configuration details. As a best practice, remove the
                                                <code class="ph codeph">PWD</code> parameter from the URL, and
                                            then enter the personal access token value in the Token
                                            property below. </div>
</td>
  </tr>
  <tr>
   <td><code>deltalake_token</code>
   </td>
   <td class="entry cellrowborder" headers="d108933e1968 ">Personal access token used to connect to the Databricks
                                            cluster.<div class="note tip"><span class="tiptitle">Tip:</span> To secure sensitive information such as tokens,
                  you can use <a class="xref" title="Similar to runtime properties, runtime resources are values that you define in a file local to the Data Collector and call from within a pipeline. But with runtime resources, you can restrict the permissions for the files to secure information.">runtime resources</a> or <span class="ph"><a class="xref">credential stores.</a></span></div>
</td>
  </tr>
  <tr>
   <td><code>deltalake_directory_for_table_location</code>
   </td>
   <td class="entry cellrowborder" headers="d108933e1968 ">Directory for the Delta table location, specified as a
                                        path on Databricks File System (DBFS). <p class="p">The destination adds
            the specified Table Name value as a subdirectory to create the final table location. For
            example, if you enter <span class="ph filepath">/mnt/deltalake</span> as the directory for the table
            location and you enter <code class="ph codeph">sales.accounts</code> as the table name, the final
                table location is <span class="ph filepath">/mnt/deltalake/sales.accounts</span>.</p>
<p class="p">When you specify a location, the destination creates
                an unmanaged Delta table. When you do not specify a location, the destination
                creates a managed Delta table. For more information, see the <a class="xref" href="https://docs.databricks.com/delta/delta-batch.html#control-data-location" target="_blank">Delta Lake
                documentation</a>.</p>
<p class="p">Available when data drift and automatic table
                                            creation are enabled.</p>
</td>
  </tr>
  <tr>
   <td><code>deltalake_S3_bucket</code>
   </td>
   <td class="entry cellrowborder" headers="d108933e2196 "><b>** NOTE ** This template uses AWS S3 as the staging location.  If you want to use ADLS, you will need to change it in the Delta Lake Destination --> Staging tab and provide all necessary configuration.</b>
   <p>Bucket name or path to the existing Amazon S3 location to
                                        write the staged files.<p class="p">Enter the bucket name or enter the
                                            full bucket path in the following
                                                format:</p>
<p class="p"><code class="ph codeph">&lt;bucket&gt;/&lt;prefix&gt;</code></p>
<p class="p">Available
                                            when using the Amazon S3 staging location.</p>
</td>
   </td>
  </tr>
  <tr>
   <td><code>deltalake_S3_access_key</code>
   </td>
   <td class="entry cellrowborder" headers="d108933e2196 ">AWS access key ID. <p class="p">Required when not using IAM roles
                                            with IAM instance profile credentials.</p>
<p class="p">Available
                                            when using the Amazon S3 staging location.</p>
</td>
  </tr>
  <tr>
   <td><code>deltalake_S3_secret_key</code>
   </td>
   <td class="entry cellrowborder" headers="d108933e2196 ">AWS secret access key. <p class="p">Required when not using IAM
                                            roles with IAM instance profile
                                            credentials.</p>
<div class="p">Available when using the Amazon S3
                                            staging location.<div class="note tip"><span class="tiptitle">Tip:</span> To secure sensitive information such as
                  access key pairs, you can use <a title="Similar to runtime properties, runtime resources are values that you define in a file local to the Data Collector and call from within a pipeline. But with runtime resources, you can restrict the permissions for the files to secure information.">runtime resources</a> or <span class="ph"><a>credential stores.</a></span></div>
</div>
</td>   
  </tr>
  <tr>
   <td><code>deltalake_database_name</code>
   </td>
   <td>The Delta Lake database name.
   </td>
  </tr>
  <tr>
   <td><code>deltalake_table</code>
   </td>
   <td>The Delta Lake table name.
   <p><b>** NOTE ** The template can handle multiple different tables, but you need to configure all the tables and key columns in the Delta Lake destination --> Data tab.  See Appendix 1 below for details.</b>
   </td>
  </tr>
  <tr>
   <td><code>deltalake_key_column</code>
   </td>
   <td>The Delta Lake key column.
   <p><b>** NOTE ** The template can handle multiple different tables, but you need to configure all the tables and key columns in the Delta Lake destination --> Data tab.  See Appendix 1 below for details.</b>
   </td>
  </tr>
</table>

### Step 4: Run the pipeline

Click the "START" button to run the pipeline.

![Step 4](images/OracletoDBDeltaLake_step4.png "Run the pipeline")

![Step 4a](images/OracletoDBDeltaLake_step4a.png "Run the pipeline")

### Step 5: Make changes to the MySQL source table and see the pipeline process them

![Step 5](images/OracletoDBDeltaLake_step5.png "View the results")
