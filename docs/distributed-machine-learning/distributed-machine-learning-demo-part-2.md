# Prepare Census Income Dataset

Welcome back to part two of our demonstration. In this part we'll use AWS Glue to set up a new crawler to go ahead and crawl our census data set. Let's begin with a quick review of what we accomplished in part one of the demonstration. In part one our demonstration, we navigated to the the UCI machine learning repository where we downloaded the census data set. We then uploaded it from our local machine into our new S3 bucket where it currently resides.

In the next part of this demonstration, we use AWS Glue to create a new crawler. The crawler will be configured to crawl the census data set resulting in meta data about this data source being registered into the Glue Data Catalog. We'll then use Amazon Athena to define a secondary table. We'll apply this to the Glue Data Catalog. This will allow us to then run an ETL job with the output source as the table derived from the Glue Crawler.

In the output source is the table created from within Athena. The function of our ETL job is to perform two tasks on our census data set. The first task is to set up named columns. The second task is to drop the redundant columns that we do not use within our machine learning script. The two tasks that we are performing within our ETL job are only being done to demonstrate the possibilities of what can be accomplished within an Amazon ETL job.



## Amazon Glue Configuration

Okay let's now begin with the configuration of Amazon Glue. Within your AWS service console, navigate to the Glue service. 

<img src="./images/Screenshot_2023-01-21_at_2.54.55_PM.png" width="75%" />

The first thing we'll need to do is set up our crawler. Click on the crawler's link in the left-hand side menu. This takes us into the crawler screen. 

Here we can see that we don't have any crawlers defined yet. Let's set up our first crawler. We do so by clicking the add crawler button. Next we need to give our crawler a name: census-data-crawler.

<img src="./images/Screenshot_2023-01-22_at_3.23.31_PM.png" width="75%" />

Optionally we can supply a description for our crawler. Let's do this now. We specify the description to be: crawler for the Census Data stored in S3 bucket. Click on the next button. Here we need to specify the location of our data source. We can choose S3 or JDBC. 

<img src="./images/Screenshot_2023-01-22_at_3.23.40_PM.png" width="75%" />

We specify that the data source in S3, is in the current AWS account. We need to define the S3 path location for our data source. We navigate to the bucket that we created in part one.


<img src="./images/Screenshot_2023-01-22_at_3.23.51_PM.png" width="75%" />

Finally we select the adult.data file that we uploaded and click the select button to set the path. We don't need to worry about any exclude patterns so we can simply click the next button to move on. In the next screen we're given the option to add another data store. We'll select no then next. 

<img src="./images/Screenshot_2023-01-22_at_3.24.01_PM.png" width="75%" />


On this screen, we need to define an IAM role that will be used by the crawler to gain access to our data store.

Here a new IAM role will be created for us called **AWS Glue Service Role - S3DataReader**. 

<img src="./images/Screenshot_2023-01-22_at_3.24.10_PM.png" width="75%" />

This role will be giving permissions to the S3 path that we chose in the previous screen. On the next screen we configure the schedule for our job. We can run it either on demand or at a frequency of our choosing. For demonstration purposes leave it run on demand.

<img src="./images/Screenshot_2023-01-22_at_3.24.39_PM.png" width="75%" />


We next need to register the database into which our crawler will put its metadata into. At the moment we have no databases, so click the Add database button and we'll add in a new database called censusdb.

<img src="./images/Screenshot_2023-01-22_at_3.26.15_PM.png" width="75%" />

Again we can optionally add a description to the new database. Let's do this, here we'll set the description to Census Database. Click the Create button to create a new database in the data catalog. There are additional configuration options that are all optional.




In our demonstration, we'll leave these as defaults and proceed by clicking the next button. This takes us to the review screen where we can review all of the options that we've set. 
<img src="./images/Screenshot_2023-01-22_at_3.26.33_PM.png" width="75%" />

Finally click the finish button at the bottom of the review screen. And this completes the configuration and creation of our crawler.

Here we can see the new crawler that we've just created. The status is set to ready. At the top of the screen we have the option to run it now.

<img src="./images/Screenshot_2023-01-22_at_3.26.59_PM.png" width="75%" />

Let's do this by clicking the link. The crawler is now active and running. We can check this by looking at the status. At the moment it's set to starting. Click on the refresh icon in the top-right-hand side to continually poll the current status.

