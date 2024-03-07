---
title : "Dọn dẹp tài nguyên"
date :  "`r Sys.Date()`" 
weight : 8
chapter : false
pre : " <b> 8. </b> "
---

#### Xoá EKS Cluster
- Truy cập **Amazon Elastic Kubernetes Service**
- Chọn cluster có tên `fcj-devops-cluser`
- Tại tab **Compute**, chọn `node-1`, click **Delete**
- Hiển thị lên modal, nhập `node-1`, click **Delete**
- Đợi Node Group xoá xong, quay lại trang **Cluster**
- Chọn `fcj-devops-cluster`, có modal hiện lên, nhập `fcj-devops, cluster`, click **Delete**

#### Xoá RDS
- Truy cập **Amazon RDS**
- Trên thanh điều hướng bên trái, chọn **Databases**
- Chọn **DB Instance** liên quan tới bài lab
- Click **Actions**.
- Click Delete
- Bỏ chọn **Create final snapshot? và chọn I acknowledge that upon instance deletion, automated backups, including system snapshots and point-in-time recovery, will no longer be available**
- Gõ **delete me** vào ô trống.
- Click **Delete**

#### Xoá CodePipline
- Truy cập **CodePipeline**
- Chọn pipepline liên quan đến bài lab
- Click **Delete**
- Nhập **delete** vào ô trống, click **Delete**

#### Xoá CodeBuild
- Truy cập **CodeBuild**
- Chọn lần lượt build project liên quan đến bài lab
- Click **Action** -> **Delete**
- Nhập **delete** vào ô trống, click **Delete**

#### Xoá CodeCommit
- Truy cập **CodeCommit**
- Chọn repository liên quan đến bài lab
- Click  **Delete repository**
- Nhập **delete** vào ô trống, click **Delete**

#### Xoá EventBrigde rule
- Truy cập **Amazon EventBrigde**
- Trên thanh điều hướng bên trái, chọn **Rules**
- Chọn tất cả rule name liên quan đến bài lab
- Click  **Delete**
- Nhập **delete** vào ô trống, click **Delete**

#### Xoá Lambda function
- Truy cập **Lambda**
- Chọn lamda function liên quan đến bài lab
- Click **Action** -> **Delete**
- Nhập **delete** vào ô trống, click **Delete**

#### Xoá role
- Truy cập **Amazon IAM**
- Trên thanh điều hướng bên trái, chọn **Roles**
- Chọn **Role name** liên quan tới bài lab
- click **Delete**
- Nhập **delete** vào ô trống, click **Delete**

#### Xoá user
- Truy cập **Amazon IAM**
- Trên thanh điều hướng bên trái, chọn **User**
- Chọn **User name** liên quan tới bài lab
- click **Delete**
- Nhập username vào ô trống, click **Delete user**
