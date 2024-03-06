---
title : "Giới thiệu"
date :  "`r Sys.Date()`" 
weight : 1
chapter : false
pre : " <b> 1. </b> "
---

#### Tổng quan

Các bạn có thể tham khảo pattern này để áp dụng cho dự án phát triển bằng Spring Framework hoặc có thể tuỳ chỉnh theo yêu cầu của dự án hay yêu cầu mà các bạn đề ra. Flow cơ bản của pattern như sau: đóng gói ứng dụng Java thành image, scan bảo mật image, tải image lên Amazon ECR và cuối cùng là triển khai image lên Amazon EKS. Pattern này cũng rất hữu ích khi muốn chuyển từ monolithic sang kiến trúc microservices lên EKS hoặc ECS, giúp giám sát và quản lý toàn bộ vòng đời của ứng dụng Java, bảo đảm mức độ tự động hoá cao hơn và tránh gặp lỗi.

![GitOps in AWS](../../images/gitops-in-aws.png)

#### Nội dung

1. [Giới thiệu](/1-introduce)
2. [Các bước chuẩn bị](2-prepare)
3. Tạo EKS cluster
4. Tạo RDS
5. Tạo luồng CI/CD
6. Tạo SNS để nhận thông báo
7. Tạo ELB truy cập tới ứng dụng Java
8. Dọn dẹp tài nguyên

Chúng ta cùng bắt tay làm nào. Let's go!!!!