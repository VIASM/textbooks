# Hình học Euclid 

## Giới thiệu

> id: thales
> goals: p1 p2 p3 move
> section: Giới thiệu
> description: Hình học là một trong những phần lâu đời nhất của toán học và có những ứng dụng cực kì hữu ích. Cách tiếp cận hệ thống, hợp lí của hình học đã được vận dụng trong nhiều lĩnh vực khác nhau. 
> color: "#0F82F2"
> level: Intermediate
> next: transformations

::: column.grow
Từ hàng ngàn năm trước, toán học đã được ứng dụng để dự đoán các mùa trong năm,
tính thuế hoặc ước tính diện tích đất canh tác.

Các nhà toán học Hi lạp Cổ đại (khoảng 500 TCN) đã rất kinh ngạc bởi các quy luật toán học và họ
mong muốn khám phá và giải thích được các quy luật này. Ban đầu, người ta bắt đầu nghiên cứu
toán học chỉ “cho vui” và hoàn toàn chưa quan tâm đến ứng dụng cụ thể nào. 
::: column(width=300)

    x-img(src="images/tablet.jpg" width=300 height=210)

{.caption} Miếng đất sét Babylon, có niên đại 1800 TCN, mô tả cách tính toán hình học.
:::

Một trong những nhà toán học này là [Thales of Miletus](bio:thales), người đã có một khám phá ngạc nhiên
khi thử tính toán với các dạng hình học:

::: column(width=420)

    x-geopad.sticky(width=420 height=320): svg

::: column.grow
Chọn hai điểm bất kì nằm trên ô bên trái.
_{span.reveal(when="p1 p2")} Vẽ một hình bán nguyệt qua hai điểm này._

{.reveal(when="p1 p2")} Bây giờ, hãy lấy một điểm thứ ba bất kì nằm trên
[chu vi](target:circumf) của hình bán nguyệt.

{.reveal(when="p3")} Chúng ta vẽ được một [{.red}tam giác](target:triangle) với hai góc nằm ở hai đầu mút cung và đỉnh thứ ba nằm trên cung tròn.

{.reveal(when="p3" delay=1000)} Thử di chuyển vị trí của ba điểm này và
quan sát sự thay đổi của[{.yellow}góc](target:angle) nằm trên đỉnh của tam giác.
_{span.reveal(when="move")} Góc này luôn [[90]]°!_
_{span.reveal(when="blank-0")} Từ đây, ta thấy tam giác này luôn có
[[góc vuông|equilateral|acute]]._
:::

---
> id: thales-1

Đối với Thales, kết quả này thật là ngoạn mục. Tại sao hai hình dạng khác nhau như hình bán nguyệt và hình vuông nhưng lại có mối liên quan cơ bản theo cách này. Theo truyền thuyết, ông ấy đã kinh ngạc về phát hiện này đến mức đã hi sinh một con bò để tạ ơn các vị thần.

    figure
      x-img(src="images/temple.svg" width=400 height=170)

Tuy nhiên, chỉ quan sát một mối liên quan này là chưa đủ đối với Thales.
Ông ấy muốn hiểu thêm tại sao quy luật này lại đúng, và ông ấy muốn chứng minh quy luật này luôn đúng, chứ không chỉ đúng với vài ví dụ ông ấy đã thử.

Một lập luận giải thích một điều gì đó tại sao đúng một cách hợp lí và chắc chắn, được gọi là [__chứng cứ__](gloss:proof). Trong các phần tiếp của của khoá học, bạn sẽ tìm hiểu thêm về các các phương thức tính toán hình học, và điều này cuối cùng giúp chúng ta chứng minh được _định lí Thales_.

---
> id: applications

Nhưng hình học không phải chỉ hữu ích để chứng minh các định lí – Hình học tồn tại ở mọi nơi quanh ta, trong tự nhiên, kiến trúc, trong kĩ thuật và thiết kế. Chúng ta ứng dụng hình học trong mọi thứ, từ đo đạc khoảng cách đến thiết kế các toà nhà chọc trời hay kể cả gửi các vệ tinh vào không  gian. Dưới đây là một vài ví dụ:


::: column(width=200)

    x-img(src="images/pyramids.jpg" credit="© Ricardo Liberato" width=200 height=200)

{.caption} Hình học giúp người Ai Cập cổ đại xây dựng các kim tự tháp khổng lồ, đều đặn một cách hoàn hảo.
::: column(width=200)

    x-img(src="images/sextant.jpg" width=200 height=200)

{.caption} Các thuỷ thủ sử dụng kính lục phân để xác định vị trí của mình trên biển dựa vào góc tạo bởi Mặt Trời hoặc các vì sao.
::: column(width=200)

    x-img(src="images/video-game.jpg" credit="© Eric Lascoña" width=200 height=200)

{.caption} Hình học được sử dụng để thiết kế đồ hoạ trong trò chơi hoặc phim thực tế.
::: column(width=200)

    x-img(src="images/plane.jpg" width=200 height=200)

{.caption} Hình học ứng dụng trong thiết kế và thử nghiệm các mô hình máy bay mới và giúp chúng an toàn và hiệu quả hơn.
::: column(width=200)

    x-img(src="images/cctv.jpg" lightbox width=200 height=200)

{.caption} Hình học là yếu tố then chốt khi thiết kế tòa nhà chọc trời này ở Bắc Kinh và đảm bảo được toà nhà không bị đổ.
::: column(width=200)

    x-img(src="images/satellite.jpg" lightbox credit="NASA" width=200 height=200)

{.caption} Hình học cho phép chúng ta dự đoán vị trí của các ngôi sao, hành tinh và các vệ tinh quay quanh Trái Đất.
:::

Trong các phần sau của khoá học, bạn sẽ được tìm hiểu về nhiều công cụ và cách thức tính toán hình học khác nhau, đã được các nhà khoa học khám phá trong nhiều thế kỉ qua. Chúng ta cũng sẽ biết được những cách tính toán này được ứng dụng để giải quyết vấn đề quan trọng nào trong thế giới thực tế.

---

## Tiên đề Euclid

> section: axioms
> id: points
 
Trước khi chúng ta đưa ra bất kỳ chứng minh nào, chúng ta cần biết một số thuật ngữ phổ biến giúp mô tả về các đối tượng hình học một cách dễ dàng hơn. Những điều này không đặc biệt thú vị, nhưng bạn nên biết hầu hết chúng:

::: column(width=240)

    x-geopad(width=240 height=160): svg
      circle.move.pulsate(cx=100 cy=30 target="move" label="P")
      circle.move.pulsate(cx=150 cy=100 target="move" label="Q")
      circle.move.pulsate(cx=40 cy=75 target="move")
      circle(x="point(200,50)" target="no-move")
      circle(x="point(70,120)" target="no-move" label="R")

::: column.grow
 Một [__điểm__](gloss:point) là một vị trí xác định trong không gian. Các điểm mô tả được vị trí nhưng không thể hiện được _kích thước_ và _hình dạng_ của chúng.

