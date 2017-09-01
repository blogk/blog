---
title: Căn giữa trong CSS
catalog: true
tags:
  - centering
  - css
id: 122
categories:
  - Frontend
date: 2016-05-21 17:17:01
subtitle:
header-img:
---

Hôm nay đổi gió chút, hôm nay chúng ta sẽ tìm hiểu 1 vấn đề khá quen thuộc trong [CSS](http://blogk.xyz/nhung-thuoc-tinh-quan-trong-khi-xay-dung-bo-cuc-website-phan-1/), tưởng dễ mà không dễ tưởng khó mà cũng chả khó:

![Các kiểu căn giữa trong CSS](../media/centering___-1.jpg)

**Các kiểu căn giữa trong CSS**

<!--more-->

Có khá nhiều cách để **căn giữa**, tùy thuộc và những trường hợp cụ thể như theo **chiều ngang hay theo chiều dọc** ta sẽ nên lựa chọn các cách phù hợp nhất. Âu cơ, ta sẽ đi vào từng trường hợp cụ thể!<!--more-->

## 1\. Theo chiều ngang

### a. Nếu nó thuộc kiểu inline hoặc inline-* (ví dụ như text, link, paragraph):

Ở trong 1 phần tử cha kiểu block ta chỉ cần style như sau:
<script src="https://gist.github.com/tutv95/8dddb24dfc229cd446904d71d0d66292.js"></script>

Ví dụ:

See the Pen [Centering Inline Elements - BlogK](http://codepen.io/blogk/pen/eZwwGd/) by BlogK ([@blogk](http://codepen.io/blogk)) on [CodePen](http://codepen.io).

<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

### b. Kiểu thứ hai là một phần tử kiểu khối block thì sao?

Để căn giữa ta để **margin-left** và <kbd>margin-right</kbd> là auto, nó sẽ tự căn đều margin hai bên. Và tất nhiên phần tử đó phải có chiều ngang cụ thể và nhỏ hơn thằng cha của nó còn nếu mà nó **full width** thì căn giữa làm méo gì nữa.

<script src="https://gist.github.com/tutv95/68cf5e4f7022cbe59a3992506f73a559.js"></script>

- Ví dụ:

See the Pen [Centering Single Block Level Element](http://codepen.io/blogk/pen/mPZZpQ/) by BlogK ([@blogk](http://codepen.io/blogk)) on [CodePen](http://codepen.io).

<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

Đôi khi bạn sẽ không hiểu tại sao bạn đã làm như trên rồi mà sao nó vẫn không căn giữa thì hãy chú ý 1 điều rằng **cách này sẽ không sử dụng được cho các phần tử đã bị float**.

### c. Khó hơn 1 chút - Căn giữa cho nhiều phần tử kiểu khối block

- Nếu bạn có nhiều hơn 1 phần tử block và mỗi phần tử đó nằm trên các hàng (row) riêng biệt thì ta vẫn sử dụng bình thường như 1 phần tử block. Ví dụ:

See the Pen [Centering Blocks on Top of Each Other](http://codepen.io/blogk/pen/pyXXKy/) by BlogK ([@blogk](http://codepen.io/blogk)) on [CodePen](http://codepen.io).

<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

- Nếu bạn có nhiều hơn 1 phần tử block nhưng trong cùng 1 hàng, để căn giữa ta sẽ sử thay đổi kiểu **display** của các phần tử đó sang dạng inline-* để đưa về cách 1 hoặc sử dụng **flex**.

Bạn có thể xem ví dụ bên dưới:

See the Pen [Centering Row of Blocks](http://codepen.io/blogk/pen/qZzzYx/) by BlogK ([@blogk](http://codepen.io/blogk)) on [CodePen](http://codepen.io).

<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

## 2\. Theo chiều dọc

Với căn giữa theo chiều dọc thì nó sẽ phức tạp hơn 1 chút nhé. Ở đây ta cũng phân chia ra 2 kiểu là dạng **inline** và dạng **block**.

### a. Nếu nó thuộc kiểu inline hoặc inline-* (ví dụ như text, link, paragraph):

#### - Kiểu 1 dòng đơn lẻ

Dễ rồi, ta chỉ cần **padding **trên dưới là xong!
<script src="https://gist.github.com/tutv95/00c447f6a7d39319b4859735ed34f639.js"></script>

Ví dụ nhé:

See the Pen [Centering text (kinda) with Padding](http://codepen.io/blogk/pen/ZWddjB/) by BlogK ([@blogk](http://codepen.io/blogk)) on [CodePen](http://codepen.io).

<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

Vì 1 lý do nào đó mà dùng padding mà vẫn không được và bạn biết chắc là phần tử đó sẽ không xuống dòng bạn có thể sử dụng **line-height** như sau:
<script src="https://gist.github.com/tutv95/5fe753b2fc4aa97ba4bb1a576dd938d5.js"></script>

Úm ba la ra kết quả:

See the Pen [Centering a line with line-height](http://codepen.io/blogk/pen/BKggPg/) by BlogK ([@blogk](http://codepen.io/blogk)) on [CodePen](http://codepen.io).

<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

#### - Kiểu nhiều dòng

Cách bên trên cũng có thể sử dụng cho trường hợp với nhiều dòng, nhưng nếu nó không hoạt động thì có lẽ các phần tử đó đang được hiển thị kiểu **table-cell** rồi. Lúc này thì [vertical-align](https://css-tricks.com/what-is-vertical-align/) sẽ ra tay cứu giúp.

Xem ví dụ nhé:

See the Pen [Centering text (kinda) with Padding](http://codepen.io/blogk/pen/ONeKKp/) by BlogK ([@blogk](http://codepen.io/blogk)) on [CodePen](http://codepen.io).

<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

Nếu mà dùng **table** vẫn không được thì hãy nghĩ đến [flexbox ](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)nhé!
<script src="https://gist.github.com/tutv95/14ac73daecdafb238203ef9b3da35880.js"></script>

Hãy xem ví dụ này:

See the Pen [Vertical Center Multi Lines of Text with Flexbox](http://codepen.io/blogk/pen/qZeWWW/) by BlogK ([@blogk](http://codepen.io/blogk)) on [CodePen](http://codepen.io).

<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

À cách này chỉ phù hợp khi thằng cha của nó phải có 1 **chiều cao định sẵn** rồi nhé!

Nếu mà vẫn không được nữa thì hãy dùng cách này nhé!
<script src="https://gist.github.com/tutv95/e18bf3e2e55598a98436c31f2eab29ea.js"></script>

See the Pen [Ghost Centering Multi Line Text](http://codepen.io/blogk/pen/NNQKWw/) by BlogK ([@blogk](http://codepen.io/blogk)) on [CodePen](http://codepen.io).

<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

### b. Kiểu thứ hai là kiểu khối block

#### - Bạn biết chiều cao của nó

Đơn giản rồi, đầu tiên bạn sử dụng** position: absolute;** và đặt **top: 50%;**, tiếp đó bạn dùng **margin (âm) để lùi lên trên bằng 1 nửa chiều cao** của khối đó. Xem code và ví dụ cho dễ hiểu này.

<script src="https://gist.github.com/tutv95/c2102edaa8e946fafe4802c7e004c57f.js"></script>

See the Pen [Center Block with Fixed Height](http://codepen.io/blogk/pen/RaXbNR/) by BlogK ([@blogk](http://codepen.io/blogk)) on [CodePen](http://codepen.io).

<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

#### - Bạn không quan tâm đến chiều cao của nó

Hơi khó nhưng vẫn giải quyết được, bạn làm y như bước đầu tiên của cách trên, nhưng ta không biết chiều cao của khối đó nên ta sẽ sử dụng 1 chiêu khác đó là **transform: translateY(-50%)**

<script src="https://gist.github.com/tutv95/4f05c093da9f336f863c3d8919d67fdd.js"></script>

See the Pen [Center Block with Unknown Height](http://codepen.io/blogk/pen/QNeLwQ/) by BlogK ([@blogk](http://codepen.io/blogk)) on [CodePen](http://codepen.io).

<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

#### - Bạn có thể sử dụng flexbox không?

Với flexbox điều này vô cùng đơn giản.

<script src="https://gist.github.com/tutv95/be4748ec524a36e787ab91abb16121ab.js"></script>

See the Pen [Center Block with Unknown Height with Flexbox](http://codepen.io/blogk/pen/EKqYaz/) by BlogK ([@blogk](http://codepen.io/blogk)) on [CodePen](http://codepen.io).

<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

## 3\. Theo cả hai chiều

Với trường hợp này ta có thể kết hợp lại của 2 trường hợp trên sao cho phù hợp. Căn giữa theo cả hai chiều sẽ **tập trung vào việc căn theo chiều dọc** vì theo chiều ngang có khá nhiều cách và dễ dàng thực hiện. Do bài dài vãi lúa nên mình sẽ không đi vào chi tiết nhưng mình sẽ liệt kê các cách chính là:
- Sử dụng position: absolute; để căn giữa và margin ngược trở lại.
- Sử dụng transform: translate(-50%, -50%); để lùi lại khi không biết chiều cao hoặc chiều rộng.
- Sử dụng flexbox.

## 4\. Kết luận

Hầu hết các cách căn giữa ở đây đều khá cơ bản và dễ dàng thực hiện, khi các cách đơn giản không thể chạy được người ta thường nghĩ đến **flexbox** là vị cứu tinh cuối cùng. Flexbox rất vi diệu, nhưng nó cũng khá mới nên chưa được hỗ trợ (hoặc hỗ trợ không đầy đủ) ở một trình duyệt nên nó chưa được sử dụng phổ biến.

Mệt value! Hết rồi đó, hãy thực hành ngay để có thể cảm nhận và nhớ lâu hơn nhé! Vẫn không thế nhớ à? Vậy búc mác lại nhé :)

Bài viết được dịch từ: https://css-tricks.com/centering-css-complete-guide/