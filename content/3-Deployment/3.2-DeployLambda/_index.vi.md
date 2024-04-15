---
title : "Triển khai Lambda"
date :  "`r Sys.Date()`" 
weight: 2
chapter: false
pre: "<b> 3.2 </b>"
---

Để triển khai Lambda ta cần tạo user để lấy Access keys

- Hãy tạo mới một user với **Attach policies directly** là **AdministratorAccess**
- Tại giao diện user vừa tạo, chọn tab **Security Credentials**
- Tại mục **Access kyes**, chọn **Create access key**
![2.4-step-1](../../../images/lambda-1.png)

- Chọn **Command Line Interface (CLI)**
- Tick vào **I understand the above recommendation and want to proceed to create an access key.**
![2.4-step-1](../../../images/lambda-2.png)
Nhấp **Create access key** để tạo

Thiết lập AWS CLI với access key id và access key vừa tạo bằng command `aws configure`
![2.4-step-1](../../../images/lambda-3.png)

Tải và cài đặt SAM CLI tại [link](https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/install-sam-cli.html)

Clone lambda tại [repo](https://github.com/vuthehuyht/cdc-lambda)

Mở CMD tại repo vừa clone, tìm đến file template.yml cập nhật thông tin OpenSearch đã tạo ở bước [2.3](/2-prepare/2.3-createopensearch/)
![2.4-step-1](../../../images/lambda-5.png)

Sau khi cập nhật xong, chạy command `sam build && sam deploy`

Khi có thông báo **Successfully created/updated stack - lambda in ap-southeast-1** là ta đã triển khai thành công.
Ta kiểm tra trên AWS
![2.4-step-1](../../../images/lambda-4.png)


