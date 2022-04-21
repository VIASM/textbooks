# Phép chia hết và Số nguyên tố

## Ước số và Bội số 

> section: Ước số và Bội số  
> id: divisibility1
> description: Số nguyên tố đại diện cho tất cả những tính chất căn bản và phức tạp nhất của những vấn đề chưa được giải quyết. Tại đây, em có thể tìm hiểu về các thành phần của toán học. 
> color: "#1AA845"
> level: Cơ bản

Đến thời điểm này, em có thể đã quen thuộc với phép cộng, phép trừ và phép nhân 
của các số nguyên. Phép chia có một sự khác biệt nhỏ, bởi vì không phải lúc nào em cũng có thể chia 
bất kỳ hai số nguyên nào cho nhau. Ví dụ 17 chia 3 được một kết quả không phải là số nguyên, kết quả
của phép chia này ở đâu đó trong khoảng 5 và 6. Em có thể phải đưa số dư (2), hoặc
thể hiện đáp án dưới dạng số thập phân (5.66…).

    .row.padded
      .grow
        include svg/divisibility-1.svg
        p.caption 12 chia hết cho 3 
      .grow
        include svg/divisibility-2.svg
        p.caption 10 không chia hết cho 4

Nếu em có thể chia một số __{.m-red} A__ bởi một số __{.m-blue}B__, mà
không có số dư, chúng ta có thể nói rằng __{.m-blue}B__ là một __thừa số__ (hoặc __ước số__) của
__{.m-red}A__, và số __{.m-red}A__ là một __bội số__ của __{.m-blue}B__. Chúng ta thường
viết __{.m-blue}B__|__{.m-red}A__, dấu gạch thẳng có nghĩa là  là _“chia hết”_.

Ví dụ, __{.m-green}7__ × 3 = __{.m-orange}21__, nên __{.m-green}7__ là một
[[ước số|bội số]] của __{.m-orange}21__. Tương tự, __{.m-orange}21__ là một [[bội số|ước số]]
của __{.m-green}7__, và chúng ta có thể viết __{.m-green}7__|__{.m-orange}21__.

---
> id: Phép chia hết - Trò chơi 

Trong trò chơi ngắn dưới đây, em phải xác định các số là ước số hay bội số: 

::: .box.blue.no-padding
#### Câu đố về ước số và Bội số: 

    x-gameplay.factors-quiz
      .circled ${x}
      | is a
      .factor-value
        .factor-bubble: .btn.btn-blue ước số 
        .factor-bubble: .btn.btn-blue bội số 
        .factor-bubble: .btn.btn-blue không 
      | of
      .circled ${y}

:::

---
> id: factor

Việc tìm ra _tất cả_ các ước số của một số thường rất hữu ích. Ví dụ, 
ước số của 60 là 1, 2, 3, 4, 5, 6, 10, 12, 15, 20, 30 và 60.

Tất nhiên, em không muốn kiểm tra hết tất cả các số từ 1 đến 60 để xác định xem nó phải là ước số hay không. 
Thay vào đó, có một cách đơn giản đó là dựa vào thực tế rằng ước số luôn xuất hiện theo [[bộ đôi|bộ ba|một nửa]].

---
> id: factors1 

Trong trường hợp của số 60 chúng ta có 60 = 1 × 60 = 2 × 30 = 3 × 20 = 4 × 15 = 5 × 12 =
6 × 10. Hoặc, trong một cách hiểu khác,


    include mixins
    +divisor-table([1, 2, 3, 4, 5, 6, 10, 12, 15, 20, 30, 60], [5, 4, 3, 2, 1, 0])


Để tìm tất cả các ước số của một số, chúng ta chỉ cần bắt đầu ở hai đầu của danh sách này 
cho đến khi gặp nhau ở giữa. 

---
> id: factors2

    include mixins
    x-slideshow
      .stage(slot="stage")
        +divisor-table([1, 2, 3, 6, 7, 14, 21, 42], [3, 2, 1, 0])
      .legend(slot="legend") Ví dụ, cặp ước số đầu tiên của 42 đơn giản là 1 và 42, và chúng ta viết ra hai số này với nhiều khoảng trắng ở giữa.
      .legend(slot="legend") Sau số 1 ở đầu, chúng ta kiểm tra xem 42 có chia hết cho 2. Nếu chia hết, cặp số tương ứng là  42 ÷ 2 = 21.
      .legend(slot="legend") Sau đó, chúng ta kiểm tra phép chia của 42 và 3. Nếu chia hết, và cặp số tương ứng là 42 ÷ 3 = 14.
      .legend(slot="legend") Bây giờ chúng ta kiểm tra phép chia của 42 và 4. Tuy nhiên, nếu không chia hết, chúng ta có thể tiếp tục.
      .legend(slot="legend") 42 cũng không chia hết cho 5, nên chúng ta tiếp tục. 
      .legend(slot="legend") 42 chia hết cho 6. Cặp số tiếp theo là 42 ÷ 6 = 7. Lưu ý rằng, chúng ta đã gặp số ở giữa chỉ qua một vài lần thử mà không phải kiểm tra tất cả các số từ 7 đến 42.

Trường hợp đặc biệt duy nhất trong cách làm này đó là số chính phương: trong trường hợp này, em 
sẽ chỉ gặp một số duy nhất ở giữa, ví dụ như 64 = 8 × 8.

    //- TODO Bài tập phân tích ước số

---

## Quy tắc chia hết

> id: divisibility2
> section: rules


Có một vài các quy tắc khác nhau giúp em có thể dễ dàng kiểm tra một số 
có chia hết cho một số khác hay không. Trong bài học này, chúng ta sẽ cùng tìm hiểu một trong số 
những quy tắc đó…


### Chia hết cho 2 và 5

Các số đều chia hết cho 1. Để xác định một số có chia hết cho 2 hay không, chúng ta
chỉ cần kiểm tra xem số đó có phải số chẵn: bất cứ số nào có đuôi là 0, 2, 4, 6, or 8 
đều chia hết cho 2. 


    include mixins
    +grid(30)

---
> id: divisibility5

Để biết một số có chia hết cho 5 hay không, chúng ta đơn giản kiểm tra chữ số cuối cùng xem 
có phải là 0 hoặc 5 hay không:

    include mixins
    +grid(30)

---
> id: divisibility5a


