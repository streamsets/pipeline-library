<p align="center">
<img src="https://github.com/streamsets/marty/blob/master/images/Full%20Color%20Transparent.png" width="300">
</p>

<h1><p align="center">MySQL CDC to Snowflake</p></h1>

# MySQL CDC to Snowflake

**Important:** *These instructions assume you have access to StreamSets Data Collector (v3.15+) and have performed all the prerequisites for MySQL and Snowflake*

- For help installing [StreamSets Data Collector](https://streamsets.com/products/dataops-platform/data-collector/), see [StreamSets Data Collector Installation](https://streamsets.com/documentation/datacollector/latest/help/datacollector/UserGuide/Installation/Install_title.html).
- For help with MySQL Binary Log prerequisites, see [MySQL Binary Log](https://streamsets.com/documentation/controlhub/latest/onpremhelp/datacollector/UserGuide/Origins/MySQLBinaryLog.html).
- For help with Snowflake prerequisites, see [Snowflake](https://streamsets.com/documentation/controlhub/latest/onpremhelp/datacollector/UserGuide/Destinations/Snowflake.html).

Here is a link to a short video on using this pipeline template: [Video Link](https://www.youtube.com/channel/UC_4K-__dngOCEmoZs7PVZAg)

## OVERVIEW

This pipeline demonstrates how to read change data capture (CDC) data from a MySQL database and replicate the changes to Snowflake.

## USING THE TEMPLATE

NOTE: [Templates](https://streamsets.com/documentation/controlhub/latest/onpremhelp/controlhub/UserGuide/Pipelines/PipelineTemplates.html) are supported in [StreamSets Control Hub](https://streamsets.com/products/dataops-platform/control-hub/). If you do not have Control Hub, you can import the template pipeline in Data Collector but will need to do that each time you want to use the template.

## PIPELINE

![Pipeline](images/pipeline.png "MySQL CDC to Snowflake")

## DOCUMENTATION

[MySQL Binlog Origin](https://streamsets.com/documentation/controlhub/latest/onpremhelp/datacollector/UserGuide/Origins/MySQLBinaryLog.html)

[Expression Evaluator](https://streamsets.com/documentation/controlhub/latest/help/datacollector/UserGuide/Processors/Expression.html)

[StreamSelector](https://streamsets.com/documentation/controlhub/latest/help/datacollector/UserGuide/Processors/StreamSelector.html)

[Field Renamer](https://streamsets.com/documentation/controlhub/latest/help/datacollector/UserGuide/Processors/FieldRenamer.html)

[Snowflake Destination](https://streamsets.com/documentation/controlhub/latest/help/datacollector/UserGuide/Destinations/Snowflake.html)

## STEP-BY-STEP

### Step 1: Download the pipeline

[Click Here](https://github.com/streamsets/marty/raw/master/datacollector/MySQL/CDCtoDeltaLake/700_TEMPLATE%5BSDC%5D_MySQL_CDC_to_Snowflake.zip?raw=true) to download the pipeline and save it to your drive.

### Step 2: Import the pipeline

Click the down arrow next to the "Create New Pipeline" and select "Import Pipeline From Archive".

![Step 2](images/MySQLtoSnowflake_step2.png "Import the Pipeline")

Click "Browse" and locate the pipeline file you just downloaded, click "OK", then click "Import"

![Step 2a](images/MySQLtoSnowflake_step2a.png "Import the Pipeline")

### Step 3: Configure the parameters

Click on the pipeline you just imported to open it and click on the "Parameters" tab and fill in the appropriate information for your environment.

**Important:** *The pipeline template uses the most common default settings for things like the Snowflake region, staging location, etc. All of these are configurable and if you need to change those, you can opt to not use the built-in parameters and choose the appropriate settings yourself. Please refer to the documentation listed in this document for all the available options.*

![Step 3](images/MySQLtoSnowflake_step3.png "Configure the parameters")

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
   <td class="entry cellrowborder" headers="d436212e853 ">MySQL password.<div class="note tip"><span class="tiptitle">Tip:</span> <span class="ph" id="task_qbt_kyh_xx__d15e6239">To secure sensitive information such as user names and passwords, you can use <a class="href" href="https://streamsets.com/documentation/datacollector/latest/help/datacollector/UserGuide/Pipeline_Configuration/RuntimeValues.html" title="Similar to runtime properties, runtime resources are values that you define in a file local to the Data Collector and call from within a pipeline. But with runtime resources, you can restrict the permissions for the files to secure information.">runtime resources</a> or <span class="ph"><a class="href" href="https://streamsets.com/documentation/datacollector/latest/help/datacollector/UserGuide/Configuration/CredentialStores.html">credential stores.</a></span></span></div>
</td>
  </tr>
  <tr>
   <td><code>snowflake_account</code>
   </td>
   <td class="entry cellrowborder" headers="d198512e2230 ">Snowflake account name.</td>
  </tr>
  <tr>
   <td><code>snowflake_user</code>
   </td>
   <td class="entry cellrowborder" headers="d198512e2230 ">Snowflake user name.</td>
  </tr>
  <tr>
   <td><code>snowflake_password</code>
   </td>
   <td class="entry cellrowborder" headers="d198512e2230 ">Snowflake password.</td>
  </tr>
  <tr>
   <td><code>snowflake_warehouse</code>
   </td>
   <td class="entry cellrowborder" headers="d198512e2372 ">Snowflake warehouse.</td>
  </tr>
  <tr>
   <td><code>snowflake_database</code>
   </td>
   <td class="entry cellrowborder" headers="d198512e2372 ">Snowflake database.</td>
  </tr>
  <tr>
   <td><code>snowflake_schema</code>
   </td>
   <td class="entry cellrowborder" headers="d198512e2372 ">Snowflake schema.</td>
  </tr>
  <tr>
   <td><code>snowflake_stage_name</code>
   </td>
   <td class="entry cellrowborder" headers="d198512e2713 ">Name of the Snowflake stage used to stage the data.
                                            <p class="p">Unless using a Snowflake internal user stage, you
                                            create this stage as part of the <a class="xref">Snowflake prerequisite tasks</a>.</p>
<p class="p">To use a
                                            Snowflake internal user stage, enter a tilde
                                                (<code class="ph codeph">~</code>).</p>
</td>
  </tr>
</table>

### Step 4: Run the pipeline

Click the "START" button to run the pipeline.

![Step 4](images/MySQLtoSnowflake_step4.png "Run the pipeline")

![Step 4a](images/MySQLtoSnowflake_step4a.png "Run the pipeline")

### Step 5: Make changes to the MySQL source table and see the pipeline process them

![Step 5](images/MySQLtoSnowflake_step5.png "View the results")