{.r} Trong Mathigon, [các chấm lớn, liền khối](target:move) biểu thị các điểm tương tác mà bạn có thể di chuyển được, trong khi [các điểm nhỏ, có đường viền](target:no-move) thể hiển các điểm cố định mà bạn không thể di chuyển.
[Continue](btn:next)
:::

---
> id: lines

::: column(width=240)

    x-geopad(width=240 height=160): svg
      path.green(x="line(point(60,100),point(90,40))" label="a")
      path.red(x="line(point(50,120),point(150,150))" label="b")
      circle.move(name="P" cx=170 cy=55 label="P")
      circle.move(name="Q" cx=200 cy=130 label="Q")
      path.yellow(x="line(P,Q)")

::: column.grow

Một [__đường thẳng__](gloss:line) là tập hợp vô số các điểm, kéo dài đến vô tận theo cả hai hướng. Đường thẳng thì luôn thẳng và không bị gián đoạn tại bất cứ điểm nào. Các đường thẳng không có _bề rộng_. 

{.r} Đường thẳng được kí hiệu bởi các chữ cái thường như _a_ or _b_. Chúng ta cũng có thể gọi tên bằng cách lấy hai điểm nằm trên đường thẳng, ví dụ 
<span class="math"><mover><mi>PQ</mi><mo value="↔">↔</mo></mover></span> or
<span class="math"><mover><mi>QP</mi><mo value="↔">↔</mo></mover></span>. Thứ tự của các điểm này không quan trọng.
[Continue](btn:next)

:::

---
> id: segments

::: column(width=240)

    x-geopad(width=240 height=160): svg
      circle.move(name="a" cx=50 cy=50 label="A")
      circle.move(name="b" cx=90 cy=120 label="B")
      path.red(x="segment(a,b)")
      circle.move(name="c" cx=120 cy=40 label="C")
      circle.move(name="d" cx=210 cy=110 label="D")
      path.blue(x="segment(c,d)")

::: column.grow
{.r} Một [__đoạn thẳng__](gloss:line-segment) là một phần đường thẳng nằm giữa hai điểm và không kéo dài đến vô tận. Chúng ta có thể kí hiệu đoạn thằng tương tự cách kí hiệu đường thẳng nhưng không có đầu mũi tên ở thanh ngang phía trên: `bar(AB)` or `bar(BA)`. Tương tự như trên, thứ tự của các điểm không quan trọng.[Continue](btn:next)
:::

---
> id: rays

::: column(width=240)

    x-geopad(width=240 height=160): svg
      circle.move(name="c" cx=40 cy=120)
      circle.move(name="d" cx=60 cy=40)
      path.green(x="ray(c,d)")
      circle.move(name="a" cx=90 cy=90 label="A")
      circle.move(name="b" cx=190 cy=130 label="B")
      path.yellow(x="ray(a,b)")

::: column.grow
Một [__tia__](gloss:ray) giống như là sự kết hợp giữa một _đường thẳng_ và một _đoạn thẳng_:
Tia chỉ kéo dài vô tận về một hướng xác định. Bạn có thể tưởng tưởng như tia sáng mặt trời: tia này bắt đầu từ một điểm (Mặt Trời) và kéo dài đến vô tận.


{.r} Khi kí hiệu tia, mũi tên được sử dụng để thể hiện hướng mà tia kéo dài đến vô tận, ví dụ  `vec(AB)`. Lúc này, thứ tự của điểm là cực kì quan trọng.
[Continue](btn:next)
:::

---
> id: circles

::: column(width=240)

    x-geopad(width=240 height=160): svg
      circle.move(name="a" cx=50 cy=60)
      path(x="segment(a,a.add(point(1,1).unitVector.scale(40)))" target="radius")
      path.red(x="circle(a,40)")

      circle.move(name="b" cx=170 cy=90)
      path(x="segment(b,b.shift(60,0))" target="radius")
      path.blue(x="circle(b,60)")

::: column.grow
{.r} Một [__đường tròn__](gloss:circle) là tập hợp các điểm có cùng một [khoảng cách](target:radius) đến một điểm ở trung tâm. Khoảng cách này được gọi là
[__bán kính__](gloss:circle-radius).
[Continue](btn:next)
:::

---
> id: congruence
> goals: pair-a-a pair-b-b pair-c-c pair-d-d pair-e1-e2 pair-e1-e3 pair-e2-e3 pair-f-f

### Sự đồng dạng

::: column(width=240)

    x-geopad(width=240 height=160): svg
      path.fill.green(name="x" x="polygon(point(30,30),point(80,20),point(100,80),point(70,110),point(30,90))" label="A" label-class="white" target="move")
      path.fill.green.light(x="x.rotate(1).shift(190,10)" target="move")
      path.fill.green#congruent-path(x="x.rotate(1).shift(190,10)" target="move" label="B" label-class="white")

::: column.grow
Hai hình này về cơ bản trông giống hệt nhau. Chúng có dùng kích thước và hình dạng, và chúng ta có thể xoay hoặc trượt [{.green}xoay and trượt](target:move) một hình sao cho khớp với hình còn lại. Trong hình học, chúng ta gọi đây là hai hình
[__đồng dạng__](gloss:congruent).

Kí hiệu của sự đồng dạng là _{span(voice="this")}`≅`_, thế nên ta có thể nói `A ≅ B`.
:::

