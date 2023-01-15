# Amazon EMR: Elastic Map Reduce

## Introduction

In this lecture, we'll introduce you to Amazon's Elastic MapReduce Service or EMR for short and how it can be launched with Apache Spark installed to provide a powerful distributed computing platform for data analytics and machine learning. Amazon EMR provides a managed Hadoop frame loop that makes it easy, fast and cost effective to process vast amounts of data.

| ![emr overview](./images/Screenshot%202023-01-14%20at%2012.58.48%20PM.png) | 
|:--:|
| *AWS EMR*|

Aside from running a purchase barc on top of EMR, you can also run other popular distributed frameworks such as H-base, Presto and Flink.

| ![emr usecases](./images/Screenshot%202023-01-14%20at%2012.59.00%20PM.png) | 
|:--:|
| *AWS EMR Usecases*|

| ![emr ecosystem](./images/Screenshot%202023-01-14%20at%2012.59.00%20PM.png) | 
|:--:|
| *EMR Ecosystem*|

Amazon EMR can be used to perform: log analysis, web indexing, ETL, financial forecasting, bioinformatics and, as we've already mentioned, machine learning. Amazon EMR, together with Spark, simplifies the task of cluster and distributed job management.

| ![emr ecosystem](./images/Screenshot%202023-01-14%20at%2012.59.59%20PM.png) | 
|:--:|
| *EMR Ecosystem*|

A rich ecosystem of big data processing applications is available to cherry pick from. You can customize the installation of applications that compliment the core EMR Hadoop application. Again, later on in this course, you will get to see us launch an EMR cluster, whereby we configure it to launch with both Spark and Zeppelin installed. When you launch an EMR cluster, you need to define and allocate compute resources to three different nodes: Master, Core and Task.

| ![emr resizable clusters](./images/Screenshot%202023-01-14%20at%201.01.53%20PM.png) | 
|:--:|
| *EMR Resizable Clusters*|

Let's go through each of these now. The Master Node. Each EMR cluster will have exactly one Master Node. The Master Node manages the cluster. This node coordinates the distribution of jobs and data to the core and task nodes. The Master Node runs the primary Hadoop demons like, Name Node, Job Trigger and Resource Manager.

The Core Node. Job tasks are performed on a collection of core nodes. Data is stored using the Hadoop distributed file system, HDFS. The Core Node runs the Data Node and task tracker demons. The Task Node. Task nodes are optional. They can also run tasks. The Task Node only runs the task tracker demon. One of the really great features available in designing and operating an EMR cluster is the ability to resize it.

You can adjust the number of Amazon EC2 instances, available to an EMR cluster, automatically or manually, in response to workloads that have varying demands. This allows you to ensure your cluster is always running optimally with respect to both cost and performance. Spark running on an email cluster can connect to multiple data storage locations.

Various connectors exist to provide this flexibility, such as: DynamoDB via the EMR DynamoDB Connector, sequel databases via JDBC connections and/or S3 via the EMR file system.

| ![emr storage connectivity](./images/Screenshot%202023-01-14%20at%201.02.28%20PM.png) |
|:--:|
| *EMR Storage Connectivity*|

In the next section we look at the networking options for EMR.

## Networking Options

Various networking options are available when it comes to deploying your EMR cluster. Most common deployments involve deploying into a VPC, Virtual Private Network. You can either deploy into either a public subnet or private subnet.

Deploying into a public subnet, as seen on this slide, provides a more simple solution but with limited security. In this configuration, the EMR nodes are provisioned with public IP addresses.

This configuration might be sufficient for some solutions in which the data in your email cluster isn't overly sensitive.

| ![emr networking](./images/Screenshot%202023-01-14%20at%201.03.24%20PM.png) |
|:--:|
| *EMR Networking - Connecting to Public Subnet*|

But as we'll see on the next slide this solution can be improved on and made more secure by instead deploying the cluster into a private subnet. In this configuration, we can connect to the web interfaces of the various starter applications hosted on the EMR Master Node via the VPC assigned public IP address. To ensure this configuration is secure,

| ![emr networking](./images/Screenshot%202023-01-14%20at%201.26.11%20PM.png) |
|:--:|
| *EMR Networking - Connecting to Private Subnet*|

we would ensure to control inbound connections through the appropriate use of security groups and/or network ACLs.

Alternatively, we can perform SSH port forwarding from the client host to the EMR Master Node for a specific application port. In this design, the security of the networking is improved by deploying the EMR cluster into a private subnet.

| ![emr networking](./images/Screenshot%202023-01-14%20at%201.27.47%20PM.png) |
|:--:|
| *EMR Networking - SSH Port Forwarding*|

To support this type of setup, ANAD instances configured for outbound internet access and a VPC in point is configured to provide private access from the EMR cluster to the S3 service.

Finally, to access the EMR cluster itself from outside of the VPC, a bastion host is provided to act as the jump host. In this configuration we would use a combination of a local web proxy to redirect all traffic through the bastion host and an SSH tunnel from the local host to the bastion host. With this configuration active, we can use the client browser to gain access to the web interface via the EMR Master Node private IP address and the respective application port number.

