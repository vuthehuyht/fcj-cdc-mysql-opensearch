---
title : "Thêm node group vào cluster"
date :  "`r Sys.Date()`" 
weight: 7
chapter: false
pre: "<b> 2.7 </b>"
---

1. Chuyển hướng trang tạo EKS
- Trên ô tìm kiếm, tìm và chọn **EKS**
![2.6-step-1](../../../images/2.6-step-1.png)

2. Tạo giao diện **Amazon Elastic Kubernetes Service**
Chọn cluster vừa tạo
![2.7-step-2](../../../images/2.7-step-2.png)

3. Chọn mục **Compute**
![2.7-step-3](../../../images/2.7-step-3.png)

4. Kéo xuống, chọn **Add node group**
![2.7-step-4](../../../images/2.7-step-4.png)

5. Thiết lập node group
- **Name**: điền `node-1`
- **Node IAM role**: tìm và chọn `AmazonEKSNodeRole`
![2.7-step-5-a](../../../images/2.7-step-5-a.png)
- Chọn **Next**
![2.7-step-5-b](../../../images/2.7-step-5-b.png)
- **Instance types**: tìm và chọn `t2.small`
![2.7-step-5-c](../../../images/2.7-step-5-c.png)
- **Node group scaling configuration**: toàn bộ điền 1
    + **Desired size**: số lượng ec2 sẽ được khởi tạo chạy
    + **Minimum size**: số lượng ec2 chạy tổi thiểu
    + **Maximum size**: số lượng ec2 chạy tối đa
![2.7-step-5-d](../../../images/2.7-step-5-d.png)
- Chọn **Next**
![2.7-step-5-e](../../../images/2.7-step-5-e.png)
- Kiểm tra lại và chọn **Create**
![2.7-step-5-f](../../../images/2.7-step-5-f.png)
