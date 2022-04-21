# Dãy số và Quy luật

## Giới thiệu

> section: introduction
> id: intro
> description: Learn about some of the most fascinating patterns in mathematics, from triangle numbers to the Fibonacci sequence and Pascal’s triangle.
> trailer: u2vwpDVj5rU
> color: "#F97E08"
> level: Intermediate
> next: fractals

Trong thời đại ngày nay, Toán học được rất nhiều chuyên ngành khác sử dụng như một 
công cụ mạnh mẽ với mục đích nghiên cứu sâu vào một khía cạnh cụ thể trong một lĩnh vực. 
Trong đó,  _việc tìm kiếm các quy luật_  của sự vật hiện tượng là một công đoạn không thể 
thiếu để dự đoán tương lai cũng như các xu hướng sắp diễn ra. Sau đây là hai ví dụ:

::: column(width=160 parent="padded-thin")

    x-img(src="images/volcanoes.jpg" width=160 height=160 alt="Volcano")

::: column(width=400)

Khi các nhà địa chất trên khắp thế giới muốn dự đoán các trận __động đất__ hoặc __núi lửa 
phun trào__, họ sẽ cố gắng tìm kiếm và phân tích các quy luật dựa trên các dữ liệu về địa chất, 
khí quyển hoặc thậm chí là hành vi của động vật trong quá khứ. Ví dụ, một trận động đất có thể 
gây ra các dư chấn sau đó.

::: column(width=160)

    x-img(src="images/finance.jpg" width=160 height=160 alt="Stock Market Charts")

::: column(width=400)

Nhiều nhà đầu tư hoặc các nhân viên tài chính làm việc ở các ngân hàng cũng dựa vào dữ liệu 
lịch sử của giá cổ phiếu, mức lãi suất và tỷ giá hối đoái để dự đoán những biến động và xu hướng
của __thị trường tài chính__ trong tương lai. Từ đó, họ đánh giá được giá trị của một cổ phiếu 
sẽ tăng hay giảm để đưa ra các các quyết định đem lại lợi nhuận tốt!

:::

Các nhà Toán học sử dụng các thuật toán vô cùng phức tạp để tìm kiếm và phân tích tất cả các 
quy luật này. Tuy nhiên giờ đây, chúng ta hãy cùng bắt đầu với những kiến thức căn bản.

---
> id: simple-patterns

### Dãy số đơn điệu

Trong Toán học, một [__dãy số__](gloss:sequence) là một dãy các số 
(hoặc các đối tượng khác ví dụ như chữ cái,...) tuân theo một quy luật nào đó. 
Mỗi phần tử trong dãy số được gọi là [__số hạng__](gloss:sequence-term) của dãy số.

Sau đây là một vài ví dụ về dãy số. Bạn có thể tìm ra quy luật của chúng 
và tính được hai số hạng tiếp theo của các dãy số này không?

{.text-center.s-orange.with-arrows.no-voice} _{.n}3_, _{.n}6 *{span.arrow}+3*_,
_{.n}9 *{span.arrow(hidden)}+3*_, _{.n}12 *{span.arrow(hidden)}+3*_,
_{.n}15 *{span.arrow(hidden)}+3*_, _{.n}[[18]] *{span.arrow(hidden)}+3*_
_{.n}[[21]] *{span.arrow(hidden)}+3*_, …
_{span.pattern.reveal(when="blank-0 blank-1")} Quy luật: “Bất kì số hạng nào trong dãy số
đều bằng số hạng liền kề trước nó cộng 3.”_

{.text-center.s-teal.with-arrows.no-voice} _{.n}4_, _{.n}10 *{span.arrow(hidden)}+6*_,
_{.n}16 *{span.arrow(hidden)}+6*_, _{.n}22 *{span.arrow(hidden)}+6*_,
_{.n}28 *{span.arrow(hidden)}+6*_, _{.n}[[34]] *{span.arrow(hidden)}+6*_,
_{.n}[[40]] *{span.arrow(hidden)}+6*_, …
_{span.pattern.reveal(when="blank-2 blank-3")} Quy luật: “Bất kì số hạng nào trong dãy số
đều bằng số hạng liền kề trước nó cộng 6.”_

{.text-center.s-purple.with-arrows.no-voice} _{.n}3_, _{.n}4 *{span.arrow(hidden)}+1*_,
_{.n}7 *{span.arrow(hidden)}+3*_, _{.n}8 *{span.arrow(hidden)}+1*_,
_{.n}11 *{span.arrow(hidden)}+3*_, _{.n}[[12]] *{span.arrow(hidden)}+1*_,
_{.n}[[15]] *{span.arrow(hidden)}+3*_, …
_{span.pattern.reveal(when="blank-4 blank-5")} Quy luật: “Bất kì số hạng nào trong dãy số
đều bằng số hạng liền kề trước nó cộng 1 hoặc 3 luân phiên.”_

{.text-center.s-lime.with-arrows.no-voice} _{.n}1_, _{.n}2 *{span.arrow(hidden)}×2*_,
_{.n}4 *{span.arrow(hidden)}×2*_, _{.n}8 *{span.arrow(hidden)}×2*_,
_{.n}16 *{span.arrow(hidden)}×2*_, _{.n}[[32]] *{span.arrow(hidden)}×2*_,
_{.n}[[64]] *{span.arrow(hidden)}×2*_, …
_{span.pattern.reveal(when="blank-6 blank-7")} Quy luật: “Bất kì số hạng nào trong dãy số
đều bằng số hạng liền kề trước nó nhân 2.”_

---
> id: simple-patterns-1

Dấu ba chấm (…) ở cuối dãy số có nghĩa là dãy số tiếp diễn mãi mãi. Mỗi khi đề cập đến 
các dãy số như thế này trong Toán học, chúng ta thường biểu diễn các số hạng trong dãy số 
bẳng một [biến](gloss:variable) đặc biệt:

    p.text-center.s-orange
      for i in [1, 2, 3, 4, 5, 6, 7]
        span.math.n
          msub
            mi x
            mn= i
        | ,&nbsp;
      | …

Con số nhỏ nằm dưới chân bên phải biến _x_ được gọi là một __chỉ số__, 
nó cho ta biết vị trí của số hạng trong dãy số. Điều này có nghĩa là số hạng 
thứ * n * của dãy số được biểu diễn bởi kí hiệu [[`x_n`|`x_i`|`x_2`]].

    // You might think that it would be easier to label the terms in the
    // sequence as _a_, _b_, _c_, _d_, and so on. However you’ll eventually
    // [[run out of letters|reach 100|forget a letter]], while the sequence
    // might go on forever!

---
> id: triangles

### Số tam giác và số hình vuông

Trong Toán học, dãy số không phải lúc nào cũng chứa các con số. Sau đây là một dãy số với 
các số hạng là các hình tam giác có kích thước tăng dần:

::: column(width=24 parent="padded-thin")
{.text-center.no-voice} __1__

    include svg/triangle-1.svg
::: column(width=52)
{.text-center.no-voice} __3__

    include svg/triangle-2.svg
::: column(width=80)
{.text-center.no-voice} __6__

    include svg/triangle-3.svg
::: column(width=108)
{.text-center.b.no-voice} [[10]]

    include svg/triangle-4.svg
::: column(width=136)
{.text-center.b.no-voice} [[15]]

    include svg/triangle-5.svg
::: column(width=164)
{.text-center.b.no-voice} [[21]]

    include svg/triangle-6.svg
:::

---
> id: triangle-1

Một tam giác trong dãy số này được tạo nên bằng cách thêm một hàng vào tam giác liền kề 
trước nó. Chiều dài của hàng mới này cũng tăng lên một đơn vị sau mỗi bước. Bạn có thể nhận 
ra quy luật này không?

{.text-center.s-orange.with-arrows.no-voice} _{.n}1_, _{.n}3 *{span.arrow}+2*_,
_{.n}6 *{span.arrow}+3*_, _{.n}10 *{span.arrow}+4*_,
_{.n}15 *{span.arrow}+5*_, _{.n}21 *{span.arrow}+6*_
_{.n}[[28]] *{span.arrow.reveal(when="blank-0")}+7*_,
_{.n}[[36]] *{span.arrow.reveal(when="blank-1")}+8*_, …

---
> id: recursive


Chúng ta cũng có thể mô tả quy luật này dưới dạng [công thức](gloss:formula):

    p.text-center.s-orange
      span.n.md `x_n`
      | &nbsp;=&nbsp;
      span.n.md `x_(n-1)`
      | &nbsp;+&nbsp;
      em#t3 n

Để nhận được giá trị của tam giác thứ _n_, ta lấy số của tam giác [[liền kề trước đó|đầu tiên|tiếp theo]] 
cộng với _n_. Ví dụ, nếu _n_&nbsp;=&nbsp;${n}{n|5|2,20,1}, thì ta có công thức
`x_var("n") = x_var("n-1") + var("n")`.

---
> id: recursive-1

Công thức biểu diễn `x_n` giống như một hàm số theo các số hạng trước đó của dãy số
được gọi là [__công thức truy hồi__](gloss:sequence-recursive). Chỉ cần ta có 
[[số hạng đầu tiên|số hạng cuối cùng|số hạng thứ hai]], ta có thể tính được tất cả các số 
hạng còn lại.

---
> id: squares

    hr

Một dãy số khác cũng có các số hạng có dạng là hình đa giác, đó là dãy số __hình vuông__
(hoặc còn được gọi là dãy số __chính phương__).
Mỗi số hạng của dãy này được biểu diễn bởi một hình vuông có kích thước tăng dần: 

::: column(width=24 parent="padded-thin squares")
{.text-center.no-voice} __1__

    include svg/square-1.svg
::: column(width=50)
{.text-center.no-voice} __4__

    include svg/square-2.svg
::: column(width=76)
{.text-center.no-voice} __9__

    include svg/square-3.svg
::: column(width=102)
{.text-center.b.no-voice} [[16]]

    include svg/square-4.svg
::: column(width=128)
{.text-center.b.no-voice} [[25]]

    include svg/square-5.svg
::: column(width=154)
{.text-center.b.no-voice} [[36]]

    include svg/square-6.svg
:::

---
> id: square-1

Đối với dãy số tam giác, chúng ta đã tìm hiểu về công thức truy hồi, công thức này cho ta biết số 
hạng _tiếp theo_ của dãy số dưới dạng một hàm số theo các số hạng _ trước đó _. 
Đối với dãy số hình vuông, ta có thể thực hiện dễ dàng hơn: công thức biểu diễn
số hạng thứ *n* một cách trực tiếp mà không cần phụ thuộc vào các số hạng trước đó:

{.text-center.s-purple} *{.n}`x_n`* = _{x-equation(solution="n^2")}_

---
> id: explicit

Công thức này được gọi là [__công thức tổng quát__](gloss:sequence-explicit).
Ví dụ, chúng ta có thể sử dụng công thức này để tính giá trị hình vuông thứ 13 là [[169]], 
mà không cần tìm tới 12 số hình vuông trước đó.

---
> id: definitions

    hr

Chúng ta hãy cùng tóm tắt lại các định nghĩa vừa tìm hiểu:

::: .theorem
[__Dãy số__](gloss:sequence) là một danh sách các con số, hoặc các đối tượng hình học,... 
tuân theo một quy luật nhất định. Mỗi phần tử riêng lẻ của dãy số được gọi là [__số hạng__](gloss:sequence-term), 
và được biểu diễn dưới dạng các biến số `x_n`.

[__Công thức truy hồi__](gloss:sequence-term) của một dãy số cho ta biết giá trị của số hạng 
thứ *n* bằng một hàm số theo [[các số hạng trước đó|số hạng đầu tiên]].
Bạn cũng phải xác định được (các) số hạng đầu tiên.

[__Công thức tổng quát__](gloss:sequence-explicit) của một dãy số cho ta biết giá trị của 
số hạng thứ *n* bằng một hàm số theo [[biến _n_|số hạng liền kề trước đó]]
mà không cần phụ thuộc vào các số hạng khác của dãy số.
:::

---
> id: action-sequence

### Dãy ảnh động

Trong các phần sau đây, chúng ta sẽ tìm hiểu về nhiều kiểu dãy số khác nhau trong Toán học, 
những quy luật đáng ngạc nhiên và những ứng dụng vô cùng thú vị của chúng.

Đầu tiên, chúng ta hãy cùng theo dõi một thứ hoàn toàn khác biệt: __dãy ảnh động__. 
Một nhiếp ảnh gia chụp liên tiếp nhiều bức ảnh trong một khoảng thời gian ngắn và sau đó hợp 
nhất chúng thành một hình ảnh duy nhất:

    figure: x-img(src="images/action-1.jpg" width=640 height=320 alt="Skiing Jump")

Bạn có nhận ra các động tác của vận động viên trượt tuyết tạo thành một dãy số hình học không? 
Quy luật ở đây không phải là cộng hoặc nhân, mà là một [phép biến hình](gloss:rigid-transformation).
Ở mỗi bước liên tiếp, vận động viên trượt tuyết vừa tịnh tiến vừa [[quay|lật|phóng to]].

