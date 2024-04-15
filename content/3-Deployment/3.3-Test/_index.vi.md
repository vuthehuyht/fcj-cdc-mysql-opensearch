---
title : "Kiểm thử"
date :  "`r Sys.Date()`" 
weight: 3
chapter: false
pre: "<b> 3.3 </b>"
---

Tại đây chúng ta kiêm thử thành quả sau một hồi hì hục triển khai.

Mình sử dụng một phần thứ ba để kết nối đến RDS là DBeaver

Sau khi kết nối thành công, giao diện hiển thị như sau
![2.4-step-1](../../../images/test-1.png)

- Tạo mới một database có tên là `test`
![2.4-step-1](../../../images/test-2.png)

- Ấn `Ctrl + J` để tạo file script mới
- Tạo một bảng `user`
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
![2.4-step-1](../../../images/test-3.png)

Tạo một record
```
INSERT INTO test.`user` (username, password, full_name) VALUES ('huyvt', '123', 'vu the huy');
```
![2.4-step-1](../../../images/test-4.png)

Quay lại với CMD ở bước 3.1, chúng ta thấy có đoạn log
![2.4-step-1](../../../images/test-6.png)

Như vậy, là đoạn code đã lắng nghe thành công sự kiện tạo mới record (tương tự với sự kiện update và delete record) và đồng thời cũng đẩy được nội dung của record vào trong Kinesis.

Tiếp đến, ta kiểm tra log của Lambda.
- Tại giao diện Lambda đã triển khai chọn tab **Monitor**, sau đó nhấp vào **View CloudWatch logs**
![2.4-step-1](../../../images/test-5.png)

Chọn đoạn log có thời gian tạo gần nhất
![2.4-step-1](../../../images/test-7.png)

Nhìn vào log ta thấy nội dung của record đã được thêm vào trong opensearch
![2.4-step-1](../../../images/test-8.png)

Ta kiểm tra url từ đoạn log
![2.4-step-1](../../../images/test-9.png)

WOW, Mọi thứ hoạt động thật mượt mà.

**Lưu ý**: Đây chỉ là một bài lab cơ bản cho bài toán Capture Data Change. Các bạn có thể tham khảo và cải thiện để phù hợp với các yêu cầu về nghiệp vụ, bảo mật...
