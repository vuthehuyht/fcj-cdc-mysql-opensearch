---
title : "Giới thiệu"
date :  "`r Sys.Date()`" 
weight : 1
chapter : false
pre : " <b> 1. </b> "
---

#### Tổng quan

Các bạn có thể tham khảo pattern này để áp dụng cho dự án phát triển bằng Spring Framework hoặc có thể tuỳ chỉnh theo yêu cầu của dự án hay yêu cầu mà các bạn đề ra. Flow cơ bản của pattern như sau: đóng gói ứng dụng Java thành image, scan bảo mật image, tải image lên Amazon ECR và cuối cùng là triển khai image lên Amazon EKS. Pattern này cũng rất hữu ích khi muốn chuyển từ monolithic sang kiến trúc microservices lên EKS hoặc ECS, giúp giám sát và quản lý toàn bộ vòng đời của ứng dụng Java, bảo đảm mức độ tự động hoá cao hơn và tránh gặp lỗi. Để dễ dàng thì mình làm đơn giản nhất có thể, hoàn toàn bỏ qua các yếu tố về security.

Ngoài ra, nếu các có thể tuỳ chỉnh theo ý mình để bài lab có thể hoàn thiện hơn.

Dưới đây là flow
![GitOps in AWS](../../images/devops-flow.png)

#### Nội dung

1. [Giới thiệu](/1-introduce)
2. [Các bước chuẩn bị](/2-prepare)
3. [Đẩy code lên ComdeCommit](/3-pushcodetocodecommit)
4. [Tạo CodeBuild](/4-createcodebuild/)
5. [Tạo CodePipeline](/5-createcodepipeline/)
6. [Tạo EventBridge Rule cho merge PR](6-createeventbridgerule/)
7. [Thiết lập CodeBuild triển khai image lên EKS Cluster](7-configcodebuilddeployeks/)
8. [Dọn dẹp tài nguyên](8-cleanup/)

Chúng ta cùng bắt tay làm nào. Let's go!!!!