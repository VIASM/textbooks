# Điểm bùng nổ
## Nấc thang tới vô cực

> section: infinity
> id: race
> description: A mathematical story developed for Global Math Week – learn about place value, infinity and p-adic numbers.
> color: "#6D3BBF"

Trong thần thoại Hy Lạp cổ đại, Achilles là một trong những vị anh hùng bất khả chiến bại vĩ đạt 
nhất. Một ngày nọ, ông được một con rùa bé nhỏ gửi lời thách đấu phân tài cao thấp bằng một 
cuộc chạy đua để xem ai nhanh hơn!

::: x-slideshow

    .race(slot="stage")
      svg(width=760 height=140 viewBox="0 0 760 140")
        line(x1=40 y1=113 x2=761 y2=113)
        line(x1=40 y1=113 x2=40 y2=121)
        text(x=40 y=135) 0
        line(x1=451 y1=113 x2=451 y2=121)
        text(x=451 y=135) 100
        g
          line(x1=616 y1=113 x2=616 y2=121)
          text(x=616 y=135) 110
        g
          line(x1=683 y1=113 x2=683 y2=121)
          text(x=683 y=135) 111
        g: line(x1=709 y1=113 x2=709 y2=121)
        g: line(x1=720 y1=113 x2=720 y2=121)
      img(src="images/achilles.png" width=80 height=110 style="left: 0%; z-index: 1;")
      img(src="images/tortoise.png" width=80 height=50 style="left: 54%; margin-top: 8%;")

Achilles biết rằng mình có thể chạy nhanh hơn gấp _mười lần_ so với rùa.
Ông rất tự tin và đã quyết định sẽ chấp chú rùa xuất phát trước mình một 
quảng đường dài 100m tính từ vạch xuất phát.

Và cuộc đua đã bắt đầu. Trong thời gian Achilles chạy hoành thành 100m đầu tiên, 
chú rùa đã di chuyển được [[10]]m: _{span.reveal(when="blank-0")}như vậy rùa đã 
cách vạch xuất phát 110m._

Khi  Achilles chạy được 110m, chú rùa đã di chuyển được thêm được
[[một]] mét nữa: _{span.reveal(when="blank-1")}như vậy rùa đã 
cách vạch xuất phát 111m._

Khi  Achilles chạy tới cột mốc 111m, chú rùa đã di chuyển được thêm được 10cm nữa.

Cứ như vậy ở mỗi bước, Achilles càng tiến đến gần hơn tới chú rùa. Và chỉ cần rùa tiếp tục 
di chuyển, ông ấy sẽ không bao giờ bắt kịp rùa. Vì Achilles không thể vượt qua rùa, dẫn tới chú
rùa sẽ giành chiến thắng trong cuộc đua này!

:::

---

    figure: x-img(src="images/mind-blown.gif" alt="Mind Blown GIF" width=300 height=200)

Lập luận này hiển nhiên đã gặp vấn đề ở đâu đó vì chúng ta biết rằng Achilles 
chắc chắn sẽ sớm vượt qua rùa. Tuy nhiên, rất khó để chỉ ra một sai lầm cụ thể
nào đó trong lời giải thích trên.

Như vậy, "tiếp tục mãi mãi" có thể là một cụm từ rất nguy hiểm trong Toán học. 
Bất kì điều gì có liên quan đến sự vô hạn đều có xu hướng vận hành rất khác
biệt so với trực giác của chúng ta. Trong khóa học này, chúng ta 
sẽ khám phá khái niệm vô hạn (vô cực) ở một vài khía cạnh khác nhau.

---

### Kẻ hở trong hệ số đếm

::: column.grow

Có thể nói, hệ thống kí tự cho số đếm là một công cụ vô cùng mạnh mẽ giúp nhân
loại khám phá ra nhiều tri thức quan trọng trong Toán học, Khoa học và Kĩ thuật. 
Ở châu Âu thuở ban đầu, các nhà Toán học đã sử dụng [hệ kí tự số đếm La Mã](gloss:roman-numerals) 
(ví dụ như I, V, X, …) trước khi [hệ kí tự Ả rập](gloss:arabic-numerals) được
ra mắt lần đầu tiên vào thế kỉ 12.