<img src="./images/Screenshot_2023-01-22_at_4.53.43_PM.png" width="75%" />

The crawler continually updates the status with how much time has elapsed since it started. Eventually it'll reach the stopping state which means it is almost completed. Let's refresh it a few more times.
<img src="./images/Screenshot_2023-01-22_at_4.54.35_PM.png" width="75%" />


Excellent we can now see the status is set to ready which means the crawler has completed running. Let's now navigate to see if our new table has been created in the data catalog. Here we can see that we have a new table called adult_data. Clicking on this table link takes us into the table attributes screen. 

<img src="./images/Screenshot_2023-01-22_at_4.55.00_PM.png" width="75%" />

<img src="./images/Screenshot_2023-01-22_at_4.55.09_PM.png" width="75%" />


Here we can see the various attributes as derived by the crawler are now registered in the data catalog. 

<img src="./images/Screenshot_2023-01-22_at_5.17.15_PM.png" width="75%" />

Here we can see the input and output formats.

<img src="./images/Screenshot_2023-01-22_at_4.58.35_PM.png" width="75%" />

<img src="./images/Screenshot_2023-01-22_at_4.59.16_PM.png" width="75%" />

We can see the record count for how many rows are in our data set and the average record size. Scrolling down further we can see each of the columns that have been pulled out as part of the derived schema. The crawler has determined the data type for each column and provided a default column name. That creates the configuration of our crawler.

We now move on and use AWS Athena to define a new table schema that will register back into our data catalog. In our browser open a new tab and navigate to the Athena service. Within Athena, the first thing we'll point out is that we can see our data catalog from the Glue service. Here we can see censusdb and our table adult_data.
<figure>
<img src="./images/Screenshot_2023-01-22_at_4.59.47_PM.png" width="75%" />
 <figcaption style="color:black;text-align: center;">View Data</figcaption>
</figure>

<figure>
<img src="./images/Screenshot_2023-01-22_at_5.14.49_PM.png" width="75%" />
 <figcaption style="color:black;text-align: center;">Query Settings</figcaption>
</figure>

<figure>
  <img src="./images/Screenshot_2023-01-22_at_5.15.21_PM.png" width="75%" />
 <figcaption style="color:black;text-align: center;">Athna Query Editor</figcaption>
</figure>

<figure>
  <img src="./images/Screenshot_2023-01-22_at_5.15.57_PM.png" width="75%"/>
  <figcaption style="color:black;text-align: center;">Results of the Query</figcaption>
</figure>

<figure>
  <img src="./images/Screenshot_2023-01-22_at_5.18.16_PM.png" width="80%" />
  <figcaption style="color:black;text-align: center;">Schema of the table</figcaption>
</figure>

### Create new Table

We're now going to create a new table within our censusdb database. This table will be called adult_data_clean. It will have the columns: age, workclass, education, relationship, occupation, country and income_cat for category. We'll specify the location of our new table to again be an S3 in the same bucket but in this case in a folder called clean.data.

Let's now execute this create table statement by clicking the run query button. This would result in a new table being registered into the censusdb database which itself is registered within the Glue data catalog. Here you can see our query is running. Excellent, it looks like it's finished and we now have our new table registered and created back within our censusdb database.

The new table is called adult_data_clean. Let's take a look at the properties for this table. Here again we highlight the underlying location of this new table which is in our cloudacademy-emr-spark-data bucket in a new folder called clean.data. Let's now close this and jump back to our AWS Glue console where we should see our new table that we've just created show up in the data catalog.

Sure enough under tables we can see our new table called adult_data_clean. Okay we're now ready to set up our ETL job. Let's click on the jobs link. First up we can see that we don't have any job defined yet. So we'll click on the add job button. This takes us into the job properties for new ETL job. Here we'll set the name to be census-job.

Next we'll need to set up an IAM role. The IAM role will be used by the Glue service when it runs your ETL job. Let's jump over to the IAM console and set this up now. Within IAM click on the roles link. Next click the create role button. Here we'll choose the Glue service. This will be the service that will be allowed to use this role. Next we'll need to assign it some permissions. Click the Next: Permissions button.

We'll now assign permissions to this IAM role to allow the role access to S3 for read access into the bucket, permissions to cloud watch logs to be able to log the output of the ETL job as it's running and permissions to the Glue service itself, again to be able to run the ETL jobs. Jumping ahead in our role creation, we see the end result. For the purposes of this demonstration, we've added the following policies: a managed policy for S3 bucket access and two inline policies.

