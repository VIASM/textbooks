# Đường tròn và số Pi
## Giới thiệu 
> section: introduction
> id: intro
> trailer: tBJUNvCBkLo
> color: "#5A49C9"
> level: Intermediate
> next: graph-theory

::: column.grow

Kể từ khi loài người xuất hiện, chúng ta không ngừng khám phá bầu trời, dùng chuyển động của các vì sao, các hành tinh và mặt trăng để lý giải những sự sống trên Trái đất.
Các nhà thiên văn học Hy Lạp cổ đại là những người đầu tiên phát hiện ra rằng tất cả các thiên thể đều chuyển động theo một đường nhất định, được gọi là “quỹ đạo”. Họ tin rằng những quỹ đạo này luôn là hình tròn. Xét cho cùng, hình tròn là “hình hoàn hảo nhất” trong tất cả các hình khối: nó đối xứng theo mọi hướng, do đó hình tròn là một lựa chọn phù hợp cho trật tự cơ bản của vũ trụ của chúng ta.

::: column(width=320)

    x-img(src="images/geocentric.jpg" width=320 height=272)

{.caption} Earth is at the center of the _Ptolemaic universe_.

:::

---
> id: radius
> goals: compass

Tất cả các điểm nằm trên [__circle__](gloss:circle) đều cách tâm một khoảng cách giống nhau. Điều này có nghĩa chúng ta có thể vẽ đường tròn bằng một chiếc com-pa.

::: column(width=320)

    x-geopad(width=320 height=300 style="position: relative;")
      svg(style="stroke-linecap: round; stroke-linejoin: round")
        circle.move(name="a" cx=160 cy=150 target="r d")
        circle.move.reveal(name="b" cx=250 cy=240 project="circle(a, 120)" target="r" when="compass")
        path.red(x="segment(a,b).contract(0.08)" target="r" arrows="both" hidden)
        path(name="c1" x="arc(a,b,1.99*pi)" hidden)
        path.blue(x="segment(b.rotate(pi/3,a),b.rotate(-2*pi/3,a)).contract(0.01)" target="d" arrows="both" hidden)
        path.green(x="arc(a,b.add(b.subtract(a).unitVector.scale(12)),1.99*pi).contract(0.02)" target="c" arrows="start" hidden)
      x-play-btn

::: column.grow

{.reveal(when="compass")} có ba đại lượng quan trọng liên quan đến đường tròn mà bạn cần biết: 

* {.reveal(when="compass" delay="1000")} 
[{.red.b}radius](target:r) Bán kính của một đường tròn là đoạn thẳng (hoặc độ dài đoạn thẳng) nối tâm với một điểm bất kì trên đường tròn.

* {.reveal(when="compass" delay="4000")} The [{.blue.b}diameter](target:d)
Đường kính là đoạn thẳng (hoặc độ dài đoạn thẳng) có 2 đầu mút nằm trên đường tròn. Đường kính là dây cung đi qua tâm, và có độ dài bằng [[twice|half|the same as]] bán kính.

* {.reveal(when="blank-0")} The [{.green.b}circumference](target:c)
Độ dài đường tròn (chu vi hình tròn) là độ dài đường biên giới hạn hình tròn.
:::

---
> id: similar
> goals: circle-0 circle-1 circle-2

Một tính chất quan trọng của đường tròn là mọi đường tròn đều đồng dạng.

[similar](gloss:similar). 
Bạn có thể chứng minh rằng mọi đường tròn đều đồng dạng bằng cách sử dụng một phép tịnh tiến[translations](gloss:translation) đơn giản và phép vị tự [dilations](gloss:dilation). 
    figure: svg.similar-circles(width=640 height=380 viewBox="0 0 640 380")

---
> id: pi-definition
> goals: digits

Bạn hãy nhớ rằng, với những đa giác giống nhau, tỉ lệ giữa các cạnh tương ứng  là không đổi. Và đường tròn cũng có tính chất đó: tỉ lệ giữa chu vi [circumference](gloss:circle-circumference) và đường kính [diameter](gloss:circle-diameter) ở tất cả các đường tròn đều giống nhau. Nó luôn là 3.14159… một dãy số bí ẩn tên là Pi  [__Pi__](gloss:pi) , viết theo tiếng Hi Lạp là π có nghĩa là p. Số Pi là một dãy số có chữ số thập phân dài vô tận mà không tuân theo bất kì một quy luật nào. 
    canvas.pi-spiral(width=800 height=760)

---
> id: wheel
> goals: unroll

Đây là một bánh xe có đường kính là 1. Khi bạn “trải dài” chu vi, bạn có thể thấy chiều dài chính xác của nó là [[`pi`|`2 pi`|3]]
    figure: include svg/wheel.svg
    x-gesture(target="#wheel .wheel" slide="100,0")

---
> id: circumference

