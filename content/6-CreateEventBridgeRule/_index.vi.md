---
title : "Tạo EventBridge Rule cho merge PR"
date :  "`r Sys.Date()`" 
weight : 6
chapter : false
pre : " <b> 6. </b> "
---
Ở đây, hẳn các bạn cũng thắc mắc tại sao mình không tạo pipeline giống như ở bước 5. Pipeline tự động chạy cũng là do EventBridge đứng ở sau, nhưng trong quá trình tạo chúng ta không thấy EventBridge vì nó được tạo ngâm.

1. Công việc đầu tiên, chúng ta cần tạo lamda function để kích hoạt codebuild chạy
- Tìm và chọn **Lambda function**
![6-step-7](../../images/6-step-7.png)
- Chọn **Create function**
![6-step-8](../../images/6-step-8.png)
- **Function name**, điền `fcj-merge-pr-function`
- **Runtime**, chọn **Python3.9**
- **Architecture**, chọn **x86_64**
![6-step-8](../../images/6-step-9.png)
- Chọn **Create function**
![6-step-10](../../images/6-step-10.png)
- Kéo xuống đến mục **Code**, paste đoạn code sau vào đó
```
import boto3
import os


def lambda_handler(event, context):
    #     Start the build process
    client = boto3.client('codebuild')
    client.start_build(
        projectName="<tên codebuild cho sự kiện merge PR>",
        sourceVersion=event['detail']['sourceReference']
    )
```
- Chọn **Deploy**
![6-step-11](../../images/6-step-11.png)
- Tại mục **Configuration**, chọn **Permission**
- Click vào **Role names**
![6-step-11](../../images/6-step-12.png)
- Tại giao diện, chọn **Add permissions** -> **Attach policies**
![6-step-13](../../images/6-step-13.png)
Chúng ta cần thêm policies cho lambda function để có thể access vào trong **CodeBuild**
- Tìm và chọn **awsCodeBuildDeveloperAccess**
- Sau đó, chọn **Next**
![6-step-14](../../images/6-step-14.png)
- Quay trở lại với role của lambda, chọn **Add permissions** -> **Create policies inline**
![6-step-15](../../images/6-step-15.png)
- Chọn **JSON** và đoạn json sau vào policies editor
```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "VisualEditor0",
            "Effect": "Allow",
            "Action": [
                "codecommit:ListPullRequests",
                "codecommit:GetPullRequest"
            ],
            "Resource": "arn:aws:codecommit:*:<AWS account id>:*"
        }
    ]
}
```
- Sau đó chọn **Next**
![6-step-16](../../images/6-step-16.png)
- **Policy name**, điền `fcj-lamdba-pr`
- Chọn **Create policy**
![6-step-16](../../images/6-step-17.png)

2. Chuyển hướng đến **EventBridge**
- Tìm và chọn **Amazon EventBridge** trên ô tìm kiếm
![6-step-1](../../images/6-step-1.png)
3. Chọn **Create Rule**
![6-step-2](../../images/6-step-2.png)
4. Thiết lập rule
- **Name**: điền `merge-pr-master-rule`
- Chọn **Next**
![6-step-3](../../images/6-step-3.png)
- **Event source**: chọn **Other**
- **Creation method**: chọn **Custom pattern (JSON editor)**
- **Event pattern**, paste đoạn json 
```
{
  "source": ["aws.codecommit"],
  "detail-type": ["CodeCommit Pull Request State Change"],
  "detail": {
    "event": ["pullRequestMergeStatusUpdated"],
    "isMerged": ["True"],
    "destinationReference": ["refs/heads/master"]
  }
}
```
![6-step-3](../../images/6-step-4.png)
- Chọn **Next**
![6-step-3](../../images/6-step-22.png)
- **Target types**: chọn **AWS Service**
- **Select a target**: chọn **Lambda function**
- **Function**: chọn function đã tạo ở bước 1
- Chọn **Next**
![6-step-18](../../images/6-step-18.png)
- Chọn **Next**
![6-step-19](../../images/6-step-19.png)
- Kiểm tra lại và chọn **Create rule**
![6-step-20](../../images/6-step-20.png)
- Trở lại lambda function kiểm tra, ta sẽ thấy **EventBrigde** được thêm ở phần **Add trigger**
![6-step-21](../../images/6-step-21.png)