---
> id: action-sequence-1

Sau đây là một số dãy ảnh động thú vị:

::: column(width=320 parent="padded-thin")

    x-img(src="images/action-2.jpg" width=320 height=160 credit="© Ray Demski" lightbox alt="Jumping Volleyball Player")

::: column(width=320)

    x-img(src="images/action-3.jpg" width=320 height=160 credit="© Ray Demski" lightbox alt="Wind Surfing")

::: column(width=320)

    x-img(src="images/action-4.jpg" width=320 height=160 credit="© Marcio Abe" lightbox alt="Snowboard Jump")

::: column(width=320)

    x-img(src="images/action-5.jpg" width=320 height=160 credit="© Jason Halayko" lightbox alt="Mountain Bike Jump")

::: column(width=320)

    x-img(src="images/action-6.jpg" width=320 height=160 credit="© Jason Halayko" lightbox alt="Mountain Bike Jump")

::: column(width=320)

    x-img(src="images/action-7.jpg" width=320 height=160 lightbox alt="Kite Surfing")

:::



--------------------------------------------------------------------------------



## Dãy số học và dãy hình học

> section: arithmetic-geometric
> id: halley

::: column.grow

Vào năm 1682, nhà Thiên văn học [Edmond Halley](bio: halley) đã quan sát thấy 
một hiện tượng bất thường : một vật thể phát sáng màu trắng có đuôi dài di 
chuyển ngang qua trên bầu trời đêm. Đó là một __sao chổi__, một tảng băng nhỏ, 
đang bay trong không gian để lại một vệt bụi và băng ở phía sau.

Halley cũng nhớ rằng các nhà Thiên văn học khác cũng đã quan sát được những sao chổi 
giống như vậy trước đó: một lần là vào năm 1530 và một lần khác là vào năm 1606. Lưu ý 
rằng khoảng thời gian giữa hai lần quan sát liên tiếp bằng nhau trong cả hai trường hợp: [[76]] năm.

::: column(width=320)

    x-img(width=320 height=256 src="images/halley.jpg" alt="Halley’s Comet")
    p.caption Hình ảnh của sao chổi Halley #[br] được chụp vào năm 1986 từ đảo Phục Sinh
    p.caption Image of Halley’s Comet,#[br]taken in 1986 on Easter Island

:::

---
> id: halley-1

Halley đã kết luận rằng: cả ba lần quan sát này trên thực tế là cùng một ngôi sao 
chổi. Ngày nay, nó có tên gọi là _sao chổi Halley_. Nó xoay quanh mặt trời và đi qua 
Trái đất khoảng 76 năm một lần. Ông cũng dự đoán được khi nào sao chổi sẽ 
xuất hiện lần kế tiếp:

{.text-center.s-orange.s-large.with-arrows.no-voice} _{span.n}1530_,
_{span.n}1606 *{span.arrow}+76*_, _{.n}1682 *{span.arrow}+76*_,
_{.n}1758 *{span.arrow}+76*_, _{.n}[[1834]] *{span.arrow}+76*_,
_{.n}[[1910]] *{span.arrow}+76*_, _{.n}[[1986]] *{span.arrow}+76*_, …

---
> id: halley-2

Trên thực tế, không phải lúc nào thời gian lặp lại này cũng _ chính xác_ là 76 năm: 
nó có thể dao động trong khoảng từ một đến hai năm vì quỹ đạo của sao chổi 
có thể bị gián đoạn bởi các hành tinh khác. Ngày nay, chúng ta biết rằng sao chổi 
Halley đã được quan sát bởi các nhà thiên văn học cổ đại từ năm 240 trước công nguyên!

    figure
      .row
        x-img(src="images/halley-1.jpg" width=160 height=180)
        x-img(src="images/halley-2.jpg" width=173 height=180 lightbox)
        x-img(src="images/halley-3.jpg" width=200 height=180 lightbox)
        x-img(src="images/halley-4.jpg" width=130 height=180 lightbox)
      p.caption Các ghi chép về sao chổi Halley ở một số thời kì: một tấm bia đá của người Babylon (164 BC), một tấm thảm trang trí ( những năm 1070), một tạp chí khoa học (1910) và một con tem Liên Xô (1986).

---
> id: ball


Một nhóm khác bao gồm các nhà khoa học đang quan sát sự nảy của quả bóng tennis. 
Họ thả một quả bóng từ độ cao 10 mét và đo vị trí cao độ của quả bóng theo thời gian. 
Với mỗi lần nảy trở lại, độ cao của quả bóng sẽ thấp hơn so với độ cao ban đầu:

    x-coordinate-system(padding="12 12 24 120" width=640 height=320 x-axis="0,7,1" label-suffix="s,m" axis-names="thời gian,cao độ")
      .tennis-ball
      .tennis-ball
    x-slider(steps=400 speed=0.5)

---
> id: ball-1
> goals: reveals

Các nhà khoa học nhận thấy rằng quả bóng giảm đi 20% độ cao sau mỗi lần nảy. 
Nói cách khác, độ cao tối đa của mỗi lần nảy lại là 80% của lần nảy liền kề trước đó. 
Điều này cho phép họ dự đoán cao độ của quả bóng ở những lần nảy sau:

{.text-center.s-teal.s-large.with-arrows.no-voice} _{span.n}10_,
_{span.n}8 *{span.arrow}×0.8*_, _{.n}[[6.4]] *{span.arrow}×0.8*_,
_{span.n}[[5.12]] *{span.arrow}×0.8*_,
_{span.n.reveal}4.096 *{span.arrow}×0.8*_*{span.reveal},*
_{span.n.reveal}3.277 *{span.arrow}×0.8*_*{span.reveal},*
_{span.n.reveal}2.621 *{span.arrow}×0.8*_*{span.reveal},*
_{span.n.reveal}2.097 *{span.arrow}×0.8*_*{span.reveal}, …*

---
> id: arithmetic-geometric

### Các định nghĩa

Nếu so sánh hai bài toán trên với nhau, ta có thể nhận ra nhiều điểm 
tương đồng: dãy số được tạo nên từ các năm mà sao chổi Halley xuất
hiện liên tiếp có cùng [[khoảng thời gian lặp lại|tỉ lệ chênh lệch|tích]], 
trong khi dãy số được tạo nên từ cao độ giữa các lần nảy của banh tenis có cùng
[[tỉ lệ |khoảng|tích]] chênh lệch.

---
> id: arithmetic-geometric-1

Mỗi dãy số với các tính chất trên sẽ có một tên gọi riêng biệt:

::: column.grow
::: .theorem.s-red

    p.text-center: include svg/comet.svg

Một [__dãy số học__](gloss:arithmetic-sequence) (cấp số cộng) có một hằng số
giữa các số hạng, được gọi là __{.m-red}công sai *d*__.

Mỗi số hạng được cộng hoặc trừ với cùng một hằng số để nhận được các số hạng tiếp theo.

:::
::: column.grow
::: .theorem.s-green

    p.text-center: include svg/ball.svg

Một [__dãy hình học__](gloss:geometric-sequence) (cấp số nhân) có một hằng số
giữa các số hạng, được gọi là __{.m-green}công sai *r*__.

Mỗi số hạng được nhân hoặc chia cho cùng một hằng số để nhận được các số hạng tiếp theo.

:::
:::

---
> id: arithmetic-geometric-select

Sau đây là một số dãy số khác nhau. Bạn có thể xác định được đâu là dãy số học và 
đâu là dãy hình học không, và giá trị công sai _{.b.m-red}d_ và công bội _{.b.m-green}r_  
tương ứng là bao nhiêu?

::: column(width=330 parent="ag-select")

{.text-center.s-grey.s-small.no-voice} _{span.n}2_, _{span.n}4_, _{span.n}8_,
_{span.n}16_, _{span.n}32_, _{span.n}64_, …

::: column(width=320)

{.no-voice} là [[cấp số nhân|cấp số cộng|không xác định]]_{span.reveal(when="blank-0")}, với công bội là
 [[2]]._

::: column(width=330)

{.text-center.s-grey.s-small.no-voice} _{span.n}2_, _{span.n}5_, _{span.n}8_,
_{span.n}11_, _{span.n}14_, _{span.n}17_, …

::: column(width=320)

{.no-voice} là [[dãy số học|dãy hình học|không xác định]]_{span.reveal(when="blank-2")}, với công sai là [[3]]._

::: column(width=330)

{.text-center.s-grey.s-small.no-voice} _{span.n}17_, _{span.n}13_, _{span.n}9_,
_{span.n}5_, _{span.n}1_, _{span.n}–3_, …

::: column(width=320)

{.no-voice} là [[dãy số học|dạy hình học|không xác định]]_{span.reveal(when="blank-4")}, với công sai là [[-4]]._

::: column(width=330)

{.text-center.s-grey.s-small.no-voice} _{span.n}2_, _{span.n}4_, _{span.n}7_,
_{span.n}11_, _{span.n}16_, _{span.n}22_, …

::: column(width=320)

{.no-voice} là [[không phải cấp số cộng cũng không phải cấp số nhân|cấp số cộng|cấp số nhân]]_{span.reveal(when="blank-6")}._

::: column(width=330)

{.text-center.s-grey.s-small.no-voice} _{span.n}40_, _{span.n}20_, _{span.n}10_,
_{span.n}5_, _{span.n}2.5_, _{span.n}1.25_, …

::: column(width=320)

{.no-voice} là [[dãy hình học|dãy số học|không xác định]]_{span.reveal(when="blank-7")}, với công sai là [[0.5]]._

:::

---
> id: arithmetic-geometric-graph

Để định nghĩa một dãy hình học hoặc một dãy số học, ta không những cần đại 
lượng công sai hoặc công bội, mà còn cần đến số hạng đầu tiên (được gọi là `a`).
Đến đây bạn có thể tự tạo cho riêng mình một dãy số bất kỳ và biểu diễn các giá trị này bằng đồ thị, 
thông qua cách thay đổi giá trị `a`, _d_ và _r_. Bạn có thể tìm ra được quy luật nào không?

::: column.ag-chart(width=320)

#### {.m-red} Dãy số học

{.text-center.no-voice} `a` = ${a}{a|2|-10,10,0.2}, _d_ = ${d}{d|2|-10,10,0.2}

    hr

{.text-center.s-red.s-small.no-voice} _{span.n}${arithmetic(a,d,0)}_,
_{span.n}${arithmetic(a,d,1)}_, _{span.n}${arithmetic(a,d,2)}_,
_{span.n}${arithmetic(a,d,3)}_, _{span.n}${arithmetic(a,d,4)}_,
_{span.n}${arithmetic(a,d,5)}_, …

    x-coordinate-system(padding="12 12 24 40" width=320 height=240)
    x-gesture(target="#arithmetic-geometric-graph x-var" slide="100,0")

::: column.ag-chart.s-green(width=320)

#### {.m-green} Dãy hình học

{.text-center.no-voice} `a` = ${b}{b|2|-10,10,0.2}, _r_ = ${r}{r|2|-10,10,0.2}

    hr

{.text-center.s-red.s-small.no-voice} _{span.n}${geometric(b,r,0)}_,
_{span.n}${geometric(b,r,1)}_, _{span.n}${geometric(b,r,2)}_,
_{span.n}${geometric(b,r,3)}_, _{span.n}${geometric(b,r,4)}_,
_{span.n}${geometric(b,r,5)}_, …

    x-coordinate-system.green(padding="12 12 24 40" width=320 height=240)

:::

{.reveal(when="var-0 var-1 var-2 var-3")} Chú ý rằng tất cả các __{.m-red}dãy số học__ trông
khá tương đồng nhau: nếu công sai là một số dương, ta gọi đây là dãy số [[tăng|giảm]] ngặt, và nếu 
công sai là một số âm, ta gọi đây là dãy số [[giảm|tăng]] ngặt.

{.reveal(when="blank-0 blank-1")} Bên cạnh đó, dãy hình học có thể vận hành hoàn toàn khác dựa trên hai 
giá trị là `a` và *r*:

::: column.frame.blue.text-center.reveal(when="blank-0 blank-1" animation="pop" width=220 parent="padded-thin")

Nếu [`r > 1`](action:set(2,2)), các số hạng sẽ [[tăng rất nhanh|giảm rất nhanh|càng tiến về 0]], _{span.reveal(when="blank-2")}tới dương vô cực. 
Các nhà Toán học gọi đây là dãy số [__phân kì__](gloss:sequence-divergence)._

::: column.frame.blue.text-center.reveal(when="blank-2" animation="pop" delay=200 width=220)

Nếu [`–1 < r < 1`](action:set(10,0.6)), các số hạng sẽ luôn [[tiến về 0|giảm tới âm vô cực|nhỏ dần]]. 
_{span.reveal(when="blank-3")}Ta gọi đây là dãy số [__hội tụ__](gloss:sequence-convergence)._

::: column.frame.blue.text-center.reveal(when="blank-3" animation="pop" delay=200 width=220)

