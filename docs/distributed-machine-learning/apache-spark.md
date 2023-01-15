# Apache Spark

In this lecture, we'll introduce you to Apache Spark. Apache Spark is an opensource cluster computing framework, used to provide lightning fast distributed computation. Apache Spark can be used to provision a cluster of machines, configured in a manner that provides a general purpose distributed computing engine, capable of processing very large amounts of data.

![dml](./images/Screenshot%202023-01-07%20at%201.15.10%20PM.png)

When using Spark, your datasets are partitioned and spread across the Spark cluster, allowing the cluster to process the data in parallel. Apache Spark is designed to process data in memory, and this alone really differentiates it from alternative distributed computing platforms. By storing and processing data and memory, a huge performance boost is gained. Apache Spark itself is built in Scala.

Scala is a typesafe JVM language that incorporates both object orientated, and functional programming into an extremely concise, logical and extraordinary powerful language. 

As we'll see later in this course, Apache Spark can be easily and quickly launched on top of an Amazon EMR cluster, through some simple configuration options. With this point in mind, you can start to see why EMR and Spark provide an excellent platform for processing large datasets. Central to the Apache Spark technology stack, is the Spark core.

## Spark Core

The Spark core is the foundation layer, and provides distributed task dispatching, scheduling and basic IO functionalities. The Spark core is exposed through an API, as can be seen in this diagram.

![dml](./images/Screenshot%202023-01-07%20at%201.15.36%20PM.png)

Interfaces to the API are available in Scala, Python, Java, and R. The Spark platform comes with in-built modules for SQL, streaming, machine learning, and graphs. In this course, we'll focus on the MLlib module that provides us with our distributed machine learning capabilities.

## MLLib

The demo that we give later in this course, will involve us building a Scala MLLib implemented decision tree, to train a decision tree model. 

![dml](./images/Screenshot%202023-01-07%20at%201.15.53%20PM.png)

Apache Spark is built using a master slave type infrastructure.

![dml](./images/Screenshot%202023-01-07%20at%201.16.27%20PM.png)

The master node acts as a central controller and coordinator. This slide illustrates the main software components within the Spark master slave architecture.

When we launch an EMR cluster with Spark enabled, AWS takes care of the installation of Spark. This is the great thing about running Spark on top of EMR. You get the installation and deployment of Spark done automatically for you. The ability to launch a working Spark environment, hosted in AWS, on an EMR cluster, is both very simple and quick, allowing you to focus and maintain your energies into the data science itself.

## Components of Spark

Regardless of this, we'll quickly go over each of the main components, to ensure that you have a basic understanding of the deployed Spark topology.

### Driver

The driver is the process where the main method runs. 

![dml](./images/Screenshot%202023-01-07%20at%201.18.13%20PM.png)

First, it converts your user program into tasks, and after that it schedules the tasks on the executors. The driver program communicates with the cluster manager, to distribute tasks to the executors. 

### Cluster Manager

The cluster manager, as the name indicates, manages the cluster.
Spark has the ability to work with a multitude of cluster managers, including YARN, Mesos, and a standalone cluster manager. 

![dml](./images/Screenshot%202023-01-07%20at%201.18.32%20PM.png)

By default, EMR will launch Spark with YARN, as the cluster manager of choice. Worker nodes are the machines where the actual work is performed. 

### Worker Nodes
Worker nodes host Spark executor processes. 

![dml](./images/Screenshot%202023-01-07%20at%201.18.32%20PM.png)

An EMR core node is the equivalent of a Spark worker node.

### Executors

Executors are the individual JVM processes that are launched within a worker. An executor process has the responsibility of running an individual task, for a specific Spark job. 

![dml](./images/Screenshot%202023-01-07%20at%201.43.28%20PM.png)

They are launched at the beginning of a Spark application, and typically run for the entire lifetime of an application. 

![dml](./images/Screenshot%202023-01-07%20at%201.43.54%20PM.png)

Once the task is completed, the executor sends the results back to the driver.

Executors also provide a memory caching of local data. 
A task is a unit of work that the driver program sends to the executor JVM process to be launched.

### SparkContext

A SparkContext is the entry point to the Spark core, and for any work you wish to submit into the Spark cluster, 

![dml](./images/Screenshot%202023-01-07%20at%201.44.19%20PM.png)

a SparkContext provides you an access point into the Spark execution environment, and acts as the controller of your Spark application.

## Data Abstractions

Apache Spark has several different but related data abstractions. 

![dml](./images/Screenshot%202023-01-07%20at%202.21.14%20PM.png)

Let's briefly cover off each of the different abstractions, and what their key benefits are.

### RDD

An RDD, or Resilient Distributed Dataset, is the original data abstraction that Spark used, and still uses. An RDD provides a fault tolerant collection of items, that can be computed on in parallel. 

![dml](./images/Screenshot%202023-01-07%20at%202.22.03%20PM.png)

It is Spark's representation of a dataset, partitioned over a cluster of machines.

An API is provided, which enables you to manipulate it. RDD's can be created from various data formats, and sources such as CSV files, JSON files, and/or databases via JDBC connections.

### DataFrames

DataFrames were next introduced. DataFrames organize data into named columns, similar to a database table. A key objective of DataFrames is to make dataset processing easier and more accessible to general users.

![dml](./images/Screenshot%202023-01-07%20at%206.13.06%20PM.png)

Later on in our demo, we'll leverage Spark DataFrames to access CSV stored data. The last abstraction, the DataSet, builds on the success of the DataFrame, by providing an additional typesafe, object oriented programming interface, that provides access to a strongly typed, immutable collection of objects, that are mapped to a relational schema.

### DAG

Spark features an advanced Directed Acyclic Graph, or DAG for short. Each Spark job created results in a DAG.

![dml](./images/Screenshot%202023-01-07%20at%206.14.24%20PM.png)

The DAG represents a sequence of task stages to be performed on the cluster. DAGs created by Spark can contain any number of stages. As can be seen on the slide, your Spark code gets converted into a DAG, which in turn is passed to the DAG scheduler. The DAG scheduler splits the graph into stages of tasks, and distributes them as task sets to the task scheduler on the cluster manager. Finally, the individual tasks are delivered to an assigned executor process, on a particular worker node.

## Summary

Later on in this course, when we build our demo, you'll see that all of this internal data management is taken care of for us. We simply as data scientists create our data scripts, and submit as jobs to Spark. Spark performs all of the above under the hood.

That concludes this lecture. Go ahead an close this, and we'll see you soon in the next lecture, where we introduce you to Spark MLlib. MLlib is Apache Spark's scalable machine learning library.
