---
title : "Tạo EC2"
date :  "`r Sys.Date()`" 
weight: 4
chapter: false
pre: "<b> 2.4 </b>"
---

1. Tạo **Security Group** cho EC2

Tại ô tìm kiếm, tìm và chọn "Security Groups"
![2.4-step-1](../../../images/rds-1.png)

Tại giao diện vừa chuyển hướng, chọn **Create security group**
![2.4-step-1](../../../images/rds-2.png)

- Tại ô **Security group name**, nhập `cdc-server-sg`
- Tại ô **VPC**, chọn `vpc-cdc`
![2.4-step-1](../../../images/ec-1.png)

Tại mục **Inbound rules**, chọn **Add rule** và điền các thông tin như sau:
- Type: `SSH`
- Source: **0.0.0.0/0**
![2.4-step-1](../../../images/ec-2.png)

2. Tạo EC2

Trên thanh điều hướng bên trái, chọn **Instance** -> **Lanch Instances**
![2.4-step-1](../../../images/ec-3.png)

- **Name**, nhập `cdc-listener`
- **OS**, chọn **Ubuntu**
![2.4-step-1](../../../images/ec-4.png)

Tạo mới Key pair với name `cdc-kp`
![2.4-step-1](../../../images/ec-5.png)

- Tại mục **Networking settings**, chọn **Edit**
- Chọn thông tin đã tạo như trong hình
![2.4-step-1](../../../images/ec-6.png)

Cuối cùng, chọn **Lanch instance** để tạo EC2