Dưới đây là một số đối tượng có dạng hình học khác nhau – Hãy nối những các cặp hình đồng dạng với nhau. Lưu ý rằng có khi _nhiều hơn hai_ hình đồng dạng với nhau, và một số hình có thể không đồng dạng với _bất kì_ hình nào:

    svg.congruence(width=760 height=320 viewBox="0 0 760 320")
      g.lines
      g.obj(data-q="a" cx="145.2" cy="166.1")
    	polygon(points="119.6,146.6 131.7,186.9 170.9,175.1 139.7,159.5 154.4,145.2")
      g.obj(data-q="a" cx="376.4" cy="73.5")
    	polygon(points="388.1,44.7 353.1,68.2 376,102.2 381.7,67.8 399.7,77.6")
      g.obj(data-q="b" cx="93" cy="258")
    	rect(x="80" y="245" transform="matrix(0.5953 0.8035 -0.8035 0.5953 244.9541 29.6955)" width=26 height=26)
      g.obj(data-q="b" cx="264" cy="200")
        rect(x="251" y="187" transform="matrix(0.1863 0.9825 -0.9825 0.1863 411.3196 -96.636)" width=26 height=26)
      g.obj(data-q="c" cx="77" cy="59.5")
    	rect(x="54" y="36.5" transform="matrix(0.9159 0.4013 -0.4013 0.9159 30.3505 -25.8995)" width=46 height=46)
      g.obj(data-q="c" cx="238" cy="78")
        rect(x="215" y="55" transform="matrix(0.828 -0.5607 0.5607 0.828 -2.8011 146.8683)" width=46 height=46)
      g.obj(data-q="d" cx="510" cy="55")
    	polyline(points="539.9,68.9 489.7,78.3 506.7,27.5")
        path(d="M523.5,72c-2.4-12.7-11.4-22.4-22.9-26.3")
      g.obj(data-q="d" cx="501" cy="258")
    	polyline(points="497.8,287.8 475.2,242.1 528.7,244.7")
        path(d="M490.4,272.9c11.6-5.7,18.5-17.1,19.1-29.1")
      g.obj(data-q="e1" cx="417" cy="166.8")
        ellipse(transform="matrix(0.9464 -0.3229 0.3229 0.9464 -31.5073 143.6043)" cx="417" cy="166.8" rx="30.7" ry="17.1")
      g.obj(data-q="e2" cx="585" cy="138.2")
        ellipse(transform="matrix(0.4618 -0.887 0.887 0.4618 192.197 593.2707)" cx="585" cy="138.2" rx="17.1" ry="30.7")
      g.obj(data-q="e3" cx="618" cy="250.2")
        ellipse(transform="matrix(0.9089 -0.4171 0.4171 0.9089 -48.0564 280.5469)" cx="618" cy="250.2" rx="17.1" ry="30.7")
      g.obj(data-q="f" cx="670.8" cy="72.5")
        line(x1="649.4" y1="65.5" x2="692.1" y2="79.5")
        path(d="M647.6,72c-3.6-1.2-5.5-5-4.3-8.5s5-5.5,8.5-4.3c3.6,1.2,5.5,5,4.3,8.5C655,71.3,651.1,73.2,647.6,72z")
        path(d="M689.7,85.8c3.6,1.2,7.4-0.8,8.5-4.3s-0.8-7.4-4.3-8.5c-3.6-1.2-7.4,0.8-8.5,4.3C684.2,80.8,686.2,84.7,689.7,85.8z")
      g.obj(data-q="f" cx="705.1" cy="190.6")
        line(x1="693.9" y1="210.1" x2="716.4" y2="171.1")
        path(d="M699.9,213.2c-1.9,3.2-6,4.3-9.2,2.5c-3.2-1.9-4.3-6-2.5-9.2c1.9-3.2,6-4.3,9.2-2.5C700.7,205.8,701.8,209.9,699.9,213.2z")
        path(d="M722.1,174.8c1.9-3.2,0.8-7.4-2.5-9.2c-3.2-1.9-7.4-0.8-9.2,2.5c-1.9,3.2-0.8,7.4,2.5,9.2C716.1,179.1,720.2,178,722.1,174.8z")
      g.obj(data-q="g" cx="357" cy="265")
    	polyline(points="372.2,298.7 336,271.4 354.3,230.3")
    	path(d="M362.1,291.2c4.3-5.6,6.9-12.6,6.9-20.2c0-13.4-8-25-19.5-30.1")

---
> id: congruence-1

Hai đoạn thẳng đồng dạng khi chúng [[có cùng độ dài|giao nhau]]. Hai góc đồng dạng khi chúng có [[có cùng kích thước|giao nhau tại một điểm]] (tính bằng độ).

Lưu ý rằng _“đồng dạng”_ không có nghĩa là _“bằng nhau”_. Ví dụ, góc và đường thẳng đồng dạng không nhất thiết phải hướng theo cùng một hướng. Tuy nhiên, đồng dạng phải có các tính chất _đẳng thức_ giống nhau:

* Đồng dạng có tính __đối xứng__: Nếu `X ≅ Y` thì `Y ≅ X`.
* Đồng dạng có tính __phản xạ__: Bất kì hình dạng nào cũng đồng dạng với chính nó. Ví dụ, `A ≅ A`.
* Đồng dạng có tính __bắc cầu__: Nếu `X ≅ Y` và `Y ≅ Z` thì `X ≅ Z`.

---
> id: parallel

### Song song và vuông góc

::: column(width=240)

    x-geopad(width=240 height=200): svg
      path.red(x="line(point(30,100),point(70,20))" name="l1" mark="arrow" label="a")
      path.red(x="l1.shift(40,10)" mark="arrow" label="b")
      path.red(x="l1.shift(100,30)" mark="arrow" label="c")
      path.yellow(x="line(point(30,120),point(160,140))" name="l2" mark="arrow2" label="d")
      path.yellow(x="l2.shift(-30,40)" mark="arrow2" label="e")

::: column.grow

Hai đường thẳng không bao giờ giao nhau được gọi là [__song song__](gloss:parallel).
Hai đường thẳng này luôn hướng về cùng một hướng, và khoảng cách giữa chúng luôn
[[không đổi|tăng|giảm]].

{.reveal(when="blank-0")} Một ví dụ điển hình về đường thẳng song song trong đời sống là các _đường ray xe lửa_. Nhưng lưu ý rằng sẽ có thể tồn tại nhiều hơn hai đường thẳng song song với nhau.

{.reveal(when="blank-0")} Trong sơ đồ, Chúng ta biểu thị các đường song song bằng cách thêm một hoặc nhiều mũi tên nhỏ. Trong ví dụ này, __{.m-red}`a ∥ b ∥ c`__ và
__{.m-yellow}`d ∥ e`__. Kí hiệu `∥` có nghĩa đơn giản là _“song song với”_.

:::

---
> id: perpendicular

::: column(width=240)

    x-geopad(width=240 height=160): svg
      path(x="angle(point(60,50),point(50,100),point(100,110))")
      path.blue(x="line(point(50,100),point(100,110))" label="a")
      path.green(x="line(point(50,100),point(70,0))" label="b")

::: column.grow

Ngược lại với _song song_ là hai đường thẳng giao nhau và tạo thành góc 90° (góc vuông).
Những đường thẳng này được gọi là [__vuông góc__](gloss:perpendicular).

{.r} Trong ví dụ này, chúng ta sẽ ghi  _{.b.m-blue}a_ `⊥` _{.b.m-green}b_. Kí hiệu
`⊥` symbol simply means _“is perpendicular to”_.

:::

---
> id: euclid

### Tiên đề Euclid

::: column.grow

Các nhà toán học Hi lạp nhận ra rằng để viết các chứng minh toán học chính thức, bạn cần một số điểm cơ bản: những phát biểu đơn giản, trực quan mà mọi người đều đồng ý là đúng. Những phát biểu này được gọi là [__tiên đề__](gloss:axiom) (or _postulates_). 

Phần then chốt của toán học là kết hợp các tiên đề khác nhau để chứng minh các kết quả phức tạp hơn bằng việc sử dụng các quy tắc logic.

Nhà toán học Hi Lạp [Euclid of Alexandria](bio:euclid),người mệnh danh là _cha đẻ của hình học_, đã đưa ra năm tiên đề của hình học:

::: column(width=220)

    img(src="images/euclid.jpg" width=220 height=269)

{.caption} Euclid of Alexandria

:::

::: column(width=220 parent="padded-thin")

    x-geopad(width=220 height=160): svg
      circle.move(name="a" cx=30 cy=130 target="1_point")
      circle.move(name="b" cx=190 cy=30 target="1_point")
      path.red(x="segment(a,b)" target="1_line")