{.r} Loài người chúng ta đã trang bị cho hệ thống số đếm này một tính chất
vô cùng quan trọng: mọi con số đều đại diện cho một giá trị __duy nhất__.
Một cách dễ hiểu hơn, không tồn tại hai số khác nhau có cùng giá trị. Ví dụ,
số 5 và số 8 là hai giá trị khác nhau; số 100 khác số 101, vân vân. [Continue](btn:next)

::: column(width=300)

    x-img(src="images/clock.jpg" alt="Clock" width=300 height=300)

{.caption} Trên một chiếc đồng hồ, số 12 (XII) có cùng giá trị với số 0.

:::

---
> id: choice
> goals: choice

Tuy nhiên, cũng giống như mọi điều luật mà con người đặt ra, chúng luôn có
các kẻ hở và các trường hợp ngoại lệ. Ví dụ, sau đây là một câu hỏi kinh điển
mà bất kì ai từng đi học cũng sẽ gặp phải:

::: blockquote
Is 0.999999… có bằng 1 không?
:::

Kí hiệu “…” có nghĩa là có _vô hạn_ chữ số 9 bên phải dấu thập phân. 
Nếu đáp án cho câu hỏi trên là _bằng_, điều này cũng có nghĩa là tồn tại hai
số hoàn toàn khác nhau nhưng đại diện cho cùng một giá trị. Bạn nghĩ sao?

    p: .btn-row.text-center
      button.btn.btn-green Hai số trên bằng nhau
      button.btn.btn-blue Hai số trên khác nhau

---

Chúng ta sẽ tìm kiếm câu trả lời ở phần sau của kháo học này, tuy nhiên
chắc là bạn cũng đang nghĩ rằng câu hỏi này nghe khá mơ hồ. Vì
chúng ta không có cách nào khác để _viết ra_ vô số chữ số 9, nên ta
phải ăn gian bằng cách viết ba chấm và tưởng tượng rằng có vô số chữ số 9. 
Câu hỏi thực sự sẽ là:

::: blockquote(style="max-width: 480px; margin: 1.5em auto")
Bằng một cách nào đó, nếu chúng ta trở thành một vị thần và có thể viết
ra được một dãy số vô hạn chữ số 9, thì kết quả con số ta nhận được có bằng 1 không?
:::

Vì chúng ta không phải thần tiên, nên bạn cũng có thể cho rằng đây là một câu hỏi
vô nghĩa. Thế nhưng chắc chắn đây không phải là một câu trả lời thấu đáo. Và mọi khám phá
luôn khởi đầu bằng cụm từ nghi vấn _“nếu như…”_

[Continue](btn:next)

---
> id: numberline
> goals: n2 n3 n4

Với khả năng hạn hẹp, loài người chúng ta chỉ có thể viết hữu hạn chữ số 9, với  ${n}{n|1|1,15,1} số:

    figure: svg(width=680 height=110 viewBox="0 0 680 110")
      line(x1="20" y1="79.5" x2="660" y2="79.5" stroke="#000" stroke-linecap="round" stroke-width="2")
      line(x1="20" y1="88" x2="20" y2="80" stroke="#000" stroke-linecap="round" stroke-width="2")
      line(x1="660" y1="88" x2="660" y2="80" stroke="#000" stroke-linecap="round" stroke-width="2")
      text(transform="translate(16.01 106.62)" font-size="18") 0
      text(transform="translate(656.01 106.62)" font-size="18") 1
      g(fill="#fd8c00")
        text(transform="translate(522.54 38.62)" font-size="16") 0.9
        line(x1="532" y1="68.53" x2="532" y2="43" stroke="#fd8c00" stroke-linecap="round" stroke-width="2")
        polygon(points="532 77 536.88 65.06 532 67.89 527.12 65.06 532 77")
      g.reveal(when="n2" fill="#22ab24")
        text(transform="translate(620.57 38.62)" font-size="16") 0.99
        line(x1="634" y1="68.53" x2="634" y2="43" stroke="#22ab24" stroke-linecap="round" stroke-width="2")
        polygon(points="634 77 638.88 65.06 634 67.89 629.12 65.06 634 77")
      g.reveal(when="n3" fill="#0f82f2")
        text(transform="translate(637.59 14.62)" font-size="16") 0.999
        line(x1="655" y1="68.53" x2="655" y2="19" stroke="#0f82f2" stroke-linecap="round" stroke-width="2")
        polygon(points="655 77 659.88 65.06 655 67.89 650.12 65.06 655 77")
    x-gesture(target="x-var" slide="100,0")