Nếu [`r < -1`](action:set(3,-1.4)), các số hạng sẽ đan dấu âm và dương xen kẽ, với [[giá trị tuyệt đối|giá trị nghịch đảo|công sai]] của chúng 
ngày càng tăng.

:::

{.reveal(when="blank-4 blank-5")} Chúng ta sẽ nghiên cứu sâu hơn về sự hội tụ và
sự phân kì ở [chương cuối](/course/sequences/convergence) của khóa học này.

---
> id: arithmetic-geometric-recursive

### Công thức truy hồi và công thức tổng quát

Ở chương trước, chúng ta đã học được rằng một [__công thức truy hồi__](gloss:sequence-recursive) 
cho ta biết được giá trị của mỗi số hạng bằng một hàm số theo các số hạng liền kề trước đó. 
Sau đây là một số công thức truy hồi cho các dãy số học và dãy hình học:

::: column.grow

{.text-center.no-voice} `x_n =` [[`x_(n-1) + d`|`x_(n-1) × d`|`x_d + n`]]

::: column.grow

{.text-center.no-voice} `x_n =` [[`x_(n-1) × r`|`x_(n-1) - r`|`x_n - r + n`]]

:::

---
> id: arithmetic-geometric-explicit

Công thức truy hồi sẽ bộc lộ một nhược điểm lớn khi ta muốn tìm số hạng thứ 100 của dãy số, 
ta phải tính được 99 số hạng trước đó – điều này rất mất thời gian. Thay vào đó,
ta có thể cố gắng tìm [__công thức tổng quát__](gloss:sequence-explicit) của dãy số 
dựa vào công thức truy hồi để tính được giá trị thứ *n* một cách tức thì.

::: column.grow

Đối với __{.m-red}các dãy số học__, ta phải cộng thêm số _d_ ở mỗi bước:

{.ag-equation.no-voice} `x_1 =` `a`

{.ag-equation.no-voice} `x_2 =` `a + d`

{.ag-equation.no-voice} `x_3 =` `a + d + d`

{.ag-equation.no-voice} `x_4 =` *{x-equation(solution="a+d+d+d")}*

{.ag-equation.no-voice.reveal(when="eqn-0")} `x_5 =` *{x-equation(solution="a+d+d+d+d")}*

{.reveal(when="eqn-1")} Ở số hạng thứ *n*, ta cộng thêm [[`n-1`|`n`|`n+1`]]
số _d_, từ đây ta suy ra công thức:

{.ag-equation.no-voice.reveal(when="blank-0")} `x_n = a + d × (n-1)`.

::: column.grow

Đối với __{.m-green}các dãy hình học__, ta phải nhân thêm số _r_ ở mỗi bước:

{.ag-equation.no-voice} `x_1 = a`

{.ag-equation.no-voice} `x_2 = a × r`

{.ag-equation.no-voice} `x_3 = a × r × r`

{.ag-equation.no-voice} `x_4 =` *{x-equation(solution="a×r×r×r")}*

{.ag-equation.no-voice.reveal(when="eqn-2")} `x_5 =` *{x-equation(solution="a×r×r×r×r")}*

{.reveal(when="eqn-3")} Ở số hạng thứ *n*, ta nhân thêm [[`n-1`|`n`|`n+1`]]
lần số _r_, từ đây ta suy ra công thức:

{.ag-equation.no-voice.reveal(when="blank-1")} `x_n = a × r^(n-1)`.

:::

---
> id: arithmetic-geometric-explicit-1

Sau đây là tổng hợp tất cả các định nghĩa và công thức mà chúng ta đã tìm hiểu:

::: column.grow
::: .theorem.s-red

Một __{.m-red}dãy số học__ có số hạng đầu tiên `a` và công sai `d`
giữa các số hạng liền kề.

{.text-center} __Công thức truy hồi__: `x_n = x_(n-1) + d`

{.text-center} __Công thức tổng quát__: `x_n = a + d × (n-1)`

:::
::: column.grow
::: .theorem.s-green

Một __{.m-green}dãy hình học__ có số hạng đầu tiên `a` và công bội `r`
giữa các số hạng liền kề.

{.text-center} __Công thức truy hồi__: `x_n = x_(n-1) × r`

{.text-center} __Công thức tổng quát__: `x_n = a × r^(n-1)`

:::
:::

Bây giờ, chúng ta hãy cùng xem một vài ví dụ cho việc áp dụng những công thức và định nghĩa trên!

---
> id: pay-it-forward
> goals: video

### Đáp đền tiếp nối

Sau đây là một trích đoạn ngắn trong bộ phim _Pay it Forward_, cậu bé Trevor 12 tuổi giải thích ý tưởng 
của bản thân về việc biến đổi thế giới trở nên tốt đẹp hơn:

    figure
      x-video(src="https://static.mathigon.org/videos/pay-it-forward.mp4" poster="images/pay-it-forward-poster.jpg" width=640 height=360 controls audio)
      .caption Trích đoạn từ bộ phim “Pay It Forward” (2000), © Warner Bros. Entertainment

---
> id: pay-it-forward-1

Điều cốt lõi trong ý tưởng của Trevor đó là nếu mỗi chúng ta đền đáp
lại ân tình mà mình nhận được bằng cách trao đi yêu thương và sự giúp đỡ với người 
khác, thì một cá nhân cũng có thể tác động một cách to lớn đối với thế giới.

    figure: img.invert(src="images/pay-it-forward.png" width=700 height=220)

Chú ý rằng số lượng người ở mỗi cấp có dạng là một [[dãy hình học|dãy số học|dãy số tam giác]], 
_{span.reveal(when="blank-0")}với công bội là [[3]]:_

{.text-center.s-orange.with-arrows.no-voice.reveal(when="blank-1")} _{span.n}1_,
_{span.n}3 *{span.arrow}×3*_, _{span.n}9 *{span.arrow}×3*_,
_{span.n}[[27]] *{span.arrow}×3*_, _{span.n}[[81]] *{span.arrow}×3*_,
_{span.n}[[243]] *{span.arrow}×3*_, …

---
> id: pay-it-forward-2

Áp dụng [công thức tổng quát](gloss:sequence-explicit) của dãy hình học,
chúng ta có thể tính được số người mới được tác động ở bất cứ cấp nào:

{.text-center} `x_n` = _{x-equation(solution="3^(n-1)")}_

---
> id: pay-it-forward-3

Số lượng người sẽ tăng nhanh một cách đáng kinh ngạc. Ở cấp thứ 10, ta sẽ đạt được con số 
là 19,683 người mới, và sau 22 cấp, con số ấy lớn hơn dân số đang tồn tại trên toàn Thế giới.

Dãy số này có một cái tên khá đặc biệt: __dãy lũy thừa của 3__. Như bạn đã thấy, mỗi 
số hạng của dãy số là một số [lũy thừa](gloss:powers) của 3:

{.text-center.s-orange.no-voice} _{span.n}`3^0`_, _{span.n}`3^1`_, _{span.n}`3^2`_,
_{span.n}`3^3`_, _{span.n}`3^4`_, _{span.n}`3^5`_, …

---
> id: millionaire

### Ai muốn trở thành một triệu phú?

{.todo} SẮP XUẤT BẢN!

    // Two siblings, Anna and Thomas, are receiving pocket money from their parents.
    // They can choose between two different options:

    // * Thomas is receiving $1 in the first month, $2s in the second month, $3 in the
    //   third month, and so on. Every month, he receives $1 more than in the previous
    //   one.
    // * Anna receives 1¢ in the first month, 2¢ in the second month

    // img.text-wrap(src="images/dishes.jpg" style="shape-outside: url(images/dishes.png)" width=280 height=276)

    // In order to make some additional pocket money, you decided to make a deal with
    // your parents: for appropriate payment, you’ll do every possible chore around
    // the house – washing the dishes, laundry, taking out the trash or walking the
    // dog.

    // The payment system works like this: on the first day, you get 1 cent. On the
    // second day, you get 2 cents – twice as much as before. On the next day you’ll
    // get 4 cents. Every day, your payment doubles.

    // 1¢ is not a lot of money – and neither are 2¢ or 4¢, especially
    // considering how much work you’re doing. But the amount will slowly increase.
    // How long do you think will it take until you’ve made $100? How long until
    // you’ve made it to 1 Million?

    // guess fields

    // Let’s try to calculate it mathematically! Just like before, your salary
    // follows an exponential model, because it changes by a constant ratio every
    // day (times 2). On day `x`, you’ll get `2^x` cents.

    // | __day__ | __payment__  |
    // | ------- | ------------ |
    // | 1       | $ 0.01       |
    // | 2       | $ 0.02       |
    // | 3       | $ 0.04       |
    // | 4       | $ [[0.08]]   |
    // | 5       | $ [[0.16]]   |
    // | 6       | $ [[0.32]]   |
    // | 7       | $ [[0.64]]   |
    // | 8       | $ 1.28       |
    // | 9       | $ 2.56       |
    // | 10      | $ 5.12       |
    // | 11      | $ 10.24      |
    // | 12      | $ [[20.48]]  |
    // | 13      | $ [[40.96]]  |
    // | 14      | $ [[81.92]]  |
    // | 15      | $ [[163.84]] |
    // | 16      | $ 327.68     |
    // | 17      | $ 655.36     |
    // | 18      | $ 1,310.72   |

    // One sibling gets $${a}{a|1|1,10,1} every day. The other sibling
    // gets ${b}{b|1|1,10,1}¢ every day.

    // As you can see, your daily payment start low but then grow rapidly. After 15
    // days you’ve reached $100. After less than a month you’re making more than 1
    // million per day, and after 2 months you’d have made more than _all the money
    // on Earth_. :1f4b0: :1f37e: :1f911:

    // Exponential growth can be truly XXXXX. Even if they start really slowly, they
    // will eventually speed up a lot, and overtake any possible linear model. Most
    // importantly, us humans tend to be very bad at estimating just _how fast_
    // exponential models can grow. Or are we?

---
> id: chessboard

### Bài toán bàn cở

{.todo} SẮP XUẤT BẢN!

    // The game of chess was invented in India, many hundreds of years ago. According
    // to legend, the Indian king loved the game so much that he invited its inventor
    // to his palace and promised him any present they ask for.

    // The inventor had just one simple request: rice. He wanted the king to place
    // one grain of rice on the first square of the chess board, two grains on the
    // second, four grains of the third, eight grains on the fourth, and so on. Every
    // new square should have twice as many grains of rice as the previous one.

    // The king, who was very wealthy, agreed immediately and asked his servants to
    // fetch bags of rice. A chessboard has 64 squares, so how many grains of rice
    // does the king need in total?

    // You might have noticed that the number of grains of rice form a geometric sequence.
    // The first term is [[1]], and the common ratio is [[2]]. Using the results from
    // above, we can calculate how many grains of rice there will be on the last square:

    // {.text-center} `a_64 = 1 * 2^63 =` 9 223 372 036 854 775 808

    // That’s 9 billion billion grains of rice! In total, they would weight about
    // 100 billion tonnes – or 100 times the weight of Mount Everest, the tallest
    // mountain on Earth.



--------------------------------------------------------------------------------



## Các số Hình học

> section: figurate
> id: figurate

Cái tên [dãy hình học](gloss:geometric-sequence) có thể khiến ta bối rối và hiểu lầm, 
bởi chúng chẳng liên quan gì đến Hình học cả. Thực tế, cách gọi này đã xuất hiện hàng trăm 
năm trước, khi các nhà Toán học liên tưởng và hình dung _phép nhân_ và _ phép khai căn bậc hai_ 
theo tư duy Hình học.

Tuy nhiên, có rất nhiều dãy số _được_ xây dựng dựa trên một số hình đa giác nhất định – trong đó có
một vài dãy số mà bạn đã thấy ở phần [giới thiệu](/course/sequences/introduction).
Các số hạng của những dãy số này có tên gọi là [__các số hình học__](gloss:figurate-numbers),
và trong phần này chúng ta sẽ tìm hiểu kỹ hơn về chúng.

---
> id: triangle-numbers

### Số tam giác

Các __số tam giác__ được tạo nên từ nhiều tam giác có kích thước tăng dần:

::: column(width=24 parent="padded-thin")
{.text-center.no-voice} __1__

    include svg/triangle-1.svg
::: column(width=52)
{.text-center.no-voice} __3__

    include svg/triangle-2.svg
::: column(width=80)
{.text-center.no-voice} __6__

    include svg/triangle-3.svg
::: column(width=108)
{.text-center.no-voice} __10__

    include svg/triangle-4.svg
::: column(width=136)
{.text-center.no-voice} __15__

    include svg/triangle-5.svg
::: column(width=164)
{.text-center.no-voice} __21__

    include svg/triangle-6.svg
:::

Bạn cũng đã nhìn thấy công thức truy hồi cho dãy số tam giác này:
`x_n =` [[`x_(n-1) + n`|`n^2 - 1`|`2 × x_(n-1) - 1`]].

---
> id: billiard-pool

Không phải ngẫu nhiên mà trò chơi Bóng gỗ luôn có 10 con ki gỗ và trò bi-da 
luôn có 15 quả bóng, chúng đều là những số tam giác!

