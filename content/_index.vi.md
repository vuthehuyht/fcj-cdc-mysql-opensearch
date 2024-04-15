---
title : "Thu thập dữ liệu thay đổi từ RDS sang Opensearch"
date :  "`r Sys.Date()`" 
weight: 1
chapter: false
pre: "<b> 1. </b>"
---

# Thu thập dữ liệu thay đổi từ RDS sang Opensearch

#### Tổng quan

Khi các bạn làm việc với database, chắc hẳn các bạn cũng đã từng có suy nghĩ "Làm thế nào ta có thể thu thập sự thay đổi của database để phục vụ cho một số mục đích như tìm kiếm, phân tích, bla bla... ?". Thì trong bài lab này, các bạn sẽ tìm hiểu  cách thu thập dữ liệu từ MySQL sang OpenSearch, mặc dù đây không phải là cách tối ưu hay đem lại hiệu năng tốt cho các dự án nhưng nó sẽ đem lại cho các bạn một cái nhìn tổng quan về phương pháp thu thập dữ liệu giữa hai lại database khác nhau hoặc giữa hai hệ quản trị cơ sở dữ liệu. Để biết thêm các phương pháp khác các bạn thể search Google với từ khoá `Capture Data Change`.