Lý do tại sao quy tắc chia hết cho 2 và cho 5 rất đơn giản để làm với hệ thống số của chúng ta. 
Hệ thống số chúng ta đang sử dụng là hệ cơ số 10, có nghĩa là mỗi chữ số trong hệ cơ số 10 
có giá trị gấp 10 lần chữ số tiếp theo ở bên phải. Nếu chúng ta lấy số 6328 làm ví dụ,


    table.base-10.base-10-fixed
      tr.base-10-large
        td: strong 6
        td: strong 3
        td: strong 8
        td: strong 2
      tr.caption
        td: | =6000
        td: | =300
        td: | =80
        td: | =2

Bây giờ, chúng ta có thể tách chữ số cuối cùng của số đó ra khỏi các chữ số khác: 

    table.table-tiny
      tr.base-10-large
        td #[strong.m-red abc]#[strong.m-green d]
        td: | =
        td #[strong.m-red abc × 10]
        td +
        td #[strong.m-green d]
      tr.caption
        td #[strong.m-red 638]#[strong.m-green 2]
        td: | =
        td #[strong.m-red 638 × 10]
        td +
        td #[strong.m-green 2]

Cả 2 và 5 đều là ước số của 10, vì vậy chúng sẽ [[luôn luôn chia hết|không bao giờ chia hết|đôi khi chia hết]] __{.m-red}abc × 10__, dù giá trị của  __{.m-red}a__, __{.m-red}b__
và __{.m-red}c__ là bao nhiêu. Vì vậy chúng ta chỉ cần kiểm tra chữ số cuối cùng: nếu
__{.m-green}d__ chia hết cho 2 thì [[cả số đó|abc]] cũng chia hết cho 2. Nếu __{.m-green}d__ chia hết cho 5 thì cả số đó cũng chia hết cho 5. 

---
> id: divisibility4b