{.text-center }__Tiên đề thứ nhất__<br>
Bạn luôn luôn vẽ được một đường thẳng qua [hai điểm] bất kì(target:1_point)
[{.red} line segment](target:1_line).

::: column(width=220)

    x-geopad(width=220 height=160): svg
      circle.move(name="c" cx=60 cy=100)
      circle.move(name="d" cx=180 cy=60)
      path.blue(x="line(c,d)" target="2_line")
      path(x="segment(c,d)" target="2_segment")
      path.blue.transparent(x="segment(c,d)" target="2_line")

{.text-center }__Tiên đề thứ hai__<br>
Bạn có thể kéo dài bất kì [đoạn thẳng](target:2_segment) nào thành một
[{.blue} đường thẳng dài vô tận](target:2_line).

::: column(width=220)

    x-geopad(width=220 height=160): svg
      circle.move(name="e" cx=120 cy=80 target="3_center" label="P")
      circle.move(name="f" cx=170 cy=130)
      path(x="segment(e,f)" label="r" target="3_radius")
      path.green(x="circle(e,distance(e,f))" target="3_circle")

{.text-center }__Tiên đề thứ ba__<br>
Cho một [điểm _P_](target:3_center) và một [khoảng cách _r_](target:3_radius), bạn có thể vẽ một đường tròn với tâm P và bán kính r.
[{.green} circle](target:3_circle) with centre _P_ and radius _r_.

::: column(width=220)

    x-geopad(width=220 height=160): svg
      circle.move(name="x" cx=50 cy=100)
      circle(hidden name="xa" x="x.translate(point(110,80).subtract(x).rotate(pi/4).unitVector.scale(50))")
      circle(hidden name="xb" x="x.translate(point(110,80).subtract(x).rotate(-pi/4).unitVector.scale(50))")
      path.fill.orange(x="angle(xb,x,xa)" target="4_angle")
      path.dark(x="segment(x,xa)")
      path.dark(x="segment(x,xb)")

      circle.move(name="y" cx=190 cy=60)
      circle(hidden name="ya" x="y.translate(point(110,80).subtract(y).rotate(pi/4).unitVector.scale(50))")
      circle(hidden name="yb" x="y.translate(point(110,80).subtract(y).rotate(-pi/4).unitVector.scale(50))")
      path.fill.orange(x="angle(yb,y,ya)" target="4_angle")
      path.dark(x="segment(y,ya)")
      path.dark(x="segment(y,yb)")

{.text-center }__Tiên đề thứ tư__<br>
Hai [{.orange} góc vuông](target:4_angle) bất kì luôn đồng dạng.

::: column(width=220)

    x-geopad(width=220 height=160): svg
      circle.move(name="g" cx=160 cy=60 target="5_point" label="P")
      path(name="line5" x="line(point(50,80),point(130,140))" target="5_line" label="L")
      path.yellow(x="line5.parallel(g)" target="5_parallel")

{.text-center }__Tiên đề thứ năm__<br>
Cho một [đường thẳng_L_](target:5_line) và một [điểm _P_](target:5_point) không nằm trên _L_, có đúng [{.yellow} một đường thẳng](target:5_parallel)đi qua _P_ mà [song song](gloss:parallel) với _L_.
:::

{.r} [Continue](btn:next)

---
> id: jefferson

::: column.grow
Mỗi tiên đề này trông khá rõ ràng và hiển nhiên, nhưng khi kết hợp với nhau chúng đã hình thành nên nền tảng của hình học, và những tiền đề này được sử dụng để suy ra hầu hết mọi điều khác. Không ai khác mà chính là [Isaac Newton](bio:newton) đã nói, _“Vinh quang của hình học thể hiện ở chỗ hoàn thành đươc rất nhiều điều dựa trên rất ít nguyên tắc”

Euclid đã xuất bản một cuốn sách có tên _“Elements”_ về năm tiên đề này. Đây là ví dụ đầu tiên trong lịch sử về phương pháp tiếp cận toán học một cách có hệ thống, và cuốn sách này đã được sử dụng như sách giáo khoa Toán học trong hàng ngàn năm qua.


::: column(width=220)

    x-img(src="images/elements.jpg" width=220 height=330 lightbox)

:::
 
Một trong những người đã nghiên cứu công trình của Euclid là tổng thống Mỹ [Thomas
Jefferson](bio:jefferson). Khi viết tuyên ngôn độc lập vào năm 1776, ông ấy đã đi theo cách tiếp cận tương tự như vậy. Ông ấy bắt đầu bằng một vài “tiên đề” đơn giản và sau đó “chứng minh” những kết quả phức tạp hơn:

{div.parchment.voice} “Chúng tôi khẳng định một chân lý hiển nhiên rằng: mọi người sinh ra đều bình đẳng, rằng tạo hóa đã ban cho họ những quyền tất yếu và bất khả xâm phạm, trong đó có quyền sống, quyền được tự do và mưu cầu hạnh phúc.”

{.text-center.follows.no-voice} `=>`

{div.parchment.voice} Vì vậy, chúng ta … tuyên bố rằng các thuộc địa liên minh với nhau này đã và có quyền phải là Quốc gia Tự do và Độc lập.”

Đây chỉ là một ví dụ về những ý tưởng của Euclid trong toán học đã truyền cảm hứng cho những chủ đề hoàn toàn khác nhau.

---

## Phép dựng hình bằng thước và com pa

> section: construction
> id: measuring

Bạn có thể nhận thấy năm tiên đề của Euclid hoàn hoàn không đề cập bất cứ điều gì về 
_đo lường_ khoảng cách hay góc. Cho đến nay, đây là một phần quan trọng của hình học, chẳng hạn như tính diện tích và thể tích.

::: column.grow
Tuy nhiên, vào thời của Thales hay Euclid, không có một khung đơn vị phổ biến nào như chúng ta có ngày nay. Người ta thường đo khoảng cách bằng việc sử dụng các bộ phận cơ thể ví dụ bề rộng của ngón tay, hoặc chiều dài cánh tay. Cách đo này thường không chính xác và khác nhau đối với những người khác nhau.

Để đo khoảng cách xa hơn, các kiến ​​trúc sư hoặc nhà khảo sát đã sử dụng dây thắt nút: đoạn dây dài chứa nhiều nút thắt với khoảng cách bằng nhau. Nhưng cách này cũng không hoàn toàn chính xác, bởi các sợi dây khác nhau có khoảng cách giữa các nút thắt hơi khác nhau.
    figure: x-img(src="images/knots.jpg" width=370 height=23 style="opacity: 0.8")

::: column(width=200)

    x-img(src="images/units.png" width=200 height=336)

:::

Các nhà toán học Hi Lạp không để tâm đến những phép tính gần đúng này. Họ quan tâm đến các định luật cơ bản của hình học, hơn là các ứng dụng thực tế của chúng.

