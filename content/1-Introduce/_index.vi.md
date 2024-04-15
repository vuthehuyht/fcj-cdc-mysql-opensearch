---
title : "Giới thiệu"
date :  "`r Sys.Date()`" 
weight : 1
chapter : false
pre : " <b> 1. </b> "
---

#### Tổng quan

Trong bài lab này, chúng ta sẽ thực hiện việc đồng bộ dữ liệu từ RDS tới Opensearch để có thể phục vụ tìm kiếm với kết quả được trả về nhanh nhất. Bài lab này chỉ là base cơ bản nhất, các bạn cũng có thể cải thiện hoặc tuỳ chỉnh nó theo các yêu cầu khác nhau để cho hợp lý nhất.

Dưới đây là flow phương pháp
![CDC Flow](../../images/cdc-flow.png)

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