The first to allow the Glue service when it runs the ETL job to log out to cloud watch logs. And the second one is to run the ETL process itself. Jumping back into our ETL job setup, we now select the IAM role that we just created. Next we configure the job to run with the proposed script. The script will be auto-generated based on the remainder of the configuration that we apply within this job setup.

We'll leave the name of our script to be census-job. Next we'll need to choose the S3 path where our script will be stored. In this case we'll store it in cloudacademy-glue-scripts. We also need to specify an S3 temporary directory that may be used by the ETL job as it runs. Here we'll use cloudacademy-glue-temp. We'll leave the final two sections as defaults and proceed by clicking the next button at the bottom of the screen.

The next thing we need to do is setup and specify our input data source. This will be adult_data, the data table that resulted when the crawler ran. Next we specify the target of our ETL script. This will be the table that we created from within Athena: adult_data_clean. Clicking the next button takes us onto the mapping screen where we map the source columns to their target columns. Here there are a number of target columns that we don't need so we will delete these now. We then need to rearrange the mappings between the columns to suit our requirements for our machine learning script.

Let's update the mappings now. Column zero in the source table gets mapped to the age column in the target table. Column one in the source table gets mapped to... workclass in the target table. Column three in the source table gets mapped to education in the target table. Column five in the source table gets mapped to relationship in the target table. Column six in the source table gets mapped to occupation in the target table. And column 14 in the source table gets remapped to income_cat in the target table.

You can go ahead now by completing the mapping by clicking on the next button at the bottom of the screen. This takes us on to the final screen which is the review screen. We can accept our configuration by clicking the finish button. We are now taken into the script screen where AWS Glue has automatically built our pyspark script based on the job ETL configuration that we applied. On the lefthand side, we have a schematic of our ETL job that highlights the basic process.

We can zoom in and out of this to get a better picture of what our ETL job actually is built around. On the right-hand side, we can actually jump into the editor and begin to manipulate the script. Before we run our script, let's jump back over into Amazon Athena and run a query to ensure that our target table is empty. and has no rows or data within it. This is the adult_data_clean.

Let's click on the preview table link to run a query to see if there are any rows in our table. And here we can see that the table is indeed empty. There are zero records returned. Jumping back into AWS Glue, we'll save our job and scroll up to the top of the script. We will take a copy of the job_name parameter. This is a parameter that is expected to be passed on.

We click on the run job button, navigate down into the job parameters, paste in the value that we just copied and give it the value job1. We're now ready to run the job. Click the Run job button. This is now running our job, as can be seen by the run job status at the top of the screen, it's in progress. Down on the log screen when the job actually cooks off, we'll start to see logging coming out.

The job can take a few minutes to kick in. We'll jump ahead in the demonstration to the point where the logging is starting to come out. As can be seen here, the logging is starting to come out. The job is still running and the logging screen will update as the job progresses. We'll fast forward the demonstration near to the point where the ETL job completes.

While we're waiting for the job to fully complete, let's jump over into the S3 console. We'll refresh our bucket to see whether any new data has arrived. Here we can see our new folder: clean.data and within it the outputs of our ETL job. This is a good outcome and shows that our ETL job as configured is working. We'll now jump back into the Glue console to see whether our ETL job has completed. It looks like it's still running, in the meantime let's jump over into the Athena console.

We'll run a query against our target table to see whether it's being populated, which we know it has based on the results in the S3 bucket. And here we go, we can see the results of our ETL job that has populated our adult_data_clean table. We have the seven correctly named columns that we set up within our mapping.

Again let's jump back to the Glue console to see whether our ETL job has successfully completed. As can be seen now the ETL job has completed. We can scroll up and down through the logs as recorded in our cloud watch logs. We can close the script window and go back to the job listings. Here we can see the runs for any of the jobs that have been kicked off. We can navigate the history for each job.

We can see the run status, in this case this current job has succeeded. We can click on the log's link and navigate into the cloud watch logs and here will be a record for each of the runs that we perform for this ETL job. It is the same logging that we saw before in the script logs pane.

Okay that concludes the second part of this demonstration. Go ahead and close this lecture and we'll see you shortly in the next one.