::: column(width=320)

    x-img(src="images/bowling.jpg" width=320 height=240)

::: column(width=320)

    x-img(src="images/billiard.jpg" width=320 height=240)

:::

---
> id: triangle-proof


Thật không may, công thức truy hồi không hữu ích cho lắm nếu chúng ta 
muốn tìm số tam giác thứ 100 hay 500 mà không phải tính tất cả các số hạng 
trước đó. Tuy nhiên như đã đề cập, chúng ta có thể tìm công thức tổng quát 
từ công thức truy hồi cho dãy số tam giác này.

{.todo} SẮP XUẤT BẢN: Chứng minh bằng hình minh họa cho công thức dãy số tam giác

    // ::: column(width=300)

    // svg(width=300 height=300)
      g

    // ::: column.grow
    // Let’s start with a triangle of size ${x}{x|5|1,10,1}.

    // First, we need to make a second copy of the triangle.

    // Now we can rearrange the two triangles, to fit together in a rectangle.

    // The size of the rectangle is ${x} × ${x + 1}, so it must have an area of
    // ${x * (x + 1)}

    // Since the rectangle is twice as large as the original triangle, we know that
    // the ${n}th triangle number must be ${x*(x+1)/2}.

    // In general, the *n*th triangle number is `T_n = (n × (n + 1)) / 2`.
    // :::

---
> id: triangle-sums

Số tam giác dường như xuất hiện ở khắp nơi trong Toán học, và bạn sẽ gặp lại 
chúng xuyên suốt khóa học này. Có một sự thật thú vị là  _bất cứ_ 
số nguyên nào cũng có thể là tổng của nhiều nhất ba số tam giác:

::: column(width=140 parent="triangle-sum")
{.text-center.no-voice} ${n}{n|42|1,100,1}

    svg.t-sum(width=140 height=140)
    x-gesture(target="#triangle-sums x-var" slide="100,0")

::: column(width=40)
{.text-center} =
::: column(width=140)
{.text-center.no-voice} __{.t-sum}__

    svg.t-sum.red(width=140 height=140)

::: column(width=40)
{.text-center} +
::: column(width=140)
{.text-center.no-voice} __{.t-sum}__

    svg.t-sum.blue(width=140 height=140)

::: column(width=40)
{.text-center} +
::: column(width=140)
{.text-center.no-voice} __{.t-sum}__

    svg.t-sum.green(width=140 height=140)

:::

{.reveal(when="slide")} Vào năm 1796, khi chỉ mới 19 tuổi, nhà Toán học 
người Đức [Carl Friedrich Gauss](bio:gauss) đã chứng minh mệnh đề trên 
là đúng đắn với _mọi_ số tự nhiên. Thật bất ngờ!

---
> id: triangle-investigate

::: .box.blue

#### Chứng minh

Tổng của 100 số [tự nhiên](gloss:integer) dương đầu tiên bằng bao nhiêu? Hay nói cách khác, kết quả của tổng sau là bao nhiêu

{.text-center} `1 + 2 + 3 + 4 + 5 + … + 97 + 98 + 99 + 100`?

Thay vì phải tính thủ công tất cả các số này với nhau, bạn có thể áp dụng các [số tam giác](gloss:triangle-numbers) 
để tìm ra đáp án không? Vậy tổng của 1000 số nguyên dương đầu tiên là bao nhiêu?

:::

---
> id: square-numbers

### Số hình vuông và số đa giác

Một dạng dãy số khác cũng dựa trên các hình đa giác là các __số hình vuông__ (hoặc số chính phương):

{.text-center.s-purple.with-arrows.no-voice} _{.n}1_,
_{.n}4 *{span.arrow.reveal(when="blank-4")}+3*_,
_{.n}9 *{span.arrow.reveal(when="blank-4")}+5*_,
_{.n}16 *{span.arrow.reveal(when="blank-4")}+7*_,
_{.n}[[25]] *{span.arrow.reveal(when="blank-4")}+9*_,
_{.n}[[36]] *{span.arrow.reveal(when="blank-4")}+11*_,
_{.n}[[49]] *{span.arrow.reveal(when="blank-4")}+13*_,
_{.n}[[64]] *{span.arrow.reveal(when="blank-4")}+15*_, …

{.reveal(when="blank-0 blank-1 blank-2 blank-3")} Bạn có thể tính các số này bằng 
cách bình phương một số nguyên bất kỳ (`1^2`, `2^2`, `3^2`, …), nhưng hóa ra ở đây
còn có thêm một quy luật khác nữa: hiệu của hai số chính phương liên tiếp liền kề nhau là 
các [[số lẻ|số tam giác|số nguyên]] theo thứ tự tăng dần!

---
> id: square-numbers-1

::: column.grow

Nếu ta vẽ một hình vuông ra giấy thì ta sẽ thấy rõ được quy luật này hơn. Mỗi bước 
chúng ta thêm một hàng và một cột vào hình vuông trước đó. Kích thước của 
những hình “gốc” này bắt đầu từ 1 và tăng thêm 2 ở mỗi bước– từ đó tạo nên một dãy các số lẻ.

Điều này đồng nghĩa với việc số hình vuông thứ *n*  cũng chính 
là tổng của *n* số lẻ đầu tiên trước đó! Ví dụ, tổng của 6 số lẻ đầu tiên là:

{.text-center} `1 + 3 + 5 + 7 + 9 + 11 =` [[36]].

::: column(width=240)

    include svg/square-steps.svg
    x-slider(steps=6 initial=6 no-play)

:::

---
> id: square-numbers-2

Hơn nữa, mỗi số chính phương cũng đồng thời là tổng của hai [số tam giác](gloss:triangle-numbers) liền kề. 
Ví dụ, ${n×n}{n|4|1,20,1} = ${n×(n+1)/2} + ${n×(n-1)/2}. Bạn có nhận ra cách để chia một hình vuông 
theo đường chéo của nó để nhận được hai hình tam giác không?

---
> id: polygon-numbers

::: column(width=300)

    svg(width=300 height=260)
    .text-center #[msub #[mi x]#[mn]]#[mo(value="=") =]#[mn]
    x-slider(steps=11 initial=3 no-play)

::: column.grow

Sau khi đã tìm hiểu rõ về số tam giác và số hình vuông, chúng ta có thể tiếp tục mở rộng
khái niệm này ra các số [đa giác](gloss:polygon), được gọi là __ dãy số đa giác__.

Ví dụ, nếu ta có các hình đa giác với ${k}{k|5|3,10,1} cạnh, ta sẽ thu được dãy số __${polygonName(k)}__.

Bạn có thể tìm ra công thức truy hồi và công thức tổng quát cho số đa giác thứ  *n* có _k_ cạnh 
không? Và bạn có phát hiện ra quy luật nào cho những đa giác có số cạnh lớn hơn không?

:::

---
> id: tetrahedral

### Số tự diện và số lập phương

Tất nhiên, chúng ta không buộc phải giới hạn tư duy ở những hình phẳng 2D. Chúng ta 
có thể chồng chất những khối cầu nhỏ lên nhau để tạo ra những khối chóp, 
cũng giống như việc bạn chất những quả cam vào giỏ hàng khi đi siêu thị vậy:

::: column(width=64 parent="padded-thin")
{.text-center.no-voice} __1__

    x-tetrahedron(size=160 layers=1 style="margin: 0 -48px")

::: column(width=88)
{.text-center.no-voice} __[[4]]__

    x-tetrahedron(size=160 layers=2 style="margin: 0 -36px")

::: column(width=112)
{.text-center.no-voice} __[[10]]__

    x-tetrahedron(size=160 layers=3 style="margin: 0 -24px")

::: column(width=136)
{.text-center.no-voice} __20__

    x-tetrahedron(size=160 layers=4 style="margin: 0 -12px")

::: column(width=160)
{.text-center.no-voice} __35__

    x-tetrahedron(size=160 layers=5)

:::

---
> id: tetrahedral-1

Các nhà Toán học thường gọi những hình tháp này là các [__tứ diện__](gloss:tetrahedron),
và dãy hình học được tạo nên bởi những tứ diện này được gọi là các [__số tứ diện__](gloss:tetrahedral-numbers).

{.todo} SẮP XUẤT BẢN: Chi tiết về số tứ diện, số lập phương số và 12 ngày Giáng sinh.



--------------------------------------------------------------------------------



## Dãy hàm số

> section: functions
> sectionStatus: dev

TODO



--------------------------------------------------------------------------------



## Dãy số Fibonacci

> section: fibonacci
> id: rabbits

Hãy tưởng tượng bạn nhận được một cặp thỏ giống. Chúng là những con thỏ rất 
đặc biệt, bởi vì chúng sẽ không bao giờ chết, và tháng nào thỏ cái cũng sinh ra 
một cặp thỏ con ( luôn là một cặp gồm một đực và một cái).

::: x-slideshow

    .stage.rabbits(slot="stage")
      .rabbits-wrap.s-orange.s-small
        svg(width=760 height=456 viewBox="0 0 760 456")
          line(y1=51  x2=760 y2=51)
          line(y1=130 x2=760 y2=130)
          line(y1=209 x2=760 y2=209)
          line(y1=287 x2=760 y2=287)
          line(y1=366 x2=760 y2=366)
          path(d="M84,91c223.68,0,405,7,405,45")
          path(d="M84,170c124.82,0,226,14,226,45")
          path(d="M84,248c74.56,0,135,20.15,135,45")
          path(d="M534,248c74.56,0,135,20.15,135,45")
          path(d="M84,327a45,45,0,0,1,45,45")
          path(d="M354,327a45,45,0,0,1,45,45")
          path(d="M534,327a45,45,0,0,1,45,45")
          polygon(points="489 150 481 130 489 135 497 130 489 150")
          polygon(points="310 229 302 209 310 214 318 209 310 229")
          polygon(points="219 307 211 287 219 292 227 287 219 307")
          polygon(points="669 307 661 287 669 292 677 287 669 307")
          polygon(points="129 386 121 366 129 371 137 366 129 386")
          polygon(points="399 386 391 366 399 371 407 366 399 386")
          polygon(points="579 386 571 366 579 371 587 366 579 386")

        img.rabbit(src="images/rabbits-1.svg" width=85 height=75 style="left: 2%; top: 0%; width: 7%")

        img.rabbit(src="images/rabbits-1.svg" width=85 height=75 style="top: 13%")

        img.rabbit(src="images/rabbits-1.svg" width=85 height=75 style="top: 30%")
        img.rabbit(src="images/rabbits-2.svg" width=85 height=75 style="left: 61%; top: 34%; width: 7%")

        img.rabbit(src="images/rabbits-1.svg" width=85 height=75 style="top: 47%")
        img.rabbit(src="images/rabbits-3.svg" width=85 height=75 style="left: 37%; top: 51%; width: 7%")
        img.rabbit(src="images/rabbits-2.svg" width=85 height=75 style="left: 59%; top: 47%")

        img.rabbit(src="images/rabbits-1.svg" width=85 height=75 style="top: 64%")
        img.rabbit(src="images/rabbits-4.svg" width=85 height=75 style="left: 25%; top: 68%; width: 7%")
        img.rabbit(src="images/rabbits-3.svg" width=85 height=75 style="left: 35%; top: 64%")
        img.rabbit(src="images/rabbits-2.svg" width=85 height=75 style="left: 59%; top: 64%")
        img.rabbit(src="images/rabbits-5.svg" width=85 height=75 style="left: 85%; top: 68%; width: 7%")

        img.rabbit(src="images/rabbits-1.svg" width=85 height=75 style="top: 81%")
        img.rabbit(src="images/rabbits-2.svg" width=85 height=75 style="left: 13%; top: 85%; width: 7%")
        img.rabbit(src="images/rabbits-4.svg" width=85 height=75 style="left: 23%; top: 81%")
        img.rabbit(src="images/rabbits-3.svg" width=85 height=75 style="left: 35%; top: 81%")
        img.rabbit(src="images/rabbits-1.svg" width=85 height=75 style="left: 49%; top: 85%; width: 7%")
        img.rabbit(src="images/rabbits-2.svg" width=85 height=75 style="left: 59%; top: 81%")
        img.rabbit(src="images/rabbits-3.svg" width=85 height=75 style="left: 73%; top: 85%; width: 7%")
        img.rabbit(src="images/rabbits-5.svg" width=85 height=75 style="left: 83%; top: 81%")

        .n(style="top: 0%") 1
        .n(style="top: 15%") 1
        .n(style="top: 32%") 2
        .n(style="top: 49%") 3
        .n(style="top: 66%") 5
        .n(style="top: 84%") 8

Ở tháng đầu tiên, những con thỏ còn khá nhỏ và chẳng thể làm gì cả, nhưng chúng lớn khá nhanh.

Sau một tháng, lũ thỏ đã lớn và bắt đầu kết đôi…

… một tháng sau nữa, thỏ cái sẽ sinh cặp thỏ đầu tiên. Bây giờ bạn đã có hai cặp thỏ giống.