Đó là lí do tại sao họ nghĩ ra một phiên bản lí tưởng hơn về vạn vật quanh ta: trong phiên bản này, điểm không có kích thước và đường thẳng không có bề dày. Tất nhiên,
[[không thể|rất khó]] để vẽ những điều này. Những điểm nhìn thấy được luôn chiếm một số không gian, và đường thẳng thì luôn có bề dày. Đây là lí do tại sao cách hình vẽ của chúng ta chỉ mang tính “gần đúng”.

---
> id: tools
> goals: play-l1 play-c1

    figure: img(src="images/divider-1.svg" width=760 height=42)

Các tiên đề Euclid cho chúng ta biết một cách cơ bản rằng _điều gì có thể xảy ra_ trong phiên bản hình học của Euclid.
Hoá ra chúng ta chỉ cần hai công cụ đơn giản để phác thảo được điều này trên giấy:

::: column(width=320)

    x-geopad.r(width=300 height=240)
      svg
        circle.move(name="a" cx=50 cy=190)
        circle.move(name="b" cx=250 cy=50)
        path.red(name="l1" x="segment(a,b)" hidden)
      x-play-btn

{.text-center} Vật có __cạnh thẳng__ trông tương tự như cây thước mà không có vạch đánh dấu. Bạn có thể sử dụng cạnh thẳng này để nối hai điểm với nhau (như trong tiên đề 1), hoặc kéo dài đoạng thẳng (như trong tiên đề 2).

::: column.reveal(width=300 when="play-l1")

    x-geopad.r(width=300 height=240)
      svg
        circle.move(name="c" cx=150 cy=120)
        circle.move(name="d" cx=250 cy=150)
        path(x="segment(c,d)")
        path.red(name="c1" x="arc(c,d,1.99*pi)" hidden)
      x-play-btn

{.text-center} __Com pa__ có thể giúp bạn vẽ một đường tròn có kích thước cho trước xung quanh một điểm (như trong tiên đề 3).
:::

---
> id: construction

Tiên đề 4 and 5 tập trung vào sự so sánh về tính chất của các hình dạng, hơn là việc vẽ ra bất cứ hình gì. Vì vậy, họ không cần dụng cụ đặc biệt nào.

::: column.grow
Bạn có thể tưởng tượng rằng các nhà toán học Hi Lạp đang suy nghĩ về Hình học ở một bãi biển và vẽ nhiều hình dạng khác nhau trên cát: bằng viêc sử dụng các tấm ván dài làm cạnh thẳng và các đoạn dây làm com pa.

Mặc dù các công cụ này trông có vẻ thô sơ, nhưng chúng giúp bạn có thể vẽ được rất nhiều hình dạng. Điều này, đối các nhà toán học gần giống như chơi một trò chơi giải đố: khi cố gắng tìm cách "tạo ra" các hình dạng hình học khác nhau chỉ bằng một vật có cạnh thẳng và compa.

::: column(width=340)

    x-img(src="images/archimedes.jpg" width=340 height=265)

{.caption} Nhà Toán học Hi LạpThe [Archimedes](bio:archimedes) đã bị giết bởi quân La Mã xâm lược khi đang nghiên cứu về Hình học. Những lời cuối cùng của ông ấy trước khi mất là “đừng làm náo động những đường tròn của tôi”.
:::

---
> id: equilateral
> goals: segment0 segment1 segment2 circle1 circle2

::: column(width=320)

    x-geopad.sticky(width=320 tools="move|line|circle" intersections projections="no"): svg

::: column.grow
{.task} Hãy vẽ một [tam giác đều](gloss:equilateral-triangle) bằng cách chỉ sử dụng thước và com pa.

