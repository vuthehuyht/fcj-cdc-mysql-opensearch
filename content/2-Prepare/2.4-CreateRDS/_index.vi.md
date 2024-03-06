---
title : "Tạo database"
date :  "`r Sys.Date()`" 
weight: 4
chapter: false
pre: "<b> 2.4 </b>"
---

1. Chuyển hướng trang tạo Database
- Trên ô tìm kiếm, tìm và chọn **RDS**
![2.4-step-1](../../../images/2.4-step-1.png)

2. Tại giao diện của RDS
- Chọn **Create database**
![2.4-step-2](../../../images/2.4-step-2.png)

3. Thiết lập Database
- **Choose a database creation method**: chọn **Standard create**
- **Engine options**: chọn **MySQL**
- **Templates**: chọn **Free Tier**
- **DB instance identifier**: điền `fcj-database`
- **Master password**: diền `Huyvt2609`
- **Confirm master password**: điền `Huyvt2609`
- **DB instance class**: chọn db.t2.micro
- **Public access**: chọn Yes
- Tại mục **Additional configuration**
    + **Initial database name**: điền `blog_dev`
    + **Backup**: bỏ chọn **Enable automated backups**
    + **Maintenance**: bỏ chọn **Enable auto minor version upgrade**
- Các mục khác để mặc định

![2.4-step-3-a](../../../images/2.4-step-3-a.png)
![2.4-step-3-b](../../../images/2.4-step-3-b.png)
![2.4-step-3-c](../../../images/2.4-step-3-c.png)
![2.4-step-3-d](../../../images/2.4-step-3-d.png)
![2.4-step-3-e](../../../images/2.4-step-3-e.png)
![2.4-step-3-f](../../../images/2.4-step-3-f.png)
![2.4-step-3-g](../../../images/2.4-step-3-g.png)
![2.4-step-3-h](../../../images/2.4-step-3-h.png)

**Lưu ý**: Quá trình tạo database sẽ diễn ra khá lâu, khoảng 10 phút.
- Do chúng ta sử dụng SG mặc định nên cần sửa một chút
- Tại tab **Connectivity & security**, click **VPC security groups**
![2.4-step-4](../../../images/2.4-step-4.png)
- Tại giao diện **Security Groups**
- Chọn **Inbound rules** -> **Edit inbound rules**
![2.4-step-5](../../../images/2.4-step-5.png)
- **Type**: chọn **MySQL/Aurora**,
- **Source**: chọn **Anywhere IPv4**
- Chọn **Save rules**
![2.4-step-6](../../../images/2.4-step-6.png)
