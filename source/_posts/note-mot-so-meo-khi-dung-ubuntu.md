---
title: '[Note] Một số mẹo khi dùng Ubuntu'
catalog: true
id: 95
categories:
  - Server
date: 2015-03-24 14:08:34
subtitle:
header-img:
tags:
---

![ubuntu2](http://blogk.xyz/wp-content/uploads/2016/05/ubuntu2.png)

Note này chủ yếu viết với mục đích để note cho chính mình nên 1 số thứ mình viết rất ngắn gọn hoặc theo ý hiểu của mình nên mong các bạn thông cảm.<!--more-->

Lần đầu tiên sử dụng Ubuntu: **15/03/2015**

### Đầu tiên là cài Unikey cho Ubuntu

Cái này làm mình phải cài lại Ubuntu 1 lần nữa :v

- Mở Terminal gõ:
`
sudo apt-get install ibus-unikey
ibus restart
`
- Vào phần thiết lập **Text Entry** thêm Vietnamese (Unikey). Done!

### 1\. Cài đặt bộ stack LAMP = Linux + Apache + MySQL + PHP

- Gõ lệnh:
`
sudo apt-get install lamp-server^
`

2\. Khởi động Apache với tên service là: apache2
`
sudo service apache2 start
`

Nếu không muốn cái thủ công có thể sử dụng các script như EasyEngine, VPSSIM.

3\. Tạo Virtual Host
- Copy file:
`
sudo cp /etc/apache2/sites-available/000-default.conf /etc/apache2/sites-available/mysite.conf
`

- Sửa file mysite.conf
Cái này tự biết nhé :v

- Enable Site: 
`
sudo a2ensite mysite
`
- Sửa file **apache2.conf** trong thư mục /etc/apache2
Không sửa file này thì bị lỗi 403 thì phải :v
- Sửa file **hosts**
Để trỏ domain do mình tự định nghĩa về **localhost**
Restart apache2

### 2\. Cài đặt phpMyAdmin trên Ubuntu

- Mở terminal gõ:
[code]sudo apt-get install phpmyadmin[/code]

- Sửa file **/etc/apache2/apache2.conf**:(Chèn vào cuối file)
`
Include /etc/phpmyadmin/apache.conf
`

Khởi động lại apache2:
`
sudo service apache2 restart
`

### 3\. Cài đặt Sublime Text

`
sudo add-apt-repository ppa:webupd8team/sublime-text-2
sudo apt-get update
sudo apt-get install sublime-text
`

`
sudo add-apt-repository ppa:webupd8team/sublime-text-3
sudo apt-get update
sudo apt-get install sublime-text-installer
`

### 4\. Xóa tag trên git Hub

`
git push origin :1.1.0
`

### 5\. Compile JavaC encoding UTF-8

`
javac -encoding UTF8 Game2048.java
<code>

### 6\. Sửa DNS

Mở Terminal gõ
<code>
sudo gedit /etc/resolvconf/resolv.conf.d/head
`

Chèn thêm 2 dòng sau (Google DNS)
`
nameserver 8.8.8.8
nameserver 8.8.4.4
`

Sau đó gõ tiếp:
`
sudo resolvconf -u
`

Done :]

### 7\. Cài đặt composer

`
curl -sS https://getcomposer.org/installer | php
`

Tiếp tục:
`
sudo mv composer.phar /usr/local/bin/composer
`

Done! Tiếp tục gõ:
`
composer --version
`
Để xem phiên bản đã cài đặt của **composer**.

Tạm thế thôi. Có gì lại viết tiếp :P