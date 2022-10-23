# sparkStreaming 
The repository includes the script for streaming kafka data from spark and writing it to cassandra (AWS Keyspaces). Also it comprises Terraform scripts for deploying EMR cluster and AWS Keyspace (AWS managed Apache Cassandra).

<img width="916" alt="image" src="https://user-images.githubusercontent.com/77616210/197401087-57ca206b-40c1-452a-86a8-24e036b75885.png">


# Assumptions
Data stream is published to the Kafka topic - babbel

# Key Requirements
Compnonents used in the architecture should be SCALABLE and FAULT TOLERANT.

# Requirements
As shown in the architecture diagram the pipeline requires AWS EMR cluster where we can deploy and run our streaming application, and also an amazon managed Cassandra database which will support update mode in write stream.

Why Spark?
Spark is a highly scalable, configurable and fault tolerant big data processing framework. Additionally structured streaming of spark supports windowing aggregations within specified time period which can be easily configured based on our requirements. In our case time period for state retention is 7 days.
With respect to scalability we can integrate auto-scaling policy of AWS EMR to terraform script through which we can cater to the increasing traffic and also we pay for the resources we use.

Why AWS Keyspace (Cassandra)?
