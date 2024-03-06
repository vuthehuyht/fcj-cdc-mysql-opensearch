---
title : "Tạo role"
date :  "`r Sys.Date()`" 
weight: 5
chapter: false
pre: "<b> 2.5 </b>"
---

1. Chuyển hướng trang **IAM**
- Trên ô tìm kiếm, tìm và chọn **IAM**
![2.5-step-1](../../../images/2.5-step-1.png)

2. Tạo giao diện **IAM**
Chọn **Roles**
![2.5-step-2](../../../images/2.5-step-2.png)

3. Chọn **Create role**
![2.5-step-3](../../../images/2.5-step-3.png)

4. Tạo role cho eks cluster
- **Trusted entity type**: chọn "AWS service"
- **Use case**: tìm và chọn **eks**
- Chọn **EKS - Cluster**

![2.5-step-4-a](../../../images/2.5-step-4-a.png)
![2.5-step-4-b](../../../images/2.5-step-4-b.png)
Chọn **Next**
![2.5-step-4-c](../../../images/2.5-step-4-c.png)
Điền tên role, kiểm tra lại và chọn **Create role**
![2.5-step-4-d](../../../images/2.5-step-4-d.png)
![2.5-step-4-e](../../../images/2.5-step-4-e.png)

5. Làm tương tự để tạo role cho node group
- Trên ô tìm kiếm, tìm và chọn **IAM**
![2.5-step-1](../../../images/2.5-step-1.png)
- Chọn **Roles**
![2.5-step-2](../../../images/2.5-step-2.png)
- Chọn **Create role**
![2.5-step-3](../../../images/2.5-step-3.png)
- Thiết lập role
    + **Trusted entity type**: chọn "AWS service"
    + **Use case**: tìm và chọn **ec2**
    + Chọn **Next**
![2.5-step-5-a](../../../images/2.5-step-5-a.png)
![2.5-step-5-b](../../../images/2.5-step-5-b.png)
- Tìm và chọn **AmazonEKSWorkerNodePolicy**
![2.5-step-5-c](../../../images/2.5step-5-c.png)
- **Role name**: Điền `AmazonEKSNodeRole` và chọn **Create role*
![2.5-step-5-d](../../../images/2.5-step-5-d.png)
![2.5-step-5-e](../../../images/2.5-step-5-e.png)
