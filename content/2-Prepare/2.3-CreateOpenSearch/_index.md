---
title : "Creating OpenSearch service"
date :  "`r Sys.Date()`" 
weight: 3
chapter: false
pre: "<b> 2.3 </b>"
---
In the search box, search and choose **Amazon OpenSearch Service**
![os](../../../images/os-1.png)

At interface, choose **Create domain**
![os](../../../images/os-2.png)

- At **Domain name**, enter `cdc-opensearch`
- At **Domain creation method**, choose **Standard create**
![os](../../../images/os-3.png)

- At **Templates**, choose **Dev/Test**
- At **Deployment options**, choose **Domain without standby**
![os](../../../images/os-4.png)

- At **Availability Zone(s)**, choose **1-AZ**
- At **Engine options**, choose version **6.8**
![os](../../../images/os-5.png)

- **Instance family**: choose **General purpose**
- **Instance type**: choose **t3.small.search**
- **Number of nodes**: enter `1`
![os](../../../images/os-6.png)

- **Network**, choose **Public access**
- **IP address type**: choose **Dual-stack mode**
- **Fine-grained access control**, tick **Enable fine-grained access control**
- **Master user**, choose **Create master user**
- **Master username**, enter `admin`
- **Master password** and **Confirm master password**, choose `Huyvt2609@`
![os](../../../images/os-7.png)

**Access policy**, choose **Only use fine-grained access control**
![os](../../../images/os-8.png)

**Note**: The service creation process will take quite long time, about 15 minutes.
