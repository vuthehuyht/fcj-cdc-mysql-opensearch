---
title : "Tạo CodeBuild"
date :  "`r Sys.Date()`" 
weight : 4
chapter : false
pre : " <b> 4. </b> "
---

- Chúng ta sẽ có mindset như sau:
    + Một codebuild sẽ chạy khi có sự kiện push
    + Một codebuild sẽ chạy khi pull request về nhánh master được merged
- VÌ thế, chúng ta sẽ tạo 2 codebuild project
1. Tạo CodeBuild Project cho sự kiện push
- Tìm và chọn **CodeBuild** trên ô tìm kiếm
![4-step-1](../../images/4-step-1.png)
- Tại giao diện CodeBuild, chọn **Create project**
![4-step-2](../../images/4-step-2.png)
- **Project name**: điền `fcj-codebuild-push`
- **Souce - Primary**: chọn **AWS CodeCommit**
- **Source provider**, chọn **AWS CodeCommit**
- **Repository**, chọn `fcj-devops-aws`,
- **Branch**, chọn **dev**
- Chọn **Next**
![4-step-3](../../images/4-step-11.png)
- Kéo xuống đến mục **Buildspec**, chọn **Use a buildspec file**
![4-step-4](../../images/4-step-4.png)
- Chọn **Create build project**
![4-step-5](../../images/4-step-5.png)

2. Tạo CodeBuild Project cho sự kiện merged PR về nhánh master
- Tìm và chọn **CodeBuild** trên ô tìm kiếm
![4-step-1](../../images/4-step-1.png)
- Tại giao diện CodeBuild, chọn **Create project**
![4-step-2](../../images/4-step-2.png)
- **Project name**: điền `fcj-merge-pr`
- **Source provider**, chọn **AWS CodeCommit**
- **Repository**, chọn `fcj-devops-aws`,
- **Branch**, chọn **master**
![4-step-3](../../images/4-step-12.png)
- Kéo xuống đến mục **Buildspec**, chọn **Use a buildspec file**
- Ở mục **Buildspec name**, điền `buildspec_docker.yml`
![4-step-4](../../images/4-step-6.png)
- Chọn **Create build project**
![4-step-5](../../images/4-step-5.png)
- Click vào CodeBuild project vừa tạo ở trên
![4-step-5](../../images/4-step-7.png)
- Vì CodeBuild sẽ pull image lưu ở ECR nên ta cần cấp quyền cho CodeBuild có thể truy cập tới ECR, chọn Service role
![4-step-8](../../images/4-tep-8.png)
- Chọn **Add permissions** -> **Attach policy**
![4-step-9](../../images/4-step-9.png)
- Tìm và chọn **AmazonElasticContainerRegistryPublicFullAccess**
- **Lưu ý**: Nếu các bạn tạo ECR public thì policy cần attach là **AmazonElasticContainerRegistryPublicFullAccess**, ECR private thì policy cần attach là **AmazonEC2ContainerRegistryFullAccess**
![4-step-10](../../images/4-step-10.png)

- Gắn thêm **DescribeCluster** policy cho role của CodeBulid
- Tại giao diện sau thêm policy mới xong, Chọn **Add permissions** -> **Create inline policy**
![4-step-10](../../images/4-step-13.png)
- Chọn **Next**
![4-step-10](../../images/4-step-14.png)
- **Policy name**. điền `describe-cluster-policy`
- Chọn **Create policy**
![4-step-10](../../images/4-step-15.png)