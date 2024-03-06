---
title : "Tạo EKS cluster"
date :  "`r Sys.Date()`" 
weight: 6
chapter: false
pre: "<b> 2.6 </b>"
---

1. Chuyển hướng trang tạo EKS
- Trên ô tìm kiếm, tìm và chọn **EKS**
![2.6-step-1](../../../images/2.6-step-1.png)

2. Tạo giao diện **Amazon Elastic Kubernetes Service**
Chọn **Create cluster**
![2.6-step-2](../../../images/2.6-step-2.png)

3. Thiếp lập cluster
- **Name**: điền `fcj-devops-cluster`

- **Cluster service role**: gõ và chọn `eksClusterRole`,
![2.6-step-3-b](../../../images/2.6-step-3-b.png)
- Các mục khác để mặc định, kéo xuống và chọn **Next**
![2.6-step-3-c](../../../images/2.6-step-3-c.png)
- **Cluster endpoint access**: để dễ dàng, ta chọn **Public**
![2.6-step-3-d](../../../images/2.6-step-3-d.png)
- Chọn **Next**
![2.6-step-3-e](../../../images/2.6-step-3-e.png)
- Chọn **Next**
![2.6-step-3-g](../../../images/2.6-step-3-g.png)
- Chọn **Next**
![2.6-step-3-h](../../../images/2.6-step-3-h.png)
- Kiểm tra lại và chọn **Create**
![2.6-step-3-i](../../../images/2.6-step-3-i.png)
**Lưu ý**: Quá trình tạo cluster xong sau 10 phút.
