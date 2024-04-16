---
title : "Giới thiệu"
date :  "`r Sys.Date()`" 
weight : 1
chapter : false
pre : " <b> 1. </b> "
---

#### Tổng quan

Trong bài lab này, chúng ta sẽ thực hiện việc thu thập sự thay đổi dữ liệu từ RDS MySQL tới Opensearch để có thể phục vụ các yêu cầu khác nhau. Bài lab này chỉ là base cơ bản nhất, các bạn cũng có thể cải thiện hoặc tuỳ chỉnh nó theo các yêu cầu khác nhau để cho hợp lý nhất.

Dưới đây là flow phương pháp
![CDC Flow](../../images/cdc-flow.png)

- RDS MySQL thực hiện tạo mới, cập nhật hay xoá bản ghi
- EC2 chạy code lắng nghe các sự kiện tạo mới, cập nhật hay xoá bản ghi và đẩy nội dung các sự kiện đó vào Kinesis
- Data stream được thêm vào Kinesis đồng thời cũng gọi một trigger Lambda với đầu vào nôi dung sự kiện được thêm vào Kinesis
- Lambda đẩy nội dung đó vào trong OpenSearch đồng thời trả ra url để truy cập đến nội dung đã được thêm

#### Nội dung

1. [Giới thiệu](/1-introduce)
2. [Các bước chuẩn bị](/2-prepare)
3. [Triển khai](/3-deployment)
4. [Dọn dẹp tài nguyên](/4-cleanup/)

Let's go!!!!