Một tháng sau, cặp thỏ giống bạn đầu sẽ sinh thêm một cặp thỏ khác. Trong khi đó, cặp thỏ 
thứ hai đã lớn, giờ đây bạn có tổng cộng ba cặp thỏ.

Vào tháng thứ năm, cặp thỏ giống ban đầu sẽ lại sinh một cặp thỏ nữa. Cùng lúc ấy,
Cặp thỏ lứa thứ hai đã đẻ thêm một cặp thỏ cháu. Giờ đây bạn có tổng cộng nam cặp thỏ.

Vào tháng thứ sáu, có ba cặp thỏ đẻ thêm ba cặp thỏ nữa: cặp thỏ giống đầu tiên, và hai 
cặp thỏ lứa đầu của chúng.

:::

---
> id: rabbits-1

{.r} Đến tháng tiếp theo, bạn sẽ có 13 đôi thỏ: 8 đôi từ tháng trước, và thêm 5 
đôi thỏ con mới sinh. Bạn có thể nhận ra quy luật cho dãy số này không? [Continue](btn:next)

---
> id: rabbits-2

Số thỏ trong một tháng cụ thể bằng [[tổng số thỏ của hai tháng liền kề trước đó|gấp đối số thỏ của tháng trước đó]]. _{span.reveal(when="blank-0")} 
Nói cách khác, bạn phải cộng tổng của *hai số hạng liền kề trước đó* để có được số hạng tiếp theo. 
Dãy số này bắt đầu bằng hai số 1, và [công thức truy hồi](gloss:sequence-recursive) là_

{.text-center.s-orange.reveal(when="blank-0")} *{span.n}`x_n`* =
*{span.n}`x_(n-1)`* + *{span.n}`x_(n-2)`*

---
> id: rabbits-3

Bạn có tính được số thỏ trong những tháng tiếp theo không?

{.text-center.s-orange} _{.n}1_, _{.n}1_, _{.n}2_, _{.n}3_, _{.n}5_, _{.n}8_,
_{.n}[[13]]_, _{.n}[[21]]_, _{.n}[[34]]_, _{.n}[[55]]_, _{.n}[[89]]_,
_{.n}[[144]]_, …

{.reveal(when="blank-5")} Vậy, sau 12 tháng bạn sẽ có tổng cộng là 144 đôi thỏ !

    figure.reveal(when="blank-5")
      x-img(src="images/rabbits.jpg" width=600 height=230)

---
> id: fibonacci

Dãy số này có tên gọi là  [__ Dãy số Fibonacci__](gloss:fibonacci-numbers), được đặt theo tên nhà Toán học 
người Ý [Leonardo Fibonacci](bio:fibonacci).

::: column.grow
Khi Fibonacci chào đời vào năm 1175, hầu hết người châu Âu vẫn sử dụng [hệ số đếm La mã](gloss:roman-numerals) 
cho các chữ số (giống như XIV hoặc MCMLIV). Cha của Fibonacci là một thương nhân, họ đã cùng nhau đi đến 
những vùng đất ở Bắc Phi và Trung Đông. Từ những nơi đó, Fibonacci lần đầu tiên được học về [hệ số đếm Ấn độ-Ả rập](gloss:arabic-numerals).

Khi quay lại Ý, Fibonacci đã viết một cuốn sách có tựa đề là _Liber Abaci_ (nghĩa là  “Sách về các phép tính”), để giới thiệu hệ 
số đếm Ấn độ - Ả rập hoàn toàn mới cho các thương nhân châu Âu. Nó lập tức ảnh hưởng rộng rãi và được chúng ta sử dụng cho đến ngày nay.

::: column(width=300)

    x-img(src="images/fibonacci.jpg" width=300 height=300)
    .caption Tranh chân dung của Leonardo Fibonacci

:::

Ở một trang trong cuốn sách, ông cũng nghiên cứu về quy luật sinh sản của loài thỏ.
Đó là lí do dãy số Fibonacci được đặt theo tên của ông.

    figure
      x-img(src="images/liber-abaci.jpg" width=440 height=290 lightbox)
      p.caption Các trang sách trong cuốn #[em Liber Abaci] của  Fibonacci

---
> id: spirals

Tất nhiên, dãy số Fibonacci không phải là phương thức sinh sản của loài thỏ trong thực tế. 
Thỏ không sinh chính xác một cặp gồm một thỏ đực và một thỏ cái mỗi lần sinh, và chúng ta 
vẫn chưa tính đến trường hợp chúng sẽ bị chết.

Nhưng trong tự nhiên, dãy số này lại xuất hiện ở rất nhiều nơi: ví dụ về đường xoắn 
ốc ở thực vật, bạn có đếm được có bao nhiêu vòng xoắn ốc ở mỗi hướng không?

::: column(width=320)

    x-select.segmented
      div Ảnh gốc
      div(data-value="cw") Cùng chiều kim đồng hồ
      div(data-value="ccw") Ngược chiều kim đồng hồ
    .spirals(style="background-image: url(images/pinecone.jpg)")
      .clockwise(style="background-image: url(images/pinecone-1.jpg)")
      .anticlockwise(style="background-image: url(images/pinecone-2.jpg)")

{.text-center} Quả thông này có [[8]] vòng xoắn ốc theo chiều kim đồng hồ và [[13]]
vòng ngược chiều kim đồng hồ.

::: column(width=320)

    x-select.segmented
      div Ảnh gốc
      div(data-value="cw") Cùng chiều kim đồng hồ
      div(data-value="ccw") Ngược chiều kim đồng hồ
    .spirals(style="background-image: url(images/sunflower.jpg)")
      .clockwise(style="background-image: url(images/sunflower-1.jpg)")
      .anticlockwise(style="background-image: url(images/sunflower-2.jpg)")

{.text-center.reveal(when="blank-0 blank-1")} Bông hoa hướng dương này có 34 vòng 
xoắn ốc theo chiều kim đồng hồ và 55 vòng ngược chiều kim đồng hồ.

:::

---
> id: spirals-1

Trong cả hai trường hợp, số vòng xoắn ốc là các số Fibonacci liên tiếp. Điều này 
cũng đúng với các loài thực vật khác: lần tới khi bạn đi ra ngoài, hãy thử đếm số 
cánh hoa của một bông hoa hay số lá mọc trên thân cây nhé. Rất có thể bạn sẽ 
tìm được số Fibonacci đấy !

Dĩ nhiên, đây không phải là sự trùng hợp ngẫu nhiên. Có một lý do quan trọng giải 
thích tại sao Mẹ thiên nhiên lại thích dãy số Fibonacci, và chúng ta sẽ tìm hiểu thêm sau.

---
> id: bees

::: column(width=320)

    x-select.segmented
      div(data-value="male") Đực
      div(data-value="female") Cái
    .bees
      img(src="images/bees-male.png")
      img(hidden src="images/bees-female.png")

::: column.grow

Các số Fibonacci cũng xuất hiện trong dân số của loài ong mật.

Trong mỗi một vương quốc ong chỉ có duy nhất một _ ong nữ hoàng_và nó đẻ rất 
nhiều trứng. Nếu một quả trứng được thụ tinh bằng một con ong đực, nó sẽ 
nở ra con ong__cái__. Nếu trứng không được thụ tinh, nó sẽ nở ra ong __đực__ 
(được gọi là ong phối giống).

Điều này có nghĩa là những con ong cái có [[hai ba mẹ|một mẹ]], 
trong khi đó ong đực chỉ có [[một mẹ|hai ba mẹ]].

{.reveal(when="blank-0 blank-1")} Nếu chúng ta vẽ cây phả hệ của một con ong, 
số lượng ong bố mẹ, ong ông bà, ong cụ kị và các thế hệ trước đó luôn luôn là các số Fibonacci !

{.i.lgrey.reveal(when="blank-0 blank-1" delay=400)} Thỉnh thoảng, những chú ong cái non được cho 
ăn một loại thức ăn đặc biệt gọi là “sữa ong chúa” . Khi đó, chúng sẽ biến thành ong chúa và bay 
đi tự xây cho mình một cái tổ mới.

:::

---
> id: golden-spiral

### Tỉ lệ vàng

Cũng giống như [số tam giác](gloss:triangle-numbers), [số hình vuông](gloss:square-numbers), 
và các dãy số khác chúng ta đã tìm hiểu từ trước, dãy số Fibonacci cũng có thể được biểu diễn bằng 
một quy luật hình học:

::: x-slideshow.golden-spiral

    .stage(slot="stage"): include svg/spiral.svg

Chúng ta cùng bắt đầu với hai hình vuông nhỏ có kích thước là 1.

Tiếp theo, chúng ta thêm vào một hình vuông mới có kích thước là 2, để tạo thành 1 hình chữ nhật có kích thước lớn hơn.

Tiếp theo ta thêm một hình vuông mới có kích thước là 3, để tạo thành 1 hình chữ nhật có kích thước lớn hơn.

Hình vuông tiếp theo có kích thước là 5. Bạn có nhận ra chúng ta đang tái tạo lại những số Fibonacci không?

Nếu chúng ta tiếp tục thêm vào những hình vuông, ta sẽ nhận được các kích thước lần lượt là 8, 13, 21, và cứ tiếp tục như thế.

Bạn có thể nhận thấy rằng, khi những hình chữ nhật trở nên lớn hơn, chúng bắt đầu tạo thành những vòng xoắn ốc ngày càng lớn.
Bạn sẽ nhìn thấy các vòng xoắn ốc một cách rõ ràng hơn nếu nối các góc của các hình chữ nhật lại với nhau.

:::

---
> id: golden-ratio

Ở mỗi bước, các hình vuông lại tạo thành một hình chữ nhật lớn hơn. 
Chiều rộng và chiều cao của nó là hai số Fibonacci liên tiếp liền kề. 
 __Tỷ lệ khung hình__ của hình chữ nhật này là tỷ lệ giữa chiều rộng trên chiều cao của nó.

::: column(width=100 parent="padded-thin golden-rect")

    include svg/golden-1.svg

{.text-center.no-voice} `2/1` = 2
::: column(width=100)

    include svg/golden-2.svg

{.text-center.no-voice} `3/2` = 1.5
::: column(width=100)

    include svg/golden-3.svg

{.text-center.no-voice} `5/3` = 1.666…
::: column(width=100)

    include svg/golden-4.svg

{.text-center.no-voice} `8/5` = 1.6
::: column(width=100)

    include svg/golden-5.svg

{.text-center.no-voice} `input(13) / input(8) reveal(= 1.625, "blank-0 blank-1")`
::: column(width=100)

    include svg/golden-6.svg

{.text-center.no-voice} `input(21) / input(13) reveal(= 1.62…, "blank-2 blank-3")`
:::

---
> id: golden-ratio-1
> goals: img-0 img-1

Nếu để ý ta sẽ thấy rằng, khi ta thêm ngày càng nhiều hình vuông, tỷ lệ khung 
hình sẽ càng tiến gần hơn tới con số xấp xỉ 1,6. Con số này có tên gọi là [__tỉ lệ vàng__](gloss:golden-ratio) 
và thường được ký kiệu bằng ký tự Hy Lạp `φ` (“phi”). Giá trị chính xác của nó là:

{.text-center} `(1 + sqrt(5))/2 = 1.61803398875…`

Nhiều người tin rằng tỷ lệ vàng mang tính nghệ thuật cao. Chính vì thế 
nó thường được các nghệ sỹ và kiến trúc sư sử dụng, giống như trong hai ví dụ dưới đây:

::: column(width=320)

    .golden-art
      x-img(src="images/pantheon.jpg" width=320 height=198)
      img(src="images/pantheon-box.png" width=320 height=198)
    x-gesture(target=".golden-art")

{.caption} Điêu khắc gia người Hy Lạp Phidias được cho là đã sử dụng 
tỉ lệ vàng để thiết kế đền _Parthenon_ ở Athen. Chữ cái đầu tiên ở tên của
ông, `φ`, chính là biểu tượng kí hiệu cho con số tỉ lệ vàng.

::: column(width=320)

    .golden-art
      x-img(src="images/dali.jpg" width=320 height=198)
      img(src="images/dali-box.png" width=320 height=198)

{.caption} _Bí tích tại Bữa tiệc Ly_, được vẽ bởi họa sĩ người Tây Ban Nha Salvador Dalí,
là một trong nhiều bức danh họa có bố cục theo tỉ lệ vàng . Ở phần nền, bạn cũng có thể thấy
một [khối mười hai mặt](gloss:dodecahedron) rất lớn.

:::

---
> id: golden-ratio-2

Ta có thể ước chừng xấp xỉ số tỷ lệ vàng bằng cách [[chia|cộng|trừ]] hai số Fibonacci liên tiếp liền kề.

{.reveal(when="blank-0")} Tuy nhiên, giá trị chính xác của `φ`
không thể được viết dưới dạng phân số thông thường: nó là một [__số vô tỉ__](gloss:irrational-numbers), 
cũng giống như số [`π`](gloss:pi), số `sqrt(2)` và những số khác bạn đã biết.

---
> id: sunflower-growing

### Đường xoắn ốc Fibonacci 

::: column.grow