{.convergence.no-voice} __{.m-yellow}0.9__ nhỏ hơn 1.<br>
_{span.reveal(when="n2")} __{.m-green}0.99__ nhỏ hơn 1._<br>
_{span.reveal(when="n3")} __{.m-blue}0.999__ nhỏ hơn 1._<br>
_{span.reveal(when="n4")} __{.m-red}0.9999__ nhỏ hơn 1._<br>
_{span.hidden} __${nines(n)}__ nhỏ hơn 1._

---

Mọi giá trị sấp xỉ ở trên đều [[nhỏ hơn|lớn hơn|bằng]] 1. Chúng tạo thành một
[dãy số](gloss:sequence) hội tụ về bên trái số 1 trên trục số (tất nhiên
là các số hạng của dãy số này không bao giờ bằng 1).

---
> id: convergence

Chú ý rằng các số hạng của dãy số này sẽ ngày càng phân bố dày đặc bên
trái số 1. Ví dụ, nếu bạn muốn tìm một giá trị sấp xỉ với số 1/${pow(x)}{x|7|1,20,1},
bạn có thể lấy giá trị ${nines(x)}.

---

Nói cách khác, bạn có thể tưởng tượng rằng không hề có khoảng trống giữa hai số 0.999999… và 1. 
Và rõ ràng rằng con số này cũng không _lớn_ hơn 1, ta có thể suy luận rằng 0.999999… bắt buộc phải
_bằng_ 1.

---
> id: dots
> goals: d1 d2 d3 d4 x1 x2 x3 x4

### Một lập luận bằng ví dụ minh họa

Nếu bạn vẫn chưa thỏa mãn với những lập luận trên, bạn hãy quan sát con số
0.9999… giống như một [cổ máy `1←10`](gloss:dot-machine):

    x-dot-machine(cells="0.9999…")
    p.text-center.reveal(when="d1"): button.btn.btn-small.btn-red Bùng nổ