Để bắt đầu, hãy vẽ một đoạn thẳng ở vị trí bất kì vào ô bên phải. Với [{.no-margins} công cụ vẽ đường thẳng](->#equilateral_.tool:nth-child(3)) được chọn, chỉ cần kéo từ đầu đến cuối. Đoạn này sẽ là một trong các cạnh của tam giác.

{.reveal(when="segment0")} Tiếp theo, vẽ hai đường tròn có tâm lần lượt là điểm cuối của đoạn thẳng và đường tròn đi qua điểm cuối còn lại của đoạn thẳng. Với [{.no-margins} công cụ vẽ đường tròn](->#equilateral_.tool:nth-child(5))được chọn, chỉ cần kéo từ điểm cuối này sang điểm cuối khác.

{.reveal(when="circle1 circle2")} Chúng ta đã có hai đỉnh của tam giác và đỉnh thứ ba là giao điểm của hai đường tròn. Sử dụng công cụ line một lần nữa để vẽ hai cạnh còn thiếu và hoàn thành hình tam giác.

{.reveal(when="segment1 segment2")} Bây giờ [hai cạnh này](target:a) và
[hai cạnh này](target:b) mỗi cặp [[radii|diameters|circumferences]] đều nằm trên cùng một đường tròn, _{span.reveal(when="blank-0")} snên chúng phải có cùng độ dài. Nói cách khác, cả ba cạnh của tam giác đều đồng dạng – và vì vậy đây thực sự là một tam giác đều._
:::

---
> id: perp-bisector

### Trung điểm và đường trung trực

{.todo} COMING SOON – Cách dựng trung điểm và đường trung trực

    // Trung điểm là điểm nằm trên đoạn thẳng và chia một đoạn thẳng thành hai đoạn thẳng đồng dạng
    // Đoạn thẳng. Nếu A,B, and C thẳng hàng, và AB=BC, thì B là trung điểm của
    // `bar(AC)`.
    //
    // Một đường thẳng, đoạn thẳng, hay tia mà đi qua trung điểm của một đoạn thẳng khác
    // và tạo một góc vuông được gọi là __đường trung trực__. `bar(DE)` là
    // đường trung trực của `bar(AC)`, nên `bar(AB) ~= bar(BC)` và `bar(AC) ⊥ bar(DE)`.

---
> id: 

### Đường phân giác
{.todo} COMING SOON – Cách dựng đường phân giác

    // Khi hai tia có chung điểm cuối thì tạo ra một góc.
    //
    // Đây là, `vec(BA)` and `vec(BC)` giao nhau và hình thành một góc. Góc được kí hiệu bởi 
    // “∠” kí hiệu này nằm ở phía trước ba kí tự được dùng để đánh dấu gócs. Góc này được
    // kí hiệu là `/_ABC` or `/_CBA`. Luôn đặt đỉnh (Điểm cuối chung của 
    // hai tia) ở chính giữa của ba điểm. Điểm phụ nào được viết trước đều không quan trọng.
    //
    // Một __đường phân giác__ là một tia chia một góc thành hai góc đồng dạng,
    // Mỗi góc có số đo chính xác bằng một nửa góc ban đầu. Mỗi góc chỉ có một đường phân giác.
    //
    // Định lí đường phân giác: Nếu một điểm nằm trên đường phân giác của một góc, thì 
    // điểm đó cách đều các cạnh của góc đó.
    // Nói cách khác, nếu BD←→ là phân giác của ∠ABC,BE−→−⊥ED, and BF−→−⊥DF, then ED=DF.

---
> id: impossible

### Phép dựng hình bất khả thi

Trong chương tiếp theo, chúng ta sẽ thấy nhiều hình dạng hơn được xây dựng
như thế này. Tuy nhiên, đây là giới hạn của hình học Euclid: một số cấu trúc
không thể xây dựng khi chỉ đơn giản sử dụng thước thẳng và com pa. 

::: column.grow
Theo truyền thuyết, thành phố Delos ở Hi Lạp cổ đại từng phải đối mặt với một
bệnh dịch khủng khiếp. Nhà tiên tri ở Delphi đã nói rằng đây là một hình phạt từ
các vị thần, và bệnh dịch sẽ biến mất nếu họ xây một bàn thờ mới cho đền thờ bởii thể tích đúng bằng gấp đôi thể tích ngôi đền hiện nay. 

    figure: img(src="images/altar.svg" width=320 height=140)

::: column(width=300)

    x-img(src="images/delphi.jpg" credit="© De Agostini Editorial" width=300 height=239)

{.caption} Ngôi đền được xây dựng lại ở Delphi
:::

Lưu ý rằng _gấp đôi thể tích_ không giống như _gấp đôi một cạnh của hình lập phương_. Thực tế, nếu thể tích [[ba chiều|hai chiều|một chiều]] tăng gấp 2, thì một cạnh một chiều [[one-dimensional|three-dimensional|two-dimensional]]
của hình lập phương sẽ tăng với hệ số `root(2,3)`.

---
> id: impossible-1

Điều này nghe có vẻ khá đơn giản, nhưng việc nhân đôi khối này thực sự là không thể trong [hình học Euclid](gloss:euclidean-geometry), khi chỉ sử dụng thước thẳng và com pa! Đối với người dân ở Delos điều không may mắn này có nghĩa là tất cả hi vọng đã biến mất. Có hai công trình khác cũng nổi tiếng là bất khả thi. Các nhà toán học đã dành rất nhiều thời gian cố gắng tìm giải pháp – nhưng không thành công:

::: column(width=220)

    figure: img(src="images/impossible-1.svg" width=200 height=180)

{.text-center} __{.m-red} Chia góc làm ba__<br>
Chúng ta đã biết cánh chia góc làm hai. Tuy nhiên, việc chia góc làm ba tuong tự như vậy.

::: column(width=220)

    figure: img(src="images/impossible-2.svg" width=200 height=180)

{.text-center} __{.m-blue} Nhân đôi khối lập phương__<br>
Không thể dựng được hình lập phương khác có thể tích gấp đôi hình lập phương có cạnh cho trước.

::: column(width=220)

    figure: img(src="images/impossible-3.svg" width=200 height=180)

{.text-center} __{.m-green} Bình phương hình tròn __<br>
Không thể dựng một hình vuông có cùng diện tích với hình tròn cho trước.
:::

Lưu ý rằng tất cả các vấn đề này đều có thể được giải quyết khá dễ dàng bằng đại số hoặc sử dụng thước đánh dấu và thước đo góc. Nhưng sẽ là bất khả thi nếu bạn chỉ sử dụng thước thẳng và com pa.

---

## Các phép dựng hình khác

> section: more-construction
> sectionStatus: dev

Xây dựng một sân bóng đá

Dựng các đường song song và vuông góc

Dựng một hình vuông

Dựng đường vuông góc; đi qua một điểm KHÔNG nằm trên đường thẳng 
Vẽ một đường nằm ngang sao và một điểm ở bên trên đường thẳng. Kí hiệu là đường thẳng l và điểm A.

* Dùng compa và đặt đầu nhọn vào điểm A. Mở Compa sao cho khoảng cách lớn hơn khoảng cách đến đường thẳn l. Vẽ một cung tròn cắt với đường thẳng hai lần.
* Di chuyển đầu kim đến điểm giao với cung tròn. Mở rộng com pa thêm một ít và vẽ một cung tròn bên dưới đường thẳng. Lặp lại tương tự với điểm còn lại sao cho hai cung tròn cắt nhau. 
* Lấy thước kẻ vẽ một đường thẳng từ điểm A đến các giao điểm của hai cung tròn bên dưới đường thẳng. Đường thẳng này vuông góc với l and đi qua A.

Định lí #1: Nếu hai đường thẳng song song và một đường thẳng thứ ba vuông góc với một trong các đường thẳng song song thì nó cũng vuông góc với đường thẳng song song còn lại. Hay, nếu l || m và l⊥n, thì n⊥m.

Định lí #2: Nếu hai đường thẳng cùng vuông góc với một đường thẳng thì chúng song song với nhau.

Khoảng cách giữa các đường song song
TKhoảng cách ngắn nhất giữa hai đường thẳng song song là độ dài đoạn vuông góc giữa chúng. Không quan trọng bạn chọc đường vuông góc nào, miễn là hai điểm nằm trên hai đường thẳng. Nhắc lại là ta có vô số đường vuông góc giữa hai đường thẳng song song.

---

## Góc và chứng minh

> section: proofs
> sectionStatus: dev

TODO

---

## Origami và gấp giấy

> id: origami
> section: origami
> sectionBackground: dark

Sử dụng thước và compa không phải là cách duy nhất để dựng các hình dạng hình học. Một kĩ thuật khác hoàn toàn không sử dụng công cụ: __Origami__.

Từ _Origami_ _{span.no-voice}(折り紙)_ bắt nguồn từ tiếng Nhật _oru_ (gấp) and _kami_
(giấy). Mục đích là tạo ra các đồ vật từ một hay nhiều tờ giấy mà không cần bất kì dụng cụ hỗ trợ nào ngoài keo hoặc kéo. Bạn có thể tạo ra những thiết kế vô cùng đẹp mắt và ấn tượng - tất cả những hình này được tạo ra bằng cách sử dụng không gì khác ngoài những tờ giấy hình chữ nhật:

::: column(width=186)

    x-img(src="images/origami/origami-1.jpg" lightbox credit="© Dirk Eisner" width=186 height=200)

::: column(width=186)

    x-img(src="images/origami/origami-2.jpg" lightbox credit="© Dirk Eisner, Thomas Hull" width=186 height=200)

::: column(width=186)

    x-img(src="images/origami/origami-3.jpg" lightbox credit="© ServeSmasher (Flickr)" width=186 height=200)

::: column(width=186)

    x-img(src="images/origami/origami-4.jpg" lightbox credit="© Dirk Eisner" width=186 height=200)

::: column(width=186)

    x-img(src="images/origami/origami-5.jpg" lightbox credit="© Meenakshi Mukerji" width=186 height=200)

::: column(width=186)

    x-img(src="images/origami/origami-6.jpg" lightbox credit="© Meenakshi Mukerji, Dennis Walker" width=186 height=200)

:::

---
> id: crane
> goals: video

Việc xây dựng những hình dạng như thế này có thể mất rất nhiều thời gian và điều quan trọng là phải cực kì chính xác. Bạn có thể thực hành một chút để tự làm điều đó!

::: column.sticky-video(width=360)

    x-video(src="https://static.mathigon.org/videos/crane.mp4" poster="images/crane.jpg" width=360 height=360 controls)

::: column.grow
{.step.active(data-t=0)} Bạn chỉ cần một tờ giấy vuông, hãy bắt đầu gấp tờ giấy theo hai đường chéo của nó.

{.step(data-t=16)} Tiếp theo, gấp giấy dọc theo tâm ngang và dọc của nó – nhưng theo hướng ngược lại.

{.step(data-t=38)} Bây giờ lấy hai góc đối diện của tờ giấy và đưa chúng lại với nhau như hình. Điều này tạo thành một hình vuông nhỏ hơn và mở ra ở phía dưới.

{.step(data-t=51)} Gấp các góc bên trái và bên phải của hình vuông về phía đường trung tâm của nó. Sau đó lật ngược và lặp lại tương tự.

{.step(data-t=83)} Bây giờ gấp hình tam giác trên cùng xuống, dọc theo đường ngang, sau đó mở các nếp gấp từ hai bước cuối cùng.

{.step(data-t=99)} Bước này khó thực hiện: bạn lấy góc dưới của tờ giấy gấp hết cỡ lên trên theo đường ngang vừa tạo. Một số nếp gấp bạn đã tạo trước đó sẽ bị đảo ngược. Sau đó lật lại và lặp lại.

{.step(data-t=135)} Đảm bảo hai "chân" hướng xuống dưới. Sau đó, lấy góc bên trái và bên phải và gấp chúng về phía đường chính giữa. Lật lại và lặp lại.

{.step(data-t=172)} Bạn sắp hoàn thành nó rồi! Mở một chút bên phải và gấp phần đầu lên phía trên. Bạn sẽ phải lật nó từ trong ra ngoài. Sau đó lặp lại tương tự với phần đuôi bên trái.. 

{.step(data-t=203)} Đảo ngược nếp gấp như hình để tạo mỏ chim. Bạn có thể quyết định chiều dài của mỏ chim bằng cách chọn vị trí của gấp vào.

{.step(data-t=215)} Cuối cùng, gập và kéo xa hai cánh xuống.
:::

---
> id: crane-1

_Con hạc_ này là một trong những mẫu Origami lâu đời và nổi tiếng nhất. Chúng tôi còn có nhiều [hướng dẫn khác cho các mô hình Origami](/origami) mà bạn có thể thử!

    figure: x-img(src="images/origami-1.jpg" credit="© Meenakshi Mukerji, Joel Lord, Dirk Eisner, Angie Harms, Michal Kosmulski" width=760 height=118)

---
> id: origami-axioms

### Tiên đề Origami 

Tương tự việc vẽ bằng thước thẳng và compa, có một số tiên đề về các _nếp gấp_ khác nhau có thể thực hiện được với origami. Những tiên đề này được liệt kê lần đầu tiên vào năm 1992, bởi nhà toán học người Ý-Nhật Humiaki Huzita.

::: column(width=220 parent="padded-thin origami-axioms")

    x-video(src="images/origami/axiom-1.mp4" width=220 height=220)

{.text-center} Bạn có thể gấp một đường nối hai điểm bất kì.
::: column(width=220)

    x-video(src="images/origami/axiom-2.mp4" width=220 height=220)

{.text-center} Bạn có thể gấp bất kỳ điểm _P_ nào lên điểm _Q_ bất kì. Điều này tạo ra [[trung trực|đường phân giác|trung điểm]] của đường thẳng `bar(PQ)`. 
::: column(width=220)

    x-video(src="images/origami/axiom-3.mp4" width=220 height=220)

{.text-center} Chúng ta có thể gấp hai đường thẳng bất kì lên nhau. Nếu các dòng
cắt nhau, thì ta đã tạo ra [[đường phân giác | đường trung trực | trung điểm]]
của góc tạo bởi hai đường thẳng này.
::: column(width=220)

    x-video(src="images/origami/axiom-4.mp4" width=220 height=220)

{.text-center} Cho một điểm _P_ đường thẳng _L_, chúng ta có thể tạo một nếp gấp
vuông góc với _L_ và đi qua _P_.
::: column(width=220)

    x-video(src="images/origami/axiom-5.mp4" width=220 height=220)

{.text-center} Cho hai điểm  _P_ and _Q_ và đường thẳng _L_, chúng ta có thể tạo một nếp gấp
đi qua _P_ và đặt _Q_ vào _L_.
::: column(width=220)

    x-video(src="images/origami/axiom-6.mp4" width=220 height=220)

{.text-center} Cho hai điểm _P_ và _Q_ bất kì và hai đường thẳng bất kỳ _K_ và _L_,
chúng ta có thể tạo một nếp gấp đặt điểm _P_ vào đường thẳng _K_ và đồng thời
đặt điểm _Q_ vào đường thẳng _L_.
::: column(width=220)

    x-video(src="images/origami/axiom-7.mp4" width=220 height=220)

{.text-center} Cho một điểm _P_ and hai đường thẳng _K_ và _L_, chúng ta có thể gấp một đường thẳng vuông góc với _K_ đặt _P_ lên _L_.
:::

---
> id: origami-axioms-1

Hóa ra những tiên đề này còn lợi hại hơn cả tiên đề Euclid.
Chúng có thể chia góc làm ba phần và gấp đôi hình lập phương chỉ bằng việc gấp giấy! 
Tất nhiên, không thể gấp để làm cong bất kì đường thẳng nào, và bạn vẫn không thể xếp hình tròn bằng Origami.

    figure: x-img(src="images/origami-2.jpg" credit="© Dirk Eisner, Meenakshi Mukerji, noricum, fdecomite" width=760 height=123)

---
> id: origami-applications
> goals: video

### Ứng dụng của Origami

Origami là một nghệ thuật cổ xưa, trong một thời gian dài Origami chủ yếu được xem là một trò chơi giải trí mà không có bất kì ứng dụng nào trong cuộc sống. Tuy nhiên, những kĩ thuật đã phát triển dành cho Origami lại có thể cực kì hữu ích trong công nghệ và kĩ thuật:

::: column(width=300)

    x-video(src="https://static.mathigon.org/videos/space.mp4" poster="images/space.jpg" width=300 height=225 credit="© Brigham Young University")

::: column.grow

#### Origami trong không gian

Các vệ tinh cần những tấm pin mặt trời lớn để tạo ra năng lượng. Thật không may, tên lửa
mang vệ tinh vào không gian lại có không gian rất hạn chế dành cho hàng hóa, và bất kì trọng lượng nào thêm vào cũng tốn rất nhiều nhiên liệu.

Kỹ thuật gấp giấy Origami cho phép các tấm pin mặt trời "mở ra" khi chúng vào không gian. Một số các nếp gấp đặc biệt hiệu quả khi cực kì nhỏ gọn và cần rất ít động cơ
và các thành phần cơ khí khác.

    // Một trong số đó là  __Miura Map Fold__, được phát minh bởi _Korio Miura_.
    // Điều này cũng đúng với gương của kính thiên văn trong không gian. Gương lớn hơn
    // Để có thể chụp ảnh đẹp hơn. Các kĩ sư có thể sử dụng Origami để chế tạo những tấm gương lớn.
    // Có thể được gấp lại rất hiệu quả khi được đưa lên tên lửa.

:::

---
> id: origami-applications-3
> goals: video

::: column(width=300)

    x-video(src="https://static.mathigon.org/videos/stents.mp4" poster="images/stents.jpg" width=300 height=225 credit="© Virtual Point")

::: column.grow

#### Origami trong Y học

Trong y học, những ý tưởng tương tự từ Origami được sử dụng ở quy mô nhỏ hơn nhiều. Vào năm
2003, các nhà nghiên cứu đã phát triển _Origami Stents_: các ống nhỏ có thể đi vào
vào mạch máu. Ban đầu chúng được gấp lại nhưng có thể mở rộng khi vào bên trong mạch máu  bệnh nhân để mở rộng các động mạch hoặc tĩnh mạch bị tắc.

:::

---
> id: origami-applications-1

::: column(width=300)

    x-img(src="images/bridge.jpg" width=300 height=225 credit="© Hiroshima University")

::: column.grow

#### Cầu có thể gập lại

Quân đội Anh và Mỹ đã sử dụng Origami để phát triển những chiếc cầu này. Việc phát triển này rất quan trọng để nhanh chóng vượt sông hoặc mương chống tăng,
và giúp triển khai nhanh hơn nhiều so với các thiết kế trước đó.


Những chiếc cầu này cũng được sử dụng để cứu trợ thiên tai, để các phương tiện cấp cứu nhanh chóng tiếp cận hiện trường sau động đất hoặc sóng thần. Hình ảnh này nguyên mẫu được thiết kế tại Đại học Hiroshima ở Nhật Bản.
:::

    // ---
    // > id: origami-applications-2
    // > goals: video
    //
    // ::: column(width=300)
    //
    // x-video(src="https://static.mathigon.org/videos/stadium.mp4" poster="images/stadium.jpg" width=300 height=225 credit="© Mercedes Benz Stadium")
    //
    // ::: column.grow
    // #### Stadium Roofs
    //
    // Bridges are difficult to construct because they have to span large distances
    // without intermediate support. This also is the case for the roofs of sports
    // stadiums, which have to cover a large area without being supported by pillars.
    //
    // The roof of the new Falcons Stadium in Atlanta consists of eight enormous
    // modules that can twist to open or close.
    // :::

---
> id: origami-applications-4
> goals: video

::: column(width=300)

    x-video(src="https://static.mathigon.org/videos/marine.mp4" poster="images/marine.jpg" width=300 height=225 credit="© Harvard University")

::: column.grow

#### Origami dưới biển

 Dưới đáy sâu đại dương là khu vực ít được khám phá nhất trên Trái đất. Động vật
sống ở đó thường có vảy và mỏng manh, điều này tìm hiểu chúng rất khó.


Tại đây, bạn có thể thấy một “cái bẫy” có hình dạng [khối đa diện] (gloss:dodecahedron)
có thể gấp xung quanh các sinh vật biển, cho phép nghiên cứu được chúng. Hệ thống
được điều khiển từ xa và chỉ có một động cơ duy nhất để điều khiển chuyển động gấp phức tạp
của năm cánh tay này.

:::

---
> id: origami-applications-5

Và còn rất nhiều ứng dụng của Origami trong cuộc sống hàng ngày: những ngôi nhà
sẽ nén lại chứ không vỡ vụn trong trận động đất, làm bung túi khí
trong ô tô, rô bốt tự lắp ráp, máy bay có trọng lượng nhẹ và chứa được nhiều hàng hoá hơn.
---
> id: origami-wings
> goals: video

### Origami trong tự nhiên

Hóa ra không phải duy nhất con người chúng ta khai thác được sức mạnh của Origami: thiên nhiên đã làm như vậy trong hàng triệu năm.

Ở đây, bạn có thể thấy cánh của một __con sâu tai__ có thể gấp lại bằng cách sử dụng một hoa văn khéo léo. Khi mở ra, kích thước của cánh sẽ mở rộng theo hệ số 10 - "tỷ lệ gấp" cao nhất trong thế giới động vật. 
::: column(width=300)

    x-img(src="images/wing.jpg" width=300 height=170 credit="© ETH Zürich")

::: column(width=300)

    x-video(src="https://static.mathigon.org/videos/wing-animation.mp4" poster="images/wing-animation.jpg" width=300 height=170 credit="© ETH Zürich")

:::

---
> id: origami-wings-1

Khi được mở rộng, các cánh lớn bắt vào một vị trí ổn định cho phép
côn trùng bay. Nhưng chỉ cần một cái chạm nhẹ nhất là đôi cánh sẽ thu lại.
Khi gấp lại, chúng đủ nhỏ gọn để cho phép đồ gài tai có thể đào dưới lòng đất.
Nhiều loài côn trùng, dơi, lá và hoa khác sử dụng các mẫu gấp tương tự để một
bề mặt lớn có thể vừa với một không gian nhỏ.

Các nhà khoa học đang nghiên cứu những loài thực vật và động vật này, hy vọng có thể bắt chước khả năng của chúng trong kĩ thuật và công nghệ. Các ứng dụng tiềm năng bao gồm có thể gập lại
linh kiện điện tử trong điện thoại thông minh, mở rộng tấm pin mặt trời cho vệ tinh, hoặc thậm chí là lều cắm trại tự gấp
---
> id: origami-dna
> goals: video

::: column(width=320)

    x-video(src="https://static.mathigon.org/videos/dna.mp4" poster="images/dna.jpg" width=320 height=240 credit="© PyMOL")

::: column.grow

Origami thậm chí còn xuất hiện trong chính cơ thể bạn: mỗi tế bào của con người chứa khoảng 2 mét của [DNA](gloss:dna),[phân tử](gloss:molecule) mang tất cả
thông tin di truyền của bạn.  Nếu bạn có thể kết hợp DNA ftừ tất cả các tế bào trong cơ thể mình, chiều dài của chúng sẽ gấp hơn 140 lần khoảng cách từ Trái Đất đến Mặt Trời!

Để phù hợp với cơ thể bạn tất cả DNA đó, mọi sợi trong DNA được cuộn tròn, gấp lại và được giữ cố định bởi các phân tử đặc biệt mà không bị xoắn hoặc rách, 
:::

---
> id: origami-dna-1

Một quá trình tương tự cũng được sử dụng bởi các phân tử phức tạp khác xuất hiện trong cơ thể sống sinh vật. Ví dụ: __[protein](gloss:protein) gấp__ ià một trong những
các vấn đề phức tạp trong sinh học. Khi hiểu rõ hơn về vấn đề này có thể giúp các nhà khoa học phát triển thuốc mới trong tương lai.