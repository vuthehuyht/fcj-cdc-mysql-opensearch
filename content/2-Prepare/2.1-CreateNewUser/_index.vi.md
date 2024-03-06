---
title : "Tạo user với quyền admin"
date :  "`r Sys.Date()`" 
weight: 1
chapter: false
pre: "<b> 2.1 </b>"
---

1. Đầu tiên, chúng ta tạo user mới với quyền admin
- Truy cập **AWS Mangament Console**
- Tìm **IAM**
- Chọn **IAM**

![find-and-select-iam](../../../images/find-and-select-iam.png)

2. Trong giao diện **IAM**, chọn User
![select-user](../../../images/select-user.png)

    Khi vào tới giao diện của **User**, chọn **Create User**

![select-create-user](../../../images/select-create-user.png)

3. Trong giao diện **Create uer**
- Tại ô Username, ta điền một username bất kỳ mà bạn muốn.
**Lưu ý**: Chúng ta nên chọn một username dễ nhớ, tránh trường hợp chọn username phức tạp và chúng ta quên ngay sau đó.
- Ở dòng **Provide user access to the AWS Management Console**, chúng ta tick vào đó
- Chọn **I want to create an IAM user**, mục đích của chúng ta là tạo user nên ta sẽ chọn dòng này.
- Để tạo mật khẩu tuỳ ý, ta chọn **Custom password**
- Bỏ chọn dòng **Users must create a new password at next sign-in**
- Sau đó chọn **Next**
![step-1-create-user-a](../../../images/step-1-create-user-a.png)
![step-1-create-user-b](../../../images/step-1-create-user-b.png)

4. attach quyền admin cho user mới
- Chọn **Attach policies directly**
- Tim và chọn **AdministratorAccess**
- Chọn **Next**
![step-2-create-user-a](../../../images/step-2-create-user-a.png)
![step-2-create-user-b](../../../images/step-2-create-user-b.png)

5. Kiểm tra lại và chọn **Create user**
![step-3-create-user](../../../images/step-3-create-user.png)
Sau khi tạo thành công, chúng ta sẽ chuyển qua màn hình dưới đây
![step-4-create-user](../../../images/step-4-create-user.png)