Tỷ lệ vàng giải thích vì sao số Fibonacci lại xuất hiện trong tự nhiên, như 
hoa hướng dương hay quả thông bạn đã thấy ở phần đầu.

Cả hai loài thực vật này có cấu trúc lớn dần từ phần trung tâm (ở thực vật được gọi là _mô phân sinh_) 
và tỏa ra phía ngoài. Giống như một hạt giống, khi lá và cánh hoa được thêm vào, 
chúng đẩy những lá và cánh hoa cũ ra phía ngoài xa hơn.

Hãy di chuyển thanh trượt dưới đây sang phải để thấy quá trình phát triển của một tán cây. 
Chú ý rằng phương thức mà mỗi chiếc lá được thêm vào theo chiều quay khác với chiều trước 
đó. Góc tạo ra giữa hai cái lá liền kề nhau là không đổi.

::: column(width=300)

    svg.petals(width=300 height=300)
      circle(r=1 cx=150 cy=150)
      - var i = 0
      while i < 40
        path(d="M166,158A20,20,0,0,1,150,150a20,20,0,0,1,32,0A20,20,0,0,1,166,158Z")
        - i += 1

    x-slider(steps=39 speed=0.5)

:::

---
> id: sunflower-spiral

Việc chọn hướng mọc thích hợp vô cùng quan trọng đối với các loài hoa: cả lá và 
hạt giống đều phải được sắp xếp hợp lý để thu được lượng ánh sáng và dinh dưỡng 
nhiều nhất. Trong biểu đồ dưới đây, bạn sẽ khám phá ra được những bông hoa sẽ 
trông như thế nào với những góc khác nhau tạo thành giữa những hạt giống của nó:

    // Notice how even tiny changes to the angle can produce a completely different arrangement:

::: x-slideshow

    .sunflower-spiral(slot="stage")
      .value
      x-slider(steps=1000 continuous speed=0.1 no-play)
      svg(width=400 height=400 viewBox="0 0 400 400")

Nếu góc bằng [0°](action:set(0)), tất cả những hạt giống sẽ mọc dọc thành một hàng dài từ trung tâm.

Nếu góc bằng [`1/2`](action:set(0.5)), tức là góc (180°), những hạt giống sẽ mọc thay phiên tạo thành hai “cánh tay” riêng biệt từ trung tâm.

Nếu góc quay là một phân số khác mà có mẫu số là 360°, ví dụ như [`2/5`](action:set(2/5)) hoặc
[`1/3`](action:set(1/3)) hoặc [`3/8`](action:set(3/8)), thì số lượng “cánh tay” sẽ bằng với [[mẫu số|tử số|thừa số nguyên tố]] của phân số ấy.

Nhưng những “cánh tay” này có vẻ không hiệu quả, bởi nó không phân chia đều những hạt giống, 
bởi phần không gian giữa những những “cánh tay” sẽ bị bỏ phí. Nhưng nếu [số hữu tỉ](gloss:rational-numbers) 
không hiệu quả, hãy thử bằng [số vô tỉ](gloss:irrational-numbers)!

Một ví dụ cho số vô tỉ là số [`pi`](gloss:pi). Nhưng nếu các góc giữa những hạt giống là
[`1/pi`](action:set(0.31831)) of 360°, chúng ta vẫn sẽ tạo ra những “cánh tay”: có tới 22 chiếc. 
Đó là bởi phân số `22/7 = 3.1429…` là số xấp xỉ gần nhất của `pi`. Nhưng thứ mà chúng ta thực 
sự cần _không thể_ được ước chừng sấp xỉ bằng bất cứ phân số nào.

Cuối cùng thì [tỉ lệ vàng](gloss:golden-ratio) vẫn là số vô tỉ “tối thượng” nhất trong tất cả các số vô tỷ. 
Nếu góc giữa những hạt giống là [`1/phi`](action:set(0.6180339)) của 360°, thì sự sắp đặt gần 
như là hoàn hảo. Đó cũng chính là góc mà các loài thực vật trong tự nhiên sử dụng.

:::

---
> id: sunflower-spiral-1

::: column(width=240)

    x-img(src="images/flowers.jpg" width=240 height=400)

::: column.grow

Bạn hẳn vẫn còn nhớ từ phần trước, tỉ lệ giữa hai số Fibonacci liên tiếp liền kề nhau sẽ 
ngày càng gần với tỷ lệ vàng – và đó là lý do tại sao khi đếm số vòng xoắn ốc 
ở một cái cây, bạn sẽ thường tìm thấy một số Fibonacci.

Nhưng nên nhớ rằng tự nhiên không biết chút gì về số Fibonacci cả. Mẹ thiên nhiên cũng 
không thể giải các phương trình để tính ra tỷ lệ vàng – nhưng qua hàng triệu năm, 
thực vật đã thử rất nhiều góc khác nhau để tìm ra góc tối ưu nhất với chúng.

Thực vật và động vật luôn muốn phát triển một cách hiệu quả nhất, đó là lý do chúng 
ta thường bắt gặp trong tự nhiên rất nhiều quy luật Toán học .

:::

---
> id: lucas-numbers

### Số Fibonacci

Đến đây, chúng ta chỉ mới tìm ra được công thức truy hồi cho dãy số Fibonacci. 
Tất nhiên cũng có cả công thức tổng quát cho cho dãy số này, nhưng sẽ hơi khó chứng minh:

{.text-center} `F_n = 1/(  sqrt(5)) ( ((1 + sqrt(5))/2)^n - ((1 - sqrt(5))/2)^n )`

Chúng ta cũng có thể thử những số hạng đầu tiên khác nhau cho dãy số Fibonacci.
Ví dụ, nếu chúng ta bắt đầu với 2, 1, … thay vì 1, 1, … chúng ta sẽ được một dãy số có tên là
_ dãy số Lucas__.

Ta rút ra rằng, khi bắt đầu bằng bất kỳ 2 số nào, ta nhận được các dãy số có rất 
nhiều tính chất giống nhau. Ví dụ, tỷ lệ giữa hai số hạng liên tiếp liển kề sẽ 
__luôn luôn_ [hội tụ](gloss:sequence-convergence) về tỷ lệ vàng.

{.text-center.s-purple.s-small.no-voice}
${a}{a|1|0,10,1}, ${b}{b|1|0,10,1}, _{span.n}${a+b}_, _{span.n}${a+2×b}_,
_{span.n}${2×a+3×b}_, _{span.n}${3×a+5×b}_, _{span.n}${5×a+8×b}_,
_{span.n}${8×a+13×b}_, …

---
> id: fibonacci-puzzles

Có rất nhiều bài toán, quy luật và ứng dụng khác liên quan tới dãy số Fibonacci. 
Dưới đây là một vài ví dụ mà bạn có thể thử tự mình suy nghĩ:

::: .box.blue

#### Chứng minh

__1.Tính chia hết Fibonacci__

(a) Số Fibonacci nào là số chẵn? Có quy luật nào cho sự sắp xếp giữa chúng trong dãy số không? Giải thích tại sao?

(b) Những số Fibonacci nào chia hết cho 3 (hoặc chia hết cho 4)? Bạn phát hiện ra điều gì?

    hr

__2.Tổng Fibonacci__

Điều gì sẽ xảy ra nếu bạn cộng ba số Fibonacci liên tiếp liền kề bất kỳ? Hãy giải thích lý do?

    hr

__3. Cầu thang Fibonacci __

Khi lên cầu thang, ta có thể bước 1 bậc hoặc bước 2 bậc mỗi lần bước. Điều này có nghĩa rằng có rất nhiều cách để lên cầu thang. Ví dụ, nếu cầu thang có 5 bậc, ta sẽ có 8 cách :

    figure: x-img(src="images/stairs.svg" width=530 height=200)

Có bao nhiêu cách để lên cầu thang nếu nó có lần lượt 6, 7 hoặc 8 bậc? Bạn có thể tìm ra quy luật không? Nó có thì các quy luật đó liên quan gì tới dãy số Fibonacci?

:::

    figure
      x-img(src="images/fibonachos.jpg" width=600 height=282)
      p.caption © FoxTrot, tranh của Bill Amend



--------------------------------------------------------------------------------



## Các dãy số đặc biệt

> section: special
> id: special-intro


Ngoài các dãy [số học](gloss:arithmetic-sequence), dãy [hình học](gloss:geometric-sequence), [ dãy số Fibonacci](gloss:fibonacci-numbers) 
và [các số hình học](gloss:figurate-numbers), còn có vô số những dãy số khác cũng rất thú vị và không tuân theo bất cứ quy luật thông thường nào cả. 

---
> id: primes

### Dãy số nguyên tố

Một ví dụ mà bạn đã thấy trước đó là [__dãy số nguyên tố__](gloss:prime). 
Ta nói rằng một số là _số nguyên tố_ nếu nó không có 
[các ước](gloss:factor) nào khác [[ngoài 1 và chính nó|1 và 2]].

---
> id: primes-1

Sau đây là một vài số nguyên tố đầu tiên:

{.text-center.s-teal} _{.n}2_, _{.n}3_, _{.n}5_, _{.n}7_, _{.n}11_,
_{.n}[[13]]_, _{.n}[[17]]_, _{.n}[[19]]_, …

---
> id: primes-2
> goals: p2 p3 p5 p7

Thật không may, số nguyên tố không tuân theo bất cứ quy luật đơn giản hay công 
thức truy hồi nào. Có lúc chúng xuất hiện liền kề nhau (gọi là [số nguyên tố sinh đôi](gloss:twin-primes)), 
nhưng cũng có lúc có khoảng rất lớn giữa chúng. Có lẽ chúng được sắp xếp hoàn toàn ngẫu nhiên!


Số nguyên tố cũng không thể được trình bày dưới dạng một hình đa giác như số
[tam giác](gloss:triangle-numbers) hay số [hình vuông](gloss:square-numbers),
nhưng kiên nhẫn tìm tòi một chút ta sẽ tìm ra được một vài quy luật thú vị:

::: column(width=320)

    .eratosthenes
      .deleted 1
      .l-red 2
      - var i = 3
      while i <= 100
        div= i
        - i += 1
    x-gesture(target=".eratosthenes .l-red")

{.caption} Nếu chúng ta bỏ qua tất cả các hợp số của các số nguyên nhỏ, phần còn lại chính là các số nguyên tố. 
Phương pháp này gọi là [__Sàng Eratosthenes__](gloss:sieve-eratosthenes).

::: column(width=320)

    x-coordinate-system(width=320 height=320 padding="8 8 20 24" axis-names="x, số các số nguyên tố nhỏ hơn x")

{.caption} Nếu ta vẽ một đồ thị tăng 1 đơn vị mỗi khi có thêm một số nguyên tố
số, ta nhận được một hàm "bậc thang" với các tính chất Toán học rất thú vị.
:::

---
> id: primes-3

Ban có thể tìm hiểu thêm về những tính chất của số nguyên tố ở chủ đề [Tính chia hết và số nguyên tố](/course/divisibility/primes). 
Chúng là một trong những khái niệm quan trọng và bí ẩn bậc nhất trong Toán học!

    figure: img(src="images/primes.svg" width=480 height=156)

---
> id: perfect

### Số hoàn hảo

