---
title : "Thiết lập CodeBuild triển khai image lên EKS"
date :  "`r Sys.Date()`" 
weight: 7
chapter: false
pre: "<b> 7. </b>"
---

Ở bước này, chúng ta cần hoàn thiện một số thiết lập để CodeBuild có thể triển khai image lên EKS. Let's gooo!
1. Cập nhật file cấu hình
- Sau khi database, container registry và kubernetes cluster được tạo xong, chúng ta cần đến các thông tin như sau:
  - database endpoint
  - database username
  - database password
  - container registry repository
  - kubernetes cluster name
  - region
- Mở file **helm/values.yaml** trong repo ở local cập nhật lại các giá trị đánh dấu
![7-step-2](../../images/7-step-2-a.png)
- Mở file **buildspec_docker.yml** trong repo ở local cập nhật lại các giá trị đánh dấu
![7-step-2](../../images/7-step2-b.png)
- Commit và push lên branch dev bằng command
    + `git add .`
    + `git commit -m "update values.yml file"`
    + `git push origin dev`

2. Thiết lập CodeBuild truy cập đến cluster
- Chuyển trang đến **IAM**
- Tìm và chọn **IAM**
![7-step-2](../../images/find-and-select-iam.png)

- Chọn **User**
![7-step-2](../../images/select-user.png)
- Chọn user đã tạo ở bước [2.1](2.1-createnewuser/)
![7-step-4](../../images/7-step-4.png)
- Chọn tab **Security credentials**, kéo xuống chọn **Create acces key**
![7-step-4](../../images/7-step-5.png)
![7-step-4](../../images/7-step-6.png)
- **Use case**: chọn **Command Line Interface (CLI)**
![7-step-4](../../images/7-step-7.png)
- Cuộn xuống, chọn **I understand the above recommendation and want to proceed to create an access key** và chọn **Next**
![7-step-4](../../images/7-step-8.png)
- Chọn **Create access key**
![7-step-4](../../images/7-step-9.png)
- Sau khi tạo xong, thu được kết quả
![7-step-4](../../images/7-step-10.png)
- Tới dây, các bạn cần cài AWS CLI trên máy, tham khảo cách cài tại [đây](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html)
- Ấn tổ hợp Window + R, gõ **cmd**, ấn **Enter**, nhập **aws configure**
- Paste từng giá trị của **Access key** và **Secret access key** vào cmd
![7-step-4](../../images/7-step-11.png)
- Update kubeconfig về máy để có thể thao tác với cluster
- Trong cmd, gõ `aws eks update-kubeconfig --name <cluster-name>`, **cluster-name** đã tạo ở bước [2.6](/2.6-createekscluste)
![7-step-4](../../images/7-step-12.png)
- Vì user vừa tạo access chưa có quyền access vào cluster, ta cần thiết lập như sau

- Tại giao diện cluster đã tạo ở bước [2.6], chọn tab **Access**
![7-step-4](../../images/7-step-13.png)
- Cuộn xuống, chọn **Create access entry**
![7-step-4](../../images/7-step-14.png)
- **IAM principal ARN**: nhập username đã tạo ở bước 2.1
![7-step-4](../../images/7-step-15.png)
- Cuộn xuống và Chọn **Next**
![7-step-4](../../images/7-step-16.png)
- Chọn **Next**
![7-step-4](../../images/7-step-17.png)
- Chọn **Create**
![7-step-4](../../images/7-step-18.png)
- Tại trang sau khi tạo xong, kéo xuống chọn **Add access policy**
![7-step-4](../../images/7-step-19.png)
- Chọn **AmazonEKSClusterAdminPolicy**
- Click **Add access policy**
![7-step-4](../../images/7-step-20.png)

- Thiết lập quyền truy cập cho CodeBuild Role, làm tương tự các bước trên đối với role của CodeBuild có tên `fcj-merge-pr`

- Tạo file `auth-patch.yml` với nội dung:
```
apiVersion: v1
data:
  mapRoles: |
    - group:
      - system:masters
      rolearn: <role arn đã lấy được ở trên>
      username: build
kind: ConfigMap
```
**Lưu ý**, ta bỏ **service-role** trong role arn, ví dụ: **arn:aws:iam::<aws account id>:role/service-role/codebuild-build-push-image-service-role** --> **arn:aws:iam::<aws account id>:role/codebuild-build-push-image-service-role**
- Sau đó chạy command `kubectl patch configmap/aws-auth -n kube-system --patch "$(cat <đường dẫn tới file auth-patch.yml>/auth-patch.yml)"`
![7-step-4](../../images/7-step-21.png)
- Như hình là đã config thành công
- Tạo PR vào master
- Tại giao diện của repository, chọn **Create pull request**
![7-step-4](../../images/7-step-22.png)
- Chọn **Create pull request**
![7-step-4](../../images/7-step-23.png)
- Chọn **Merge**
![7-step-4](../../images/7-step-24.png)
- Chọn **Merge pull request**
![7-step-4](../../images/7-step-25.png)
- Sau một khoảng thời gian chơ, CodeBUild cho sự kiện merge đã chạy xong
![7-step-4](../../images/7-step-27.png)
- Lấy endpoint để test thành quả
- Mở cmd, nhập `kubectl get svc`
![7-step-4](../../images/7-step-28.png)
- Lấy `<endpoint>/api/v1/demo` vào trình duyệt. WOW! Mọi thứ đã hoạt động thật mượt mà =))))))
![7-step-4](../../images/7-step-29.png)