Một đường tròn có đường kính là d, thì chu vi là C = π × d. Tương tự, với đường tròn có bán kính r thì chu vi sẽ tính theo công thức 
C =` [[`2 π r`|`π r`|`π r^2`]].
{.text-center} `C =` [[`2 π r`|`π r`|`π r^2`]].

---
> id: nature

Đường tròn có tính đối xứng cao, nó không có bất kì “đầu nhọn” nào như các góc của đa giác, Đây là một trong những lý do tại sao chúng có thể được tìm thấy nó ở khắp mọi nơi trong tự nhiên:
::: column(width=130 parent="padded-thin")

    x-img(src="images/flower.jpg" width=130 height=130)

{.caption} Flowers

::: column(width=130)

    x-img(src="images/earth.jpg" width=130 height=130)

{.caption} Planets

::: column(width=130)

    x-img(src="images/tree.jpg" width=130 height=130)

{.caption} Trees

::: column(width=130)

    x-img(src="images/orange.jpg" width=130 height=130)

{.caption} Fruit

::: column(width=130)

    x-img(src="images/soap.jpg" width=130 height=130)

{.caption} Soap Bubbles

:::

{.r} Và có rất nhiều các ví dụ khác như cầu vồng hay các gợn sóng. Bạn có thể nghĩ được những thứ khác tương tự không?[Continue](btn:next)

---
> id: max-area
> goals: area-circle

::: column.grow

Đường tròn cũng được biết đến là hình có chu vi lớn nhất. Ví dụ nếu bạn có một sợi dây dài 100 m, bạn có thể tạo ra được một không gian rộng nhất nếu bạn xếp sợi dây thành một hình tròn (thay vì các hình dạng khác như hình chữ nhật hoặc hình tam giác).

Trong tự nhiên, các vật thể như giọt nước hoặc bong bóng khí có thể  tiết kiệm năng lượng bằng cách biến đổi thành hình tròn hoặc hình cầu, và giảm diện tích bề mặt của chúng.


::: column(width=320)

    x-select.segmented
      div(data-value="0") Triangle
      div(data-value="1") Square
      div(data-value="2") Pentagon
      div(data-value="3") Circle
    svg(width=320 height=200)

{.caption} _Circumference_ = __{.m-green}100__, _Area_ = __${area}__


:::

---
> id: area
> goals: slider

### Diện tích của đường tròn

Nhưng làm thế nào để chúng ta thực sự tính toán được diện tích của đường tròn? Hãy thử một cách mà chúng ta đã sử dụng trước đó [finding the area of quadrilaterals](/course/polyhedra/quadrilaterals): chúng ta cắt hình tròn ra thành các phần bất kì khác nhau, sau đó ghép chúng lại vào hình mà chúng ta đã biết diện tích trước đó (ví dụ: hình chữ nhật hay hình tam giác).

Điều khác biệt là, đường tròn là những đường cong nên chúng ta chỉ có kết quả xấp xỉ
::: column(width=340)

    svg.circle-area.red(width=340 height=245)
      defs
        marker#area-arrow(refX=4 refY=4 markerWidth=5 markerHeight=8 orient="auto-start-reverse")
          path(d="M 1 1 L 4 4 L 1 7" stroke-width=1)
      g.labels
        line.reveal(x1=62 y1=158 x2=62 y2=212 marker-start="url(#area-arrow)" marker-end="url(#area-arrow)" when="blank-1")
        line.reveal(x1=80 y1=226 x2=268 y2=226 marker-start="url(#area-arrow)" marker-end="url(#area-arrow)" when="blank-2")
        text.reveal(x=50 y=190 when="blank-1") r
        text.reveal(x=165 y=241 when="blank-2") πr
    x-slider(steps=400)

::: column.grow

Bạn có thể nhìn thấy đường tròn được chia làm ${toWord(n1)} phần bằng nhau. Di chuyển thanh trượt để xếp các phần này thành 1 hàng.

{.reveal(when="slider")} Nếu chúng ta tăng số lượng mảnh cắt lên ${n1}{n1|6|6,30,2} hình này sẽ càng ngày càng giống [[rectangle|circle|square]].

{.reveal(when="blank-0")} Chiều cao của hình chữ nhật bằng với [[radius|circumference|diameter]] của đường tròn
_{span.reveal(when="blank-1")} Chiều rộng của hình chữ nhật bằng [[half the circumference|the circumference|twice the radius]] đường tròn

_{span.reveal(when="blank-2")} Lưu ý rằng một nửa số mảnh cắt để mặt úp và một nửa để mặt ngửa_

{.reveal(when="blank-2" delay=1000)} Do đó, tổng diện tích của hình chữ nhật xấp xỉ A = π r^2
:::

---
> id: area-1
> goals: slider

::: column(width=340)

    svg.circle-area.blue(width=340 height=245)
      g.labels
        line.reveal(x1=20 y1=156 x2=20 y2=206 marker-start="url(#area-arrow)" marker-end="url(#area-arrow)" when="blank-1")
        line.reveal(x1=34 y1=218 x2=355 y2=218 marker-start="url(#area-arrow)" marker-end="url(#area-arrow)" when="blank-2")
        text.reveal(x=10 y=185 when="blank-1") r
        text.reveal(x=165 y=236 when="blank-2") 2πr
    x-slider(steps=400)

::: column.grow

Ở đây, bạn có thể nhìn thấy đường tròn được chia thành ${toWord(n)}  vòng tròn. Như trước đó, bạn có thể di chuyển thanh trượt để “tháo” các vòng.

{.reveal(when="slider")} Nếu chúng ta tăng số lượng vòng lên ${n2}{n2|4|2,12,1}, hình này sẽ càng ngày càng giống [[triangle|rectangle|trapezium]].

{.reveal(when="blank-0")} Chiều cao của hình tam giác bằng với [[radius|diameter|circumference]] của đường tròn

_{span.reveal(when="blank-1")} Đáy của hình tam giác bằng [[thecircumference|twice the diameter]] của đường tròn

_{span.reveal(when="blank-2")} Do đó tổng diện tích của hình tam giác xấp xỉ 
{.text-center.reveal(when="blank-2")} `A = 1/2 "base" × "height" = π r^2`.

:::

---
> id: area-2

Nếu chúng ta có thể sử dụng vô số các vòng tròn hoặc nêm vòng tròn, các giá trị gần đúng ở trên sẽ trở nên hoàn hảo - và cả hai đều cho ta cùng một công thức về diện tích đường tròn:
{.text-center.r} `A = π r^2`.
[Continue](btn:next)

---
> id: pi-approximations

### Calculating Pi

Như bạn đã biết, số pi π = 3.1415926…không phải là một số nguyên và dãy thập phân của nó là các chuỗi không chấm dứt, cũng không lặp lại. Các số có thuộc tính này được gọi là số vô tỉ [__irrational numbers__](gloss:irrational-numbers), điều đó có nghĩa là số `π` không thể biểu thị dưới dạng phân số đơn giản `a/b`.

Đó cũng có nghĩa chúng ta không bao giờ có thể viết hết tất cả chữ số đằng sau của số Pi bởi nó là vô cùng. Các nhà toán học Hy Lạp và Trung Quốc cổ đại đã tính toán bốn chữ số thập phân đầu tiên của Pi bằng cách tính gần đúng các vòng tròn, bằng cách sử dụng
đa giác. Họ để ý rằng, càng thêm nhiều cạnh, đa giác bắt đầu [[more and more|less|exactly]] giống đường tròn.

    figure: x-img(src="images/polygons.svg" width=460 height=110)

---
> id: pi-record

::: column(width=280)

    x-img(src="images/iss.jpg" width=280 height=330 credit="NASA")

::: column.grow

Vào năm 1665, Isaac Newton đã tính thêm được 15 chữ số. Ngày nay, chúng ta có thể sử dụng những siêu máy tính để tính toán giá trị của Pi với độ chính xác cao hơn.

Kỷ lục hiện tại được ghi nhận là 31.4 nghìn tỷ chữ số. Một cuốn sách chứa tất các chữ số này ước chừng dày 400km -  bằng độ cao của Trạm Vũ Trụ Quốc tế quay quanh Trái Đất. 

Và tất nhiên, bạn không cần nhớ nhiều chữ số của Pi như vậy. Thực tế, dùng phân số `22/7 = 3.142…` cũng có tỉ lệ chính xác tương đối cao.
:::

---
> id: pi-sequence

Một cách tiếp cận khác để tính được số Pi là sử dụng dãy số vô hạn. Đây là một ví dụ được phát hiện bởi [Gottfried Wilhelm Leibniz](bio:leibniz) vào năm 1676
{.text-center} `π = 4/1 - 4/3 + 4/5 - 4/7 + 4/9 - 4/input(11) + …`

{.reveal(when="blank-0")} Khi chúng ta tiếp tục tính toán theo dãy trên, áp dụng cùng cách làm, kết quả sẽ ngày càng gần với số Pi.
---
> id: pi-colours
> goals: hover

::: column.grow

Nhiều nhà toán học tin rằng, số Pi còn có nhiều tính chất thú vị hơn: đó là một số thực. Có nghĩa là các chữ số từ 0-9 xuất hiện hoàn toàn ngẫu nhiên, như thể tự nhiên đã tung xúc xắc 10 mặt vô số lần để xác định giá trị của Pi.

Ở đây, bạn có thể thấy 100 chữ số đầu tiên của Pi. Di chuyển tới các ô để xem các chữ số được sắp xếp như thế nào
::: column(width=330)

    .pi-grid
      .pi-left
        .pi-cell 3
        .pi-operator .
      .pi-mid
        for d in '1415926535897932384626433832795028841971693993751058209749445923078164062862089986280348253421170679'.split('')
          .pi-cell= d
      .pi-right: .pi-operator …

:::

---
> id: pi-digits
> goals: search

Nếu số Pi là số thực, điều đó có nghĩa bạn có thể nghĩ tới bất kì dãy số nào, và nó chắc chắn sẽ xuất hiện ở đâu đó trong dãy số Pi. Bạn có thể tìm kiếm trong một triệu số Pi đầu tiên xem có chứa ngày sinh nhật bạn không?
::: .box.red.pi-box
#### Một triệu chữ số của số Pi
    .pi-controls
      | Search for a string of digits:
      input(type="text" pattern="[0-9]*" maxlength=12)
      .pi-warning
    x-pi-scroll
      .first-row 3.

:::

---
> id: pi-movies

Chúng ta có thể chuyển đổi toàn bộ một cuốn sách, ví dụ như Harry Potter thành một chuỗi các chữ số rất dài  (a = 01, b = 02,...), nếu Pi là số thực, chuỗi này sẽ xuất hiện ở đâu đó trong dãy số Pi - nhưng nó sẽ mất hàng triệu năm để tính toán đủ các chữ số trong dãy.

Số Pi nhìn có vẻ rất dễ nhưng lại làm cơ sở quan trọng trong khoa học và toán học. Đó có thể là lý do tại sao số Pi trở nên phổ biến bất thường trong văn hoá của chúng ta (ít nhất là so với các chủ đề khác của toán học )
::: column(width=220 parent="padded-thin")

    x-video(src="images/museum.mp4" poster="images/museum.jpg" width=220 height=140 audio credit="© 20th Century Fox")
Số Pi là mật mã cho chiếc máy tính bảng trong “Night at the Museum 2”.
::: column(width=220)

    x-video(src="images/simpsons.mp4" poster="images/simpsons.jpg" width=220 height=140 audio credit="© Fox")
  Giáo sư Frink (“Simpsons”) làm cả phòng các nhà khoa học im lặng khi nói rằng số Pi bằng 3.
::: column(width=220)

    x-video(src="images/star-trek.mp4" poster="images/star-trek.jpg" width=220 height=140 audio credit="© NBC")
    Spock (“Star Trek”) vô hiệu hóa một máy tính xấu xa bằng cách yêu cầu nó tính toán chữ số cuối cùng của Pi.
:::

---
> id: pi-day

Thậm chí có cả ngày của số Pi mỗi năm vào 14/3, bởi vì `pi ≈ 3.14`, hoặc 22/7 vì `pi ≈ 22/7`.
    figure: x-img(src="images/pies.jpg" width=500 height=150 credit="Evan Shelhamer, Matman from Lublin")



--------------------------------------------------------------------------------



## Độ và Radian
> section: radians
> id: degrees

Cho đến nay, trong hình học chúng ta vẫn đo góc bằng độ [degrees](gloss:degrees). Một __{.m-red} đường tròn có số đo là [[360]]°, nửa đường tròn có số đo là [[180]]°, một phần tư đường tròn có số đo là [[90]]°….
::: column(width=160)

    x-geopad(width=160 height=160): svg
      circle(x="point(150,80)" name="a0" hidden)
      circle(x="point(80,80)" name="b0")
      circle(x="c0" hidden)
      path.red.fill(x="angle(c0,b0,a0)" round size=40)
      path(x="segment(a0,b0)")
      path(x="segment(b0,c0)")

::: column(width=160)

    x-geopad(width=160 height=160): svg
      circle(x="point(150,80)" name="a1" hidden)
      circle(x="point(80,80)" name="b1")
      circle(x="c1" hidden)
      path.green.fill(x="angle(c1,b1,a1)" round size=40)
      path(x="segment(a1,b1)")
      path(x="segment(b1,c1)")

::: column(width=160)

    x-geopad(width=160 height=160): svg
      circle(x="point(150,80)" name="a2" hidden)
      circle(x="point(80,80)" name="b2")
      circle(x="c2" hidden)
      path.yellow.fill(x="angle(c2,b2,a2)" round size=40)
      path(x="segment(a2,b2)")
      path(x="segment(b2,c2)")

:::

---
> id: degrees-1

{.r} Con số 360 rất thuận tiện vì nó chia hết cho rất nhiều số: 2, 3, 4, 5, 6, 8, 9, 10, 12, 15, … Như vậy kết quả số đo của đường tròn sẽ là số nguyên. Nhưng bạn đã bao giờ tự hỏi con số 360 đến từ đâu chưa? [Continue](btn:next)

---
> id: babylon

::: column.grow

Từ xa xưa, con số 360 độ là một trong những khái niệm cổ nhất trong toán học mà hiện tại vẫn được dùng. Chúng được phát triển từ thời Babylon cổ và đã có lịch sử hơn 5000 năm.

Ở thời điểm đó, một trong những ứng dụng quan trọng nhất của toán học là trong lĩnh vực thiên văn học. Mặt trời là cơ sở để xác định 4 mùa, nhờ đó mà người nông dân biết khi nào đến mùa vụ. Tương tự, mặt trăng là cơ sở để xác định thuỷ triều, như vậy ngư dân sẽ biết đúng thời điểm đi đánh cá. Con người cũng nghiên cứu về những vì sao để dự đoán trước tương lai, hoặc để giao tiếp với các vị thần.
::: column(width=260)

    x-img(src="images/babylon.jpg" width=260 height=250 credit="Yale University")

{.caption} Một phiến đá của người Babylon để tính toán “√2”
:::

---
> id: constellations
> goals: rotate

Các nhà thiên văn học nhận thấy rằng, ta có thể nhìn thấy các chòm sao vào một thời điểm nhất định trong đêm, tuy nhiên chúng không đứng yên mà di chuyển từng chút mỗi ngày - cho đến sau khoảng 360 ngày sau, nó lại quay trở lại điểm xuất phát ban đầu. Và điều này có thể giải thích lý do tại sao người xưa chia đường tròn thành 360 độ. 
    figure: .constellations
      .label.md Midnight on day ${day}
      .bg
      .wheel: svg(width=760 height=760 viewBox="0 0 760 760")
      .fg
    x-gesture(target=".constellations" offset="0,-120", slide="-160,0")

---
> id: constellations-1
> goals: video

Thực tế có 365 ngày một năm (chính xác là 365.242199), nhưng những nhà toán học Babylon đã đo trên đồng hồ mặt trời, và con số xấp xỉ này là hoàn toàn khớp với kết quả. 

Kết quả cũng trùng khớp với hệ thống cơ số 60 hiện có của họ (vì 6 xx 60 = 360). Hệ thống này giải thích tại sao chúng ta có 60s trong một phút và 60 phút trong một giờ - mặc dù các đơn vị khác được đo bằng cơ số 10 [base 10](gloss:base-10) (ví dụ: 10 năm=1 thập kỉ, 100 năm = 1 thế kỉ) 
::: column.grow

Đối với nhiều người, khái niệm độ đã trở nên quá quen thuộc trong cuộc sống: ta dùng “video 360 độ” (để chỉ video có thể xem mọi góc độ khi phát lại), vận động viên trượt ván thực hiện vòng xoay 540s, và khi ai đó đột ngột thay đổi quyết định ta nói: “thay đổi 180 độ”).

Nhưng dưới góc độ toán học, lựa chọn con số 360 là hoàn toàn bất kì. Nếu chúng ta sống trên sao Hoả, một đường tròn có thể có số đo 670°, và một năm trên sao Mộc thậm chí có 10,475 ngày.
::: column(width=280)

    x-video(src="images/skateboard.mp4" poster="images/skateboard.jpg" width=280 height=200 credit="© RIDE Channel, from YouTube")

{.caption} The 540 McFlip, a 540° rotation

:::

---
> id: radians

### Radians

Thay vì chia một đường tròn thành các đoạn có số đo góc (như 360 độ), các nhà toán học thường đo các góc bằng các cung tròn [circumference](gloss:circle-circumference) của một đường tròn [__unit circle__](gloss:unit-circle) ( đường tròn có bán kính là 1) 
::: column(width=280)

    x-geopad(width=280 height=280): svg
      circle(x="point(140,140)" name="c")
      path.thin(x="circle(c,100)" name="circ")
      circle.move.blue.pulsate(cx=240 cy=140 name="a" project="circ")
      circle.move.green(cx=240 cy=140.4 name="b" project="circ")
      path.fill.green(x="angle(b,c,a)" label="${round(ang.deg)}°" name="ang" round)
      path.red.thick(x="arc(c,b,ang.rad)" label="${rad(ang.rad)}π")
      path.thin(x="segment(c,a)")
      path.thin(x="segment(c,b)")

::: column.grow

[full circle](action:setState(0)) Một đường tròn có chu vi là _{x-equation.small(solution="2 π" keys="+ × π" numeric)}_.

{.reveal(when="eqn-0")} Một nửa đường tròn  [half circle rotation](action:setState(1)) , độ dài tương ứng theo chu vi là {x-equation.small(solution="π" keys="+ × π" numeric)}_.

{.reveal(when="eqn-1")} Một phần tư đường tròn  [quarter circle rotation](action:setState(2)), độ dài tương ứng theo chu vi là _{x-equation.small(solution="π/2" keys="+ × π frac" numeric)}_.

{.reveal(when="eqn-2")} Cách tính toán góc này được gọi là radian [__radians__](gloss:radians) ( đơn vị radian).
:::

---
> id: radians-conversion

Mỗi góc tính bằng độ đều có kích thước tương ứng khi chuyển sang radian. Chuyển đổi giữa hai đơn vị cũng dễ dàng - giống như đổi đơn vị m sang km hay từ độ C sang độ F.
{.text-center} __{.m-red} 360°__ _{span.space}=_ __{.m-green} 2*π* rad__

::: column(width=180 parent="padded-thin")

{.text-center} _{span.rotate.left}`=>`_<br>
__{.m-red} 1°__ _{span.space}=_ [[`pi/180`|`180pi`|`360/pi`]] __{.m-green} rad__

::: column(width=180)

{.text-center} _{span.rotate.right}`=>`_<br>
__{.m-green} 1 rad__ _{span.space}=_ [[`180/pi`|`180-pi`|`2pi-360`]] __{.m-red} °__

:::

---
> id: radians-table

Bạn có thể biểu diễn giá trị radian dưới dạng bội số của Pi hoặc số thập phân. Bạn có thể điền vào bảng các số đo góc tương đương giữa độ và radian chứ?
::: .overflow-wrap.overflow-table

| __{.m-red}degrees__ | 0 | 60 | _{x-equation.small(solution="360/π" keys="π frac" numeric)}_ | 180 | _{x-equation.small(solution="270" keys="π frac" numeric)}_    |
| __{.m-green}radians__   | 0 | _{x-equation.small(solution="π/3" keys="π frac" numeric)}_ | 2    | _{x-equation.small(solution="π" keys="π frac" numeric)}_ | `3/2 pi` |
{.table-small.grid}

:::

---
> id: radians-distance

### Quãng đường chuyển động

Bạn có thể coi radian là một “con chạy” di chuyển quanh một đơn vị đường tròn. Điều này rất hữu ích khi tính toán một vật đang chuyển động theo quỹ đạo tròn.
::: column.grow

Ví dụ, Trạm vũ trụ quốc tế [International Space Station](gloss:iss) quay xung quanh trái đất 1,5h một lần. Có nghĩa là tốc độ quay của nó là  [[`(2 pi)/1.5`|`1.5/(2 pi)`|`1.5 * pi`]] radian mỗi giờ.

{.reveal(when="blank-0")} Trong một đơn vị đường tròn tiêu chuẩn (radian là 1) [unit circle](gloss:unit-circle), tốc độ quay bằng với tốc độ thực tế, bởi vì chiều dài của một cung tròn bằng với một vòng quay hoàn chỉnh tính bằng radian (đều là 2pi)

{.reveal(when="blank-0" delay=1000)} Bán kính của quỹ đạo ISS là 6800\ km có nghĩa tốc độ thật sự của ISS phải là [[`(2 pi)/1.5 xx 6800`|`(2 pi)/1.5 ÷ 6800`|`6800/(2 * pi)`]] _{span.reveal(when="blank-1")}= 28483 km mỗi giờ. 
::: column(width=300)

    x-geopad.r(width=300 height=300)
      .earth
      svg.r
        circle(x="point(150,150)" name="c")
        circle(x="point(280,150)" name="a")
        circle(x="a.rotate(p*2*pi,c)" name="b" hidden)
        path.red(x="arc(c,a,p*2*pi)")
        path.fill(x="angle(a,c,b)" label="${round(2*p,1)}π" round)
        path.red(x="segment(c,a)")
        path.red(x="segment(c,b)")
      .var.iss(style="transform: translate(${a.rotate(p*2*pi,c).x}px,${a.rotate(p*2*pi,c).y}px) rotate(${(p+0.25)*2*pi}rad)")
      .time.var ${round(p*1.5,1)}h
      x-play-btn

:::

---
> id: radians-distance-1

Bạn có thấy rằng trong ví dụ này, radian là một đơn vị thuận tiện hơn nhiều so với
độ không ? Khi chúng ta biết tốc độ quay, chúng ta chỉ cần nhân với bán kính để ra tốc độ thực tế.

Lấy một ví dụ khác: bánh xe ô tô của bạn có bán kính là 0.25m. Nếu bạn lái với tốc độ 20m/s, bánh xe sẽ quay [[`20/0.25 =80`|`20 xx 0.25 = 5`|`0.25/50 = 0.0125`]] radian mỗi giây. 
_{span.reveal(when="blank-0")}(or `80/(2pi) = 13` rotations per second)._
---
> id: radians-trig

### Lượng giác

Trong các hình học đơn giản, độ và radian hoàn toàn có thể thay thế cho nhau - bạn có thể chọn bất kì đơn vị nào bạn thích hoặc trong đề bài sẽ yêu cầu bạn dùng đơn vị nào để trả lời. Tuy nhiên, khi bạn nghiên cứu chuyên sâu hơn về lượng giác  [trigonometry](gloss:trigonometry) hoặc giải tích [calculus](gloss:calculus), thì radian sẽ tiện lợi hơn nhiều so với độ.
::: column.grow

Phần lớn các máy tính đều có nút đặc biệt (->.button.mode) để chuyển đổi giữa độ và radian. Bạn sẽ nhập vào số đo các hàm lượng giác như  [__sin__](gloss:sin), [__cos__](gloss:cos) và __tan__ để nhận được kết quả là số đo góc của các hàm ngược của chúng như __arcsin__, __arccos__ and __arctan__.
Hãy thử dùng chiếc máy tính này để tính toán 
{.text-center} sin(30°) = [[0.5]] _{span.eqn-gap}_ cos(1°) = [[0.999]]<br>
sin(30 rad) = [[-0.988]] _{span.eqn-gap}_ cos(1 rad) = [[0.54]]

::: column(width=300)

    .calculator
      .display
        span
        .setting DEG
      .button.num 7
      .button.num 8
      .button.num 9
      .button.wide sin
      .button.num 4
      .button.num 5
      .button.num 6
      .button.wide cos
      .button.num 1
      .button.num 2
      .button.num 3
      .button.wide tan
      .button.num 0
      .button .
      .button C
      .button.wide.mode mode

:::

---
> id: small-angle

Sử dụng Radian sẽ có lợi thế hơn khi tính hàm Sin. Nếu `θ` là một góc rất nhỏ (bé hơn 20° hoặc 0.3 rad), thì sin(θ) ≈ θ. Ví dụ, 
{.text-center} sin(${x}{x|0.1|0,0.5,0.05}) `≈` ${sin(x)}…

{.reveal(when="var-0")} Đây được gọi là góc gần đúng, và nó có thể đơn giản hóa rất nhiều phương trình có chứa hàm lượng giác.
Bạn sẽ tìm hiểu thêm về điều này trong tương lai. 



--------------------------------------------------------------------------------



## Tiếp tuyến, dây cung và cung tròn

> section: tangets-chords-arcs
> id: circle-parts

Trong các phần trước, bạn đã biết khái niệm một số thành phần liên quan đến đường tròn - như tâm, bán kính, đường kính và chu vi. 
Tuy nhiên, chúng ta vẫn cần tìm hiểu thêm nhiều khái niệm có liên quan đến đường tròn để giải quyết những bài toán phức tạp hơn.
::: column(width=300)

    x-geopad.sticky(width=300 height=300): svg
      circle(x="point(150,150)" name="x")

      path.teal.fill.reveal(x="sector(x,d1,pi/2.5)" target="sector" when="next-3" label="Sector" label-class="white")
      path.purple.fill.reveal(x="arc(x,b1,pi/2.5)" target="segment" when="next-4" label="Segment")

      path.black(x="circle(x,100)" name="c")

      circle.red(x="c.at(0.5)" name="a1" target="secant")
      circle.red(x="c.at(0.7)" name="a2" target="secant")
      path.red.thick(x="line(a1,a2)" label="Secant" target="secant")

      circle.green.reveal(x="c.at(0.8)" name="b1" target="chord" when="next-0" animation="pop")
      circle.green.reveal(x="c.at(0)" name="b2" target="chord" when="next-0" animation="pop")
      path.green.thick.reveal(x="segment(b1,b2)" label="Chord" target="chord" when="next-0" animation="draw")

      circle.blue.reveal(x="c.at(0.1)" name="c1" target="tangent" when="next-1" animation="pop")
      path.blue.thick.reveal(x="c.tangentAt(0.1)" label="Tangent" target="tangent" when="next-1" animation="draw")

      circle.yellow.reveal(x="c.at(0.2)" name="d1" target="arc" when="next-2" animation="pop")
      circle.yellow.reveal(x="c.at(0.4)" name="d2" target="arc" when="next-2" animation="pop")
      path.yellow.thick.reveal(x="arc(x,d1,pi/2.5)" label="Arc" target="arc" when="next-2" animation="draw")

::: column.grow(parent="right")

* {.r} A [{.red.b} secant](target:secant) Cát tuyến là một đường thẳng cắt đường tròn tại 2 điểm [Continue](btn:next)

* {.r.reveal(when="next-0")} A [{.green.b} chord](target:chord) Dây cung là đoạn thẳng có 2 đầu mút nằm trên đường tròn. [Continue](btn:next)

* {.r.reveal(when="next-1")} A [{.blue.b} tangent](target:tangent)Tiếp tuyến là đường thẳng tiếp xúc với đường tròn tại một điểm duy nhất. Điểm này gọi là tiếp điểm. [Continue](btn:next)

* {.r.reveal(when="next-2")} An [{.yellow.b} arc](target:arc) Cung tròn là một đoạn đóng bất kì trên đường tròn. [Continue](btn:next)

* {.r.reveal(when="next-3")} A [{.teal.b} sector](target:sector)Hình quạt tròn là phần hình tròn giới hạn bởi hai bán kính và cung tròn bị chắn bởi hai bán kính này. [Continue](btn:next)

* {.r.reveal(when="next-4")} Finally, a [{.purple.b} segment](target:segment) Hình viên phân là  phần bị giới hạn bởi cung tròn và dây căng cung. [Continue](btn:next)

:::

---
> id: circle-parts-1

Trong phần này, chúng ta sẽ xem xét mối quan hệ giữa tất cả các yếu tố này,
và chứng minh các định lý về các tính chất của chúng. Đừng lo lắng về việc ghi nhớ tất cả
định nghĩa ngay bây giờ - bạn luôn có thể sử dụng bảng thuật ngữ [glossary](->.footer-link[data-modal=glossarym])


---

### Tiếp tuyến

{.todo} COMING SOON!

    // https://www.mathopenref.com/tangentline.html
    // https://www.mathopenref.com/consttangents.html
    // https://www.mathopenref.com/consttangent.html

    // __[CC] Dựng một đường tiếp tuyến từ một điểm bên ngoài một đường tròn đã cho đến đường tròn.__
    //
    // Tiếp điểm: Giao điểm của tiếp tuyến và đường tròn.
    //
    // Đường tiếp tuyến và bán kính được xuất phát từ tiếp điểm có mối quan hệ đặc biệt. Hãy cùng tìm hiểu nó trong phần này.
    //
    // _Định lý tiếp tuyến với đường tròn_: Một đường thẳng là tiếp tuyến của đường tròn khi và chỉ khi đường thẳng vuông góc với bán kính tại tiếp điểm.
    //
    // Để chứng minh định lý này, cách dễ nhất là làm gián tiếp (chứng minh bằng phản chứng). Ngoài ra, hãy chú ý rằng định lý này sử dụng các từ “khi và chỉ khi”, làm cho nó trở thành một phát biểu hai điều kiện. Do đó, điều ngược lại của định lý này cũng đúng. Bây giờ chúng ta hãy xem xét hai đoạn tiếp tuyến, được vẽ từ cùng một điểm bên ngoài. Nếu chúng ta đo hai đoạn này, chúng ta sẽ thấy rằng chúng bằng nhau.
    //
    // Nếu hai tiếp tuyến cùng xuất phát từ một điểm ngoài đường tròn thì chúng bằng nhau. 
    //
    // Tiếp tuyến thực chất là một khái niệm được phổ biến rộng rãi.
    // Tiếp tuyến của hai đường tròn: Hai hoặc nhiều đường tròn có chung tiếp tuyến và cắt nhau.
    // Hai đường tròn có thể tiếp tuyến với nhau theo hai cách khác nhau, tiếp tuyến trong hoặc tiếp tuyến ngoài.

---

### Dây cung 

{.todo} COMING SOON!

    // Dây cung là một đoạn thẳng có 2 đầu mút nằm trên đường tròn. Đường kính là dây cung dài nhất của đường tròn. Có một số định lý về tính chất của dây cung.
    //
    // Định lý dây cung #1: Trong cùng một đường tròn hoặc các đường tròn đồng dạng, các cung nhỏ bằng nhau khi và chỉ khi dây cung tương ứng của chúng bằng nhau.
    //
    // Chú ý, ta dùng “khi và chỉ khi” trong định lý. Điều này có nghĩa định lý 1 là một phát biểu hai điều kiện. Như vậy, nếu hai góc ở tâm bằng nhau thì dây cung xuất phát từ tâm và cung tròn tương ứng cũng bằng nhau. Trong cả hai hình này, BE≅CD và BEˆ≅CDˆ. Trong hình thứ hai, chúng ta có △ BAE≅ △ CAD vì các góc ở tâm bằng nhau và BA≅AC≅AD≅AE vì chúng đều là bán kính (SAS). Bằng CPCTC, BE≅CD.

    //
    // Thực hàn: Đường trung trực của một dây cung
    // 1. Vẽ một đường tròn tâm A.
    // 2. Vẽ một dây cung của ⨀A. Cắt đường tròn tại B, C
    // 3. Tìm trung điểm D của BC bằng thước kẻ.
    // 4. Kẻ 1 đường kính đi qua hai điểm A và D. Mối quan hệ của AD với dây cung là gì, với BC?
    //
    // Định lý dây cung #2: Đường trung trực của một dây cung cũng là một đường kính
    // Trong hình bên trái, AD⊥BC và BD≅DC. Từ định lý này, chúng ta cũng nhận thấy rằng AD cũng chia đôi cung tương ứng tại E, do đó BEˆ≅ECˆ.

    //
    // Định lý dây cung #3: Nếu đường kính vuông góc với một dây cung thì đường kính đó chia đôi dây cung và cung tròn tương ứng của nó.

    //
    // Thực hành: Tính chất của hai dây cung bằng nhau
    // 1. Vẽ một đường tròn có bán kính 2 inch và hai dây cung đều là 3 inch. Đánh dấu các điểm như hình bên phải. Biểu đồ này phải được vẽ theo đúng tỷ lệ.
// 2. Từ tâm kẻ đoạn vuông góc với AB và CD.     
// 3. Xóa các dấu cung và các đường nằm ngoài các điểm giao nhau, để lại FE và E. Tìm số đo của các đoạn này. Bạn nên chú ý điểm gì?

    //
    // Định lý dây cung #4: Trong cùng một đường tròn hoặc hai đường tròn đồng dạng, hai dây cung bằng nhau khi và chỉ khi chúng cách đều tâm.
    //
    // Chúng ta đã biết rằng hai đường thẳng cách đều cùng một điểm khi và chỉ khi khoảng cách ngắn nhất từ điểm đó đến hai đường thẳng bằng nhau. Khoảng cách ngắn nhất từ bất kỳ điểm nào đến một đường thẳng là đường trung trực giữa chúng. Theo định lý này, việc FE = EG có nghĩa là AB và CD cách đều tâm và AB≅CD.

    // Đường tròn đồng tâm: Hai hoặc nhiều đường tròn có cùng tâm, nhưng bán kính khác nhau.
    // Đường tròn bằng nhau: Hai hoặc nhiều đường tròn có cùng bán kính, nhưng khác tâm.

---
> id: earth-arc

### Cung tròn và Vectơ


::: column.grow

Hầu hết các nhà khoa học ở Hy Lạp cổ đại đều đồng ý rằng Trái đất có hình cầu. Có
rất nhiều bằng chứng cho nhận định trên: từ những con tàu biến mất sau đường chân trời trên biển, đến chuyển động tròn của các ngôi sao trong đêm.

Tuy nhiên, không ai biết chính xác _ Trái đất lớn như thế nào - cho đến khoảng năm 200 trước Công nguyên, khi nhà toán học [Eratosthenes](bio:eratosthenes)  tìm ra một cách khéo léo để đo bán kính Trái đất, sử dụng các hình học cơ bản. Tất cả những gì chúng ta cần là những kiến thức về cung tròn và hình quạt tròn của đường tròn.

::: column(width=280)

    x-solid(size=280 rotate="0.5")

:::

---
> id: arcs

::: column(width=280)

    x-geopad.sticky(width=280 height=280): svg
      circle(x="point(140,140)" name="c")
      path(x="circle(c,100)" name="circ")
      circle.move(cx=240 cy=140 name="a" project="circ" label="A")
      circle.move(cx=85 cy=60 name="b" project="circ" label="B")

      path.yellow.fill(x="sector(c,b,angle(b,c,a).rad).minor" label="Sector" target="sector" label-class="white")
      path.red.thick(x="arc(c,b,angle(b,c,a).rad).minor" label="Arc" target="arc")
      path.purple.thick.transparent(x="arc(c,a,2*pi-angle(b,c,a).rad).major" target="major")

::: column.grow

Bạn có thể nhìn thấy trong biểu đồ, cung tròn  [{.red} arc](target:arc) là một phần [[circumference|diameter|tangent]] của đường tròn, và phần quạt tròn [{.yellow} sector](target:sector) là một phần [[interior|radius|perimeter]] của đường tròn.
::: .reveal(when="blank-0 blank-1")

Cung giữa 2 điểm A và B được viết là `arc(AB)`. Định nghĩa này dễ gây nhầm lẫn bởi còn một cung tròn còn lại [{.purple} second arc](target:major) cũng nối 2 điểm A và B nhưng lại ở hướng ngược lại của đường tròn.
Cung tròn nhỏ hơn gọi là cung nhỏ, và cung lớn hơn gọi là cung lớn. Nếu hai điểm A, B đối diện nhau, cả hai cung có cùng độ dài là [[semicircles|diameters|circumferences]]
:::
:::

---
> id: arcs-1

::: column.grow

Để tìm độ dài của cung hoặc diện tích của hình quạt, chúng ta cần tính góc tương ứng tại tâm của đường tròn: gọi là góc ở tâm [{.blue.b} central angle](target:angle).

Lưu ý rằng, cung tròn, phần quạt tròn và góc đều chiếm tỷ lệ giống nhau trong đường tròn. Ví dụ, nếu  [{.blue} central angle](target:angle) là  [90°](action:set90Deg()), nó chiếm [[one quarter|one half|one third]] của  [{.teal} full circle](target:fangle).
::: .reveal(when="blank-0")

Điều này có nghĩa là độ dài của cung bằng ¼ của độ dài đường tròn [{.purple} whole circumference](target:circ). Và diện tích phần quạt tròn  [{.yellow} area of the sector](target:sector) chiếm ¼  hình tròn.

Chúng ta có thể biểu thị mối quan hệ này thông qua một phương trình:
{.text-center} `"arc length" / "circumference" = blank("sector area","circle radius","arc area") / "circle area" = "central angle" / blank("360°","180°","90°")`
:::

::: column(width=280)

    x-geopad.sticky(width=280 height=280): svg
      circle(x="point(140,140)" name="c")
      path(x="circle(c,100)" name="circ")
      circle.move(cx=240 cy=140 name="a" project="circ")
      circle.move(cx=85 cy=60 name="b" project="circ")

      path.yellow.fill(x="sector(c,b,angle(b,c,a).rad)" label="Sector" target="sector" label-class="white")
      path.red.thick(x="arc(c,b,angle(b,c,a).rad)" label="Arc" target="arc")
      path.fill.blue(x="angle(b,c,a)" target="angle")

      path.fill.orange.transparent(x="circ" target="area")
      path.thick.purple.transparent(x="circ" target="circ")
      path.teal.fill.transparent(x="circle(c,32)" target="fangle")

:::

---
> id: arcs-2

Bây giờ chúng ta có thể biến đổi phương trình này để tìm giá trị chúng ta muốn . Ví dụ: 
::: column(width=320 parent="padded-thin")

| [arc length](pill:red) | = | `"circumference" × c/360` |
|                        | = | `2 π r × c/360`          |
{.eqn-system}

::: column(width=320)

| [sector area](pill:yellow) | = | `"circle area" × c/360` |
|                            | = | `π r^2 × c/360`         |
{.eqn-system}

:::

trong đó r là bán kính của đường tròn và c là số đo của góc ở tâm.
    // Ở công thức này, ta lấy diện tích của toàn bộ hình tròn, sau đó lấy một phần nhỏ của nó tùy thuộc vào phần diện tích mà phần quạt tròn chiếm.
    // Độ dài của cung là khoảng cách dọc theo đường cong của chu vi hình tròn. Nó dài hơn một chút so với đoạn thẳng nối hai điểm giống nhau (dây cung).

---
> id: arcs-rad

Nếu góc ở tâm được đo bằng radian [radians](gloss:radians) mà không phải độ, chúng ta có thể sử dụng phương trình tương tự, nhưng phải thay 360° bằng [[`2 π`|`1/2 π`|`π`]]:

::: .reveal(when="blank-0")
::: column(width=320 parent="padded-thin")

| [arc length](pill:red) | = | `2 π r × c/(2π)` |
|                        | = | `r × c`          |
{.eqn-system}

::: column(width=320)

| [sector area](pill:yellow) | = | `π r^2 × c/(2π)` |
|                            | = | `1/2 r^2 c`      |
{.eqn-system}

:::

Hãy chú ý cách để biến các hàm trở nên đơn giản hơn bằng cách rút gọn π
Điều này có được theo như định nghĩa của radian  [definition of
radians](/course/circles/radians#radians) về cơ bản là độ dài của một cung của đường tròn với đơn vị radian là 1

:::
Bây giờ hãy cùng khám phá cách con người sử dụng cung tròn và hình quạt để tính toán chu vi của Trái đất.  [Continue](btn:next)
---
> id: eratosthenes

Ở Ai Cập cổ đại, thành phố Swenet nằm dọc theo sông Nile. Swenet nổi tiếng bởi một cái giếng với một đặc tính kỳ lạ: hàng năm có một khoảnh khắc ánh sáng mặt trời chiếu tới tận đáy giếng - vào trưa ngày 21 tháng 6, ngày hạ chí. Vào đúng khoảnh khắc đó, đáy giếng được chiếu sáng, nhưng không chiếu sáng hai bên, có nghĩa là Mặt trời đang ở ngay trên miệng giếng.
::: column(width=300)

    x-img(src="images/egypt-map.jpg" width=300 height=300 lightbox credit="© Google Maps")

{.caption} Người Ai Cập cổ đại đo khoảng cách bằng cách đếm số bước phải đi bộ.

::: column(width=300)

    x-img(src="images/well.jpg" width=300 height=300 lightbox)

{.caption} Một số nguồn nói rằng "Giếng Eratosthenes" là đảo Elephantine ở sông Nile.
.

:::

Nhà toán học [Eratosthenes](bio:eratosthenes) sống ở Alexandria, nơi cách Swenet 800km về phía Bắc, và cũng là nơi ông đang làm việc với vị trí giám đốc của Great Library. Ở trung tâm thành phố Alexandria có một đài tưởng niệm hình kim tự tháp rất cao và hẹp.

Eratosthenes nhận thấy rằng vào giữa trưa của ngày hạ chí, cái bóng của cái tháp sẽ đổ xuống  - có nghĩa là mặt trời không ở ngay phía trên cái tháp. Ông suy luận rằng điều này là do Trái đất bị cong và nhận ra rằng điều này có thể được sử dụng để tính toán chu vi hành tinh của chúng ta.
---
> id: eratosthenes-1

::: column.grow

{.r} Here you can see the well in Swenet as well as the obelisk in Alexandria.
The sun rays fall directly into the well, but hit the obelisk at an angle and
cast a shadow. [Continue](btn:next)
{.r}  Chúng ta có thể thấy giếng ở Swenet cũng như tháp ở Alexandria, các tia nắng mặt trời chiếu thẳng vào giếng, nhưng khi chiếu vào tháp lại đổ bóng và tạo thành một góc.
::: .reveal(when="next-0")

Eratosthenes tính toán rằng góc [{.teal} angle](target:angle1) được tạo bởi tháp và cái bóng của nó là 7.2°. Góc này bằng với góc ở tâm[{.purple} central angle](target:angle2) của cung tròn đi từ Alexandria đến Swenet, bởi vì chúng là các góc [[alternating|vertical|corresponding]].
:::

::: .reveal(when="blank-0")
Bây giờ chúng ta có thể sử dụng phương trình cho độ dài cung mà chúng ta đã suy ra ở trên:
{.text-center} `pill("arc length","red","arc") / pill("circumference","blue","circ") = (input(7.2)"°") / "360°"`
:::

::: .reveal(when="blank-1")
Nếu chúng ta biến đổi công thức, chúng ta sẽ tính được chu vi của Trái Đất là
{.text-center} `pill("circumference","blue","circ") = "360°" / "7.2°" × pill("800 km","red","arc") = input(40000) "km"`
:::

::: .reveal(when="blank-2")
Cuối cùng, chúng ta biết rằng chu vi của một đường tròn là `C = 2 pi r`, nên bán kính của Trái Đất sẽ là:
{.text-center} `r_"Earth" = (40000 "km") / (2 pi) ≈ 6400 "km"`.
:::

::: column(width=300)

    x-geopad.sticky(width=300 height=400)
      img.sunrays(src="images/sunlight.png" width=300 height=400)
      svg.r
        defs: radialGradient#grad1(cx=200 cy=200 r=200 gradientUnits="userSpaceOnUse")
          stop(offset=0 stop-color="#63a3ff")
          stop(offset=1 stop-color="#0f82f2")

        circle(x="point(150,250)" name="c" hidden)
        circle(x="point(150,120)" name="a" hidden)
        circle.move.pulsate(cx=80 cy=140 name="b" project="arc(c,point(64,155),1.47)")
        circle(x="c.add(b.subtract(c).scale(1.465))" name="d" hidden)

        path.shadow(x="triangle(c,d,point(d.x,c.y))")
        path.earth(d="M153,120,152,150h-4l-.95-30a130,130,0,1,0,5.9,0Z" fill="url(#grad1)")
        path.earth-cover.fill(x="circle(c,130)")

        path.red.thick.reveal(when="next-0" animation="draw" x="arc(c,b,angle(b,c,a).rad).minor" target="arc")
        path.fill.teal.reveal(when="next-0" x="angle(c,d,point(d.x,c.y)).sup" target="angle1")
        path.fill.purple.reveal(when="next-0" x="angle(b,c,a).sup" name="ang" target="angle2")
        path.thin.white.reveal(when="next-0" animation="draw" x="segment(c,b)")
        path.blue.transparent(x="circle(c,130)" target="circ")

        image.obelisk.var(xlink:href="images/obelisk.svg" height=60 width=8 style="transform: translate(${b.x-4}px, ${b.y-60}px) rotate(-${angle(b,c,a).rad}rad)")

:::

---
> id: eratosthenes-2

Phép đo của Eratosthenes là một trong những thí nghiệm quan trọng nhất trong thời cổ đại. Ước lượng của ông về kích thước của Trái Đất chính xác đến ngạc nhiên, đặc biệt khi ông chỉ có những dụng cụ đo lường hết sức cơ bản.
::: column(width=280)

    x-img(src="images/obelisk.jpg" width=280 height=450 lightbox)

::: column.grow

Tất nhiên, rất khó để chuyển đổi những kết quả ban đầu của ông thành các đơn vị hiện đại như km. Ở thời Hy Lạp cổ đại, khoảng cách được đo bằng stadia (khoảng 160 m), nhưng không có tiêu chuẩn chung. Mỗi khu vực lại có cách đo khác nhau nên chúng ta không thể biết Eratosthenes đã sử dụng phương pháp nào để đo.
Trong những thế kỷ tiếp theo, các nhà khoa học đã cố gắng sử dụng nhiều phương pháp khác nhau để tính bán kính Trái đất - đôi khi cho kết quả không giống nhau và không chính xác.

Chính một trong những phép đo không chính xác này đã thúc đẩy Christopher Columbus đi thuyền về phía tây từ Bồ Đào Nha. Ông cho rằng Trái đất nhỏ hơn nhiều so với thực tế và hy vọng sẽ đến được Ấn Độ. Trên thực tế, ông đã đến một lục địa khác ở giữa: Châu Mỹ.
:::

---

### Hình viên phân

{.todo} COMING SOON!

    // Phần cuối cùng mà chúng ta có thể tính diện tích của đường tròn là hình viên phân ( phần của hình tròn), cẩn thận tránh nhầm lẫn với các đoạn thẳng. Hình viên phân của hình tròn là bị phần bị chặn bởi một cung (cung nhỏ hơn 180°) của đường tròn và bởi dây cung nối hai điểm đầu cuối của cung. Diện tích  của hình viên phân bằng diện tích của hình quạt tròn trừ đi diện tích của phần tam giác tương ứng tạo bởi hai cạnh nối tâm và hai điểm đầu cuối của cung và dây cung (Asegment=Asector−A△ABC).

--------------------------------------------------------------------------------



## Các định lý về đường tròn
> section: circle-theorems
> sectionStatus: dev

https://www.mathsisfun.com/geometry/circle-theorems.html
https://mathsmadeeasy.co.uk/gcse-maths-revision/circle-theorems-gcse-revision-and-worksheets/
http://amsi.org.au/teacher_modules/Circle_Geometry.html

__[CC] Xác định và biểu diễn được mối quan hệ giữa các góc nội tiếp, bán kính và dây cung. Bao gồm quan hệ giữa các góc ở tâm, góc nội tiếp và đường tròn; góc nội tiếp chắn nửa đường tròn là góc vuông; bán kính của đường tròn vuông góc với tiếp tuyến của đường tròn tại tiếp điểm.__

Góc nội tiếp là góc có đỉnh nằm trên đường tròn và hai cạnh chứa 2 dây cung của đường tròn đó. Còn cung nằm bên trong góc được gọi là cung bị chắn. Đỉnh của một góc nội tiếp có thể ở bất kỳ đâu trên đường tròn miễn là các cạnh của nó cắt đường tròn để tạo thành một cung bị chắn. 

__Định lý góc nội tiếp__
Số đo góc nội tiếp bằng nửa số đo cung bị chắn

Để chứng minh các định lý của góc nội tiếp, bạn cần phải chia làm 3 trường hợp, 

__Định lý về góc nội tiếp bằng nhau__:
Các góc nội tiếp chắn cùng 1 cung thì bằng nhau.

__Định lý góc nội tiếp nửa đường tròn__
Góc nội tiếp chắn nửa đường tròn là góc vuông

Trong định lý góc nội tiếp chắn nửa đường tròn chúng ta có thể nói rằng góc đó nội tiếp trong nửa đường tròn. Góc nội tiếp chắn nửa đường tròn là góc vuông và ngược lại khi góc vuông nội tiếp thì chắn nửa đường tròn.
Khi một góc nằm trên một đường tròn, thì nó có đỉnh nằm bên trên đường tròn

Góc tạo bởi tiếp tuyến và dây cung
__Định lý góc tạo bởi tiếp tuyến và dây cung__ 
Số đo của góc hợp bởi tia tiếp tuyến và dây cung thì bằng nửa số đo cung bị chắn.

Từ Định lý góc tạo bởi tiếp tuyến và dây cung, chúng ta biết rằng có 2 loại góc có số đo bằng nửa dây cung bị chắn: góc nội tiếp và góc tạo bởi tiếp tuyến và dây cung.

Một góc được coi là nằm trong đường tròn khi đỉnh của nó nằm đâu đó trong đường tròn, nhưng không phải ở tâm. Tất cả các góc như vậy đều bị chắn bởi 2 dây cung.

__Định lý góc tạo bởi hai dây cung__
Số đo của góc có đỉnh nằm trong đường tròn bằng nửa tổng số đo 2 cung bị chắn.

Một góc được coi là nằm ngoài đường tròn nếu đỉnh của góc nằm ngoài đường tròn và các cạnh là tiếp tuyến hoặc cát tuyến. Có ba loại góc nằm ngoài một đường tròn: một góc tạo bởi hai tiếp tuyến, một góc tạo bởi một tiếp tuyến và một cát tuyến, và một góc tạo bởi hai cát tuyến. Cũng giống như góc bên trong hoặc trên một đường tròn, một góc bên ngoài một đường tròn cũng có công thức cụ thể, liên quan đến các cung bị chắn.

__Định lý về góc có đỉnh nằm ngoài đường tròn__
Góc tạo bởi 2 cát tuyến, 2 tiếp tuyến, hoặc 1 tiếp tuyến và 1 cát tuyến có đỉnh nằm bên ngoài đường tròn có số đo bằng nửa hiệu số đo 2 cung bị chắn.

Khi hai dây cung cắt nhau bên trong đường tròn, chúng tạo ra 2 tam giác đồng dạng, các cạnh của tam giác này tỉ lệ với các cạnh tương ứng của tam giác kia. Nếu chúng ta bỏ AD và BC thì tỉ số giữa AE, EC, DE và EB sẽ không đổi.

__Định lý các dây cung cắt nhau__

Nếu hai dây cung cắt nhau nằm trong đường tròn thì nó chia dây cung thành các đoạn có độ dài a, b và c, d và ab=cd. Nói cách khác, tích của hai dây cung thứ nhất bằng tích hai dây cung thứ hai. 
Ngoài việc tạo thành một góc bên ngoài đường tròn, đường tròn có thể chia đường cát tuyến thành các đoạn tỷ lệ với nhau.

Nếu chúng ta vẽ hai cung cắt nhau, ta sẽ được hai tam giác đồng dạng

Từ các góc nội tiếp và các góc tương ứng (∠R≅∠R),△PRS∼△TRQ. Vì hai tam giác đồng dạng, ta có tỉ lệ tương ứng giữa các cạnh. Sau đó, ta nhân chéo ac+d=ca+b⇒a(a+b)=c(c+d)

__Hai đường cát tuyến cắt nhau__
Nếu hai cát tuyến cắt nhau tại một điểm nằm ngoài đường tròn như hình bên, khi đó a(a+b)=c(c+d). Nói cách khác, tích của phần bên ngoài đoạn dây với toàn đoạn dây này bằng tích của phần bên ngoài đoạn dây với toàn đoạn dây kia.

Nếu một tiếp tuyến và cát tuyến cắt nhau tại một điểm nằm ngoài đường tròn. Các đoạn tạo ra có mối quan hệ tương tự như của hai tia tiếp tuyến. Chúng ta hãy nhớ lại tích của phần bên ngoài đoạn dây với toàn đoạn dây này bằng tích của phần bên ngoài đoạn dây với toàn đoạn dây kia .Nếu một trong những đoạn này là tiếp tuyến, nó sẽ vẫn là tích của phần bên ngoài và toàn bộ đoạn dây. Tuy nhiên, đối với một đường tiếp tuyến, phần bên ngoài và phần toàn bộ bằng nhau.

__Định lý tiếp tuyến - cát tuyến__
Nếu tiếp tuyến và cát tuyến được vẽ từ một điểm chung bên ngoài đường tròn (và các đoạn được đánh dấu như hình bên trái) thì a2 = b (b + c). Điều này có nghĩa là tích của đoạn bên ngoài của đường với toàn bộ đường cát tuyến bằng bình phương của đoạn tiếp tuyến.
---

### Định lý Thales

Chứng minh bằng cách sử dụng tam giác cân

Kết hợp tất cả Hình học Euclid

{.todo} TODO



--------------------------------------------------------------------------------



## Đa giác nội tiếp 
> sectionStatus: dev
> section: cyclic-polygons

__[CC] Dựng hình tam giác đều, hình vuông và hình lục giác đều nội tiếp đường tròn.__
Một đa giác nội tiếp là một đa giác mà mọi đỉnh đều nằm trên một đường tròn. Lưu ý rằng không phải mọi tứ giác hoặc đa giác đều có thể nội tiếp được trong một đường tròn. Tứ giác nội tiếp còn được gọi là tứ giác tuần hoàn. Đối với các loại tứ giác này, chúng có những tính chất riêng biệt. Chúng ta sẽ được tìm hiểu kĩ hơn trong phần này.

Những thử nghiệm cho thấy rằng các góc đối trong tứ giác nội tiếp bù nhau. Bằng cách cắt chéo nửa hình tứ giác, chúng ta có thể chứng minh rằng hai góc còn lại (mà chúng ta không cắt qua) tạo thành một cặp đường thẳng khi ghép lại với nhau.

Định lý Tứ giác nội tiếp: Một tứ giác nội tiếp được trong đường tròn khi và chỉ khi hai góc đối bù nhau.
https://www.youtube.com/watch?v=bJOuzqu3MUQ



--------------------------------------------------------------------------------



## Hình cầu, Hình nón và Hình trụ
> section: spheres-cones-cylinders
> id: solids

Ở các phần trước, chúng ta đã nghiên cứu tính chất của đường tròn trên mặt phẳng. Nhưng thế giới của chúng ta thực chất là không gian ba chiều, vì vậy chúng ta hãy tìm hiểu một số khối 3D dựa trên các đường tròn:
::: column(width=220 parent="padded-thin")

    x-solid(size=220)

{.text-center} A [__cylinder__](gloss:cylinder) Hình trụ tròn bao gồm hai đường tròn bằng nhau, song song và được nối với nhau bởi một mặt cong.
::: column(width=220)

    x-solid(size=220)

{.text-center} A [__cone__](gloss:cone) Hình nón có đáy là hình tròn được nối với một điểm duy nhất (gọi là đỉnh).
::: column(width=220)

    x-solid(size=220 static)

Mỗi điểm trên mặt cầu [__sphere__](gloss:sphere) đều cách đều tâm
:::

Chú ý rằng định nghĩa của một hình cầu gần giống như định nghĩa của [[circle|radius|cube]] - nhưng là ở không gian ba chiều!
---
> id: gasometer

### Hình trụ tròn
::: column.grow

Trong ảnh là ống đựng khí hình trụ Gasometer ở Oberhausen, Đức. Nó được sử dụng để lưu trữ khí đốt tự nhiên được sử dụng làm nhiên liệu trong các nhà máy và nhà máy điện gần đó. Gasometer cao 120m, đế và trần của nó là hai vòng tròn lớn có bán kính 35m. Có hai câu hỏi quan trọng mà các kỹ sư có thể muốn giải đáp:

* Ống có thể dự trữ được bao nhiêu lượng khí thiên nhiên? Đây là [[volume|area|diameter]] của ống hình trụ.
* {.reveal(when="blank-0")} Cần bao nhiêu thép để xây dựng được ống đựng Gasometer. Đây là ( gần đúng) [[surface area|circumference|diagonal]] của ống hình trụ.

{.reveal(when="blank-0 blank-1")} Hãy cùng khám phá câu trả lời của cả hai câu hỏi này nhé!
::: column(width=300)

    x-img(src="images/gasometer.jpg" width=300 height=400 lightbox)

{.caption} Gasometer Oberhausen

:::

---
> id: cylinder-prism

#### Thể tích của hình trụ

Trên và dưới của hình trụ tròn là hai đường tròn bằng nhau, được gọi là đáy. Chiều cao h  __{.m-blue} height *h*__ của hình trụ tròn là khoảng cách của hai đáy theo phương thẳng đứng, và bán kính r __{.m-red} radius *r*__ của hình trụ là bán kính của đường tròn đáy.

Chúng ta có thể cơ bản tạo một hình trụ tròn bằng tăng ${n}{n|5|3,20,1}-sided
[__prism__](gloss:prism) mặt. Khi số mặt tăng lên, hình lăng trụ sẽ càng ngày càng giống hình trụ tròn:
::: column(width=240)

    x-solid(size=240)

::: column(width=240)

    x-solid(size=240)

:::

---
> id: cylinder-volume

Mặc dù một hình trụ nói chính xác thì không phải là một hình lăng trụ, nhưng chúng có nhiều tính chất giống nhau. Trong cả hai trường hợp, chúng ta có thể tìm thể tích bằng cách nhân diện tích đáy__{.m-red} base__ with their __{.m-blue} height__ với chiều cao của chúng.

{.text-center} `V =` _{x-equation(solution="π r^2 h" keys="+ − × ÷ π frac sup brackets" short-var hints="cylinder-volume-hint1 cylinder-volume-hint2")}_

{.reveal(when="eqn-0")} Remember that radius and height must use the same units.
For example, if _r_ and _h_ are both in cm, then the volume will be in
[[`"cm"^3`|`"cm"^2`|cm]].

---
> id: oblique-cylinder
> goals: slide

::: column.grow

Trong các ví dụ trên, hai đáy của hình trụ luôn nằm đối diện theo phương thẳng đứng: đây được gọi là hình trụ tròn phẳng. Nếu các đáy không nằm đối diện theo phương thẳng đứng, chúng ta có một hình trụ xiên. Hai đáy vẫn song song, nhưng các cạnh sẽ nghiêng một góc khác 90°.
    x-solid(size="300,200" static)
    x-gesture(target="#oblique-cylinder x-solid" slide="40,0")

::: column(width=300)

    x-img(src="images/pisa.jpg" width=300 height=360 lightbox)

{.caption} The _Leaning Tower of Pisa_ in Italy is not quite an oblique
cylinder.

:::

---
> id: cavalieri
> goals: slide

The volume of an oblique cylinder turns out to be exactly the same as that of a
right cylinder with the same radius and height. This is due to [__Cavalieri’s
Principle__](gloss:cavalieri), named after the Italian mathematician
[Bonaventura Cavalieri](bio:cavalieri): if two solids have the same
cross-sectional area at every height, then they will have the same volume.
Thể tích của hình trụ tròn phẳng hoàn toàn bằng thể tích hình trụ xiên có cùng bán kính và chiều cao. Điều này có được là do nguyên lý Cavalieri [__Cavalieri’s Principle__](gloss:cavalieri), được đặt tên theo một nhà toán học người Ý [Bonaventura Cavalieri](bio:cavalieri): Nếu hai hình khối có thể đặt sao cho với mọi mặt phẳng song song với một mặt cho trước, thiết diện của các hình khối cắt bởi các mặt phẳng này là tương đương, thì thể tích các hình khối này bằng nhau.

Hãy tưởng tượng cắt một hình trụ thành nhiều đĩa mỏng. Sau đó, chúng ta trượt các đĩa này theo chiều ngang để có được một hình trụ xiên. Thể tích của các đĩa riêng lẻ không thay đổi khi bạn làm cho nó xiên, do đó tổng thể tích cũng không đổi:
::: column(width=240)

    x-solid(size=280 style="margin: -20px")

::: column(width=240)

    x-solid.slide-me(size=280 static style="margin: -20px")
    x-gesture(target=".slide-me" slide="60,0")

:::

    // TODO You must always use the _perpendicular_ height. This is
    // the vertical line to left in the figure above.

    // TODO Volume of horizontal cylinder segments
    // https://www.mathopenref.com/cylindervolpartial.html

---
> id: cylinder-surface

#### Diện tích bề mặt của hình trụ 

::: column.grow

Để tìm diện tích của hình trụ, chúng ta phải “trải” nó trong mặt phẳng [net](gloss:net). Bạn có thể tự mình thử cách này chẳng hạn như bóc nhãn dãn trên một cái lon đựng đồ ăn.

Có hai [[circles|spheres|squares]], một là ở trên và một ở đáy của hình trụ tròn. Mặt cong thực chất là hình [[rectangle|square|ellipse]] lớn. 
* {.reveal(when="blank-0 blank-1")} Hai hình tròn có diện tích _{x-equation.small(solution="π r^2" keys="+ × π sup" short-var)}_.

* {.reveal(when="eqn-0")} Chiều cao của hình chữ nhật là _{x-equation.small(solution="h" keys=" " short-var)}_.
  _{span.reveal(when="eqn-1")} và chiều rộng của hình chữ nhật bằng với [[circumference|diameter|tangent]] của hình tròn: _
  _{x-equation.small.reveal(when="blank-2" solution="2 π r" keys="+ × π sup" short-var)}_.

::: column(width=320)

    x-solid(size=340 style="margin: -10px;")
    x-slider(steps=100 speed=0.5)

:::

---
> id: cylinder-surface-1

Điều này có nghĩa là tổng diện tích bề mặt của hình trụ tròn với bán kính r và chiều cao h là:
{.text-center} `A =` _{x-equation(solution="2 π r^2 + 2 π r h" keys="+ − × ÷ π frac sup brackets" short-var)}_.

---
> id: cylinder-real-life

    figure: x-img(src="images/cylinders.jpg" width=460 height=125)

Chúng ta có thể tìm thấy hình trụ tròn ở khắp mọi nơi trên thế giới - từ lon coca đến lõi giấy vệ sinh hoặc đường ống nước. Bạn còn nghĩ ra được những ví dụ nào không ?
Ống hình trụ Gasometer có bán kính 35m và cao 120m. Giờ đây chúng ta có thể tính toán thể tích của nó khoảng [[461,000 ± 1000]] `" m "^ 3` và diện tích bề mặt của nó là khoảng [[34,080 ± 100]]` "m" ^ 2`.
---
> id: cone

### Hình nón

::: column.grow

Hình nón [__cone__](gloss:cone) là một khối không gian ba chiều có đáy là hình tròn __{.m-red}base__.Mặt của nó “thuôn nhọn lên trên” như trong hình và đi qua một điểm duy nhất được gọi là đỉnh __ {. M-green} __.


Bán kính của hình nón là bán kính của đáy hình tròn và  chiều cao của hình nón là khoảng cách vuông góc từ mặt đáy đến đỉnh.
Cũng giống như các hình khối khác mà chúng ta đã gặp trước đó, hình nón có ở khắp mọi nơi xung quanh chúng ta: vỏ kem ốc quế, chóp nón giao thông, một số mái nhà và thậm chí cả cây thông Noel. Bạn có nghĩ đến những đồ vật nào nữa không?

::: column(width=280)

    x-solid(size=280)

:::

::: column(width=120 parent="padded-thin")

    x-img(src="images/ice-cream.jpg" width=120 height=120 lightbox)

::: column(width=120 parent="padded-thin")

    x-img(src="images/traffic.jpg" width=120 height=120 lightbox)

::: column(width=120 parent="padded-thin")

    x-img(src="images/roof.jpg" width=120 height=120 lightbox)

::: column(width=120 parent="padded-thin")

    x-img(src="images/christmas.jpg" width=120 height=120 lightbox)

::: column(width=120 parent="padded-thin")

    x-img(src="images/tipi.jpg" width=120 height=120 lightbox)

:::

---
> id: cone-volume

#### Thể tích hình nón

::: column.grow


Trước đó, chúng ta đã tính được thể tích gần đúng của hình trụ tròn bằng bằng khối lăng trụ. Tương tự, chúng ta có thể tìm thể tích gần đúng của hình nón bằng kim tự tháp [__pyramid__](gloss:pyramid)..

Bạn có thể nhìn thấy ở đây có  ${n}{n|5|3,18,1} mặt kim tự tháp. Khi số mặt tăng lên, kim tự tháp sẽ càng lúc càng giống hình nón. Thực tế, chúng ta có thể coi hình nón là một kim tự tháp có vô số mặt!
::: column(width=280)

    x-solid(size=280 style="margin: -44px 0 -20px 0")

:::

---
> id: cone-volume-1


Như vậy, chúng ta cũng có thể sử dụng công thức thể tích đã có: V=⅓ đáy×chiều cao. Đáy của hình nón là hình tròn, vì vậy thể tích của hình nón với bán kính r và chiều cao h là
{.text-center} `V =` _{x-equation(solution="1/3 π × r^2 h" keys="+ − × ÷ π frac sup brackets" short-var hints="cone-volume-hint1 cone-volume-hint2")}_

---
> id: cone-circumscribed


Lưu ý sự tương tự với phương trình thể tích của một hình trụ. Hãy tưởng tượng bạn vẽ một hình trụ xung quanh hình nón, có cùng đáy và chiều cao - ta sẽ có hình gọi là hình trụ nội tiếp. Bây giờ, hình nón sẽ chiếm đúng [[onethird|half|one quarter]] thể tích của hình trụ.
    figure: x-solid(size=280)

---
> id: cone-hilbert


{.i.lgrey}  Chú ý: có thể bạn nghĩ rằng vô số những mặt tí hon với số đo gần đúng sẽ làm kết quả không chính xác. Các nhà toán học đã dành một thời gian dài để cố gắng tìm ra một cách đơn giản hơn để tính thể tích của một hình nón. Vào năm 1900, nhà toán học vĩ đại [David Hilbert](bio:hilbert) thậm chí còn đặt tên nó là một trong 23 vấn đề chưa giải được quan trọng nhất trong toán học! Hôm nay chúng ta biết rằng điều đó thực sự là không thể.

---
> id: oblique-cone
> goals: slide

::: column.grow


Cũng giống như hình trụ, hình nón không nhất thiết phải "thẳng". Nếu đỉnh nằm ngay trên tâm của đáy, chúng ta có một hình nón phẳng. Nếu không thẳng, chúng ta gọi nó là hình nón xiên.

Một lần nữa, chúng ta có thể sử dụng nguyên lý của Cavalieri để chỉ ra rằng tất cả các hình nón xiên đều có cùng thể tích, miễn là chúng có cùng đáy và chiều cao.
::: column(width=280)

    x-solid(size="280,240" static)
    x-gesture(target="#oblique-cone x-solid" slide="60,0")

:::

---
> id: cone-surface

#### Diện tích bề mặt của hình nón

::: column.grow

Finding the surface area of a cone is a bit more tricky. Like before, we can
unravel a cone into its net. Move the slider to see what happens: in this
case, we get one circle and one [[circle sector|circle segment|circle arc]].
Tìm diện tích bề mặt của một hình nón khó hơn một chút. Giống như trước đây, chúng ta có thể tháo một hình nón vào lưới của nó. Di chuyển thanh trượt để xem điều gì xảy ra: trong trường hợp này, chúng ta nhận được một hình tròn và một {.reveal(when="blank-0")}.

Bây giờ chúng ta chỉ cần thêm diện tích của cả hai thành phần này. Đáy  __{.m-yellow}base__  là một hình tròn với bán kính r, vì vậy diện tích sẽ là {.text-center.reveal(when="blank-0")} `pill(A_"Base","yellow","circle") =`
_{x-equation.small(solution="π r^2" keys="+ × π sup" short-var)}_.
::: column(width=320)

    x-solid(size=340 style="margin: -32px -10px -10px;")
    x-slider(steps=100 speed=0.5)

:::

---
> id: slant-height

::: column.grow

Bán kính của __ {. M-green} sector__ bằng với khoảng cách từ vành của một hình nón đến đỉnh của nó. Đây được gọi là độ dài cạnh bên [{.green.b} slant height *s*](target:s) của hình nón và không giống với đường cao[{.blue.b} height * h *] (target: h) thông thường . Chúng ta có thể tìm  độ dài cạnh bên bằng cách sử dụng định ly Pi-ta-go[Pythagoras](gloss:pythagoras-theorem):
| `s^2` | `=` | _{x-equation(solution="r^2 + h^2" keys="+ × π sup")}_       |
| `s`   | `=` | _{x-equation(solution="sqrt(r^2 + h^2)" keys="+ × sup sqrt")}_ |
{.eqn-system}

::: column(width=280)

    x-geopad.geo-sketch.no-background(width=280 height=200): svg
      circle(x="point(140, 10)" name="a" hidden)
      circle(x="point(140, 170)" name="b" hidden)
      circle(x="point(220, 170)" name="c" hidden)
      circle(x="point(60, 170)" name="d" hidden)
      ellipse(cx=140 cy=172 rx=81 ry=20)
      path(x="angle(a,b,c)" size=12)
      path(x="triangle(a,c,d)")
      path.yellow(x="segment(b,c)" label="r" target="r")
      path.green(x="segment(a,c)" label="s" target="s")
      path.blue(x="segment(a,b)" label="h" target="h")

:::

---
> id: cone-surface-1

::: column.grow

Cung tròn [{.red} arc length](target:arc) của hình quạt giống với [[circumference|diameter|arc]] của đáy [{.yellow}base](target:base):_{span.reveal(when="blank-0")}`2 π r`. Bây giờ chúng ta có thể tìm diện tích bằng cách sử dụng công thức [formula](gloss:circle-sector) mà chúng ta đã suy ra trong phần trước: _
::: x-equation-system.reveal(when="blank-0" steps="π s^2 * ( 2 π r ) / (2 π s) | π r s" hints="cone-surface-1|cone-surface-1")
| `pill(A_"Sector","green","sector")` | `=` | `pill(A_"Circle","teal","circle") × pill("arc","red","arc") / pill("circumference","teal","circumference")` |
|                | `=` | _{x-equation(solution="π r sqrt(r^2 + h^2)" fns="/" substitutions="s: sqrt(r^2 + h^2)" keys="+ − × ÷ π frac sup sqrt" short-var)}_ |
:::

::: column(width=280)

    x-geopad.geo-sketch.no-background(width=280 height=300 style="margin-top: -20px"): svg
      circle(x="point(140,110)" name="c1" hidden)
      circle(x="point(140,250)" name="c2" hidden)
      circle(x="point(235,141.5)" name="a" hidden)
      circle(x="point(45,141.5)" name="b" hidden)

      path.yellow.fill.light(x="circle(c2, 40)" target="base")
      path.yellow(x="circle(c2, 40)" target="base")
      path.yellow(x="segment(c2,point(180, 250))" label="r" target="base")
      path.red.thick.reveal(when="blank-0" animation="draw" duration=1500 x="circle(c2, 40)")

      path.teal.fill.light(x="circle(c1, 100)" name="circ" target="circle")
      path.green.fill.light(x="sector(c1, a, 2.5)" target="sector circle")

      path.green(x="segment(c1, a)" label="s")
      path.green(x="segment(c1, b)" label="s")
      path.red.thick(x="arc(c1, a, 2.5)" target="arc")
      path.teal.thick.transparent(x="circle(c1, 100)" target="circumference")

:::

---
> id: cone-surface-2

Cuối cùng, chúng ta chỉ cần cộng diện tích của đáy __{.m-yellow}base__  và diện tích xung quanh __{.m-green}sector__ để có được tổng diện tích của hình nón:
{.text-center} `A =` _{x-equation(solution="π r^2 + π r sqrt(h^2 + r^2)" keys="+ − × ÷ π frac sup sqrt" short-var)}_

---
> id: sphere

### Hình cầu

::: column.grow


Hình cầu [__sphere__](gloss:sphere) là một khối ba chiều bao gồm tất cả các điểm có cùng khoảng cách từ tâm C __{.m-green}center *C*__. Khoảng cách này gọi là bán kính r __{.m-red}radius *r*__ của hình cầu.

Bạn có thể coi hình cầu là “hình tròn ba chiều”[circle](gloss:circle). Giống như một hình tròn, hình cầu cũng có đường kính d __{.m-blue}diameter *d*__ có chiều dài bằng [[twice|half]]  bán kính cũng như các dây cung và cát tuyến. 
::: column(width=240)

    x-solid(size=240)

:::

---
> id: sphere-1

{.r}Trong các phần trước [previous section](/course/circles/tangets-chords-arcs#eratosthenes-1), chúng ta đã biết cách nhà toán học Hy Lạp  [Eratosthenes](bio:eratosthenes) tính toán bán kính của Trái Đất bằng cách sử dụng bóng của các vật cao - 6,371 km. Bây giờ, hãy thử tìm tổng thể tích và diện tích bề mặt của Trái đất. [Continue](btn:next)
---
> id: sphere-volume

#### Thể tích của một hình cầu

Để tính thể tích của một hình cầu, một lần nữa chúng ta phải sử dụng nguyên lí của Cavalieri. Hãy bắt đầu từ nửa bán cầu - một hình cầu bị cắt làm đôi dọc theo đường xích đạo. Chúng ta cần một hình trụ tròn cùng bán kính và chiều cao với bán cầu, nhưng có một hình nón ngược "cắt ra" ở giữa.

Khi bạn di chuyển thanh trượt bên dưới, bạn có thể thấy mặt cắt của cả hai hình này ở độ cao cụ thể phía trên phần đáy:
::: column(width=240)

    x-solid(size=240 style="margin: -24px 0 10px")

    x-geopad.r.no-background(width=220 height=120): svg
      circle(x="point(110,110)" name="c1")
      circle(x="c1.shift(0,-100*h)" name="h1")
      circle(x="h1.shift(-100 * sqrt(1-h*h),0)" name="a1")

      path.yellow.fill.light(x="triangle(c1,a1,h1)" target="tri")
      path(x="arc(c1,point(10,c1.x),pi)")
      path(x="segment(point(10,c1.x),point(210,c1.x))")
      path.green.thin(x="segment(c1,a1)" label="r" target="r tri")
      path.blue.thin(x="segment(h1,c1)" label="h" target="h h1 tri")
      path.red.thick(x="segment(h1,a1)" label="x" target="x tri")
      path.red.thick(x="segment(h1,point(220-a1.x,a1.y))")

::: column(width=240)

    x-solid(size=240 style="margin: -24px 0 10px")

    x-geopad.r.no-background(width=220 height=120): svg
      circle(x="point(10,10)" name="a2" hidden)
      circle(x="point(210,10)" name="b2" hidden)
      path(x="polygon(a2,b2,point(210,110),point(10,110))")

      circle(x="point(110,110)" name="c2")
      circle(x="c2.shift(0,-100*h)" name="h2")
      circle(x="h2.shift(-100*h,0)" name="x2")

      path.thin(x="segment(a2,c2)")
      path.thin(x="segment(b2,c2)")
      path.blue.thin(x="segment(h1,c1)" label="h" target="h")
      path.blue.thin(x="segment(h1,point(110-100*h,h2.y))")
      path.red.thick(x="segment(point(10,h2.y),point(110-100*h,h2.y))")
      path.red.thick(x="segment(point(110+100*h,h2.y),point(210,h2.y))")

:::

    x-slider(steps=100)



{.reveal(when="slider-0")}  Chúng ta hãy thử tìm diện tích mặt cắt ngang của cả hai khối này, ở khoảng cách [{.blue} height * h *] (target: h) phía trên đáy.
::: column.grow


{.reveal(when="slider-0")} Mặt cắt của bán cầu luôn là [[circle|ring|cylinder]].

{.reveal(when="blank-0")} The [{.red} radius *x*](target:x) of the cross-section is part of a
[{.yellow} right-angled triangle](target:tri), so we can use
[Pythagoras](gloss:pythagoras-theorem):
{.reveal(when="blank-0")} Bán kính [{.red} radius *x*](target:x) của mặt cắt ngang là một phần của tam giác vuông [{.yellow} right-angled triangle](target:tri), vì vậy chúng ta có thể sử dụng định lý Pi-ta-go [Pythagoras](gloss:pythagoras-theorem):
::: .reveal(when="blank-0")
{.text-center} `pill(r^2,"green","r") = pill(h^2,"blue","h1") + pill(x^2,"red","x")`.

Bây giờ, diện tích của mặt cắt ngang là
    x-equation-system(steps="π x^2" hints="circle-cross-sec")
      table: tr
        td: em A
        td =
        td: x-equation(solution="π * (r^2 - h^2)" substitutions="x: sqrt(r^2 - h^2)" fns="sqrt" keys="+ − × ÷ π sup sqrt brackets" short-var)
:::

::: column.grow.reveal(when="eqn-0")

Thiết diện của hình trụ bị cắt luôn là [[ring|circle|cone]].
::: .reveal(when="blank-1")

Bán kính của hình tròn nhỏ là h. Chúng ta có thể tìm diện tích của chiếc vòng tròn bằng cách lấy diện tích của hình tròn lớn hơn trừ đi diện tích của hình tròn nhỏ :
| _A_ | = | `π r^2 - π h^2` |
|     | = | `π (r^2 - h^2)` |
{.eqn-system}
:::

:::

---
> id: sphere-volume-1

Dường như hai khối hình đều có cùng diện tích mặt cắt ngang ở mọi mức độ. Theo nguyên lý Cavalieri, cả hai khối cũng phải có cùng [[volume|surface
area|circumference]]! _{span.reveal(when="blank-0")}.  Chúng ta có thể tìm thể tích của bán cầu bằng cách trừ thể tích của hình trụ [cylinder](gloss:cylinder-volume) và thể tích của hình nón [[cone](gloss:cone-volume):_
::: x-equation-system.reveal(when="blank-0" steps="π r^3 - 1/3 π r^3" hints="sphere-volume")
| `V_"Hemisphere"` | = | `V_"Cylinder" - V_"Cone"` |
|                  | = | _{x-equation(solution="2/3 π r^3" keys="+ − × ÷ π frac sup brackets" short-var)}_ |
:::

---
> id: sphere-volume-2


Hình cầu bao gồm hai bán cầu, _{span.reveal(when="blank-0")} điều đó có nghĩa thể tích của nó phải là _
{.text-center.reveal(when="blank-0")} `V = 4/3 π r^3`.

---
> id: earth-volume
> goals: numbers

::: column.grow

Trái đất là một hình cầu có bán kính (xấp xỉ)  6.371 \ km. Do đó thể tích của nó là: 
| `V` | `=` | _{x-equation(solution="4/3 pi × 6371^3" keys="+ − × ÷ π frac sup sqrt" short-var)}_ |
|     | `=` | _{span.numbers}1_ `"km"^3` |
{.eqn-system}


{.reveal(when="numbers")} Mật độ trung bình của Trái đất là `5510" kg / m "^ 3`.
Điều này có nghĩa là tổng khối lượng của nó là

{.text-center.reveal(when="numbers")} `"Mass" = "Volume" × "Density" ≈ 6 × 10^24 "kg"`

{.reveal(when="numbers")} Đó là số 6 theo sau bởi 24 chữ số 0

::: column(width=280)

    x-solid(size=280 rotate="0.5")

:::

---
> id: sphere-sum

Nếu bạn so sánh các phương trình về thể tích của một hình trụ tròn, hình nón và hình cầu, bạn có thể nhận thấy đây là một trong những mối quan hệ làm ta thỏa mãn nhất trong hình học. Hãy tưởng tượng chúng ta có một hình trụ có cùng chiều cao với đường kính đáy của nó. Bây giờ chúng ta có thể lắp cả hình nón và hình cầu một cách hoàn hảo vào bên trong của nó:
::: column.r(width=220)

    x-solid(size=220 style="margin-top: -20px")
    .large-op.reveal(when="blank-0" animation="pop") +

{.text-center} This cone has radius `r` and height `2r`. Its volume is
_{x-equation.small(solution="2/3 π r^3" keys="× π sup frac" short-var)}_

::: column.r(width=220)

    x-solid(size=220 style="margin-top: -20px")
    .large-op.reveal(when="blank-0" animation="pop") =

{.text-center} This sphere has radius `r`. Its volume is
_{x-equation.small(solution="4/3 π r^3" keys="× π sup frac" short-var)}_

::: column(width=220)

    x-solid(size=220 style="margin-top: -20px")

{.text-center} This cylinder has radius `r` and height `2r`. Its volume is
_{x-equation.small(solution="2 π r^3" keys="× π sup frac" short-var)}_

:::

{.reveal(when="eqn-0 eqn-1 eqn-2")} Chú ý, nếu chúng ta [[add up|subtract|multiply]] thể tích của hình nón và hình cầu, chúng ta được chính xác thể tích của hình trụ!
---
> id: sphere-maps
> goals: move projection

#### Diện tích bề mặt của một hình cầu

Tìm công thức diện tích mặt cầu rất khó. Lý do là chúng ta không thể mở và "làm phẳng" bề mặt của một hình cầu, giống như chúng ta đã làm đối với hình nón và hình trụ trước đây.

Đây là một vấn đề điển hình khi con người cố gắng tạo ra bản đồ. Trái đất có bề mặt cong, ba chiều, nhưng mọi bản đồ được in ra phải phẳng và hai chiều. Điều này có nghĩa là các Nhà địa lý phải ăn gian: bằng cách kéo căng hoặc thu nhỏ các khu vực nhất định.

Ở đây bạn có thể thấy một số loại bản đồ khác nhau, được gọi là __projutions__. Hãy thử di chuyển hình vuông màu đỏ và xem khu vực này trông như thế nào trên hình ảnh địa cầu:
    figure
      x-select.tabs
        .projection(data-name="mercator") Mercator
        .projection(data-name="cylindrical") Cylindrical
        .projection(data-name="robinson") Robinson
        .projection(data-name="mollweide") Mollweide
      .box.no-padding.sphere-maps
        .left
          svg.sphere-map(width=240 height=240 viewBox="0 0 240 280")
            path.outline
            path.grid
            path.land
            path.map-select
        .right
          svg.sphere-map#projection(width=440 height=280 viewBox="0 0 440 280")
            path.outline
            path.grid
            path.land
            rect.map-select(x="-24" y="-24" width=48 height=48 style="cursor: move")
          p.caption As you move the square on the map, notice how the size and shape of the #[em actual] area changes on the three-dimensional globe.
    x-gesture(target="#projection" slide="50, 20")

---
> id: sphere-surface

Để tìm diện tích bề mặt của một hình cầu, một lần nữa chúng ta có thể tính gần đúng nó bằng cách sử dụng một hình khác - ví dụ như một hình đa diện có nhiều mặt. Khi số lượng mặt tăng lên, hình đa diện bắt đầu giống hình cầu hơn.
{.todo} COMING SOON: Sphere Surface Area Proof

    // Nếu chúng ta nối các đa giác nhỏ với tâm của hình cầu, chúng ta sẽ có rất nhiều hình chóp nhỏ hướng vào trong. Sơ đồ cho thấy một trong những kim tự tháp này có màu đỏ. Chiều cao của mỗi hình chóp là [[radius|diameter]] của hình cầu.
    // Chúng ta có: thể tích = rất nhiều hình nón = 1/3 * bán kính * nhiều đáy= 1/3 * bán kính * diện tích bề mặt

    //  Và do đó, diện tích bề mặt = 3 * thể tích / bán kính =

    // Nói cách khác, diện tích bề mặt của một hình cầu có bán kính r là `S = 4 π r^2`.
    // ---

    // > id: earth-surface
    //
    // surface of earth



--------------------------------------------------------------------------------



## Đường Conic
> section: conic-sections
> id: conics
> goals: ellipse parabola hyperbola

Hình tròn là một trong bốn hình khối khác nhau có thể được tạo ra bằng cách sử dụng các “lát cắt” thông qua một hình nón [cone](gloss:cone). Điều này có thể được chứng minh bằng cách sử dụng ánh sáng hình nón của một ngọn đuốc:
    x-conic-section
    x-scale-box(width=760).conics
      .row
        .active
          p.no-voice: strong Circle
          include svg/circle.svg
        .hide
          p.no-voice: strong Ellipse
          include svg/ellipse.svg
        .hide
          p.no-voice: strong Parabola
          include svg/parabola.svg
        .hide
          p.no-voice: strong Hyperbola
          include svg/hyperbola.svg

---
> id: conics-1

Nếu bạn hướng ngọn đuốc theo chiều dọc xuống dưới, bạn sẽ thấy ánh sáng hình [[circle|ellipse|oval]].  _{span.reveal(when="blank-0")} Nếu bạn nghiêng hình nón, bạn sẽ nhìn thấy hình [__ellipse__](gloss:ellipse). Nếu bạn nghiêng nó hơn nữa, bạn sẽ có hình [__parabola__](gloss:parabola) hoặc là  [__hyperbola__](gloss:hyperbola)._
> id: conics-2

::: column.grow

Tựu chung lại, bốn hình dạng này được gọi là phần conic [__conic sections__](gloss:conic-section).
Mặc dù tất cả chúng trông rất khác nhau, nhưng chúng có liên quan chặt chẽ với nhau: trên thực tế, tất cả chúng đều có thể được tạo ra bằng cách sử dụng cùng một phương trình!
 
Các phần conic lần đầu tiên được nghiên cứu bởi nhà toán học Hy Lạp cổ đại [Apollonius
of Perga](bio:apollonius), người đặt cho chúng những cái tên độc đáo.

Trong các khóa học sau này, bạn sẽ học thêm nhiều điều về parabol và hyperbol. Bây giờ, chúng ta hãy xem tìm hiểu kĩ hơn hình elip.
::: column(width=300)

    x-img(src="images/conics.svg" width=300 height=340)

:::

---
> id: ellipses

### Hình Elip

Một hình elip trông gần giống như một "hình tròn thuôn dài". Trên thực tế, bạn có thể coi nó như một vòng tròn có hai tâm - chúng được gọi là tiêu điểm.  Với mọi điểm trên đường cong, tổng khoảng cách đến hai tiêu điểm là hằng số.

Nếu bạn có một sợi dây được nối bằng hai điểm cố định, bạn có thể vẽ một hình elip hoàn hảo bằng cách vẽ đường tròn theo độ dài tối đa của sợi dây.
    p.todo Coming soon: Ellipses drawing interactive
    //- figure: x-ellipse
      x-geopad(width=600 height=400 x-axis="-6,6,1" y-axis="-4,4,1"): svg.r
        circle.move(name="a" x="point(-2,0)" project="segment(point(-4,0),point(-0.5,0))")
        circle.move(name="b" x="point(2,0)" project="segment(point(0.5,0),point(4,0))")

    // Bạn cũng có thể di chuyển các tiêu điểm xung quanh. Lưu ý rằng, nếu chúng càng xa nhau, thì hình elip sẽ [[more | less]] dài ra. Nếu chúng ở gần nhau, nó sẽ gần giống như một  [[circle|parabola|trapezium]].

---
> id: ellipses-2
> goals: v0 v1 v2 v3

Có nhiều cách khác nhau để bạn có thể vẽ một hình elip:
::: column(width=320 parent="padded-thin")

    x-video(src="images/gears.mp4" poster="images/gears.jpg" width=320 height=230 credit="© Pavel Boytchev, Elica Logo")
    p.caption Gears

::: column(width=320)

    x-video(src="images/trammel.mp4" poster="images/trammel.jpg" width=320 height=230 credit="© Pavel Boytchev, Elica Logo")
    p.caption Trammel

::: column(width=320)

    x-video(src="images/disk.mp4" poster="images/disk.jpg" width=320 height=230 credit="© Pavel Boytchev, Elica Logo")
    p.caption Disk

::: column(width=320)

    x-video(src="images/swing.mp4" poster="images/swing.jpg" width=320 height=230 credit="© Pavel Boytchev, Elica Logo")
    p.caption Swing

:::

---
> id: orbits

### Quỹ đạo của các hành tinh
::: column.grow

Bạn có thể nhớ ngay từ đầu của khóa học này, các nhà thiên văn Hy Lạp cổ đại tin rằng Trái đất là trung tâm của vũ trụ và mặt trời, mặt trăng và các hành tinh chuyển động quanh Trái đất trên những quỹ đạo tròn.

Thật không may, những quan sát thiên văn trên bầu trời chúng ta đã có không hoàn toàn ủng hộ quan điểm này.
Ví dụ, mặt trời vào một số thời điểm trong năm sẽ rất lớn và có lúc lại rất nhỏ. Trên một đường tròn, mọi điểm phải có khoảng cách [[the same|an increasing|a
decreasing]] từ tâm của nó.

::: column(width=330)

    x-img(src="images/hipparchus.jpg" width=330 height=280 lightbox)

{.caption} Greek astronomer Hipparchus of Nicaea

:::

---
> id: epicycles
> goals: play

Để khắc phục điều này, các nhà thiên văn học đã thêm __Epicycles__ vào mô hình hệ mặt trời của họ: các hành tinh chuyển động trên một vòng tròn lớn quanh Trái đất, đồng thời quay trên một vòng tròn nhỏ hơn. Mặc dù rất phức tạp, nhưng đây là mô hình vũ trụ được chấp nhận rộng rãi nhất của chúng ta trong hơn 1000 năm:

::: column(width=320)

    .r
      svg(width=320 height=320)
        circle.large-circle(cx=160 cy=160 r=120 fill="none" stroke="#ccc" stroke-width="2px")
        circle.small-circle(cx=280 cy=160 r=30 fill="none" stroke="#ccc" stroke-width="2px")
        path(fill="none" stroke="#fd8c00" stroke-width="3px" opacity="0.8" stroke-linejoin="round")
        circle(cx=160 cy=160 r=15 fill="#0f82f2")
        circle.earth(cx=310 cy=160 r=10 fill="#fd8c00")
      x-play-btn

{.caption} Hành tinh này quay ${n}{n|6|2,12,1} vòng quanh một vòng tròn nhỏ (the __epicycle__) trong một lần quay quanh vòng tròn lớn (the__deferent__).
.
::: column(width=320)

    x-img(src="images/epicycles.jpg" width=320 height=320)

{.caption} Một bản vẽ ở thế kỷ 16 về các chu kỳ trong mô hình địa tâm__Geocentric model__. Từ “hành tinh” trong tiếng Hy Lạp có nghĩa là “những kẻ lang thang”.
:::

---
> id: kepler
> goals: play

::: column.grow

Theo thời gian, mọi người nhận ra rằng Trái đất chỉ là một trong nhiều hành tinh quay quanh mặt trời ( Thuyết Nhật tâm ), nhưng phải đến năm 1609, nhà thiên văn học Johannes Kepler mới phát hiện ra rằng các hành tinh thực sự chuyển động theo quỹ đạo hình elip.

Mặt trời nằm ở một trong hai tiêu điểm của các hình elip này. Các hành tinh tăng tốc khi chúng đến gần mặt trời và chậm lại khi chúng di chuyển ra xa hơn.
::: column(width=320)

    .r
      svg(width=320 height=240)
        path.sweep(fill="#0f82f2" opacity="0.25")
        path.orbit(fill="none" stroke="#ccc" stroke-width="3px" opacity="0.8" stroke-linejoin="round")
        circle.earth(cx=280 cy=120 r=10 fill="#0f82f2")
        circle(cx=220 cy=120 r=15 fill="#fd8c00")
        circle(cx=100 cy=120 r=4 fill="#ccc")
      x-play-btn

:::

---
> id: newton
> goals: apple


Một vài thập kỷ sau, [Isaac Newton] (bio: newton) đã có thể chứng minh các quan sát của Kepler, sử dụng định luật hấp dẫn [__gravity__](gloss:gravity)  mới được phát triển của ông.
Newton nhận ra rằng có một lực hút giữa hai vật có khối lượng bất kỳ trong vũ trụ - tương tự như lực hút giữa hai nam châm.

Lực hấp dẫn là lực khiến mọi thứ rơi xuống đất và lực hấp dẫn cũng là lực khiến các hành tinh chuyển động xung quanh mặt trời. Chỉ có tốc độ lớn mà các hành tinh di chuyển tạo ra mới có thể ngăn chúng rơi trực tiếp vào mặt trời.
::: column(width=280)

    // Source: https://www.flickr.com/photos/hikingartist/6217869031
    .newton.interactive
      img(src="images/newton-2.jpg" width=280 height=370)
      img.over(src="images/newton-1.jpg" width=280 height=370)
      img.apple(src="images/newton-apple.png" width=30 height=40)
      .credit Frits Ahlefeldt
    x-gesture(target=".newton" offset="20,-120")

::: column.grow

Sử dụng các định luật của Newton, bạn có thể suy ra đường đi của các vật thể khi chuyển động dưới tác dụng của lực hấp dẫn. Hóa ra là các hành tinh di chuyển trên các hình elip, nhưng các vật thể khác như sao chổi có thể di chuyển trên các đường [parabolic](gloss:parabola) hoặc [hyperbolic](gloss:hyperbola): chúng bay đến gần mặt trời trước khi quay lại và rơi vào vũ trụ, không bao giờ quay trở lại.

Theo truyền thuyết, một quả táo rơi đã truyền cảm hứng cho Newton suy nghĩ về lực hấp dẫn. Ông là một trong những nhà khoa học có ảnh hưởng nhất mọi thời đại và những ý tưởng của ông đã định hình sự hiểu biết của chúng ta về thế giới trong gần 300 năm - cho đến khi Albert Einstein khám phá ra thuyết tương đối vào năm 1905.
:::