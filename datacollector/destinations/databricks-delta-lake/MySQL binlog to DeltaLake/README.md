![StreamSets Logo](images/Full%20Color%20Transparent.png)

<h1><p align="center">MySQL CDC to Databricks Delta Lake</p></h1>

# MySQL CDC to Databricks Delta Lake

**Important:** *These instructions assume you have access to StreamSets Data Collector (v3.15+) and have performed all the prerequisites for MySQL and Databricks Delta Lake*

- For help installing [StreamSets Data Collector](https://streamsets.com/products/dataops-platform/data-collector/), see [StreamSets Data Collector Installation](https://streamsets.com/documentation/datacollector/latest/help/datacollector/UserGuide/Installation/Install_title.html).
- For help with MySQL Binary Log prerequisites, see [MySQL Binary Log](https://streamsets.com/documentation/controlhub/latest/onpremhelp/datacollector/UserGuide/Origins/MySQLBinaryLog.html).
- For help with Databricks Delta Lake prerequisites, see [Databricks Delta Lake](https://streamsets.com/documentation/datacollector/latest/help/datacollector/UserGuide/Destinations/DeltaLake.html).

For more information, see [Loading Data into Databricks Delta Lake](https://streamsets.com/documentation/datacollector/latest/help/index.html?contextID=concept_a5b_wvk_ckb) in [StreamSets Data Collector documentation](https://streamsets.com/documentation/datacollector/latest/help/).

Here is a link to a short video on using this pipeline template: [Video Link](https://www.youtube.com/channel/UC_4K-__dngOCEmoZs7PVZAg)

## OVERVIEW

This pipeline demonstrates how to read change data capture (CDC) data from a MySQL database and replicate the changes to Databricks Delta Lake.

**Disclaimer:** *This pipeline is meant to serve as a template for performing MySQL binlog CDC to Databricks Delta Lake.  Some of the parameters, tables and fields may be different for your environment and may need additional customizations.  Please consult the StreamSets documentation (linked below) for full information on configuration of each stage used below.  For example, this pipeline has a single table defined with keys.  If you want to handle multiple tables, you will need to add them to the Delta Lake destination --> Data tab.*


## USING THE TEMPLATE

NOTE: [Templates](https://streamsets.com/documentation/controlhub/latest/onpremhelp/controlhub/UserGuide/Pipelines/PipelineTemplates.html) are supported in [StreamSets Control Hub](https://streamsets.com/products/dataops-platform/control-hub/). If you do not have Control Hub, you can import the template pipeline in Data Collector but will need to do that each time you want to use the template.

## PIPELINE

![Pipeline](images/pipeline.png "MySQL CDC to Databricks Delta Lake")

## DOCUMENTATION

[MySQL Binlog Origin](https://streamsets.com/documentation/controlhub/latest/onpremhelp/datacollector/UserGuide/Origins/MySQLBinaryLog.html)

[Expression Evaluator](https://streamsets.com/documentation/controlhub/latest/help/datacollector/UserGuide/Processors/Expression.html)

[StreamSelector](https://streamsets.com/documentation/controlhub/latest/help/datacollector/UserGuide/Processors/StreamSelector.html)

[Field Renamer](https://streamsets.com/documentation/controlhub/latest/help/datacollector/UserGuide/Processors/FieldRenamer.html)

[Delta Lake Destination](https://streamsets.com/documentation/controlhub/latest/onpremhelp/datacollector/UserGuide/Destinations/DeltaLake.html)

## STEP-BY-STEP

### Step 1: Download the pipeline

[Click Here](./MySQL_CDC_to_DeltaLake.zip?raw=true) to download the pipeline and save it to your drive.

### Step 2: Import the pipeline

Click the down arrow next to the "Create New Pipeline" and select "Import Pipeline From Archive".

![Step 2](images/MySQLtoDBDeltaLake_step2.png "Import the Pipeline")

Click "Browse" and locate the pipeline file you just downloaded, click "OK", then click "Import"

![Step 2a](images/MySQLtoDBDeltaLake_step2a.png "Import the Pipeline")

### Step 3: Configure the parameters

Click on the pipeline you just imported to open it and click on the "Parameters" tab and fill in the appropriate information for your environment.

**Important:** *The pipeline template uses the most common default settings for things like the region, staging location, etc. All of these are configurable and if you need to change those, you can opt to not use the built-in parameters and choose the appropriate settings yourself. Please refer to the documentation listed in this document for all the available options.*

![Step 3](images/MySQLtoDBDeltaLake_step3.png "Configure the parameters")

The following parameters are set up for this pipeline:
<table>
  <tr>
   <td><code>mysql_hostname</code>
   </td>
   <td class="entry cellrowborder" headers="d436212e756 ">MySQL server hostname.</td>
  </tr>
  <tr>
   <td><code>mysql_port</code>
   </td>
   <td class="entry cellrowborder" headers="d436212e756 ">MySQL server port. </td>
  </tr>
  <tr>
   <td><code>mysql_serverid</code>
   </td>
   <td class="entry cellrowborder" headers="d436212e756 ">Replication server ID that the origin uses to connect to
                                        the master MySQL server. Must be unique from the server ID
                                        of the replication master and of all the other replication
                                            slaves.<p class="p">When the MySQL server database is enabled for
                                            GTID, the server ID is optional. </p>
</td>
  </tr>
  <tr>
   <td><code>mysql_username</code>
   </td>
   <td class="entry cellrowborder" headers="d436212e853 ">MySQL username. <div class="p">The user must have the following MySQL
                                                privileges:<ul>
                                                <li>REPLICATION CLIENT</li>
                                                <li>REPLICATION SLAVE</li>
                                            </ul>
</div>
</td>
  </tr>
  <tr>
   <td><code>mysql_password</code>
   </td>
   <td class="entry cellrowborder" headers="d436212e853 ">MySQL password.<div class="note tip"><span class="tiptitle">Tip:</span> <span class="ph" id="task_qbt_kyh_xx__d15e6239">To
                        secure sensitive information such as user names and passwords, you can use
                              <a class="xref" href="https://streamsets.com/documentation/datacollector/latest/help/index.html?contextID=concept_bs4_5nm_2s" title="Similar to runtime properties, runtime resources are values that you define in a file local to the Data Collector and call from within a pipeline. But with runtime resources, you can restrict the permissions for the files to secure information.">runtime resources</a> or <span class="ph"><a class="xref" href="https://streamsets.com/documentation/datacollector/latest/help/index.html?contextID=concept_bt1_bpj_r1b">credential stores.</a>
</span></span></div>
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
                                            cluster.<div class="note tip"><span class="tiptitle">Tip:</span> To secure sensitive information such as tokens, you can use <a class="xref" href="https://streamsets.com/documentation/datacollector/latest/help/index.html?contextID=concept_bs4_5nm_2s" title="Similar to runtime properties, runtime resources are values that you define in a file local to the Data Collector and call from within a pipeline. But with runtime resources, you can restrict the permissions for the files to secure information.">runtime resources</a> or <span class="ph"><a class="xref" href="https://streamsets.com/documentation/datacollector/latest/help/index.html?contextID=concept_bt1_bpj_r1b">credential stores.</a>


</span></div>
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
                  access key pairs, you can use <a class="xref" href="https://streamsets.com/documentation/datacollector/latest/help/index.html?contextID=concept_bs4_5nm_2s" title="Similar to runtime properties, runtime resources are values that you define in a file local to the Data Collector and call from within a pipeline. But with runtime resources, you can restrict the permissions for the files to secure information.">runtime resources</a> or <span class="ph"><a class="xref" href="https://streamsets.com/documentation/datacollector/latest/help/index.html?contextID=concept_bt1_bpj_r1b">credential stores.</a>

</span></div>
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
   <p><b>** NOTE ** The template can handle multiple different tables, but you need to configure all the tables and key columns in the Delta Lake destination --> Data tab.</b>
   </td>
  </tr>
  <tr>
   <td><code>deltalake_key_column</code>
   </td>
   <td>The Delta Lake key column.
   <p><b>** NOTE ** The template can handle multiple different tables, but you need to configure all the tables and key columns in the Delta Lake destination --> Data tab.</b>
   </td>
  </tr>
</table>

### Step 4: Run the pipeline

Click the "START" button to run the pipeline.

![Step 4](images/MySQLtoDBDeltaLake_step4.png "Run the pipeline")

![Step 4a](images/MySQLtoDBDeltaLake_step4a.png "Run the pipeline")

### Step 5: Make changes to the MySQL source table and see the pipeline process them

![Step 5](images/MySQLtoDBDeltaLake_step5.png "View the results")
