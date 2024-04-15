---
title : "Tạo OpenSearch service"
date :  "`r Sys.Date()`" 
weight: 3
chapter: false
pre: "<b> 2.3 </b>"
---

Tại ô tìm kiếm, tìm và chọn **Amazon OpenSearch Service**
![os](../../../images/os-1.png)

Tại giao diện, chọn **Create domain**
![os](../../../images/os-2.png)

- Tại **Domain name**, điền `cdc-opensearch`
- Mục **Domain creation method**, chọn **Standard create**
![os](../../../images/os-3.png)

- Mục **Templates**, chọn **Dev/Test**
- Mục **Deployment options**, chọn **Domain without standby**
![os](../../../images/os-4.png)

- Mục **Availability Zone(s)**, chọn **1-AZ**
- **Engine options**, chọn version **6.8**
![os](../../../images/os-5.png)

- **Instance family**: chọn **General purpose**
- **Instance type**: chọn **t3.small.search**
- **Number of nodes**: nhập `1`
![os](../../../images/os-6.png)

- **Network**, chọn **Public access**
- **IP address type**: chọn **Dual-stack mode**
- **Fine-grained access control**, tick **Enable fine-grained access control**
- **Master user**, chọn **Create master user**
- **Master username**, điền `admin`
- **Master password** và **Confirm master password**, điền `Huyvt2609@`
![os](../../../images/os-7.png)

**Access policy**, chọn **Only use fine-grained access control**
![os](../../../images/os-8.png)

**Lưu ý**: Quá trình tạo service sẽ diễn ra khá lâu, khoảng 15 phút.
