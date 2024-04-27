---
title : "Cleanup"
date :  "`r Sys.Date()`" 
weight: 4
chapter: false
pre: "<b> 4. </b>"
---

#### Delete Kinesis Data Stream
- Access to Kinesis page
- Choose `cdc-data-stream`
- Choose Actions -> Delete

#### Delete RDS
- Access Amazon RDS
- On the left navigation bar, choose Databases
- Select the DB Instance related to the lab
- Click Actions.
- Click Delete
- Untick Create final snapshot? và choose I acknowledge that upon instance deletion, automated backups, including system snapshots and point-in-time recovery, will no longer be - available
- Enter delete me in the field.
- Click Delete

#### Delete EC2
- Access EC2 page
- Choose cdc-listener
- Choose Instance state -> Terminate instance

#### Delete Opensearch
- Access OpenSearch page
- Choose Delete
- Enter delete and click Xoá

#### Delete Lambda
- Run CMD in repo clone, enter `sam delete` and enter `Y` if required

#### Delete VPC
- Access to VPC page
- Choose `cdc-vpc`
- Choose Actions -> Delete VPC
- Enter delete and click Delete