Bạn hãy nhấn chuột vào [hộp thập phân đầu tiên](->#dots_.dot-decimal+.dot-cell)
để tạo một [cặp gồm một điểm và một điểm rỗng](gloss:anti-dot). Điều này không
làm con số ban đầu thay đổi.


{.reveal(when="d1")} Bây giờ, bạn hãy nhấn chuột vào [nút bùng nổ](->#dots_button) để
đơn giản hóa con số ban đầu bằng quy tắc `1←10`.

{.reveal(when="x1")} Thực hiện tương tự đối với [hộp thập phân thứ hai](->#dots_.dot-decimal+.dot-cell+.dot-cell). 
Đầu tiên hãy thêm vào một điểm và một điểm rỗng, sau đó kích nổ.

{.reveal(when="d2 x2")} Chú ý rằng cặp điểm/điểm rỗng có thể được hủy bỏ!
Điều này được gọi là [sự triệt tiêu](gloss:dot-annihilation). Con số mà chúng ta 
nhận được sau khi thực hiện các bước này vẫn là 0.9999… Hãy tiếp tục với những
hộp còn lại.

{.reveal(when="d3 x3 d4 x4")} Nếu chúng ta tiếp tục thực hiện các bước trên vô hạn lần, 
thì điều này cũng giống như việc chứng minh  0.9999… chính là 1.0000…!

---

### Một lập luận bằng Số học

Nếu bạn vẫn chưa thỏa mãn, chúng ta hãy kết thúc vấn đề này bằng một lập
luận Số học. Nếu bạn tin rằng 0.9999… một số hợp lệ (có thể hoặc không thể bằng 1), 
khi đó nó cũng phải tuân theo các quy tắc Số học.

    ol.proof
      li Đầu tiên ta hãy đặt cho con số này một cái tên, gọi là #[.ivar F] là viết tắt của từ #[strong.m-green Frederica]:
        .text-center.r #[.ivar F] = 0.9999…#[button.next-step Continue]
      li.reveal(when="next-0") Bây giờ, ta nhân số này với 10, ta nhận được
        .text-center.r 10#[.ivar F] = 9.9999…#[button.next-step Continue]
      li.reveal(when="next-1") Trừ vế theo vế của hai đẳng thức ở bước 1 và bước 2. Vì cả hai vế phải của hai đẳng thức trên đều là số thập phân có phần sau dấu phẩy là giống nhau, ta dễ dàng đơn giản:
        .text-center.r 9#[.ivar F] = 9#[button.next-step Continue]
      li.reveal(when="next-2") Cuối cùng, chia cả hai vế của đẳng thức ở bước 3 cho 9, ta thu được
        .text-center.md #[.ivar F] = [[1]]

---

Thật ấn tượng! Nhưng bạn cần hiểu rõ những gì mà chúng ta đã thiết lập ở đây.
__NẾU__ bạn chọn việc tin rằng con số 0.9999… là một đại lượng có nghĩa
trong Toán học, __KHI ĐÓ__ bạn phải kết luận rằng số này phải bằng 1. Điều 
này rất quan trọng, vì cùng một lập luận Số học có thể dẫn ta tới một sai lầm
về bản chất Triết học. Chúng ta sẽ được thấy rõ điều này ở phần sau...


--------------------------------------------------------------------------------



## Những con số bất thường

> section: unusual

Ở [chương trước](/course/exploding-dots/infinity), chúng ta
đã được thấy một số có vô hạn chữ số 9 ở bên phải dấu phẩy thập phân:

{.text-center} __0.999999…__

Ở phần này, chúng ta hãy cùng xem chuyện gì sẽ xảy ra nếu thêm vô hạn
chữ số 9 vào bên _trái_ phần thập phân:

{.text-center} __…999999__

---

Nếu ta giả sử rằng con số này là một con số có nghĩa (ví dụ như không “vô hạn”), 
ta có thể thử sử dụng các lập luận Số học như phần trước để tìm kiếm giá trị 
của số này:

    ol.proof.s-yellow
      li Đầu tiên ta hãy đặt một cái tên cho con số này, gọi là #[.ivar A] nghĩa là #[strong.m-yellow Allistaire]:
        .text-center.r #[.ivar A] = …999999#[button.next-step Continue]
      li.reveal(when="next-0") Bây giờ ta hãy nhân số này với 10, ta nhận được
        .text-center.r 10#[.ivar A] = …999990#[button.next-step Continue]
      li.reveal(when="next-1") Chú ý rằng số #[.ivar A] và số 10#[.ivar A] chỉ khác nhau ở chữ số hàng đơn vị. Do đó, nếu ta trừ vế theo vế của hai đẳng thức ở bước 1 và bước 2, ta được
        .text-center.r 9#[.ivar A] = –9#[button.next-step Continue]
      li.reveal(when="next-2") Cuối cùng, ta chia hai vế của đẳng thức ở bước 3 cho 9, ta được
        .text-center.md #[.ivar A] = [[-1]]

---


Như vậy, ta đã hoàn thành chứng minh _{strong.m-yellow.nowrap}…999999_ = −1.
Rõ ràng, nếu chúng ta thực hiện một phép tính vô hạn với tổng của 9 +
90 + 900 + 9000 + …, kết quả ta nhận được chính là −1!

_Bạn có tin nỗi không? :)_

    figure: x-img(src="images/confused.gif" alt="Confused GID" width=200 height=200)

---

### Số học bất thường

Mặc dù chúng ta biết rõ rằng …9999999 không phải là một con số thông thường, nhưng
giờ đây chúng ta cứ giả sử rằng con số này tồn tại và tuân theo các quy tắc cơ bản của
Số học. Trong trường hợp này, chúng ta sẽ nhận được …9999999 + 1 = [[0]].

---
> id: dots-1
> goals: dot

Hãy sử dụng [cổ máy `1←10`](gloss:dot-machine) để thấy rõ trường hợp trên.
Bạn hãy nhấn chuột vào bất kì đâu ở hộp thứ nhất để thêm 1 đơn vị vào:

    x-dot-machine(cells="…99999")
    x-gesture(target="#dots-1 .dot-cell:last-child")

---

Có vẻ như ví dụ minh họa này hoạt động khá tốt! Nếu ta cộng 1 với _{span.nowrap}…9999999_,
ta sẽ nhận được kết quả là 0.

Nên nhớ rằng tất cả những điều trên chỉ xảy ra __NẾU__ chúng ta lựa chọn việc tin rằng  
…999999 là một con số có nghĩa và tuân theo các quy tắc Số học, __KHI ĐÓ__ 
giá trị của con số này mới bằng –1. Tuy nhiên, đa số mọi người nói rằng nó _không phải_
là một con số và mọi việc kết thúc tại đây. Đúng là một nhận định tốt!

Điều này dẫn tới một câu hỏi: Liệu rằng có một cấu trúc Số học _bất thường_ nào
mà trong đó con số …999999 sẽ có nghĩa?

::: .box.blue
#### Thử thách

Chúng ta hãy làm vấn đề trên phức tạp hơn! Xét một con số có vô hạn chữ số 9
cả bên trái  _và_ bên phải của dấy phẩy thập phân: __{.m-red.nowrap}…9999.9999…__.
Bạn hãy sử dụng các lập luận Số học tương tự như các phần trên để chứng minh
rằng con số này bằng __{.m-red}không__.

*Với một phép màu nào đó mà điều này lại có nghĩa, bởi vì __{.m-red.nowrap}…9999.9999…__ =
__{.m-green.nowrap}…9999__ + __{.m-yellow.nowrap}0.9999…__ = __{.m-green}−1__ +
__{.m-yellow}1__ = __{.m-red}0__.*

:::

[Continue](btn:next)

---
> id: warp-1

### Bẻ cong trục số thực

Ở chương trước, chúng ta đã thấy _{span.nowrap}0.999999… = 1_. Điều này 
khá hợp lý bởi vì dãy số có số hạng xấp sỉ 0.9, 0.99, 0.999, 0.9999, vân vân
ngày càng tiến gần đến 1. 

Trong ví dụ trên, trường hợp ngược lại cho thấy các số 9, 99, 999, 9999, vân vân
lại chạy ra xa –1. Đây chính là lý do khiến chúng ta khó hiểu và bối rối khi 
phải nghĩ rằng _{span.nowrap}…999999_ có thể bằng –1.

    figure: include svg/number-line-1.svg

[Continue](btn:next)

---
> id: warp-2

Tuy nhiên, việc xây dựng và phát triện một cấu trúc Số học hoàn toàn mới mà 
trong đó con số _{span.nowrap}…999999_  trở nên có nghĩa là hoàn toàn 
khả thi. Để làm được việc này, ta chỉ việc thay đổi phương thức đo đạc “khoảng cách”
giữa các số trên trục số thực. 

Thông thường, _khoảng cách_ luôn được xác định bằng __phép cộng__ và __phép trừ__. 
Ví dụ, khoảng cách giữa 2 và 6 là [[4]], _{span.reveal(when="blank-0")}vì `2 + 4 = 6`._

    figure: include svg/number-line-2.svg

---

Thay vào đó, chúng ta có thể định nghĩa một “kiểu khoảng cách khác” bằng
cách sử dụng __phép nhân__ và __phép chia__.

{.r} Trong tập hợp số nguyên, 0 là một số _chia hết_ cho mọi số. Nó có thể chia hết
bất kì số nào với số lần chia tùy ý nhưng vẫn luôn cho một kết quả là số nguyên
(cụ thể là 0). Nếu ta tập trung vào hệ cơ số 10, ta có thể thấy rằng 0 có thể bị 
chia cho 10 với một lần, hai lần, ba mươi bảy lần, hoặc một triệu lần. 
[Continue](btn:next)

---
> id: zero-list

* Số __40__  “hơi giống số không” ở điểm là ta có thể chia số này cho
10 và kết quả nhận được vẫn là một số nguyên.
* Số __1700__ giống số không hơn: nó có thể chia cho 10 [[hai lẩn|ba lần|bốn lần]] 
mà kết quả nhận được vẫn là số nguyên.
* {.reveal(when="blank-0")} Số __230,000__ thậm chí càng giống số không hơn. Nó có thể chia cho 10 [[bốn]] lần
mà kết quả nhận được vẫn là số nguyên.
* {.reveal(when="blank-1")} Mặt khác, số __5__ không giống số không. Ta không thể chia số này cho 10 bất kì lần 
nào và nhận được kết quả là một số nguyên.

---

Bây giờ chúng ta sẽ phát triển một __công thức khoảng cách__ dựa vào số lần mà
ta có thể chia một con số cho 10 mà kết quả nhận được là một số nguyên. Nếu ta có thể chia
một số _a_ nào đó cho 10 với tối đa _k_ lần mà vẫn nhận được một số nguyên, ta 
định nghĩa công thức sau:

{.text-center} `abs(a)_(ten) = 1/10^k`

Ví dụ, `abs(850)_(ten) = 1/(10^1) = 0.1`, và `abs(8500)_(ten) = 1/(10^2) = 0.01`,
và `abs(850000)_(ten) =` [[0.0001]].

---

Ta cũng có thể dùng công thức này để đo khoảng cách giữa hai số khác nhau. Ví dụ,
khoảng cách giữa 3 và 33 là  `abs(33−3)_(ten) = abs(30)_(ten) = 1/(10^1) = 0.1`.

Với cách tính khoảng cách hoàn toàn mới này, ta nhận được 1, 10, 100, 1000, … là
một dãy số ngày càng tiến gần về [[không|1|–1|vô cực]]. Tương tự,  9, 99,
999, 9999, … cũng ngày càng tiến gần về [[-1]].

---
> id: p-adic-numbers

Các nhà Toán học gọi cách tính khoảng cách giữa các số không âm này
là [__Số học mười-adic__](gloss:adic). Hậu tố “adic” nghĩa là 
“một phép đếm của các phép toán”. Ở đây, chúng ta đang đếm số nhân
tử 10.

---
> id: dots-2
> goals: dots

### Phân số âm và số âm 

Chúng ta đã thấy hệ thống số 10-adic cũng hỗ trợ các số âm:
_{span.nowrap}…999999 = –1_. Ta cũng có thể thực hiện tương tự
cho các số âm khác. Bạn phải cộng thêm bao nhiều vào  _{span.nowrap}…999998_
để con số này bùng nổ?

    x-dot-machine(cells="…99998")
    x-gesture(target="#dots-2 .dot-cell:last-child")

---

Nói cách khác, _{span.nowrap}…999998 = [[-2]]_. _{span.reveal(when="blank-0")}
Ta có thể thực hiện các phép tính tương tự *{span.nowrap}…999997 = [[-3]]*,
*{span.nowrap}…999953 = [[-47]]*, *{span.nowrap}…999700 = –300*, vân vân.
Mọi số nguyên âm đều có một số 10-adic tương đương.

---
> id: dots-3
> goals: dots

{.text-center} •

Việc xây dựng các phân số 10-adic khó hơn một chút. Cùng xem chuyện gì sẽ xảy ra nếu
ta nhân  _{span.nowrap}…6666667_ với 3:

    x-dot-machine.tiny(cells="…66667")
    p.text-center: button.btn.btn-small.btn-red nhân với 3
    x-gesture(target="#dots-3 button")

---

Vì _{span.nowrap}…6666667_ × 3 = [[1]], *{span.reveal(when="blank-0")} nên 
ta nhận được _{span.nowrap}…6666667_ = `1/3`.*

---

::: .box.blue
#### Thử thách

Bạn có thể tìm ra các số 10-adic tương ứng với `2/3` không?

Phân số `4/7` hoặc `2/13` thì sao?

:::

_Như vậy, có một vài phân số không thể được biểu diễn trong hệ thống
số 10-adic: tất cả các phân số này, dưới dạng rút gọn, có một [mẫu số](gloss:denominator)
là một hợp số của 2 và 5 (hoặc cả hai). Bạn có thể khắc phục điều này 
bằng cách tuân theo hệ số 10-adic để có một số có hữu hạn chữ số thập phân.
Bây giờ, mọi số [hữu tỉ](gloss:rational-numbers) có một số 10-adic tương ứng._

---
> id: flaw

### Một sai xót nghiêm trọng

Giờ đây chúng ta thấy mọi phân số đều có một số 10-adic
tương ứng, và chúng ta có thể cộng, trừ, và nhân các số 10-adic này,
giống như khi chúng ta thực hiện với các số nguyên thông thường. Thật không may, 
cách xây dựng này dẫn tới một thiếu xót nghiêm trọng: chúng ta không thể
_chia_ các số 10-adic.

Để hiểu rõ lý do tại sao, chúng ta cần xác định các số lũy thừa của 2 và 5:

::: column(width=180)

{.text-center} `2^1` = 2<br>
`2^2` = 4<br>
`2^3` = 8<br>
`2^4` = 16<br>
`2^5` = [[32]]<br>
`2^6` = [[64]]<br>
`2^7` = 128<br>
…

::: column(width=180)

{.text-center} `5^1` = 5<br>
`5^2` = 25<br>
`5^3` = [[125]]<br>
`5^4` = [[625]]<br>
`5^5` = 3,_{span.po2}125_<br>
`5^6` = 15,_{span.po2}625_<br>
`5^7` = 78,_{span.po2}125_<br>
…

:::

---
> id: flaw-1

Chú ý rằng mọi số lũy thừa của 5 kết thúc với [{.no-margins}một số khác, nhỏ hơn lũy thừa của 
5](->.po2). Điều tương tự cũng xảy ra với các số lũy thừa của 2. Như vậy, ta có thể tạo ra hai số 
10-adic vô hạn luôn kết thúc lần lượt với các số lũy thừa của 2 và 5:

::: column(width=140)

{.text-right} `2^1` = 2<br>
`2^5` = 32<br>
`2^25` = 33554432<br>
__{.i.m-red}M__ = …33554432

::: column(width=140)

{.text-right} `5^1` = 5<br>
`5^2` = 25<br>
`5^3` = 125<br>
__{.i.m-yellow}N__ = …1953125

:::

[Continue](btn:next)

---
> id: flaw-2

Nếu ta cố gắng nhân các số lũy thừa của 2 và 5, ta sẽ nhận được một dãy
số các số hạng có dạng tích ngày càng tiến gần về không (theo nghĩa hệ 10-adic):

|    |   |     |   |           |
| -: | - | --: | - | --------: |
|  2 | × |   5 | = |        10 |
|  4 | × |  25 | = |       100 |
|  8 | × | 125 | = |  [[1000]] |
| 16 | × | 625 | = | [[10000]] |

---
> id: flaw-3

Điều tương tự cũng xảy ra nếu ta cố gắng nhân __{.i.m-red}M__ với __{.i.m-yellow}N__:

|   |   |    |    |    |    |
| - | - | -- | -- | -- | -- |
|   | … |  3 |  1 |  2 |  5 |
| × | … |  4 |  4 |  3 |  2 |
|   | … |  6 |  2 |  4 | 10 |
|   | … |  3 |  6 | 15 |    |
|   | … |  8 | 20 |    |    |
| + | … | 20 |    |    |    |
| = | … | 37 | 28 | 19 | 10 |
| = | … |  0 |  0 |  0 |  0 |

---

Nói cách khác, ta đã tìm được hai số không âm __{.i.m-red}M__ và
__{.i.m-yellow}N__ sao cho __{.i.m-red}M__ × __{.i.m-yellow}N__ = 0.

Điều này có nghĩa là trong cấu trúc Số học 10-adic, việc chia cho
__{.i.m-red}M__ hoặc __{.i.m-yellow}N__ là không khả thi. (Vì nếu có thể, ta chỉ cần chia đẳng 
thức equation __{.i.m-red}M__ × __{.i.m-yellow}N__ = 0 cho __{.i.m-yellow}N__, ta nhận được
__{.i.m-red}M__ = 0, điều này là mâu thuẩn.)




--------------------------------------------------------------------------------



## Các số P-adic

> section: p-adic
> id: p-adic

Ở [chương trước](/course/exploding-dots/unusual), chúng ta đã xây dựng
hai số [số 10-adic](gloss:adic) không âm là _M_ và _N_ sao cho `M×N=0`. 
Điều này có nghĩa là việc thực hiện phép chia các số giống như _M_ và _N_
là không khả thi, một kẻ hở nghiêm trong trong bất kì cấu trúc số nào.

Như vậy, vấn đề chỉ xảy ra khi con số nền tảng không phải là một
[số nguyên tố](gloss:prime). Vì 10 [[không là số nguyên tố|là số nguyên tố]],
_{span.reveal(when="blank-0")}nên các số 10-adic là có thiếu xót. Tuy nhiên, các số
2-adic hoặc 3-adic thì không._

---

Các nhà Toán học gọi các số này là __các số *p*-adic__, với *p* là viết tắt của
từ “prime” (số nguyên tố). Mặc dù các số này có vẻ như không hữu dụng cho lắm
trong cuộc sống thường nhật, nhưng _p_-adic lại rất hữu ích trong một
số chuyên ngành Toán học.

Ví dụ, nhiều vấn đề vẫn chưa có lời giải trong Toán học có liên qua đến các số
nguyên tố và [các thừa số nguyên tố](gloss:factorisation). Vì các số _p_-adic
được định nghĩa bằng _phép nhân_ thay vì là _phép cộng_, nên chúng khá phù hợp
để phân tích cho các vấn đề này. Các số *P*-adic thậm chí đã được dùng trong 
bài chứng minh nỗi tiếng cho [Định lí cuối cùng của Fermat](gloss:fermat-last) 
của nhà Toán học Andrew Wiles.

---
> id: square

Một trong các ứng dụng đáng ngạc nhiên nhất của số p-adic hiện diện trong Hình
học. Ở phần minh họa dưới đây, bạn sẽ thấy một hình vuông được phân chia 
thành ${2*x}{x|9|1,50,1} tam giác nhỏ hơn có diện tích bằng nhau:

    figure: svg.square(width=320 height=320)
    x-gesture(target="x-var" slide="100,0")

---
> id: square-1

Khi bạn di chuyển thanh trượt ở trên, bạn có thể thấy ta phân chia được
hình vuông thành bất kì các số [[chẵn|lẻ|số nguyên tố]] tam giác bằng nhau.

{.r.reveal(when="blank-0")} Nhưng còn các số _lẻ_ thì sao? Hãy vẽ một hình vuông
trên một mảnh giấy, và sau đó thử chia nó thành 3, 5 hoặc 7 tam giác có diện tích bằng 
nhau.
[Continue](btn:next)

---
> id: square-3

Sau đây sẽ là một mệnh đề gây sốc: Là _bất khả thi_ khi chia một hình vuông
thành một số  _lẻ_ các tam giác có diện tích bằng nhau! Định lí này đã được chứng
minh vào năm 1970 bởi nhà Toán học [Paul Monsky](bio:monsky). Bạn
có thể xem tựa đề bài báo khoa học này tại đây:

    figure
      x-img(src="images/paper.jpg" alt="Paper by Paul Monsky" width=400 height=132)
      p.caption #[a(href="http://ieee.scripts.mit.edu/urgewiki/images/0/00/Monsky.pdf" target="_blank") The American Mathematical Monthly]

Trong bài chứng minh, Monsky đã sử dụng hệ thống số 2-adic. Toán học, không quan trông
nó trừu tượng như thế nào, nhưng luôn luôn ẩn chứa nhiều ứng dụng bất ngờ và thú vị.
