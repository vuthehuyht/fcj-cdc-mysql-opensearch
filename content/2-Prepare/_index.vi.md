---
title : "Các bước chuẩn bị"
date :  "`r Sys.Date()`" 
weight: 2
chapter: false
pre: "<b> 2. </b>"
---

Trước khi bắt tay vào triển khai phương pháp này, chúng ta cần bổ sung một xíu kiến thức về một số dịch vụ được sử dụng trong bài lab.

#### AWS RDS
Đây là một trong những dịch vụ điển hình của AWS, được sử dụng rất nhiều và rộng rãi. Vì nó phổ biến nên chúng ta sẽ tiếp tục với phần khác. Trong bài lab này, RDS sẽ đóng vai trò là source để lấy data.

#### AWS Lambda
**AWS Lambda** là một dịch vụ điện toán phi máy chủ, theo định hướng sự kiện (hiểu nôm na là khi nào có request đến thì nó mới chạy), giúp cho chúng ta chạy code hầu hết mọi loại application hoặc backend service mà không cần cung cấp hay quản lý máy chủ. **AWS Lambda** có thể được kích hoạt từ hơn 200 dịch vụ của AWS và các application dưới dạng SaaS và chúng ta chỉ cần trả phí theo mức sử dụng.

#### AWS EC2

### AWS VPC

#### AWS Kinesis Data Stream
**AWS Kinesis** là dịch vụ giúp các bạn xây dựng được một ứng dụng có khả năng phần tích và xử lý luồng dữ liệu (stream data) theo thời gian thực (realtime),**AWS Kinesis** có khả năng thu nhận, lưu trữ đến hàng terabytes data trong một giờ.

**AWS Kinesis** có thể nhận data từ nhiều nguồn khác nhau như logs, live stream từ các ứng dụng...

Hiện tại, **AWS Kinesis** gồm 4 components như sau:
- **Kinesis Data Streams**: thu thập, xử lý và lưu trữ data stream
- **Kinesis Data Firehorse**: load data stream vào AWS data store (ví dụ: S3)
- **Kinesis Data Analytics**: phân tích data stream với SQL hoặc Apache Flink
- **Kinesis Video Stream**: thu thập, xử lý và lưu trữ data stream

Trong bài lab, chúng ta dùng đến **Kinesis Data Stream** để thu thập và xử lý data rồi đẩy về OpenSearch.

#### AWS OpenSearch
**AWS OpenSearch** là một bộ công cụ tìm kiếm và phân tích phân tán, hướng tới cộng đồng, được cấp phép của Apache 2.0, 100% nguồn mở được sử dụng cho hàng loạt các trường hợp như giám sát ứng dụng theo thời gian thực, phân tích bản ghi và tìm kiếm trang web. OpenSearch cung cấp một hệ thống có quy mô linh hoạt để mang tới khả năng truy cập và phản hồi nhanh khối lượng lớn dữ liệu với công cụ trực quan hóa được tích hợp sẵn, OpenSearch Dashboards, giúp người dùng dễ dàng khám phá dữ liệu của họ. OpenSearch được hỗ trợ bởi thư viện tìm kiếm Apache Lucene và nó hỗ trợ hàng loạt các tính năng tìm kiếm và phân tích, chẳng hạn như tìm kiếm lân cận k gần nhất (KNN), SQL, Phát hiện bất thường, Thư viện Machine Learning Commons, Phân tích dấu vết, tìm kiếm toàn văn bản, v.v.

Tiền thân của **OpenSearch** là **Elasticsearch**, nhưng mình không biết vì lý do gì **AWS Elasticsearch** lại đổi tên thành **AWS OpenSearch**

#### Nội dung

1. [Tạo user quyền admin](/2-prepare/2.1-createnewuser/)
2. [Tạo repository](2-prepare/2.2-createrepository/)
3. [Tạo container registry](/2-prepare/2.3-createecr/)
4. [Tạo database](/2-prepare/2.4-createrds/)
5. [Tạo role](/2-prepare/2.5-createrole/)
6. [Tạo EKS cluster](2-prepare/2.6-createekscluster/)
7. [Thêm node group vào eks cluster](2-prepare/2.7-addnodegrouptocluster/)
