---
title : "Preparation"
date :  "`r Sys.Date()`" 
weight: 2
chapter: false
pre: "<b> 2. </b>"
---

Before getting started to deploy this method, let's take a look some of the services used in the lab.

#### AWS RDS
**AWS RDS** is the one of typical services of AWS, used very much and popular. In the lab, RDS will be the beginning point.

#### AWS Lambda
**AWS Lambda** is a serverless computing service, an event-driven (it means when request coming, service works), help us run code for almost any type of application or backend service without needing to provision or manage server. **AWS Lambda** can be enabled from more than 200+ AWS services and application as SaaS and we only need to pay as we use. 

#### AWS EC2
EC2 is cloud computing insfrastructure provided by AWS. In this lab, we build EC2 to run Python code that listen data change events from RDS then push them to Kinesis.

#### AWS VPC
VPC is a service that allows AWS resources to be created in an isolated virtual network and completely control by user.

#### AWS Kinesis Data Stream
AWS Kinesis is a service that helps you to build an application capable of analyzing and processin data in real time, capable of receiving and storing up to terrabytes of data in an hour, capable of collecting data from different sources like logs, live stream...

Now, AWS Kinesis consists of 4 components:
- **Kinesis Data Streams**: collecting, processing and storing data stream
- **Kinesis Data Firehorse**: loading data stream into AWS data store
- **Kinesis Data Analytics**: analyzing data stream with SQL or Apache Flink
- **Kinesis Video Stream**: collecting, processing and storing data stream

In this lab, we use **Kinesis Data Stream** to collect and process data then push them to OpenSearch.

#### AWS OpenSearch
**AWS OpenSearch** is a distributed, community-driven, Apache 2.0-licensed, 100% open source suite of distributed search and analytics tools used for a variety of use cases such as real-time application monitoring, logs and site search. OpenSearch provides a scalable system for quickly accessing and responding to large volumes of data with built-in visualization tools, OpenSearch Dashboards, that help users easily explore data their. OpenSearch is powered by the Apache Lucene search library and it supports a wide range of search and analysis features, such as k-nearest neighbor (KNN) search, SQL, Anomaly Detection, Machine Libraries Learning Commons, Trace analysis, full-text search, and more.

#### Content

1. [Creating VPC](/2-prepare/2.1-createvpc/)
2. [Creating RDS for MySQL](2-prepare/2.2-createrds/)
3. [Creating OpenSearch](/2-prepare/2.3-createopensearch/)
4. [Creating EC2](/2-prepare/2.4-createec2/)
5. [Creating Kinesis Data Stream](/2-prepare/2.5-createkinesisdatastream/)