Để xác định một số có phải là [số nguyên tố](gloss:prime) hay không, ta phải tìm được tất cả
[các ước](gloss:factor) của nó. Thông thường chúng ta sẽ _nhân_ các ước số này 
để được số ban đầu, nhưng hãy xem điều gì sẽ xảy ra nếu ta _cộng_ tất cả những ước 
số của nó lại với nhau ( tính cả số ấy):

    - list = function(n) { return Array.apply(null, {length: n}).map((x,i) => i+1); }
    - factors = function(n) { return list(n-1).filter(i => !(n % i)); }
    - total = function(a) { return a.reduce((a, c) => a + c, 0); }

    table.grid.perfect-table
      tr
        td: strong Số
        td: strong Các ước số
        td: strong Tổng các ước số
      for i in [5,6,7,8,9,10,11,12,13,14,15,16,17,18]
        tr
          td: .c= i
          td
            for j in factors(i)
              .c.small= j
          if i >= 10
            td.md [[#{total(factors(i))}]]
          else
            td= total(factors(i))

---
> id: perfect-1

Hãy so sánh những số này với tổng các ước số của chúng:

::: column.frame.blue.text-center(width=222 parent="padded-thin")

Với hầu hết các số thì tổng các ước của chúng sẽ [[nhỏ hơn|lớn hơn|bằng]]
chính số đó. Những số này được gọi là các __số thiếu hụt__.

::: column.frame.green.text-center.reveal(when="blank-0" animation="pop" width=222)

Đối với một vài số khác, tổng các ước chung của chúng sẽ lớn hơn chính nó. 
Những số này được gọi là các __số dư__.

::: column.frame.yellow.text-center.reveal(when="blank-0" animation="pop" delay=500 width=222)

Chi có một số duy nhất trong danh sách trên có tổng các ước số _bằng_ chính số 
đó: [[6]]. Số này được gọi là [__số hoàn hảo__](gloss:perfect-numbers).

:::

---
> id: perfect-2

Số hoàn hảo tiếp theo là 28, vì khi cộng tổng tất cả các ước số của nó lại ta sẽ được
`1 + 2 + 4 + 7 + 14 = 28`. Càng về sau số hoàn hảo xuất hiện càng ít hơn:

{.text-center.s-purple.s-vertical.perfect-list.no-voice.no-voice} _{.n}6_, _{.n}28_,
_{.n}496_, _{.n}8,128_, _{.n}33,550,336_, _{.n}8,589,869,056_,
_{.n}137,438,691,328_, _{.n}2,305,843,008,139,952,128_, …

Chú ý rằng tất cả những số này đều là [[số chẵn|ước của 3|2 số hình vuông]]. _{span.reveal(when="blank-0")} 
Thật ra các số này cũng đều là số tam giác!_

---
> id: perfect-3

::: column.grow

Những số hoàn hảo được nghiên cứu sớm nhất bởi các nhà Toán học Hy Lạp cổ đại như
[Euclid](bio:euclid), [Pythagoras](bio:pythagoras) và [Nicomachus](bio:nicomachus),
từ hơn 2000 năm trước. Họ tính toán được những số hoàn hảo đầu tiên, và họ tự hỏi rằng liệu có số nào là _số lẻ_ hay không.

Ngày nay, các nhà Toán học đã sử dụng máy tính để kiểm tra 10<sup>1500</sup>
số đầu tiên (đó là con số có 1 chữ số 1 theo sau bởi 1500 chữ số không), nhưng không thành công: tất cả 
những số hoàn chỉnh họ tìm được đều là số chẵn. Cho đến nay, người ta vẫn chưa biết 
được liệu có số hoàn hảo nào là số lẻ hay không, vấn đề này trở thành bài toán chưa có lời giải lâu đời nhất trong lịch sử Toán học!

::: column(width=220)

    x-img(src="images/euclid.jpg" width=220 height=269)

{.caption} Euclid, tranh của Alexandria
:::

---
> id: hailstone

### Dãy số Mưa đá

Hầu hết các dãy số mà chúng ta đã tìm hiểu có duy nhất một quy luật. 
Nhưng không có lý do gì mà chúng ta không tìm kiếm cho chúng nhiều quy luật khác, 
ví dụ một công thức truy hồi như sau:

    table.grid.text-left
      tr
        td: strong.md Nếu `x_n` là số chẵn:
        td.md `x_(n+1) = x_n // 2`
      tr
        td: strong.md Nếu `x_n` là số lẻ:
        td.md `x_(n+1) = 3 x_n + 1`

Hãy bắt đầu với `x_1 = 5` và xem chuyện gì xảy ra:

{.text-center.s-orange.with-arrows.no-voice} _{.n}5_, _{.n}[[16]] *{span.arrow}×3 +1*_,
_{.n}[[8]] *{span.arrow.reveal(when="blank-0")}÷2*_,
_{.n}[[4]] *{span.arrow.reveal(when="blank-1")}÷2*_,
_{.n}[[2]] *{span.arrow.reveal(when="blank-2")}÷2*_,
_{.n}[[1]] *{span.arrow.reveal(when="blank-3")}÷2*_,
_{.n}[[4]] *{span.arrow.reveal(when="blank-4")}×3 +1*_,
_{.n}[[2]] *{span.arrow.reveal(when="blank-5")}÷2*_,
_{.n}[[1]] *{span.arrow.reveal(when="blank-6")}÷2*_, …

---
> id: hailstone-1

Dường như sau một vài số hạng đầu tiên, dãy số này sẽ đạt tới một “vòng tuần hoàn”, lặp lại không bao giờ kết thúc.

Dĩ nhiên, chúng ta đã có thể chọn một điểm bắt đầu khác, như là ${n}{n|10|5,40,1}.
Khi đó dãy số sẽ như sau:

{.text-center.no-voice} _{span.var.s-orange(:html="hailstones(n)")}_, *{span.s-red}_{.n}4_,
_{.n}2_, _{.n}1_,* *{span.s-purple}_{.n}4_, _{.n}2_, _{.n}1_,*
*{span.s-blue}_{.n}4_, _{.n}2_, _{.n}1_, …*

---
> id: hailstone-2

Có vẻ như độ dài của dãy số sẽ khá giống nhau, nhưng nó sẽ luôn kết thúc với một 
vòng tuần hoàn 4, 2, 1 – bất kể dù cho ta có chọn số nào để bắt đầu đi nữa. 
Chúng ta thậm chí có thể biểu diễn các số hạng của dãy số bằng một đồ thị:

    x-coordinate-system(width=600 height=400 padding="12 12 24 40")
      .hailstone-slider.md #[span Start value:]${n}{n|12|1,50,1}

{.reveal(when="var-0")} Lưu ý rằng với một vài điểm khởi đầu thì chuỗi sẽ lập lại rất nhanh,
trong khi những số (như [31](action:set(31)) hay [47](action:set(47))) cần nhiều bước hơn trước 
khi tới được vòng tuần hoàn 4, 2, 1.

---
> id: hailstone-3

::: column.grow

Tất cả những dãy số có công thức truy hồi như thế được gọi là [__Dãy số mưa đá__](gloss:hailstone-sequence), 
bởi vì các số hạng có thể tăng hoặc giảm một cách ngẫu nhiên trước khi tới được vòng tuần hoàn 4, 2, 1 – cũng 
giống như mưa đá cũng di chuyển lên và xuống trong các đám mây trước khi rơi xuống mặt đất.

Vào năm 1937, nhà Toán học [Lothar Collatz](bio:collatz) đưa ra giả thuyết rằng _mọi_
dãy số mưa đá cuối cùng cũng kết thúc bằng vòng tuần hoàn 4, 2, 1 – bất kể giá trị ban 
đầu bạn chọn là gì. Bạn cũng đã kiểm tra với một vài điểm bắt đầu ở trên, và máy tính 
cũng đã thử đến `10^20` số – tương đương với 100 tỷ tỷ hoặc là số có chữ số là 1 và theo sau 
bởi hai mươi chữ số 0.

::: column(width=240)

    x-img(src="images/storm.jpg" width=240 height=340)

:::

Tuy nhiên, chúng ta có vô hạn số nguyên. Chúng ta không có cách nào kiểm tra hết 
chúng được, và cũng chưa ai tìm ra [ cách chứng minh](gloss:proof) mệnh đề trên cho mọi số nguyên.

Cũng giống như việc tìm kiếm những số hoàn hảo lẻ, đây cũng vẫn là một bài toán 
mở chưa có lời giải trong Toán học. Thật đáng ngạc nhiên khi những quy 
luật ngỡ như đơn giản của các dãy số này lại đánh đố cả những nhà Toán 
học xuất chúng nhất của nhân loại trong hàng thế kỷ!


---
> id: look-and-say

### Dãy số nhìn và nói

Dưới đây là một dãy số sẽ khác đôi chút so với những dãy số bạn đã biết. 
Bạn có nhìn ra quy luật của chúng không?

{.text-center.s-lime.s-vertical} _{span.n}1_, _{span.n}11_, _{.n}21_,
_{.n}1211_, _{.n}111221_, _{.n}312211_, …

[Continue](btn:next)

---
> id: look-and-say-1

Dãy số này có tên gọi là dãy số __Nhìn-và-Nói__, quy luật của dãy số này giống như tên gọi: 
bạn sẽ bắt đầu với 1, và các số hạng sau đó là những gì bạn có nếu bạn “đọc to” 
số hạng trước. Dưới đây là một ví dụ:

    p: x-img(src="images/look-and-say.svg" width=240 height=130 style="margin: 0 auto")

Bạn có thể tìm được những số hạng tiếp theo không?

{.text-center.s-lime.s-vertical} …, _{.n}312211_, _{.n}[[13112221]]_,
_{.n}[[1113213211]]_, …

---
> id: look-and-say-2

Dãy số này thường được sử dụng như một câu đố để đánh bại các nhà Toán 
học – Bởi vì quy luật của nó thường hoàn toàn phi Toán học. Tuy nhiên, 
hóa ra, những chuỗi này lại có rất nhiều điểm thú vị xoay quanh. 
Ví dụ, mọi só hạng kết thúc bằng [[1]], thì sẽ không có chữ số nào lớn hơn [[3]] được sử dụng.

---
> id: look-and-say-3

Nhà Toán học người Anh [John Conway](bio:conway) phát hiện ra rằng, bất kể 
là bạn có chọn giá trị đầu tiên nào, thì dãy số cuối cùng cũng sẽ tách ra thành những 
“phần” khác biệt mà không liên quan gì tới nhau. Conway gọi đó là _Định lý vũ trụ_, 
và đặt tên cho những phần khác nhau đó bằng tên của các nguyên tố Hóa học như 
_Hydro_, _Heli_, _Liti_, …, cho đến _Plutoni_.

---
> id: quiz

### Bài kiểm tra về Dãy số

Bạn đã tìm hiểu hàng loạt các dãy số Toán học khác nhau – có dãy số dựa 
trên Hình học, có dãy số tuân theo công thức tổng quát, và có cả những dãy số gần như ngẫu nhiên.

Trong bài kiểm tra này bạn có thể kết hợp tất cả những kiến thức của mình 
liên quan đến dãy số. Chỉ với một mục tiêu duy nhất là: tìm ra quy luật của dãy số
 và hai số hạng kế tiếp!

::: .box.blue

#### Tìm số hạng tiếp theo

{.text-center.s-yellow.no-voice} _{span.n}7_, _{span.n}11_, _{.n}15_, _{.n}19_, _{.n}23_,
_{.n}27_, _{.n}[[31]]_, _{.n}[[35]]_, …
_{span.pattern.reveal(when="blank-0 blank-1")} Quy luật: Luôn +4_

{.text-center.s-orange.no-voice} _{span.n}11_, _{span.n}14_, _{.n}18_, _{.n}23_, _{.n}29_,
_{.n}36_, _{.n}[[44]]_, _{.n}[[53]]_, …
_{span.pattern.reveal(when="blank-2 blank-3")} Quy luật: +3, +4, +5, +6, …_

{.text-center.s-red.no-voice} _{span.n}3_, _{span.n}7_, _{.n}6_, _{.n}10_, _{.n}9_,
_{.n}13_, _{.n}[[12]]_, _{.n}[[16]]_, …
_{span.pattern.reveal(when="blank-4 blank-5")} Quy luật: +4, –1, +4, –1, …_

{.text-center.s-purple.no-voice} _{span.n}2_, _{span.n}4_, _{.n}6_, _{.n}12_, _{.n}14_,
_{.n}28_, _{.n}[[30]]_, _{.n}[[60]]_, …
_{span.pattern.reveal(when="blank-6 blank-7")} Quy luật: ×2, +2, ×2, +2, …_

{.text-center.s-blue.no-voice} _{span.n}1_, _{span.n}1_, _{.n}2_, _{.n}3_, _{.n}5_,
_{.n}8_, _{.n}[[13]]_, _{.n}[[21]]_, …
_{span.pattern.reveal(when="blank-8 blank-9")} Quy luật: Dãy số Fibonacci_

{.text-center.s-teal.no-voice} _{span.n}27_, _{span.n}28_, _{.n}30_, _{.n}15_, _{.n}16_,
_{.n}18_, _{.n}[[9]]_, _{.n}[[10]]_, …
_{span.pattern.reveal(when="blank-10 blank-11")} Quy luật: +1, +2, ÷2, +1, +2, ÷2, …_

{.text-center.s-green.no-voice} _{span.n}1_, _{span.n}9_, _{.n}25_, _{.n}49_, _{.n}81_,
_{.n}121_, _{.n}[[169]]_, _{.n}[[225]]_, …
_{span.pattern.reveal(when="blank-12 blank-13")} Quy luật: Bình phương các số lẻ_

:::



--------------------------------------------------------------------------------



## Tam giác Pascal

> section: pascals-triangle
> id: pascal-intro

Dưới đây là một kim tự tháp số được tạo thành bằng cách sử dụng một quy luật 
rất đơn giản: bắt đầu với số “1” ở trên đỉnh kim tự tháp, mỗi ô tiếp theo sẽ là tổng 
của hai ô ngay trên nó cộng lại. Di chuột vào một vài ô để thấy rõ hơn, sau đó 
bạn hãy điền tiếp vào những ô còn trống:

    - var fact = function(x) { return !x ? 1 : (x * fact(x-1)); };
    - var bin = function(a, b) { return fact(a) / fact(b) / fact(a - b); };

    .overflow-wrap: .pascal-grid(style="width: 560px")
      - var i = 0;
      while i < 13
        - var j = 0
        .r
          while j <= i
            if (i == 6 && j == 2) || (i == 8 && j == 5) || (i == 10 && j == 5)  || (i == 12 && j == 3)  || (i == 12 && j == 9)
              .c.md [[#{bin(i, j)}]]
            else
              .c= bin(i, j)
            - j += 1;
        - i += 1;

---
> id: pascal-intro-1

Sơ đồ trên chỉ thể hiện 12 hàng đầu tiên, nhưng dãy số này có thể tiếp tục không có hồi kết,
chỉ việc thêm hàng vào dưới đáy kim tự tháp. Lưu ý rằng tam giác này là tam giác
[[cân|vuông|đều]], nó có thể giúp bạn tính toán một vài ô.

---

> id: pascal-triangle

Tam giác này được gọi là [__tam giác Pascal__](gloss:pascals-triangle), được đặt 
theo tên nhà Toán học người Pháp [Blaise Pascal](bio:pascal). Ông là 
một trong những nhà Toán học người châu Âu đầu tiên nghiên cứu về những 
quy luật và đặc tính của tam giác này, nhưng nó đã được biết tới bởi những nền văn 
minh khác hàng nhiều thế kỷ trước đó:

::: column(width=200)

    x-img(src="images/pascal-1.jpg" width=130 height=280 style="margin: 0 auto")

{.caption} Vào năm 450 trước công nguyên, nhà Toán học người Ấn độ [Pingala](bio:pingala) đã 
gọi tam giác này là __“Nấc thang trên đỉnh Meru”__, được đặt theo tên của một ngọn núi linh thiêng của người Hindu.

::: column(width=200)

    x-img(src="images/pascal-2.jpg" width=200 height=280)

{.caption} Ở Iran, tam giác này được biết tới với tên gọi là  __“tam giác Khayyam”__ (مثلث خیام),
được đặt theo theo nhà Toán học kim nhà thơ người Pa tư [Omar Khayyám](bio:khayyam).

::: column(width=200)

    x-img(src="images/pascal-3.jpg" width=200 height=280)

{.caption} Ở Trung Quốc, nhà Toán học Jia Xian cũng đã khám phá ra tam giác này.
Nó được đặt theo tên người kế vị của ông, __“ tam giác Yang Hui”__ (杨辉三角).

:::

Tam giác Pascal có thể được tạo thành từ một quy luật vô cùng đơn giản, 
nhưng lại là những quy luật và đặc tính rất đáng ngạc nhiên. Đó là lý 
do nó gây hứng thú với các nhà Toán học trên toàn thế giới qua hàng trăm năm.

[Continue](btn:next)


---
> id: pascal-sequences

### Đi tìm dãy số

Ở những phần trước bạn đã biết được rất nhiều dãy số Toán học khác nhau. 
Những dãy số ấy hóa ra lại có thể được tìm thấy trong chính tam giác Pascal này:

    - var fact = function(x) { return !x ? 1 : (x * fact(x-1)); };
    - var bin = function(a, b) { return fact(a) / fact(b) / fact(a - b); };

    .overflow-wrap: .pascal-grid.sums(style="width: 760px")
      - var i = 0;
      while i < 17
        - var j = 0
        .r
          while j <= i
            - b = bin(i, j)
            if b == 120
              .c: span.s120= b
            else if b == 3003
              .c: span.s3003= b
            else
              .c= b
            - j += 1;
          .c.sum
        - i += 1;

::: tab(parent="pascal-tabs")
#### {.btn.yellow} _{span.check(when="blank-0")}_
Các số trên đường chéo đầu tiên ở hai bên tam giác đều
[[là số một|tăng|chẵn]].
::: tab
#### {.btn.orange} _{span.check(when="blank-1")}_
Các số trên đường chéo thứ hai ở hai bên đều là
[[số nguyên|số nguyên tố|số hình vuông]].
::: tab
#### {.btn.red} _{span.check(when="blank-2")}_
Các số trong đường chéo thứ ba ở hai bên đều là [[số tam giác|số hình vuông|số Fibonacci]].
::: tab
#### {.btn.purple} _{span.check(when="blank-3")}_
Các số trong đường chéo thứ tư ở hai bên đều là [[số tứ diện|số lập phương|lũy thừa của 2]].
::: tab
#### {.btn.blue} _{span.check(when="blank-4")}_
Nếu bạn cộng tất cả các số trong một hàng, tổng của chúng tạo thành một dãy số khác: 
[[các số lũy thừa của hai|các số hoàn hảo|các số nguyên tố]].
::: tab
#### {.btn.teal} _{span.check(when="blank-5")}_
Trên mỗi hàng có một số nguyên tố trong ô thứ hai của nó, tất cả các số sau đó
là [[hợp số|ước số|nghịch đảo]] của số nguyên tố ấy.
::: tab
#### {.btn.green} _{span.check(when="blank-6")}_
Biểu đồ trên có các “đường chéo” được đánh dấu bằng nhiều màu sác khác nhau, cộng tổng các số ở mỗi đường chéo, ta sẽ được [[ số Fibonacci|số Mưa đá|dãy hình học]].
:::

---
> id: pascal-sequences-1

Tất nhiên, một trong các quy luật này đều có một quy tắc Toán học nào đó giải thích tại sao nó 
lại xuất hiện.  Có lẽ bạn đã tìm ra một vài trong số chúng!

Một câu hỏi khác có lẽ bạn sẽ thắc mắc: mỗi một số sẽ xuất hiện bao nhiêu lần trong 
tam giác Pascal. Rõ rằng có rất nhiều số 1, một số 2, và các số khác xuất hiện [[ít nhất hai lần|ít nhất một lần|đúng hai lần]],
_{span.reveal(when="blank-0")} ở đường chéo thứ hai của cả hai cạnh của tam giác._

---
> id: pascal-sequences-2

Một vài số ở giữa của tam giác có thể xuất hiện ba hoặc bốn lần.
Có một số ít xuất hiện sáu lần: bạn có thể bắt gặp cả hai số [120](->.s120) và
[3003](->.s3003) xuất hiện bốn lần ở tam giác trên, và chúng sẽ xuất hiện thêm hai lần nữa ở hàng 120 và 3003.

Bởi vì 3003 là một số tam giác, nó sẽ xuất hiện thêm hai lần nữa ở đường chéo thứ _ba_ của hình tam giác, và tổng cộng sẽ xuất hiện tám lần.

Ta vẫn chưa thể biết được liệu có số nào khác ngoài số 3003 xuất hiện tám lần, hay nhiều hơn tám lần trong tam giác. 
Nhà toán học người Mỹ [David Singmaster](bio:singmaster) đặt ra giả thuyết rằng có một số lượng nhất định và không đổi 
các số có thể xuất hiện trong tam giác Pascal, nhưng phát biểu này vẫn chưa được chứng minh.

---
> id: modular
> goals: select

### Tính chia hết

Một số quy luật trong tam giác Pascal không dễ để có thể tìm ra. 
Ở đồ thị bên dưới, bạn hãy làm nổi bật những ô mà có số chẵn:

    - var fact = function(x) { return !x ? 1 : (x * fact(x-1)); };
    - var bin = function(a, b) { return Math.round(fact(a) / fact(b) / fact(a - b)); };

    .overflow-wrap: .pascal-grid#pascal-select(style="width: 340px")
      - var i = 0;
      while i < 8
        - var j = 0
        .r
          while j <= i
            .c= bin(i, j)
            - j += 1;
        - i += 1;
    x-gesture(target="#pascal-select .r:nth-child(3) .c:nth-child(2)")

{.reveal(when="select")} Có vẻ như số chẵn trong tam giác Pascal tạo ra những
[[tam giác|ma trận|hình vuông]] khác có kích thước nhỏ hơn.

---
> id: modular-1
> goals: c2 c3 c4 c5

Việc tô màu thủ công rất mất thời gian, nhưng ở đây bạn có thể thấy điều gì 
sẽ xảy ra nếu bạn làm vậy với nhiều hàng hơn nữa. Và với những ô có thể chia 
hết cho các số khác thì sao?

    - var fact = function(x) { return !x ? 1 : (x * fact(x-1)); };
    - var bin = function(a, b) { return Math.round(fact(a) / fact(b) / fact(a - b)); };

    .overflow-wrap: .pascal-grid.small(style="width: 760px")
      - var i = 0;
      while i < 25
        - var j = 0
        .r
          while j <= i
            - b = bin(i, j)
            if b > 99999
              .c: span.small= b
            else
              .c= b
            - j += 1;
        - i += 1;
      .pascal-buttons
        button.btn.btn-red(data-value="2") Chia hết cho 2
        button.btn.btn-blue(data-value="3") Chia hết cho  3
        button.btn.btn-green(data-value="4") Chia hết cho  4
        button.btn.btn-yellow(data-value="5") Chia hết cho  5

---
> id: modular-2

::: column.grow
Wow! Những ô được tô màu luôn luôn xuất hiện với hình [[tam giác|hình vuông|cặp đôi]] 
(ngoại trừ một vài ô đơn lẻ có thể được nhìn thấy như những tam giác có kích thước bằng 1).

Nếu ta tiếp tục quy luật này với các ô chia hết cho 2, chúng ta sẽ được một dãy số rất giống với 
__tam giác Sierpinski __ như hình bên phải. Các hình học giống như vậy với những quy luật 
đơn giản mà dường như không có điểm dừng và càng ngày càng nhỏ hơn 
được gọi là một [__Fractal__](gloss:fractal).  Bạn sẽ được tìm hiểu kỹ hơn ở những phần sau…

::: column.width(280)

    img(src="images/sierpinski.svg" width=280 height=243 alt="Sierpinski Triangle")
    p.caption The Sierpinski Triangle

:::

---
> id: pascal-binomial

### Các hệ số của nhị thức bậc cao

Còn một phần quan trọng nữa về tam giác Pascal mà chúng ta cần phải đề cập tới. 
Để hiểu nó, chúng ta sẽ thử giải một bài toán với hai cách hoàn toàn khác nhau,
 và xem chúng có điểm gì tương đồng.

{.todo} SẮP XUẤT BẢN

    // Galton Board, normal distribution



--------------------------------------------------------------------------------



## Giới hạn và Sự hội tụ

> section: convergence
> sectionStatus: dev
> id: convergence-intro

{.todo} SẮP XUẤT BẢN

    // In some sequences, such as Prime numbers or Perfect numbers, the individual
    // terms are very special and interesting. In other sequences we may only be
    // interested in what happens to the terms as we calculate more and more of
    // them (what happens to xn as n gets very large). Here are a few examples
    // of what could happen (the numbers, for clarity, are represented by dots):

    // This sequence gets closer and closer to a particular number. We say that it converges.
    // This sequence doesn’t converge, since it doesn’t keep getting closer to one single number.
    // This sequence keeps on growing. We say that it diverges.

    // Convergence means that the terms keep getting closer to a particular number,
    // and divergence means that the terms keep getting bigger, whether towards
    // infinity or negative infinity. Remember that the sequence of ratios of
    // consecutive Fibonacci numbers above converged to the golden ratio.

    // Unfortunately “getting closer” is not a particularly precise description
    // in mathematics. A sequence could for example first get very big and then
    // turn around and converge. We don’t really care about what happens at the
    // beginning, only what happens to the most distant terms. All of the
    // following sequences converge:

    // Here is how mathematicians define the notion of convergence precisely,
    // and this is one of the most important definitions in all of mathematics:

    // A sequence with terms x1, x2, x3, … tends to a limit y if we can think of
    // any tiny positive number, let us call it ε (the Greek letter Epsilon), and
    // if eventually all terms of the sequence will be within ε of the limit y.
    // This means that there is some (sometimes very big) integer N so that xN,
    // xN+1, xN+2, … are all between y – ε and y + ε.

    // Using special mathematical notation, it is possible to express this
    // definition without any words. We use ∀ meaning “for all”, ∃ meaning
    // “there exists” and : meaning “such that”:

    // ∀ ε ∃ N : |xn – y| < ε ∀ n > N
    // For all ε there exists a number N such that the distance |xn – y|
    // between xn and y is less than ε for all n > N.

    // Sequences and their convergence is studied in an area of mathematics
    // called Analysis. We use sequences to define crucial concepts in mathematics
    // such as series, continuity and differentiation.

    // Litov’s Mean Value Theorem

    // Start with two numbers, say 8 and 2.
    // Let’s generate a sequence where the next number is the mean of the previous two numbers.
    // So the next number is half of (8+2), and the sequence continues: 8,2,5
    // The next number is half of (2+5), and the sequence continues: 8,2,5,3.5
    // What would happen if you continued this process indefinitely?
    // Choose a few pairs of starting numbers and repeat the process.
    // Each time, your sequence should get closer and closer to a value which we call the limit.
    // Can you find a relationship between your starting numbers and the limit of the sequence they generate?
    // Can you explain why this happens?
    // Now start with three numbers.
    // This time, we can generate a sequence where the next number is the mean of the last three numbers.
    // Check you agree that if we start with 4,1,10, the next number is 5, and the number after that is 163.
    // What would happen if you continued this process indefinitely?
    // Choose some more sets of three starting numbers.
    // Can you find a relationship between your starting numbers and the limit of the sequence they generate?
    // Can you explain why this happens?

    // After a while of playing with the numbers on a spreadsheet I have
    // discovered that the formula to find the “limiting value” for 2 starting
    // numbers is: (x+2y)/3
    // where x is the first number chosen and y is the second number chosen.
