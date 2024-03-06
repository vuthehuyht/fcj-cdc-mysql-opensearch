---
title : "Tạo CodePipeline"
date :  "`r Sys.Date()`" 
weight : 5
chapter : false
pre : " <b> 5. </b> "
---

Trong phần này, chúng ta tạo một codepipeline để mỗi lần có sự kiện push thì codebuild sẽ tự động chạy build và test cho source code.

1. Chuyển hướng đến **CodePipeline**
- Tìm và chọn **CodePipeline** trên ô tìm kiếm
![5-step-1](../../images/5-step-1.png)

2. Trong giao diện **CodePipeline**
- Chọn **Create pipeline**
![5-step-2](../../images/5-step-2.png)

3. Thiết lập Pipeline
- **Pipeline name**, điền `fcj-push-pipeline`
- **Pipeline type**, chọn **V1**
![5-step-3](../../images/5-step-3.png)
- Chọn **Next**
![5-step-4](../../images/5-step-4.png)
- **Source provider**: Chọn **AWS CodeCommit**
- **Repository name**: chọn **fcj-devops-name**
- **Branch name**: chọn **dev**
![5-step-6](../../images/5-step-6.png)
- Chọn **Next**
![5-step-7](../../images/5-step-7.png)
- **Build provider**: chọn **AWS CodeBuild**
- **Region**: sẽ tự động chọn
- **project name**, chọn `fcj-codebuild-push`
![5-step-8](../../images/5-step-8.png)
- Chọn **Next**
![5-step-9](../../images/5-step-9.png)
- Chọn **Skip deploy stage**
![5-step-10](../../images/5-step-10.png)
![5-step-11](../../images/5-step-11.png)
- Kiểm tra lại và chọn **Create pipeline**
![5-step-12](../../images/5-step-12.png)
- Sau khi tạo thành công, pipeline sẽ tự chạy
![5-step-13](../../images/5-step-13.png)
