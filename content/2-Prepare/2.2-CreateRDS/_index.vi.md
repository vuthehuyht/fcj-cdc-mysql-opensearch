---
title : "Tạo RDS"
date :  "`r Sys.Date()`" 
weight: 2
chapter: false
pre: "<b> 2.2 </b>"
---

1. Tạo **Security Group** cho RDS

Tại ô tìm kiếm, tìm và chọn "Security Groups"
![2.4-step-1](../../../images/rds-1.png)

Tại giao diện vừa chuyển hướng, chọn **Create security group**
![2.4-step-1](../../../images/rds-2.png)

- Tại ô **Security group name**, nhập `cdc-mysql-sg`
- Tại ô **VPC**, chọn `vpc-cdc`
![2.4-step-1](../../../images/rds-3.png)

Tại mục **Inbound rules**, chọn **Add rule** và điền các thông tin như sau:
- Type: `MySQL/Aurora`
- Source: **0.0.0.0/0**
![2.4-step-1](../../../images/rds-4.png)

Cuối cùng, chọn **Create security group** để tạo SG.

2. Tạo **Parameter Group** cho RDS MySQL

Tại thanh điều hướng bên trái của giao diện RDS, chọn **Parameter groups** -> **Create parameter group**
![2.4-step-1](../../../images/rds-5.png)

- ở mục **Parameter group family**, chọn **mysql8.0**
- ở mục **Group Name**, nhập `cdc-group`
- Chọn **Create** để tạo.
![2.4-step-1](../../../images/rds-6.png)

3. Tạo RDS MySQL

Chuyển hướng trang tạo Database
- Trên ô tìm kiếm, tìm và chọn **RDS**
![2.4-step-2](../../../images/2.4-step-1.png)

Tại giao diện của RDS
- Chọn **Create database**
![2.4-step-2](../../../images/2.4-step-2.png)

Thiết lập Database
- **Choose a database creation method**: chọn **Standard create**
- **Engine options**: chọn **MySQL**
- **Templates**: chọn **Free Tier**
- **DB instance identifier**: điền `cdc-database`
- **Master password**: diền `Huyvt2609`
- **Confirm master password**: điền `Huyvt2609`
- **DB instance class**: chọn db.t2.micro
- **Public access**: chọn **Yes**
- **VPC security group (firewall)**: chọn `cdc-rds-sg`
- Tại mục **Additional configuration**
    + **DB parameter group**: chọn `cdc-group`
    + **Encryption**:  bỏ chọn **Enable encryption**
    + **Maintenance**: bỏ chọn **Enable auto minor version upgrade**
- Các mục khác để mặc định

![2.4-step-1](../../../images/rds-7.png)
![2.4-step-1](../../../images/rds-8.png)
![2.4-step-1](../../../images/rds-9.png)
![2.4-step-1](../../../images/rds-10.png)
![2.4-step-1](../../../images/rds-11.png)
![2.4-step-1](../../../images/rds-12.png)
![2.4-step-1](../../../images/rds-13.png)
![2.4-step-1](../../../images/rds-14.png)

**Lưu ý**: Quá trình tạo database sẽ diễn ra khá lâu, khoảng 10 phút.

Sau khi tạo xong, chúng ta cần xác nhận đã Enable MySQL bin log:
- Kết nối đến RDS bằng terminal: `mysql -h rds_enpoint -u admin -p `, sau đó nhập password
- Nhập `show global variables like "log_bin"`, néu kết quả **log_bin ON** là ok rồi

