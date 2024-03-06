---
title : "Đẩy source code lên CodeCommit"
date :  "`r Sys.Date()`" 
weight : 3
chapter : false
pre : " <b> 3. </b> "
---

- Đăng nhập lại bằng root account
- Tìm và chọn **IAM**
![find-and-select-iam](../../images/find-and-select-iam.png)
-Trong giao diện **IAM**, chọn User
![select-user](../../images/select-user.png)
- Tìm và chọn user đã tạo ở bước [2.1](2-prepare/2.1-createnewuser/)
![3-step-1](../../images/3-step-1.png)
- Chọn mục **Security credentials**
![3-step-1-b](../../images/3-step-1-b.png)
- Kéo xuống đến phần **HTTPS Git credentials for AWS CodeCommit**, chọn **Generate credentials**
![3-step-1-c](../../images/3-step-1-c.png)
- Chọn **Download credentials**
![3-step-1-d](../../images/3-step-1-d.png)
- Quay lại CodeCommit để lấy url clone, chọn **Clone HTTPS**
![3-step-1-d](../../images/3-step-1-e.png)
- Clone repo về máy, sau đó nhập credential đã tải về trước đó
![3-step-1-f](../../images/3-step-1-f.png)
- Copy source từ [source](../../file/fcj-devops-aws.zip) đến repo vừa clone
- Push code lên repo bằng các câu lệnh sau:
    + `git add .`
    + `git commit -m "initial project"`
    + `git push -u origin master`
- Ta kiểm tra lại trên repo xem đã thành công chưa
![3-step-1-g](../../images/3-step-1-g.png)
Như hình là chúng ta đã push lên repo thành công
- Tạo thêm branch dev bằng các command sau:
    + `git checkout -b dev`
    + `git push origin dev`
![3-step-2](../../images/3-step-2.png)


