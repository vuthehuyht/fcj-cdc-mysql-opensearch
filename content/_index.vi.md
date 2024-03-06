---
title : "Xây dựng và triển khai triển tự động ứng dụng Java lên Amazon EKS"
date :  "`r Sys.Date()`" 
weight: 1
chapter: false
pre: "<b> 1. </b>"
---

# Xây dựng và triển khai triển tự động ứng dụng Java lên Amazon EKS

#### Tổng quan

Đây là workshop đầu tay của mình khi tham gia First Cloud Journey. Trong workshop này, chúng ta cùng đi tìm hiểu cách tạo pipeline CI/CD liên tục để build và triển khai ứng dựng Java cùng với các biện pháp bảo mật được khuyên dùng tới Amazion Elastic Kubernetes Service trên AWS Cloud. Đồng thời cũng tạo một endpoint để có thể truy cập vào ứng dụng Java bằng Elastic Load Balancing.

#### Lưu ý
- Workshop này mình cũng sử dụng kha khá các dịch vụ của AWS cho nên các bạn cần có kiến thức cơ bản về một số dịch vụ điển hình để có thể hiểu được.