Đơn giản nhất là quy tắc chia hết cho 10: chúng ta chỉ cần kiểm tra xem
[[chữ số cuối cùng là 0|chữ số đầu tiên là 1|chữ số cuối cùng là số chẵn].

---
> id: divisibility4

### Chia hết cho 4 và chia hết cho 8 

Thật không may là 10 không chia hết cho 4, vì vậy chúng ta không thể nhìn vào chữ số cuối cùng –
nhưng 100 có thể chia hết cho 4, vì vậy chúng ta chỉ cần thay đổi quy tắc này một chút.
Bây giờ, chúng ta viết __{.m-red}ab__**{.m-green}cd** = __{.m-red}ab × 100__ +
__{.m-green}cd__. Chúng ta biết rằng __{.m-red}ab × 100__ sẽ luôn luôn chia hết cho 4, vì vậy chúng ta cần nhìn vào [[two]] chữ số cuối cùng để kiểm tra xem số đó có chia hết cho 4 không. 

Ví dụ, __{.m-green}24__ chia hết cho 4 vì vậy __{.m-red}2735__**{.m-green}24**
[[cũng|không]] chia hết cho 4, và __{.m-green}18__ không chia hết cho 4 nên 
__{.m-red}1947__**{.m-green}18** [[cũng |không ]] không chia hết cho 4. 

---
> id: divisibility4a

Quy tắc chia hết cho 8 thì phức tạp hơn một chút nữa, vì 100 không chia hết cho 8. Thay vào đó, chúng ta cần phải xem [[1000|800|108]] và nhìn xem [[ba]] chữ số cuối của số đó. 
Ví dụ, __{.m-green}120__ chia hết cho 8 nên 
__{.m-red}271__**{.m-green}120** cũng chia hết cho 8. 

---
> id: divisibility3a

### Chia hết cho 3 và 9 

Quy tắc chia hết cho 3 lại khó hơn nữa. 10 không thể chia hết cho 3, và thậm chí 100, 1000, hoặc bất kỳ luỹ thừa nào của 10 cũng không thể chia hết cho 3. Việc chỉ nhìn vào một vài chữ số cuối cùng của số đó không thể giúp chúng ta tìm được xem số đó có chia hết cho 3 hay không. 

Thay vào đó, chúng ta sử dụng  __tổng chữ số__ của một số, đơn giản là chúng ta cộng các chữ số của số đó lại với nhau. Ví dụ, tổng các chữ số của ${13×n+123}{n|3|0,20,1}
là ${digitSumString(123+13×n)} = ${digitSum(123+13×n)} và tổng của các chữ số của số 3254 là
[[14]].

---
> id: divisibility3b

    include mixins
    +grid(40, function(n) { if (!(n % 3)) { var s = '' + n; return +s[0] + (+s[1] || 0); } })

Ở đây, chúng ta đã đánh dấu rất cả các số là bội số của ba. Em có thể thấy rằng các tổng của các chữ số này luôn là [[bội số của 3| 0 hoặc 3|các số lẻ]].

{.reveal(when="blank-0")} Vì vậy, để xác định rằng một số có chia hết 3 hay không, chúng ta cần tính tổng của các chữ số của số đó, và kiểm tra xem tổng này có chia hết cho 3 hay không. 

---
> id: divisibility9

Tiếp theo, chúng ta hãy cùng quan sát bội số của 9. :

    .number-grid
      for x in [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20]
        .number-cell.yellow= x*9
          .number-badge= (x == 11 ? 18 : 9)

Dường như tất cả các số chia hết cho 9 đều có tổng các chữ cố 
[[cũng|không]] chia hết cho 9. _{span.reveal(when="blank-0")}Ví dụ, tổng các chữ số của 4752 là  [[18]], vì vậy 4752 [[có|không]] chia hết có 9._

---
> id: divisibility9a

Tất nhiên, các quy tắc của các số chia hết cho 3 và 9 đều xuất phát từ một số lý do – giống như trước đây chúng ta làm với hệ cơ số 10 . Như chúng ta nhìn thấy, khi viết số __{.m-red}6__**{.m-blue}3**__{.m-green}8__**{.m-yellow}4**
có nghĩa là

{.text-center} __{.m-red}6 × 1000__ + __{.m-blue}3 × 100__ + __{.m-green}8 × 10__ + __{.m-yellow}4__.

Chúng ta có thể chia tích nhân này làm hai phần: 

{.text-center} __{.m-red}*{span.digit-sum-else}6 × 999* + *{span.digit-sum-is}6*__ +
__{.m-blue}*{span.digit-sum-else}3 × 99* + *{span.digit-sum-is}3*__ +
__{.m-green}*{span.digit-sum-else}8 × 9* + *{span.digit-sum-is}8*__ +
__{.m-yellow.digit-sum-is}4__.

Dĩ nhiên, __{.m-green}9__, __{.m-blue}99__, __{.m-red}999__, luôn luôn chia hết cho 3 (hoặc 9). Chúng ta chỉ cần kiểm tra phần xem phần con lại có chia hết cho 3 (hoặc 9) hay không. 


{.text-center} __{.m-red}6__ + __{.m-blue}3__ + __{.m-green}8__ + __{.m-yellow}4__

Đây chỉ là tổng các chữ số! Nếu [{.no-margins}tổng chữ số](->.digit-sum-is) là một bội số của 3, chúng ta biết rằng [{.no-margins}phần còn lại](->.digit-sum-else) là một bội số của 3, thì kết quả cũng phải là một bội số của 3. 

---
> id: divisibility6
> goals: btn2 btn3

### Chia hết cho 6

Chúng ta đã bỏ qua số 6 – nhưng chúng ta đã làm qua những phần khó. 
Hãy nhớ rằng  6 = 2 × 3.

    include mixins
    +grid(40)
    p.btn-row.text-center.no-voice(style="margin-bottom:1em")
      button.btn.btn-small(data-display="visibility") Show multiple of 2
      button.btn.btn-small(data-display="visibility") Show multiple of 3

Để kiểm tra một số có chia hết cho 6 hay không chúng ta chỉ cần kiểm tra xem số đó có chia hết cho 2 [[và |hoặc]] chia hết cho 3 hay không. Lưu ý rằng điều này áp dụng với số 6, nhưng không được áp dụng cho  bắt kỳ_ số nào là tích của hai số khác. 
Còn rất nhiều điều ở sau đó .... 

    //- TODO Các bài tập thực hành
---

## Số Nguyên tố 

> id: primes
> section: primes

Khi tính toán các cặp ước số, có thể xảy ra trường hợp một số không có bất kỳ ước số nào khác ngoài cặp ước số đầu tiên.  Một ví dụ là số 13 – chỉ có một cặp ước số là 
1 và 13. Những số có tính chất đặc biệt này được gọi  __Số Nguyên tố__. Các số này không thể tách số này thành tích của các số nhỏ hơn, và chính bởi cách này biến chúng thành "nguyên tử của số đó"

Lưu ý rằng số 1 _không phải_ là một số nguyên tố, vì vậy một số số nguyên tố đầu tiên là 
2, 3, 5, 7, 11, 13, …

    //- TODO Bài tập

---
> id: primes1

Bất kỳ số nào không phải là số nguyên tố có thể được viết dưới dạng tích của các số nguyên tố: đơn giản là chúng ta tiếp tục chia số này thành các phần nhỏ hơn cho đến khi tất cả các ước số là số nguyên tố. Ví dụ, 

    table.table-tiny
      tr
        td(colspan=4)
        td: .number-ball.legs.b.a 84
      tr
        td(colspan=2)
        td: .number-ball.blue 2
        td(colspan=3) ×
        td: .number-ball.blue.legs.b 42
      tr
        td(colspan=4)
        td: .number-ball.green 2
        td(colspan=2) ×
        td: .number-ball.green.legs(style="margin: 0 -10px") 21
      tr.td-border-bottom
        td(colspan=6)
        td: .number-ball.yellow 3
        td ×
        td: .number-ball.yellow 7
      tr
        td: .number-ball 84
        td: | =
        td: .number-ball.blue 2
        td ×
        td: .number-ball.green 2
        td ×
        td: .number-ball.yellow 3
        td ×
        td: .number-ball.yellow 7

Bây giờ 2, 3 và 7 đều là số nguyên tố và không thể chia được hơn nữa. Tích của 
2 × 2 × 3 × 7 được gọi là __tích số nguyên tố__ của 84, và 2, 3 và 7 là
 __thừa số nguyên tố__ của nó. Lưu ý rằng, với một số số nguyên tố, như số 2 trong trường hợp này, có thể xuất hiện nhiều lần trong tích số nguyên tố. 

Mỗi số nguyên có một tích số nguyên tố  và không có hai số nguyên nào có cùng tích số nguyên tố. Hơn nữa, chỉ có một cách duy nhất để viết bất kỳ số nào dưới dạng tích của các số nguyên tố – trừ khi chúng ta thay đổi thứ tự của các số nguyên tố trong tích đó. Điều này được gọi là __Định lý cơ bản của số học __ (Fundamental Theorem of Arithmetic - FTA).

Sử dụng Định lý cơ bản của số học có thể khiến cho các bài toán trở nên đơn giản hơn: chúng ta chia các số thành các thừa số nguyên tố của chúng, chúng ta giải các bài toán cho các số nguyên tố riêng lẻ, thường là các bài toán này dễ hơn, và sau đó chúng ta sẽ kết hợp các kết các kết quả này để giải bài toán ban đầu. 
    //- TODO Bài tập

---
> id: eratosthenes

### Sàng Eratothenes (The Sieve of Eratosthenes)

Việc xác định một số là số nguyên tố khá khó vì bạn luôn phải tìm 
 _tất cả_ các thừa số nguyên tố của chúng, việc này sẽ càng trở nên khó khăn hơn khi chúng ta gặp các số lớn. Thay vào đó, Nhà toán học Hy Lạp [Eratosthenes of
Cyrene](bio:eratosthenes)đã đưa ra một thuật toán đơn giản để tìm tất cả các số nguyên tố đến 100: __Sàng Eratosthenes__.

    include mixins
    x-slideshow
      .stage(slot="stage")
        +grid(100)
      .legend(slot="legend") Đầu tiên chúng ta cần viết các số đến 100. 
      .legend(slot="legend") Chúng ta biết rằng, 1 không phải là số nguyên tố nên chúng ta sẽ xoá số 1.
      .legend(slot="legend") Số nguyên tố nhỏ nhất là #[strong.m-red 2]. Bất kỳ bội số của 2 đều không thể là số nguyên tố vì các số đó đã có 2 là thừa số. Vì vậy chúng ta có thể xoá đi tất cả các bội số của 2. 
      .legend(slot="legend") Số tiếp theo trong danh sách là số  #[strong.m-blue 3] – lại là một số nguyên tố. Tất cả các bội số của 3 sẽ không thể là số nguyên tố , vì các số này đã có 3 là thừa số. Vì vậy, chúng ta có thể loại bỏ các số này đi. 
      .legend(slot="legend") Số tiếp theo, 4, đã bị loại nên chúng ta sẽ chuyển đến số tiếp theo #[strong.m-green 5]: đây là một số nguyên tố và tất nhiên chúng ta cũng sẽ loại các bội số của 5. 
      .legend.md(slot="legend") Số nguyên tố tiếp theo là số  [[7]], vì số 6 đã bị loại bỏ đi trước đó. Một lần nữa, chúng ta cũng sẽ loại bỏ các bội số của 7. 
      .legend.md(slot="legend") Số nguyên tố tiếp theo là [[11]]. Tuy nhiên, lưu ý rằng, tất cả các bội số của chúng  [[đã bị gạch bỏ| bội số của 3]]. Điều này cũng đúng với tất cả các số còn lạị. Do đó tất cả các số còn lại này đều là số nguyên tố. 

Bây giờ chúng ta có thể đếm được có [[25]] số nguyên tố nhỏ hơn 100. 

---
> id: primes3

### Có tất cả bao nhiêu số nguyên tố? 

::: column.grow
Tất nhiên, chúng ta hoàn toàn có thể sử dụng Sàng Eratosthenes để tìm các số nguyên tố lớn hơn.  Có 21 số nguyên tố nằm trong khoảng từ  100 đến 200, 16 số nguyên tố nằm giữa 200 đến 300,
17 số nguyên tố nằm giữa 400 và 500 và chỉ có 11 số nguyên tố nằm giữa 10,000 và 10,100.

Các số nguyên tố dường như sẽ còn xuất hiện nhiều hơn nữa, nhưng liệu chúng có bao giờ dừng lại? 
Liệu có số nguyên tố  _lớn nhất_ hoặc số nguyên tố _cuối cùng_?

Nhà toán học Hy Lạp cổ đại [Euclid of Alexandria](bio:euclid) đã lần đầu tiên chứng minh rằng có vô hạn số nguyên tố, bằng cách sử dụng lập luận sau: 
::: column(width=220)

    x-img(lightbox width=220 height=300 src="images/euclid.jpg" alt="Euclid of Alexandria Portrait")

:::

    ol.proof
      li Giả sử rằng, chúng ra chỉ có hữu hạn các số nguyên tố.
        .text-center #[em.number-ball.blue P], #[em.number-ball.blue P], #[em.number-ball.blue P], #[em.number-ball.blue P], #[em.number-ball.blue P]
      li Hãy nhân các số đó lại với nhau, chúng ta sẽ được một số rất lơn gọi là #[em N].
        .text-center #[em.number-ball N] = #[em.number-ball.blue P] × #[em.number-ball.blue P] × #[em.number-ball.blue P] × #[em.number-ball.blue P] × #[em.number-ball.blue P]
      li Bây giờ hãy cùng xem xét #[em N] + 1. Bất kỳ số nguyên tố nào chia hết #[em N] không thể chia hết #[em N] + 1. Và vì vậy tất cả các số nguyên tố chúng ta đã biết có thể chia hết #[em N], và chúng không thể chia hết  #[em N] + 1.
        .text-center #[em.number-ball.blue P], #[em.number-ball.blue P], #[em.number-ball.blue P], #[em.number-ball.blue P], #[.number-ball.blue P] #[span.divides] #[em.number-ball N]
        .text-center #[em.number-ball.blue.cross P], #[em.number-ball.blue.cross P], #[em.number-ball.blue.cross P], #[em.number-ball.blue.cross P], #[.number-ball.blue.cross P] #[span.divides] #[em.number-ball N] + 1
      li.md Chúng ta biết rằng từ [Định lý cơ bản của số học](gloss:fta) #[em N] + 1, phải có một thừa số nguyên tố. Bản thân #[em N] + 1 là một số nguyên tố, hoặc có một số nguyên tố mới là #[em P’] chia hết #[em N] + 1.
        .text-center #[em.number-ball.green P’] #[span.divides] #[em.number-ball N] + 1
      li Trong cả hai trường hợp này, chúng ta đều tìm ra một số nguyên tố mới không có trong danh sách ban đầu – mặc dù chúng ta đã giả sử rằng #[em all] các số nguyên tố đều nằm trong danh sách này. 
      li Rõ ràng, có điều gì đó đã sai ở đây! Tuy nhiên từ bước  #[span.proof-step 2]–#[span.proof-step 4] đều chắc chắn hợp lệ, khả năng duy nhất là giả định ban đầu của chúng ta trong #[span.proof-step 1] đã sai. Điều này có nghĩa thực tế phải có vô số nguyên tố. 

    // Lưu ý rằng bất kỳ số nguyên tố nào chia hết N không thể chia hết N + 1. (Nếu có thể
    // số đó cũng chia hết cho hiệu của N và N + 1, đó chính là số 1. Tuy nhiên
    // số nguyên chỉ chia hết 1 là chính nó)

---
> id: primes4

Lời giải thích Euclid là một trong những ví dụ đầu tiên trong lịch sử về một  __chứng minh__ toán học chính thức – một lập luận logic cho thấy một mệnh đề chắc chắn phải đúng. Ví dụ này thường được gọi là __chứng minh bằng phản chứng __: chúng ta bắt đầu với một giả định, suy ra một điều gì đó không thể, và từ đó biết rằng giả định của chúng ta là không chính xác. 


---

## Phân bố của Số nguyên tố

> id: prime-test
> goals: calculator
> section: distribution-of-primes

Cách dễ nhất để kiểm tra xem một số có phải một số nguyên tố hay không là cố gắng chia số đó cho các số nguyên nhỏ hơn. Máy tính có thể làm việc này rất nhanh và hiệu quả. Với các số _rất lớn_, với hàng trăm chữ số, cũng có những thuật toán hiệu quả hơn. Một trong số đó thậm chí còn sử dụng xác suất để xác định xem một số 
_gần như chắc chắn_ là số nguyên tố.

Đây là một chiếc máy tính cho phép chúng ta kiểm tra một số bất kỳ có phải số nguyên tố hay không: 
    .calculator
      h3 Kiểm tra Số nguyên tố
      input(type="number" min="2")
      .result.var(:html="result")

---
> id: prime-test-1

::: column.grow

Trong suốt lịch sử, con người đã cố gắng tìm ra những số nguyên tố ngày càng lớn hơn.
Vào năm 1460, số nguyên tố lớn nhất là 131,071. Năm 1772, [Leonard Euler](bio:euler)
chỉ ra rằng 2,147,483,647 cũng là một số nguyên tố. 

Với sự xuất hiện của máy tính vào thế kỷ 20, Việc tính toán các số nguyên tố lớn hơn trở nên dễ dàng hơn rất nhiều. Số nguyên tố lớn nhất hiện đang được biết đến đã được phát hiện vào tháng 12 năm 2018
và có 24,862,048 chữ số.  Em sẽ cần 8000 tờ giấy để in được số này ra. 

::: column(width=300)

    img(src="images/network.jpg" width=300 height=200)

{.caption} GIMPS (_Great Internet Mersenne Prime Search_) là một dự án hợp tác, tại đây các tình nguyện viên có thể tìm các số nguyên tố bằng cách sử dụng phần mềm miễn phí. 

:::

---
> id: prime-generator
> goals: calculator

Việc tính toán những số nguyên tố lớn có vẻ chỉ tốn thời gian, tuy nhiên, ở phần sau của khoá học này, em sẽ tìm hiểu về các ứng dụng thực tế khác nhau trong đó máy tính phải sử dụng các số nguyên tố lớn. 

Tại đây, em có thể tự tạo ra các số nguyên tố với số chữ số cho sẵn. 

    .calculator
      h3 Tạo số nguyên tố
      p.no-voice.md Số các chữ số: ${d}{d|6|2,16,1}
      p.no-voice(style="margin: 10px 0"): button.btn.btn-white Tạo
      .result.var(:html="result")

---
> id: ulam

    //- Stanislaw M. Ulam đang vẽ nguệch ngoạc trong buổi thuyết trình về một " tờ giấy dài và nhàm chán" tại một cuộc họp khoa học vào năm 1963. 

### Xoắn ốc Ulam

Nhà toán học Ba Lan [Stanisław Ulam](bio:ulam) đã nghĩ ra một cách tuyệt vời để hiển thị sự phân bố của các số nguyên tố lớn, trong khi vẽ nguệch ngoạc trong một cuộc họp _“dài và nhàm chán”_ vào năm 1963. 

    .number-grid.ulam-grid
      for x in [37, 36, 35, 34, 33, 32, 31]
        .number-cell(data-display="visibility")= x
      for x in [38, 17, 16, 15, 14, 13, 30]
        .number-cell(data-display="visibility")= x
      for x in [39, 18,  5,  4,  3, 12, 29]
        .number-cell(data-display="visibility")= x
      for x in [40, 19,  6,  1,  2, 11, 28]
        .number-cell(data-display="visibility")= x
      for x in [41, 20,  7,  8,  9, 10, 27]
        .number-cell(data-display="visibility")= x
      for x in [42, 21, 22, 23, 24, 25, 26]
        .number-cell(data-display="visibility")= x
      for x in [43, 44, 45, 46, 47, 48, 49]
        .number-cell(data-display="visibility")= x

Chúng ta viết ra tất cả các số nguyên trong một lưới hình chữ nhật, bắt đầu bằng số 1 ở giữa và sau đó theo hình xoắn ốc ra ngoài. Sau đó, chúng ta đánh dấu tất cả các số là số nguyên tố. 

---
> id: ulam1

Cho đến nay, xoắc ốc Ulam trông không đặc biệt thú vị. Nhưng nếu chúng ta thu nhỏ lại, các mô hình thú vị sẽ xuất hiện. Dưới đây là hình ảnh các số nguyên tố tới 160,000:

    figure: img(src="images/ulam.png" width=399 height=399)

::: column.grow
Thay vì xuất hiện một cách ngẫu nhiên, như người ta mong đợi, có vẻ dường như một số đường chéo nhất định phổ biến hơn với các số nguyên tố hơn những cái khác. Điều này tạo ra một mẫu "kẻ sọc" gây tò mò. 
_{.lgrey} Các đường chéo này đều tương ứng với một số phương trình bậc hai nhất định mà dường như tạo ra các số nguyên tố thường xuyên hơn. Tuy nhiên, điều này hiện tại vẫn chưa được giải thích…_
::: column(width=200)

    x-img(lightbox credit="© Scientific American" width=200 height=272 src="images/magazine.jpg" alt="Scientific American Magazine Cover")

{.caption} Trang bìa của Tạp chí Khoa học Mỹ số tháng 3 năm 1964. 
:::

---
> id: goldbach1
> goals: calculator

### Giả thuyết Golbach

Vào năm 1972, nhà toán học người Đức có tên là [Christian Goldbach](bio:goldbach)đã thực hiện 
một khám phá: ông nhận ra rằng tất cả các số nguyên chẵn (trừ số 2) đều có thể viết được dưới dạng tổng của hai số nguyên tố.
Ví dụ, 8 = 5 + 3 và 24 = 13 + 11. Điều này khá bất ngờ, vì số nguyên tố được xác định bằng phép nhân và thừa số, và hoàn toàn không liên quan nhiều đến phép cộng. 
    .calculator
      h3 Goldbach Calculator
      p.no-voice Chọn một số chẵn bất kỳ, để tính xem nó #[br]có thể viết thế nào dưới dạng tổng của hai số nguyên tố. 
      input(type="number", min=4, step=2)
      .result.var(:html="result")

Goldbach đã viết về quan sát của mình trong một bức thư gửi nhà toán học nổi tiếng
[Leonhard Euler](bio:euler), nhưng cả hai đều không chứng minh được điều đó. Và từ đó nó có tên gọi là  __Giả thuyết Goldbach__.

Máy tính đã kiểm tra Giả thuyết Goldbach đúng với mọi số chẵn đến 
4 × 10<sup>18</sup> (đó là 4 với 18 số không), nhưng các nhà toán học đều chưa tìm được cách chứng minh rằng giả thuyết là đúng cho  _tất cả_ các số nguyên chẵn. Và đây là một vấn đề rất lớn, vì chúng ta có vô hạn các số nguyên, vì vậy chúng ta không thể kiểm tra tất cả chúng.

Sự đơn giản rất rõ ràng trong Giả thuyết của Goldbach đã trở thành một trong những bài toán chưa có lời giải nổi tiếng nhất trong toán học. 
---
> id: twin-primes

### Số nguyên tố sinh đôi (Twin Primes) 

Chúng ta đã thấy rằng các số nguyên tố trải ra nhiều hơn khi chúng lớn hơn. 
Nhưng chúng dường như luôn luôn xuất hiện hoàn toàn ngẫu nhiên, và đôi khi chúng ta tìm thấy hai số nguyên tố ngay cạnh nhau, hoặc chỉ cách nhau một số: những số này được gọi là  __Số nguyên tố sinh đôi.

    p.text-center
      span.twin
        span.number-ball 3
        span.number-ball 5
      | ,
      span.twin
        span.number-ball.blue 11
        span.number-ball.blue 13
      | ,
      span.twin
        span.number-ball.green 41
        span.number-ball.green 43
      | ,
      span.twin
        span.number-ball.yellow 101
        span.number-ball.yellow 103
      | ,
      span.twin
        span.number-ball 2027
        span.number-ball 2029
      | ,
      span.twin
        span.number-ball.blue 108,377
        span.number-ball.blue 108,379
      | ,
      span.twin
        span.number-ball.green 1,523,651
        span.number-ball.green 1,523,653

Cặp số nguyên tố sinh đôi lớn nhất  được biết đến có đến tận 58,711 chữ số! Tuy nhiên, số nguyên tố sinh đôi có vô hạn hay không, giống như sự vô hạn của các số nguyên tố?
Không một ai biết điều này _Giả thuyết về số nguyên tố sinh đôi_ là một trong những vấn đề chưa được giải quyết xung quanh các số nguyên tố. 

---
> id: riemann
> goals: zoom
> title: Sự phân bố của các số nguyên tố

### Giả thuyết Riemann 

Các nhà toán học đã dành nhiều thế kỷ để khám phá mô hình và sự phân bố của các
số nguyên tố. Các số nguyên tố dường như xuất hiện hoàn toàn ngẫu nhiên - và đôi
có khoảng cách lớn giữa các số nguyên tố liên tiếp và đôi khi chúng ta tìm thấy [số nguyên tố sinh đôi](gloss:twin-primes)
ngay cạnh nhau.
Khi chỉ mới 15 tuổi, nhà toán học người Đức [Carl Friedrich Gauss](bio:gauss)
đã có một ý tưởng đột phá: ông đếm số lượng các số nguyên tố đến một điểm nhất định, và hiển thị kết quả dưới dạng biểu đồ:

    figure(style="max-width:680px; position:relative;")
      svg(width=680 height=300 viewBox="0 0 680 300")
        line.axis(x1=0 y1=280 x2=680 y2=280)
        g.chart
          path.pi(fill="none" stroke="#0f82f2")
          path.log(fill="none" stroke="#cd0e66")
          g.small-primes
        g.numbers
      .zoom-icon: svg(viewBox="0 0 32 32" class="icon" width=32 height=32)
        use(xlink:href="/icons.svg#search")

Dọc theo trục x, em có thể nhìn thấy tất cả các số nguyên. Bất cứ khi nào có một số nguyên tố, the
_{span.m-blue}Hàm đếm các số nguyên tố_ (shown in __{.m-blue}blue__) tăng lên một. Khi chúng ta [thu nhỏ](->#riemann_.zoom-icon), đường màu xanh trở nên rất mịn.
Gauss nhận thấy rằng hình dạng của hàm số này khá giống với với hàm số 
_{span.m-red}`x/(log(x))`_ (shown in __{.m-red}red__). Ông dự đoán rằng hai hàm này “gần giống nhau”, và điều này được chứng minh vào năm 1896. 

---
> id: riemann1
> title: Giả thuyết Riemann 

Tuy nhiên, như em có thể thấy ở trên, vẫn có một sai số đáng kể giữa các số nguyên tố 
và sự tính toán gần đúng của Gauss. Vào năm 1859, nhà toán học
[Bernhard Riemann](bio:riemann) đã phát hiện ra một phép toán gần đúng và có vẻ tốt hơn, nhưng ông không thể chứng minh rằng nó sẽ  _luôn luôn_ hoạt động.
Ý tưởng của ông được biết đến dưới tên gọi __ Giả thuyết Riemann__.

Hằng trăm nhà toán học đã cố gắng chứng minh Giả thuyết của Riemann, nhưng không ai thành công. Giả thuyết này cũng được coi là một trong những bài 
toán khó giải và quan trọng nhất trong toán học. Năm 2000, Viện Toán học Clay đã đặt tên nó là một trong bảy [__Các bài toán Thiên niên kỷ__](gloss:millennium-prize)
and bất cứ nhà toán học nào giải được sẽ được nhận giải thưởng có giá trị $1,000,000. 
---

## Bội chung nhỏ nhất 

> id: race
> goals: race
> section: lcm

Hai vận động viên chạy bộ đang luyện tập trên đường đua hình tròn. __{.m-blue}Vận động viên thứ nhất__
mất __{.m-blue}60__ giây cho 1 vòng. __{.m-green}Vận động viên thứ hai chỉ mất __{.m-green}40__ giây để hoàn thành một vòng chạy. Nếu cả hai xuất phát cùng một lúc ở vạch xuất phát, thì khi nào họ gặp lại nhau ở vạch xuất phát? 

    figure: include svg/race.svg

---
> id: race1

Câu hỏi này thực sự không phải về hình dạng của đường đua, hay về vận tốc và tốc độ - mà đây là câu hỏi về bội số và tính chia hết. 

Vận động viên thứ nhất sẽ vượt qua vạch xuất phát sau 60 giây, 120 giây, 180 giây, 240 giây, ... 
Đây đơn giản là  [[bội số|ước số]] của __{.m-blue}60__. Vận động viên thứ hai sẽ vượt qua vạch xuất phát sau 40 _{span(voice="seconds")}s_, 80 _{span(voice="seconds")}s_, 120
_{span(voice="seconds")}s_, 160 _{span(voice="seconds")}s_,.... Lần đầu tiên cả hai vận động viên cùng qua vạch xuất phát là sau [[120]] giây. 
{.reveal(when="blank-0 blank-1")} Những gì chúng ta vừa tìm được là bội số nhỏ nhất của __{.m-green}40__ và __{.m-blue}60__.
Số này được gọi là __bội chung nhỏ nhất__ hoặc__BCNN__.

---
> id: race2

Để tìm BCNN của hai số bất kỳ, điều quan trọng cần nhận ra rằng nếu a 
__{.m-yellow}a__ chia hết __{.m-blue}b__, thì __{.m-blue}b__ cần có tất cả
các thừa số nguyên tố của  __{.m-yellow}a__ (cộng thêm một số nữa):

    table.table-tiny
      tr
        td.text-right: .number-ball.yellow 12
        td: .divides
        td(style="text-align: left"): .number-ball.blue 60
      tr
        td
          .number-ball.l-yellow 2
          | &nbsp;×&nbsp;
          .number-ball.l-yellow 2
          | &nbsp;×&nbsp;
          .number-ball.l-yellow 3
        td
        td
          .number-ball.l-yellow 2
          | &nbsp;×&nbsp;
          .number-ball.l-yellow 2
          | &nbsp;×&nbsp;
          .number-ball.l-yellow 3
          | &nbsp;×&nbsp;
          .number-ball.l-blue 5

Điều này rất dễ kiểm chứng: nếu một thừa số nguyên tố chia hết a __{.m-yellow}a__, và
__{.m-yellow}a__ chia hết __{.m-green}b__, thì các thừa số nguyên tố _cũng_
chia hết __{.m-green}b__.

---
> id: race3

Để tìm BCNN của  __{.m-green}40__ và __{.m-blue}60__, đầu tiên chúng ta cần phải tìm
[thừa số nguyên tố](gloss:factorisation) của cả hai số:

    table.table-tiny
      tr
        td: .number-ball.blue 40
        td: | =
        td: .number-ball.l-blue 2
        td: | ×
        td: .number-ball.l-blue 2
        td: | ×
        td: .number-ball.l-blue 2
        td(colspan=3): | ×
        td: .number-ball.l-blue 5
      tr
        td: .number-ball.green 60
        td: | =
        td: .number-ball.l-green 2
        td: | ×
        td: .number-ball.l-green 2
        td(colspan=3): | ×
        td: .number-ball.l-green 3
        td: | ×
        td: .number-ball.l-green 5

Giả sử __{.m-red}X__ là BCNN của __{.m-green}40__ và __{.m-blue}60__.
Khi đó __{.m-green}40__ chia hết __{.m-red}X__, nên _{span.number-ball.small.l-blue}2_,
_{span.number-ball.small.l-blue}2_, _{span.number-ball.small.l-blue}2_ và
_{span.number-ball.small.l-blue}5_ phải là một thừa số nguyên tố của__{.m-red}X__. Ngoài ra,
__{.m-blue}60__ chia hết __{.m-red}X__, nên __{span.number-ball.small.l-green}2__,
_{span.number-ball.small.l-green}2_, _{span.number-ball.small.l-green}3_ và
_{span.number-ball.small.l-green}5_ phải là thừa số nguyên tố của__{.m-red}X__.

---
> id: race4

Để tìm __{.m-red}X__, chúng ta đơn giản chỉ cần kết hợp tất các các thừa số nguyên tố của __{.m-green}40__
và__{.m-blue}60__, nhưng với các số trùng nhau, chúng ta chỉ cần giữ lại duy nhất một số:

{.text-center} __{.m-red}X__ &nbsp;=&nbsp; _{span.number-ball.l-blue-green}2_ ×
_{span.number-ball.l-blue-green}2_ × _{span.number-ball.l-blue}2_ ×
_{span.number-ball.l-green}3_ × _{span.number-ball.l-blue-green}5_

Điều này cho chúng ta __{.m-red}X__ = 120, như chúng ta nhìn thấy. Lưu ý rằng
nếu một thừa số nguyên tố xuất hiện nhiều lần, giống như số 2, chúng ta cần giữ nguyên số lần xuất hiện tối đa của một trong hai số (3 lần trong số __{.m-green}40__ is
nhiều hơn 2 lần trong __{.m-blue}60__).

---
> id: race5

Bây giờ chúng ta có một phương pháp đơn giản để tìm BCNN của hai số:

    ol.proof
      li Tìm thừa số nguyên tố của mỗi số.
      li Nhân các thừa số nguyên tố với nhau, với những số trùng nhau, chúng ta chỉ cần giữ lại số đó 1 lần. 

Chúng ta có thể dùng cách này để tìm được BCNN của ba hoặc nhiều số khác nhau
ví dụ __{.m-blue}12__, __{.m-green}30__ và __{.m-yellow}45__:

    table.table-tiny
      tr
        td: .number-ball.blue 12
        td: | =
        td: .number-ball.l-blue 2
        td: | ×
        td: .number-ball.l-blue 2
        td: | ×
        td: .number-ball.l-blue 3
      tr
        td: .number-ball.green 30
        td: | =
        td: .number-ball.l-green 2
        td(colspan=3): | ×
        td: .number-ball.l-green 3
        td(colspan=3): | ×
        td: .number-ball.l-green 5
      tr
        td: .number-ball.yellow 45
        td: | =
        td(colspan=4)
        td: .number-ball.l-yellow 3
        td: | ×
        td: .number-ball.l-yellow 3
        td: | ×
        td: .number-ball.l-yellow 5

Vì vậy BCNN của __{.m-blue}12__, __{.m-green}30__ và __{.m-yellow}45__ là
2 × [[2]] × 3 × 3 × [[5]] = 180.

---
> id: race6

Số nguyên tố là một trường hợp đặc biệt: BCNN của hai số nguyên tố đơn giản là [[tích|tổng|hiệu]]của chúng, bởi vì các số này không có thừa số nguyên tố chung nào bị "loại bỏ".

    //- TODO Các bài tập

---
> id: cicadas
> goals: bound-low bound-high

### Ve sầu

::: column.grow
Bắc Mỹ là nơi cứ trú của nhiều loại ve sầu. Loài ve sầu này có đặc tính kỳ lạ 
là chúng chỉ xuất hiện vài năm một lần vào mùa hè để sinh sản - thời gian còn lại, 
chúng ở dưới lòng đất. 


Ví dụ, loài ve sầu ở Floria và Mississippi cứ 13 năm mới xuất hiện một lần. 
Loài ve sầu ở Illinois và Iowa phải 17 năm mới xuất hiện 1lần. Nhưng không 
có loài ve sầu nào có chu kỳ 12, 14, 15 hay 16 năm. 
::: column(width=360)

    x-img(width=360 height=240 src="images/cicadas.jpg" alt="Cicadas")

:::

Cả 13 và 17 đều là các số nguyên tố – và điều này có lý do rất thú vị. Hãy tưởng tượng rằng
có những kẻ săn mồi trong rừng giết ve sầu. Những kẻ săn mồi này cũng xuất hiện theo chu kỳ đều 
đặn, khoảng 6 năm 1 lần.


Bây giờ hãy tưởng tượng rằng một bầy ve sầu xuất hiện mỗi ${n}{n|13|4,20,1} năm
(${isPrime(n) ? 'số nguyên tố' : 'không phải số nguyên tố'}). Hai vật sẽ gặp nhau mỗi
${lcm(n,6)} năm, đây là [[BCNN|tích|trung bình cộng]] của 6 và ${n}.

    figure
      include svg/cicadas.svg
      p.caption Thời gian cho đến khi ve sầu gặp kẻ săn mồi, đối với nhiều độ dài chu kỳ khác nhau của ve sầu.

---
> id: cicadas1

Số này dường như  lớn hơn rất nhiều nếu chu kỳ của ve sầu là một số nguyên tố như là số 13, 17.  
Đó là bởi vì các nguyên tố thì không có thừa số chung với số 6, nên khi tính tính BCNN chúng ta 
không bỏ đi bất kỳ thừa số chung nào. 
Dĩ nhiên, ve sầu không có khái niệm gì về số nguyên tố – nhưng qua hàng triệu năm, quá trình tiến 
hoá đã phát hiện ra rằng chu kỳ nguyên tố là an toàn nhất. Động vật săn mồi dường như đã tuyệt chủng
theo thời gian, nhưng chu kỳ các số nguyên tố vẫn còn.

    //- TODO Exercises

---

## Ước chung lớn nhất 

> id: gcd
> section: gcf

Một kiến trúc sư đang thiết kế cho một khoảng sân rộng 18mx30m. Cô ấy muốn nó được bao phủ bởi những viên gạch 
vuông mà không có bất kỳ khoảng trống hoặc chồng chéo dọc theo các bên. Kích thước viên gạch vuông lớn nhất mà 
cô ấy có thể sử dụng là bao nhiêu?
    figure
      include svg/floorplan.svg
      p.text-center.md Viên gạch có kích thước là of ${x}{x|3|1,18,1}m.#[br]#[span.result.var.no-voice]

---
> id: gcd1

Cũng giống như trước đây, đây không phải là một câu hỏi về hình học - đấy là câu hỏi về tính chia hết. 
Chiều dài các cạnh của viên gạch phải chia hết cả 18 và 30,
và số lớn nhất thoả mãn điều kiện đó là [[6]]. Số này được gọi là 
__Ước chung lớn nhất__ hoặc __ƯCLN__ của 18 và 30.

---
> id: gcd2

Một lần nữa, chúng ta có thể sử dụng [phân tích ra thừa số nguyên tố](gloss:factorisation) để tính toán ƯCLN của bất kỳ hai số nào.
Hãy nhớ rằng, bất kỳ thừa số của một số phải có thừa số nguyên tố của số đó. 
    table.table-tiny
      tr
        td: .number-ball.blue 18
        td: | =
        td: .number-ball.l-blue 2
        td: | ×
        td: .number-ball.l-blue 3
        td: | ×
        td: .number-ball.l-blue 3
      tr
        td: .number-ball.green 30
        td: | =
        td: .number-ball.l-green 2
        td: | ×
        td: .number-ball.l-green 3
        td(colspan=3): | ×
        td: .number-ball.l-green 5

Giả sử rằng __{.m-red}X__ là ƯCLN của __{.m-green}18__ và __{.m-blue}30__.
Khi đó __{.m-green}18__ chia hết cho  __{.m-red}X__  nên các thừa số nguyên tố của  __{.m-red}X__
phải nằm trong _{span.number-ball.small.l-blue}2_, _{span.number-ball.small.l-blue}3_
và _{span.number-ball.small.l-blue}3_. Ngoài ra,  __{.m-blue}30__ chia hết cho __{.m-red}X__ 
nên thừa số nguyên tố của __{.m-red}X__ phải nằm trong các số_{span.number-ball.small.l-green}2_,
_{span.number-ball.small.l-green}3_và_{span.number-ball.small.l-green}5_.

---
> id: gcd3

Để tìm__{.m-red}X__, chúng ta đơn giản chỉ cần nhân tất cả các số là thừa số
 nguyên tố của [[cả hai số|một trong hai số] __{.m-green}18__ và __{.m-blue}30__:

{.text-center} __{.m-red}X__ &nbsp;=&nbsp; _{span.number-ball.l-blue-green}2_ ×
_{span.number-ball.l-blue-green}3_ &nbsp;=&nbsp; 6.

---
> id: gcd4

Bây giờ chúng ta có một cách đơn giản để tìm ƯCLN của hai số: 

    ol.proof
      li Tìm thừa số nguyên tố của mỗi số. 
      li Nhân các thừa số nguyên tố chung của cả hai số. 

Một lần nữa, các số nguyên tố rất đặc biệt: ƯCLN của hai số nguyên tố luôn luôn là 
[[1]], bởi vì các số này không có thừa số nguyên tố nào chung nào. 
---
> id: crypto

### Mật mã học - Cryptography

::: column.grow
Một trong những ứng dụng hiện đại quan trọng nhất của số nguyên tố là một lĩnh vực 
trong toán học có tên gọi là__Mật mã học__. Từ hàng ngàn năm nay, người ta cố
gắng che giấu các tin nhắn chỉ để người nhận dự kiến mới có thể đọc được chúng
- đây được gọi là mã hoá. Mã hoá được sử dụng bởi tất cả mọi người, từ các tướng 
lĩnh trao đổi mệnh lệnh bí mật trong chiến tranh đến các email riêng tư hoặc thông tin chi
tiết của ngân hàng trực tuyến. 

Con người luôn cố gắng đưa ra các phương pháp mã hoá tốt hơn, an toàn hơn, tuy nhiên 
sau một thời gian, tất cả chúng đều bị phá vỡ bởi một thuật toán tiên tiến hơn. Trong 
Chiến tranh Thế giới thứ 2, quân đội Đức sử dụng Enigma: một cỗ máy phức tạp bao gồm 
bàn phím, bánh xe quay và phích cắm.Cỗ máy này mã hoá các tin nhắn bằng cách sử dụng 
một trong 158 triệu triệu triệu khả năng  (đó là số 158 với 18 số không phía sau!). 
Mật mã được tin rằng không thể phá vỡ, tuy nhiên một Cơ quan Mật vụ Anh, được dẫn 
dắt bởi nhà toán học Alan Turning, đã dây dựng một số máy tính đầu tiên để có thể giải
mã nó. 
::: column(width=240)

    x-img(lightbox credit="Magnus Manske, via Wikipedia" width=240 height=344 src="images/enigma.jpg" alt="Enigma Machine")
    p.caption Máy Enigma bốn rotor của Đức. 

:::

Ngày nay, máy tính đã tân tiến hơn nhiều, có khả năng thử hàng triệu khả năng
 trong mỗi giây.  Để phát triển các thuật toán mã hoá tốt, em phải tìm được 
các phép toán khó ngay cả đối với các máy tính mạnh. Máy tính thực hiện các 
phép tính cộng, trừ, nhân, chia rất nhanh. Tuy nhiên, máy tính lại rất chậm 
trong việc phân tích các số nguyên lớn thành các số nguyên tố. 


---
> id: crypto1

{.todo} SẮP DIỄN RA – Ví dụ RSA cùng Alice và Bob

Thuật toán mã hoá này được gọi là  __ Mật mã RSA__, được gọi theo tên của ba nhà 
phát minh đó là Ron Rivest, Adi Shamir và Leonard Adleman công bố vào năm 1977. 
Đây cũng là một phương pháp khá tương tự đã được Sở Mật vụ Anh biết đến vào năm 1973, 
nhưng vẫn được phân loại cho đến sau này. 

Ngày nay, các số nguyên tố được sử dụng bởi các máy tính trên toàn thế giới để trao 
đổi dữ liệu. Khi em tìm kiếm trên mạng internet hoặc gửi một tin nhắn, điện thoại hoặc
 máy tính của em sẽ tự tạo ra các số nguyên tố lớn và trao đổi khoá công khai với các máy tính khác.