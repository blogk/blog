---
title: Các Front-end Dev nên biết về CSS Specificity
catalog: true
tags:
  - css
id: 142
categories:
  - Frontend
date: 2016-05-27 02:02:04
subtitle:
header-img:
---

**CSS Specificity** (khó đọc vãi) có nghĩa là trình duyệt sẽ quyết định giá trị của CSS nào được **ưu tiên cao nhất** vì thế nó sẽ được **áp dụng** cho phần tử đang được chọn đó. Lúc mới học CSS mấy ổng dạy mình từng lôi cái này ra loè mình vì những định nghĩa phức tạp của nó, nhưng thực tế cho thấy thì ta ít khi gặp phải vấn đề phức tạp liên quan đến specificity vì mấy dev nhà ta chỉ sử dụng 1 số luật lệ cơ bản :))<!--more-->

Nhưng nếu chúng ta hiểu tường minh về **Specificity trong CSS** thì bạn sẽ giải quyết được các vấn đề liên quan đến việc tại sao viết CSS này nó chạy nhưng ở chỗ khác nó lại méo chạy? Vậy thì làm thế nào để chúng ta có thể biết được **thứ tự ưu tiên** của chúng để ta có thể hoàn toàn điều khiển được quy luật đó?

### Các định nghĩa trong CSS Specificity

1\. Nếu hai selectors cùng áp dụng vào 1 phần tử thì cái nào có specificity cao hơn sẽ được áp dụng.
2\. Đây là 4 loại mức của specificity từ cao xuống thấp: inline styles, IDs, class + attributes và lements.
3\. Khi 2 selector có specificity bằng nhau thì selector nào được thực thi sau sẽ ghi đè những cái trước.

Để tính được specificity cho các selectors mình có tham khảo 1 [bài viết](https://stuffandnonsense.co.uk/archives/css_specificity_wars.html) khá hay và dễ hiểu. Như thế này, 1 selector "tổng" (1 đội quân) là tổ hợp của các selector "nguyên tử" (thành viên) với các sức mạnh như sau:

- Style inline: 1000
- IDs: 100
- Class+attribute: 10
- Elements: 1
- Universal (*): 0

![specificity](http://blogk.xyz/wp-content/uploads/2016/05/specificity.jpg)

Ở đây không đề cập đến inline-style, dựa vào trọng số từng selector "nguyên tử" ta sẽ cộng lại để tạo ra sức mạnh của selector "tổng":

![specificitywars-05v2](http://blogk.xyz/wp-content/uploads/2016/05/specificitywars-05v2.jpg)

Như vậy đội quân nào (selector "tổng") **có sức mạnh lớn hơn** sẽ dành chiến thắng, tương ứng với selector sẽ được áp dụng.

### Ví dụ

Ta có 1 bảng các ví dụ minh hoạ nhé:

<table class="table-overview">
<tbody>
<tr>
<td class="num">1</td>
<td>* { }</td>
<td>0</td>
</tr>
<tr class="pdd">
<td class="num">2</td>
<td>li { }</td>
<td>1 (one element)</td>
</tr>
<tr>
<td class="num">3</td>
<td>li:first-line { }</td>
<td>2 (one element, one pseudo-element)</td>
</tr>
<tr class="pdd">
<td class="num">4</td>
<td>ul li { }</td>
<td>2 (two elements)</td>
</tr>
<tr>
<td class="num">5</td>
<td>ul ol+li { }</td>
<td>3 (three elements)</td>
</tr>
<tr class="pdd">
<td class="num">6</td>
<td>h1 + *[rel=up] { }</td>
<td>11 (one attribute, one element)</td>
</tr>
<tr>
<td class="num">7</td>
<td>ul ol li.red { }</td>
<td>13 (one class, three elements)</td>
</tr>
<tr class="pdd">
<td class="num">8</td>
<td>li.red.level { }</td>
<td>21 (two classes, one element)</td>
</tr>
<tr>
<td class="num">9</td>
<td>style=””</td>
<td>1000 (one inline styling)</td>
</tr>
<tr class="pdd">
<td class="num">10</td>
<td>p { }</td>
<td>1 (one HTML selector)</td>
</tr>
<tr>
<td class="num">11</td>
<td>div p { }</td>
<td>2 (two HTML selectors)</td>
</tr>
<tr class="pdd">
<td class="num">12</td>
<td>.sith</td>
<td>10 (one class selector)</td>
</tr>
<tr>
<td class="num">13</td>
<td>div p.sith { }</td>
<td>12 (two HTML selectors and a class selector)</td>
</tr>
<tr class="pdd">
<td class="num">14</td>
<td>#sith</td>
<td>100 (one id selector)</td>
</tr>
<tr>
<td>15</td>
<td>body #darkside .sith p { }</td>
<td>112 (HTML selector, id selector, class selector, HTML selector; 1+100+10+1)</td>
</tr>
</tbody>
</table>

Để khỏi tính toán mệt mỏi có thằng đã làm hẳn một website để [tính toán specificity](https://specificity.keegan.st/) nhé luôn này.

![Specificity Calculator](http://blogk.xyz/wp-content/uploads/2016/05/Specificity-Calculator.png)

### Thắc mắc nhỏ

Ta nhận thấy **id** cũng là 1 attribute vậy thì ở trường hợp sau selector nào sẽ thắng?

<script src="https://gist.github.com/tutv95/c9586e5fd5fcb4d9fb5f5a3cc976d3de.js"></script>

Tất nhiên là trường hợp 1 sẽ thắng đúng không nào? Trường hợp 1 specificity là 101 còn trường hợp 2 ta sử dụng attribute để chọn nên specificity là 11, kết quả đã rõ.

### Kết luận

Nói là khó nhưng thực ra cũng dễ mà! Dựa vào **CSS Specificity** ta sẽ viết CSS 1 cách dễ dàng, gọn gàng, dễ bảo trì hơn trong nghiệp làm front-end của bản thân. Như mình thấy nhiều bố thấy style mà không nhận toàn chơi **!important** từa lưa luôn, sau này muốn phát triển hoặc mở rộng hay debug các kiểu cũng khó. Vậy là từ nay bạn có thể cầm cái này và đập vào đầu thằng nào khi nó viết CSS ngu, sử dụng !importan loạn lên hoặc không tối ưu nhé :))