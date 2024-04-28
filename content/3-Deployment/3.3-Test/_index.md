---
title : "Testing"
date :  "`r Sys.Date()`" 
weight: 3
chapter: false
pre: "<b> 3.3 </b>"
---

Here let's test the result after a period of hard work

I use the third party software to connect to RDS that is DBeaver

When connection is done, the interface show as following
![2.4-step-1](/images/test-1.png)

- Create new database is `test`
![2.4-step-1](/images/test-2.png)

- Press `Ctrl + J` to add new script file
- Create new table name `user`
```
CREATE TABLE test.`user` (
	id INT auto_increment primary key,
	username varchar(255) NULL,
	password varchar(255) NULL,
	full_name varchar(255) NULL
)
ENGINE=InnoDB
DEFAULT CHARSET=utf8mb4
COLLATE=utf8mb4_0900_ai_ci;
```
![2.4-step-1](/images/test-3.png)

Add new record to `test` table
```
INSERT INTO test.`user` (username, password, full_name) VALUES ('huyvt', '123', 'vu the huy');
```
![2.4-step-1](/images/test-4.png)

Back to CMD in step 3.1, we will see log
![2.4-step-1](/images/test-6.png)

So, Python code has listened successfully the event of creating a new record (similar to update and delete record events) and at the same time, it can also push the content of the record into Kenisis.

So on, let's check log of Lambda
- In Lambda interface deployed, choose **Monitor** tab, then click **View CloudWatch logs**
![2.4-step-1](./images/test-5.png)

Choose log has latest creation time
![2.4-step-1](/images/test-7.png)

Look at the log, we see that the content of record has been added to opensearch 
![2.4-step-1](/images/test-8.png)

We check url from log
![2.4-step-1](/images/test-9.png)

WOW, everythings work smoothly

**Note**: This is just a basic lab exercise for the Capture Data Change problem. You can refer to and improve to suit business and security requirements...
