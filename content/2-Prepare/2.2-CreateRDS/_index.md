---
title : "Creating RDS"
date :  "`r Sys.Date()`" 
weight: 2
chapter: false
pre: "<b> 2.2 </b>"
---

1. Creating **Security Group** for RDS

Tại ô tìm kiếm, tìm và chọn "Security Groups"
On the search bar, search and choose "Security Groups"
![2.4-step-1](../../../images/rds-1.png)

On navigation interface, choose **Create security group**
![2.4-step-1](../../../images/rds-2.png)

- On **Security group name** section, enter `cdc-mysql-sg`
- On **VPC**, choose `vpc-cdc`
![2.4-step-1](../../../images/rds-3.png)

On **Inbound rules** item, choose **Add rule** and enter informations:
- Type: `MySQL/Aurora`
- Source: **0.0.0.0**
![2.4-step-1](../../../images/rds-4.png)

Cuối cùng, chọn **Create security group** để tạo SG.
Lastly, click **Create security group** to create.

2. Creating **Parameter Group** for RDS MySQL

At left navigation bar of the RDS interface, choose **Parameter groups** -> **Create parameter group**
![2.4-step-1](../../../images/rds-5.png)

- At **Parameter group family**, choose **mysql8.0**
- At **Group Name**, enter `cdc-group`
- Choose **Create**
![2.4-step-1](../../../images/rds-6.png)

3. Creating RDS for MySQL

Navigate to database creation page
- On navigation bar, search and choose **RDS**
![2.4-step-2](../../../images/2.4-step-1.png)

At RDS interface
- Choose **Create database**
![2.4-step-2](../../../images/2.4-step-2.png)

Database configuration
- **Choose a database creation method**: choose **Standard create**
- **Engine options**: choose **MySQL**
- **Templates**: choose **Free Tier**
- **DB instance identifier**: enter `cdc-database`
- **Master password**: enter `Huyvt2609`
- **Confirm master password**: enter `Huyvt2609`
- **DB instance class**: choose db.t2.micro
- **Public access**: choose **Yes**
- **VPC security group (firewall)**: choose `cdc-rds-sg`
- At **Additional configuration** item
    + **DB parameter group**: choose `cdc-group`
    + **Encryption**:  untick **Enable encryption**
    + **Maintenance**: untick **Enable auto minor version upgrade**
- Other items are left as default

![2.4-step-1](../../../images/rds-7.png)
![2.4-step-1](../../../images/rds-8.png)
![2.4-step-1](../../../images/rds-9.png)
![2.4-step-1](../../../images/rds-10.png)
![2.4-step-1](../../../images/rds-11.png)
![2.4-step-1](../../../images/rds-12.png)
![2.4-step-1](../../../images/rds-13.png)
![2.4-step-1](../../../images/rds-14.png)

**Note**: The database creation process will take quite a long time, about 10 minutes.

After creation done, we need to verify `MySQL bin log` is enabled
- Connecting to RDS by terminal: `mysql -h rds_enpoint -u admin -p`, then enter password
- Enter `show global variables like "log_bin`, if the result get **log_bin ON**, it will be OK

