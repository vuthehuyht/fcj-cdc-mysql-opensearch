---
title : "Create EC2"
date :  "`r Sys.Date()`" 
weight: 4
chapter: false
pre: "<b> 2.4 </b>"
---

1. Creating **Security Group** for EC2

On the search box, search and choose "Security Groups"
![2.4-step-1](../../../images/rds-1.png)

At the navigation interface, choose **Create security group**
![2.4-step-1](../../../images/rds-2.png)

- At **Security group name**, enter `cdc-server-sg`
- At **VPC**, choose `vpc-cdc`
![2.4-step-1](../../../images/ec-1.png)

At **Inbound rules**, choose **Add rule** và enter information:
- Type: `SSH`
- Source: **0.0.0.0/0**
![2.4-step-1](../../../images/ec-2.png)

2. Creating EC2

On the left navigation bar, choose **Instance** -> **Lanch Instances**
![2.4-step-1](../../../images/ec-3.png)

- **Name**, Enter `cdc-listener`
- **OS**, choose **Ubuntu**
![2.4-step-1](../../../images/ec-4.png)

Tạo mới Key pair với name `cdc-kp`
Create new key pair with name `cdc-kp`
![2.4-step-1](../../../images/ec-5.png)

- At **Networking settings**, choose **Edit**
- Select the created information as shown in the image
![2.4-step-1](../../../images/ec-6.png)

Last, click **Lanch instance**
