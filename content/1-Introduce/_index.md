---
title : "Introduce"
date :  "`r Sys.Date()`" 
weight : 1
chapter : false
pre : " <b> 1. </b> "
---

#### Overview

In this lab, we will perform collecting change in data from RDS for MySQL to OpenSearch to be able to serve different requirements. This lab is just the most base, you can also improve or customize it according to different requirements to make it mosit suitable.

The following method flow
![CDC Flow](../../images/cdc-flow.png)

- We create, update or delete record with RDS for MySQL
- EC2 run code that listen for record creation, update or deletion event and push the content of event into Kinesis
- The data stream added to Kinesis also called as Lambda trigger with event content input add Kinesis
- Lambda push that content into OpenSearch and return the URL access the content

#### Content

1. [Introduce](/1-introduce)
2. [Prepare](/2-prepare)
3. [Deployment](/3-deployment)
4. [Cleanup](/4-cleanup/)

Chúng ta cùng bắt tay làm nào. Let's go!!!!