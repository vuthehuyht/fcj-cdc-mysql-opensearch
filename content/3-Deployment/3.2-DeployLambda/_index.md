---
title : "Deploy Lambda function"
date :  "`r Sys.Date()`" 
weight: 2
chapter: false
pre: "<b> 3.2 </b>"
---

To deploy Lambda, we need to create new user to get access keys

- Create new user with **Attach policies directly** is **AdministratorAccess**
- In **User** interface, choose **Security Credentials** tab
- In section **Access kyes**, choose **Create access key**
![2.4-step-1](/images/lambda-1.png)

- Choose **Command Line Interface (CLI)**
- Tick **I understand the above recommendation and want to proceed to create an access key.**
![2.4-step-1](/images/lambda-2.png)
Click **Create access key**

Configure AWS with access key id and access key by `aws configure` command
![2.4-step-1](/images/lambda-3.png)

Download and install SAM CLI in [link](https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/install-sam-cli.html)

Clone lambda repository tại [repo](https://github.com/vuthehuyht/cdc-lambda)

Run CMD in repo cloned, find and open template.yml, update OpenSearch created in step 2.3
![2.4-step-1](/images/lambda-5.png)

After updating done, run command `sam build && sam deploy`

Khi có thông báo **Successfully created/updated stack - lambda in ap-southeast-1** là ta đã triển khai thành công.
When the result is **Successfully created/updated stack - lambda in ap-southeast-1**, let's deploy successfully.

Ta kiểm tra trên AWS
Let's check in AWS Lambda
![2.4-step-1](/images/lambda-4.png)
