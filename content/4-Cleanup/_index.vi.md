---
title : "Dọn dẹp tài nguyên"
date :  "`r Sys.Date()`" 
weight: 4
chapter: false
pre: "<b> 4. </b>"
---

#### Xoá Kinesis Data Stream
- Truy cập vào trang Kinesis
- Chọn `cdc-data-stream`
- Chọn Actions -> Delete

#### Xoá RDS
- Truy cập Amazon RDS
- Trên thanh điều hướng bên trái, chọn Databases
- Chọn DB Instance liên quan tới bài lab
- Click Actions.
- Click Delete
- Bỏ chọn Create final snapshot? và chọn I acknowledge that upon instance deletion, automated backups, including system snapshots and point-in-time recovery, will no longer be - available
- Gõ delete me vào ô trống.
- Click Delete

#### Xoá EC2
- Truy cập vào trang EC2
- Chọn cdc-listener
- Chọn Instance state -> Terminate instance

#### Xoá Opensearch
- Truy cập vào trang OpenSearch
- Chọn Delete
- Gõ delete và nhấp Xoá

#### Xoá Lambda
- Mở CMD tạo repo clone, gõ `sam delete` và gõ `Y` nếu được yêu cầu

#### Xoá VPC
- Truy cập vào trang VPC
- Chọn `cdc-vpc`
- Chọn Actions -> Delete VPC
- Gõ delete và nhấp Delete