If we wish, we can consider connecting our VPC back to our corporate networks. In doing so we can access sensitive data that has to remain within our om-prim networks. The connectivity can be achieved either via an IP Sec VPN connection or through a direct connect connection. Either way, this connectivity will allow the VPC hosted EMR cluster access to data sets located within our om-prim networks.

This style of design would also allow us to connect directly to the web interfaces of the various data applications on the EMR Master Node via its private IP. Without need for an SSH port forwarding, etc. Launching an EMR cluster can be performed either with an AWS web console or from the command line via the AWSCRLI.

Regardless of method, both achieve the same outcome in much the same way when it comes to providing the configuration. The AWS EMR service console provides both a Quick Options and an Advanced Options approach. The difference being that the Advanced Options screen gives you finer control over the various configuration options.

Let's now take a look at each of these. As you can see, the Quick Options screen is composed of four main sub-sections.

![create cluster quick option](./images/Screenshot%202023-01-14%20at%201.31.11%20PM.png)
*Create Cluster: Quick Option*

They are: the General Configuration, Software Configuration, Hardware Configuration and Security and Access. General Configuration is self-explanatory except for the launch mode. The launch mode can either be set to, cluster or step execution. This options specifies whether to launch an ongoing cluster or a transient cluster.


If you set it to cluster mode, EMR will launch a cluster that remains up and running until you proactively terminate it yourself. If you set it to step execution mode, EMR will launch a cluster, perform and execute all of the added steps and, upon completion, terminate itself. Software Configuration requires you to select the software version of EMR itself with a list of presets to select from.

Next, within the Applications section, there are four pre-configured groupings of various big data processing applications. Hardware Configuration requires you to specify the EC2 instance type that will be used for both the Master and Core nodes. Note, the deployment here will take place in the default VPC of the current AWS account.

Security and Access. You can optionally specify an EC2 Key Pair. By doing so, will allow you to SSH into any of the nodes. You can also configure either default or custom IM role positions for both the EMR role and/or EMR instance profile. Note, that the difference here is that the EMR role is used by the EMR service itself whereas the ERM instance profile is assigned to the EC2 instances within the EMR cluster.

## Advanced Options for EMR Cluster

We now move onto the advance options launching approach. This approach has the same four sub-sections but in this case has separate screens for each and stitched all together in a wizard-style manner. The first screen covers the Software and Steps section. This screen allows you select a custom release of the EMR software.

| ![create cluster quick option](./images/Screenshot%202023-01-14%20at%201.32.15%20PM.png) | 
|:--:|
| *Create Cluster: Advanced Option - General and Software Config*|

By default, the latest and most recent version is always selected. Next, you have the option of cherry picking additional software to be installed on top of the EMR cluster. In the example here, we have additionally added both Zeppelin and Spark into the mix. Aside from these two packages, the rest were selected for us by default. Next we have the ability to enable AWS Glue data catalog settings. If we are using the AWS Glue service for ETL purposes, then we can integrate our EMR cluster with the respective AWS Glue data catalog and enable Hive and/or Spark to use it for metadata storage.

| ![create cluster quick option](./images/Screenshot%202023-01-15%20at%2010.10.09%20AM.png) | 
|:--:|
| *Create Cluster: Advanced Option - Hardware Configuration*|

This is a neat feature and one for which we will use in our machine learning demonstration lecture. Under Software Settings, we can specify configuration properties that will be used to control the behavior of the various applications that are deployed. Finally, a Step is a unit of work you submit to the cluster. For instance, a Step might contain one or more Hadoop or Spark jobs.

The second screen covers the Hardware section. This screen allows you to specify the style of deployment, the VPC network and subnet into which the EMR cluster is deployed. You increase or decrease the route device EBS volume size of which you should do depending on how many applications you configured to be deployed on the previous screen.

For each EMR node, you can specify a particular EC2 instance type in purchasing option either On Demand or Spot. You also have the ability here to deploy Task nodes. The third screen covers the general cluster settings section. This screen allows you to specify the name of your EMR cluster and to enable or disable logging, debugging and termination protection. EMR cluster tags can be supplied.

## Tags for Nodes

Tags supplied here are propagated down to all of the EC2 instances launched as part of the cluster. You can specify a customer AMI ID, if you so wish to do so. And finally, you can specify custom boot strapping scripts to install other applications or required packages. The fourth and final screen covers the Security section. This screen allows you to specify the EC2 key pair to be configured on the cluster instances. This again, will give you SSH access onto these instances.

You can control the cluster visibility by enabling or disabling the cluster visibility setting. The IN role permission settings are the same as they were in the quick screen options. You have the ability to configure a security configuration policy that controls things like: data encryption at rest, and transit, and/or authentication and authorization.

And finally, you can specify custom security groups per EMR node type. EMR comes with an option to install Zeppelin when launching your EMR cluster. If you're more inclined to use Jupyter Edge or Notebook Manager, then you can do so by installing Jupyter through the EMR bootstrapping mechanism. In our demonstration later on, we'll use Zeppelin to author our decision tree machine learning example. In doing so, we'll be able to perform our example in an interactive session.

## Summary

That concludes our lecture on EMR. In the next lecture, we'll introduce you to AWS Glue. Here, we'll learn about how to use AWS Glue to perform ETL on our datasets, to prepare them for machine learning. Go ahead and close this lecture and we'll see you shortly in the next one.