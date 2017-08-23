---
title: Tự tạo email hosting miễn phí
catalog: true
tags:
  - email
id: 83
categories:
  - Linh tinh
date: 2016-05-06 00:39:54
subtitle:
header-img:
---

Các công ty hay tổ chức hay dùng email dạng: abc@domain.com trông nó hoàng tráng không? Nó vừa thể hiện sự chuyên nghiệp vừa chắc chắn là email đó là của công ty hay tổ chức đó nên người nhận email sẽ rất yên tâm!

Ngày xưa Google đã ra mắt dịch vụ này và người dùng sử dụng nó **miễn phí**. Nhưng thời thế đã thay đổi! Hiện tại Google đã thu phí dịch vụ này. Vậy làm sao có thể sở hữu 1 custom domain kiểu vậy mà không phải setup 1 email hosting phức tạp mà vẫn tiện dụng như gmail của Google.<!--more-->

Với chi phí hạn hẹp đã thúc đẩy mình tìm ra 1 cách khác thay thế. Đó là Yandex. Nó là dịch vụ của Nga ngố. Theo bảng xếp hang Alexa thì nó đứng thứ 2 tại Nga ngố chỉ sau Google.ru.
Bạn có thể tạo custom mail tại đây: [https://domain.yandex.com](https://domain.yandex.com). Ứng dụng này gần tương tự Google Apps của Google và nó sẽ không hịn bằng Google là điều hiển nhiên :))

### 1\. Đăng ký email tại Yandex

**- Bước 1:**
Sau khi mình đăng ký 1 tài khoản tại Yandex và bắt đầu xác nhận domain của mình. Có 3 cách để xác nhận là:

*   1\. Upload 1 file html và có nội dung như hướng dẫn của nó
*   2\. Tạo 1 bản ghi CNAME cho domain.
Ở đây mình dùng cách 2 vì nó không cần phải có server hay hosting để upload file html lên.

**- Bước 2:**
Tiếp theo chúng ta sẽ thêm 1 bản ghi MX theo hướng dẫn của nó như sau:

`
Subdomain name — @
Type of record — MX
Data — mx.yandex.net
Priority — 10
`

Sau bước này nó sẽ báo **Domain connected**.

![Domain connected](http://blogk.xyz/wp-content/uploads/2016/05/connected_domain.png)

Tiếp bạn có thể tạo bất kì email nào theo domain mà bạn vừa xác nhận. Sau khi tạo bạn phải đăng nhập vào email đó để **hoàn tất đăng ký**.

### 2\. Sử dụng Yandex như gmail

Bạn đang quen sử dụng gmail và không muốn check mail thêm ở chỗ khác. Đừng lo!
Ở đây mình sẽ sử dụng Gmail để nhận và gửi mail thông quan Yandex với 2 tính năng mà Gmail cung cấp là : **Send mail as** và **Check mail from other accounts (using POP3)**.

Để cấu hình bạn vào phần Setting email của Google (góc trên bên phải) và chuyển sang tab **Accounts and Import**

#### Cấu hình gửi thư đi

**- Bước 1:**
Ở phần Send mail as bạn chọn **Add another email address you own**.
Trong trường Name bạn đặt tên tùy ý bạn, Email address bạn nhập email mà bạn vừa tạo ở phần 1.
**- Bước 2: Cấu hình SMTP servers**
`
SMTP Server: smtp.yandex.com
Port: 465
`
Usernam và Password chính là email và password của email đó mà bạn đã tạo. Đánh dấu vào phần **Secured connection using SSL** và chọn Add Account.
Sau đó Gmail sẽ gửi cho bạn 1 email để xác nhận để hoàn tất. Sau bước này bạn có thể gửi mail bằng gmail với email là email bạn đã tạo ở phần trước.

#### Cấu hình phần nhận thư đến

**- Bước 1:**
Trong phần Check mail from other accounts (using POP3) bạn chọn **Add a POP3 mail account you own**. Nhập email vào trường Email address.
**
- Bước 2: Cấu hình email POP Server**
`
POP Server: pop.yandex.com
Port: 995
`
Username và password tương tự phần trên. Tích chọn **Always use a secure connection (SSL) when retrieving mail** sau đó chọn Add account.
Ở mục chọn: **Label incoming messages**, bạn nên add 1 label riêng cho email này để tránh nhầm lần với mail của Gmail nhé.

Xong bước này là bạn đã hoàn tất. Bây giờ bạn có thể gửi mail bằng Gmail với địa chỉ mail dạng custom mail theo domain của chính bạn rồi.

À còn nữa nếu bạn sử dụng trình duyệt Chrome thường xuyên thì mình có thể giới thiệu đến bạn tiện ích này của Chrome:
[Checker Plus for Gmail™](https://chrome.google.com/webstore/detail/checker-plus-for-gmail/oeopbcgkkoapgobdbedcemjljbihmemj)

Ứng dụng này giúp bạn kiểm tra mail thường xuyên cho bạn hơn. Nếu bạn nào có tiện ích nào khác hay có cách nào khác để tạo 1 email theo domain thì có thể chia sẻ với mình và mọi người nhé.