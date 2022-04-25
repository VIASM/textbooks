<<<<<<< Updated upstream
# Các phép biến hình và Tính đối xứng
=======
﻿# Các phép biến hình và Tính đối xứng
>>>>>>> Stashed changes

## Giới thiệu

> id: intro section: introduction description: Tính đối xứng có thể được tìm thấy ở khắp nơi trong tự nhiên  – nhưng chính nó cũng nằm ở nền tảng của các định luật tự nhiên vô hình. Toán học có thể giúp chúng ta lý giải sự việc trên. color: "#2274E8" level: Intermediate next: triangles

Nhiều khái niệm hình học như [đường thẳng](gloss:line) hay [đa giác](gloss:polygon) được “phát minh” bởi các nhà toán học. Ngược lại, tính đối xứng lại có mặt ở khắp mọi nơi trong cuộc sống. Hầu hết các loài thực vật, động vật và thậm chí là chính chúng ta cũng mang tính đối xứng.

::: column(width=200)

```
x-img(src="images/butterfly.jpg" width=200 height=200 lightbox alt="Butterfly")
```

::: column(width=200)

```
x-img(src="images/lion.jpg" width=200 height=200 lightbox alt="Lion")
```

::: column(width=200)

```
x-img(src="images/starfish.jpg" width=200 height=200 lightbox alt="Starfish")
```

:::

Qua thời gian, chúng ta đã bắt chước và áp dụng tính đối xứng của tự nhiên vào nghệ thuật, kiến trúc, công nghệ và thiết kế. Những hình dạng và hoa văn luôn có vẻ *thu hút hơn* khi chúng mang tính đối xứng.

::: column(width=200)

```
x-img(src="images/taj-mahal.jpg" credit="© Yann Forget / Wikimedia Commons" width=200 height=200 lightbox alt="Taj Mahal")
```

::: column(width=200)

```
x-img(src="images/capitol.jpg" credit="© Martin Falbisoner" width=200 height=200 lightbox alt="US Capitol")
```

::: column(width=200)

```
x-img(src="images/window.jpg" width=200 height=200 lightbox alt="Mosaic Church Window")
```

:::

Tuy nhiên, sự đối xứng có ý nghĩa quan trọng hơn nhiều so với việc chỉ đơn giản là để *đẹp mắt*. Nó nằm ở nền tảng vũ trụ của chúng ta, và thậm chí có thể lý giải những Định luật Vật lý cơ bản nhất.

[Continue](btn:next)

---

> id: transformations goals: t1 t2 t3

Tuy tính đối xứng là một khái niệm rất trực quan, việc mô tả nó theo ngôn ngữ Toán học có thể khó hơn bạn nghĩ. Đầu tiên, chúng ta phải nghiên cứu [**các phép biến hình**](gloss:transformation). Chúng là những cách biến đổi một đối tượng hình học thành một hình khác. Sau đây là một vài ví dụ:

::: column.r(width=200 parent="padded-thin")

```
.animation
  include svg/transform-1.svg
  x-play-btn
```

::: column.r(width=200)

```
.animation
  include svg/transform-2.svg
  x-play-btn
```

::: column.r(width=200)

```
.animation
  include svg/transform-3.svg
  x-play-btn
```

:::

---

> id: transformations-1

Kết quả của một phép biến hình được gọi là [**ảnh**](gloss:transformation-image). Chúng ta thường kí hiệu cho ảnh của một hình `A` là `A'`, đọc là “A phẩy”. Có nhiều phép biến hình khác nhau, và chúng ta sẽ tìm hiểu về chúng sâu hơn trong suốt khóa học này.

---

## Phép dời hình

> id: rigid section: rigid

[**Phép dời hình**](gloss:rigid-transformation) là một phép biến hình đặc biệt mà không làm thay đổi kích thước hay hình dạng của hình ban đầu. Chúng ta có thể hình dung hình của chúng ta được làm từ gỗ hoặc kim loại: chúng ta có thể di chuyển, xoay, hoặc lật nó nhưng chúng ta không thể uốn cong, kéo dãn hoặc làm biến dạng nó.

Phép biến hình nào trong năm phép dưới đây là phép dời hình?

```
x-picker.rigid
  .item: img(src="images/picker-1.svg" width=130 height=240)
  .item(data-error="not-rigid-1"): img(src="images/picker-2.svg" width=130 height=240)
  .item: img(src="images/picker-3.svg" width=130 height=240)
  .item(data-error="not-rigid-2"): img(src="images/picker-4.svg" width=130 height=240)
  .item: img(src="images/picker-5.svg" width=130 height=240)
```

---

> id: rigid-1 goals: t1 t2 t3

Hóa ra rằng chỉ tồn tại ba dạng phép dời hình:

::: column.r(width=200)

```
.animation
  include svg/rigid-1.svg
  x-play-btn
```

{.text-center} Một phép biến hình mà chỉ *dịch chuyển* hình ban đầu được gọi là [**phép tịnh tiến**](gloss:translation).

::: column.r(width=200)

```
.animation
  include svg/rigid-2.svg
  x-play-btn
```

{.text-center} Một phép biến hình mà *lật* hình ban đầu được gọi là [**phép đối xứng trục**](gloss:reflection).

::: column.r(width=200)

```
.animation
  include svg/rigid-3.svg
  x-play-btn
```

{.text-center} Một phép biến hình mà *quay* hình ban đầu được gọi là [**phép quay**](gloss:rotation).

:::

---

> id: rigid-2

Chúng ta cũng có thể kết hợp nhiều phép biến hình để tạo thành một phép biến hình phức tạp hơn – ví dụ, chúng ta tịnh tiến một hình và sau đó quay hình vừa được tịnh tiến đó.

Nhưng đầu tiên, chúng ta hãy cùng tìm hiểu thật thấu đáo từng dạng phép biến hình trên.

---

> id: translations

### Phép tịnh tiến

Một [**phép tịnh tiến**](gloss:translation) là một phép biến hình dịch chuyển mọi điểm của hình ban đầu với cùng một khoảng cách theo cùng một hướng.

Trên mặt phẳng tọa độ, chúng ta có thể định rõ một phép tịnh tiến bằng khoảng cách mà hình ban đầu bị dịch chuyển dọc theo trục *x* và trục *y*. Ví dụ, phép tịnh tiến bởi (3, 5) sẽ dịch chuyển một hình 3 đơn vị theo trục *x* và 5 đơn vị theo trục *y*.

::: column(width=220)

```
x-geopad(width=220 height=140 grid=20 no-points): svg
  path.fill.orange.light(x="polygon(point(2,2),point(1,5),point(4,5),point(3,2))" name="s1" label="A" label-class="white")
  path.fill.orange(x="s1.shift(5,-1)" label="A'" label-class="white")
  path.reveal(x="segment(point(4,5),point(9,5))" mark="arrow" when="blank-0" animation="draw")
  path.reveal(x="segment(point(9,5),point(9,4))" mark="arrow" when="blank-1" animation="draw")
```

{.caption} Tịnh tiến bởi ([[5]], [[1]]) ::: column(width=220)

```
x-geopad(width=220 height=140 grid=20 no-points): svg
  path.fill.red.light(x="circle(point(7,4),1.5)" name="s2" label="B" label-class="white")
  path.fill.red(x="s2.shift(-4,-2)" label="B'" label-class="white")
  path.reveal(x="segment(point(6,5),point(2,5))" mark="arrow" when="blank-2" animation="draw")
  path.reveal(x="segment(point(2,5),point(2,3))" mark="arrow" when="blank-3" animation="draw")
```

{.caption} Tịnh tiến bởi  ([[-4]], [[2]]) ::: column(width=220)

```
x-geopad(width=220 height=140 grid=20 no-points): svg
  path.fill.light.purple(x="polygon(point(2,0),point(5,0),point(5,2),point(4,2),point(4,1),point(3,1),point(3,4),point(2,4))" name="s3" label="C")
  path.fill.purple(x="s3.shift(4,2)" label="C'")
  path.reveal(x="segment(point(2,6),point(6,6))" mark="arrow" when="blank-4" animation="draw")
  path.reveal(x="segment(point(2,4),point(2,6))" mark="arrow" when="blank-5" animation="draw")
```

{.caption} Tịnh tiến bởi  ([[4]], [[-2]]) :::

---
<<<<<<< Updated upstream

> id: translations-1 goals: drag-0 drag-1 drag-2

Bây giờ đến lượt bạn - hãy tịnh tiến các hình sau đây:

::: column(width=220)

=======

> id: translations-1 goals: drag-0 drag-1 drag-2

Bây giờ đến lượt bạn - hãy tịnh tiến các hình sau đây:

::: column(width=220)

>>>>>>> Stashed changes
```
svg(width=220 height=140)
  each i in [10,30,50,70,90,110,130,150,170,190,210]
    line(x1=i x2=i y1=0 y2=140 stroke="#e6e6e6" stroke-width=2)
  each i in [10,30,50,70,90,110,130]
    line(x1=0 x2=220 y1=i y2=i stroke="#e6e6e6" stroke-width=2)
  polygon(points="30,10 10,70 70,70 50,10" style="fill: #289782; opacity: .5;")
  polygon(points="30,10 10,70 70,70 50,10" style="fill: #289782; cursor: move")
```

{.caption} Tịnh tiến bởi (3, 1) *{span.check(when="drag-0")}* ::: column(width=220)

```
svg(width=220 height=140)
  each i in [10,30,50,70,90,110,130,150,170,190,210]
    line(x1=i x2=i y1=0 y2=140 stroke="#e6e6e6" stroke-width=2)
  each i in [10,30,50,70,90,110,130]
    line(x1=0 x2=220 y1=i y2=i stroke="#e6e6e6" stroke-width=2)
  polygon(points="50,10 90,50 50,90 10,50" style="fill: #2ba058; opacity: .5;")
  polygon(points="50,10 90,50 50,90 10,50" style="fill: #2ba058; cursor: move")
```

{.caption} Tịnh tiến bởi (–4, –2) *{span.check(when="drag-1")}* ::: column(width=220)

```
svg(width=220 height=140)
  each i in [10,30,50,70,90,110,130,150,170,190,210]
    line(x1=i x2=i y1=0 y2=140 stroke="#e6e6e6" stroke-width=2)
  each i in [10,30,50,70,90,110,130]
    line(x1=0 x2=220 y1=i y2=i stroke="#e6e6e6" stroke-width=2)
  polygon(points="10,10 30,10 30,50 50,50 50,10 70,10 70,70 10,70" style="fill: #2ea92e; opacity: .5;")
  polygon(points="10,10 30,10 30,50 50,50 50,10 70,10 70,70 10,70" style="fill: #2ea92e; cursor: move")
```

{.caption} Tịnh tiến bởi (5, –1) *{span.check(when="drag-2")}* :::

---

> id: reflections goals: r0 r1 r2

### Phép đối xứng trục

Một [**phép đối xứng trục**](gloss:reflection) là một phép biến hình mà “lật” hoặc “phản chiếu” một hình qua một đường thẳng. Đường thẳng này được gọi là **trục đối xứng**.

Hãy vẽ trục đối xứng cho các ví dụ sau đây:

::: column(width=220)

```
x-geopad.draw.reflection(width=220 height=180 grid=20 no-points): svg
  path(x="polygon(point(2,1),point(1,2),point(2,3),point(8,2))" style="stroke: #363644; stroke-width: 3px; fill: rgba(179,4,105,0.4)" name="from0")
  path(hidden name="line0" x="line(point(-1,4),point(11,4))")
  path(x="from0.reflect(line0)" style="stroke: #363644; stroke-width: 3px; fill: rgba(179,4,105,0.4)")
```

::: column(width=220)

```
x-geopad.draw.reflection(width=220 height=180 grid=20 no-points): svg
  path(x="polygon(point(1,1),point(1,5),point(3,5),point(2,3),point(4,1))" style="stroke: #363644; stroke-width: 3px; fill: rgba(154,24,130,0.4)" name="from1")
  path(hidden name="line1" x="line(point(9,-1),point(-1,9))")
  path(x="from1.reflect(line1)" style="stroke: #363644; stroke-width: 3px; fill: rgba(154,24,130,0.4)")
```

::: column(width=220)

```
x-geopad.draw.reflection(width=220 height=180 grid=20 no-points)
  x-img.background(src="images/rorschach.jpg" width=220 height=180 alt="Rorschach Test")
  svg
    path(hidden name="line2" x="line(point(5,-1),point(5,9))")
```

:::

---

> id: reflections-1 goals: r0 r1 r2

Bây giờ đến lượt bạn - hãy vẽ hình đối xứng cho các ví dụ dưới đây:

::: column(width=220)

```
x-geopad.draw(width=220 height=180 grid=20 no-points): svg
  path(x="polygon(point(1,2),point(3,1),point(4,3),point(4,5),point(2,6),point(1,4))" name="from0" style="fill: rgba(105,63,180,0.4)")
  path.red(x="line(point(5,0), point(5,1))" name="line0")
  path.finished(hidden x="from0.reflect(line0)" name="to0" style="fill: rgba(105,63,180,0.4)")
```

::: column(width=220)

```
x-geopad.draw(width=220 height=180 grid=20 no-points): svg
  path(x="polygon(point(2,6),point(6,4),point(8,6),point(5,7))" name="from1" style="fill: rgba(80,83,205,0.4)")
  path.red(x="line(point(-1,4), point(11,4))" name="line1")
  path.finished(hidden x="from1.reflect(line1)" name="to1" style="fill: rgba(80,83,205,0.4)")
```

::: column(width=220)

```
x-geopad.draw(width=220 height=180 grid=20 no-points): svg
  path(x="polygon(point(2,3),point(3,3),point(3,5),point(5,5),point(5,6),point(2,6))" name="from2" style="fill: rgba(56,102,230,0.4)")
  path.red(x="line(point(2,1), point(3,2))" name="line2")
  path.finished(hidden x="from2.reflect(line2)" name="to2" style="fill: rgba(56,102,230,0.4)")
```

:::

---

> id: reflections-2

Hãy lưu ý rằng nếu một điểm nằm trên trục đối xứng, thì điểm này sẽ [[đứng yên|xoay|bị lật ngược]] khi qua phép đối xứng trục: *{span.reveal(when="blank-0")} ảnh của nó là chính nó.*

---

> id: reflections-3

Ở tất cả các ví dụ trên, các trục đối xứng là các đường nằm ngang, thẳng đứng, hoặc nghiêng một góc 45° – điều này khiến việc vẽ chúng đơn giản. Trong trường không như trên, việc dựng hình sẽ cần thêm một chút công sức:

::: column(width=300)

```
x-geopad.sticky(width=300): svg
  circle.move.pulsate(name="l1" cx="180" cy="30" target="refl")
  circle.move.pulsate(name="l2" cx="120" cy="270" target="refl")
  path(name="refl" x="line(l1,l2)" target="refl")

  circle.reveal(name="a" x="point(60,50)" when="next-0" animation="pop" target="circ")
  circle(name="b" x="point(120,100)" hidden)
  circle(name="c" x="point(110,170)" hidden)
  circle(name="d" x="point(65,200)" hidden)
  circle(name="e" x="point(30,120)" hidden)

  circle.reveal(name="p" x="refl.project(a)" when="next-0" animation="pop" delay=1500)
  path.reveal.fill.light(x="angle(a,p,l1)" size=16 when="next-0" delay=1500)

  circle.reveal(name="a1" x="a.reflect(refl)" when="next-1" animation="pop" target="circ")
  circle(name="b1" x="b.reflect(refl)" hidden)
  circle(name="c1" x="c.reflect(refl)" hidden)
  circle(name="d1" x="d.reflect(refl)" hidden)
  circle(name="e1" x="e.reflect(refl)" hidden)

  path.fill.blue(x="polygon(a,b,c,d,e)")
  path.fill.reveal.blue1(x="polygon(a1,b1,c1,d1,e1)" when="next-3")

  path.reveal(x="line(a,a1)" when="next-0" animation="draw" delay=1000)
  path.reveal.thin.light(x="segment(b,b1)" when="next-2" animation="draw" delay=400)
  path.reveal.thin.light(x="segment(c,c1)" when="next-2" animation="draw" delay=500)
  path.reveal.thin.light(x="segment(d,d1)" when="next-2" animation="draw" delay=600)
  path.reveal.thin.light(x="segment(e,e1)" when="next-2" animation="draw" delay=700)

  circle.transparent(name="ax" x="refl.project(a)" target="circ")
  path.transparent(x="segment(a,ax)" target="d1 circ")
  path.transparent(x="segment(a1,ax)" target="d2 circ")
  path.transparent(x="circle(ax,distance(a,ax))" target="circ")
```

::: column.grow {.r} Để tìm ảnh của hình này qua [trục đối xứng](target:refl), chúng ta phải tìm ảnh của từng [đỉnh](gloss:polygon-vertex) của hình rồi nối tất cả chúng lại. [Tiếp tục](btn:next)

{.r.reveal(when="next-0")} Bạn hãy chọn một trong các đỉnh, sau đó vẽ một đường thẳng vuông góc với trục đối xứng qua đỉnh vừa chọn. [Tiếp tục](btn:next)

{.r.reveal(when="next-1")} Giờ chúng ta có thể đo [khoảng cách](target:d1) từ đỉnh đến trục đối xứng, và vẽ điểm [cùng khoảng cách](target:d2) tới đường thẳng ở bên còn lại. *{span.lgrey}(Chúng ta có thể dùng thước hoặc [com-pa](target:circ) để làm việc này.)* [Tiếp tục](btn:next)

{.r.reveal(when="next-2")} Chúng ta có thể làm tương tự cho các đỉnh còn lại của hình. [Tiếp tục](btn:next)

{.r.reveal(when="next-3")} Bây giờ chúng ta chỉ cần nối tất cả các điểm ảnh theo đúng thứ tự, và chúng ta sẽ tìm được ảnh của hình ban đầu! :::

---

> id: rotations goals: r0 r1 r2

### Phép quay

Một [**phép quay**](gloss:rotation) là một phép biến hình “quay” một hình theo một góc xác định quanh một điểm cố định. Điểm đó được gọi là [**tâm quay**](gloss:center-of-rotation). Các phép quay có thể cùng chiều hoặc ngược chiều kim đồng hồ.

Hãy thử quay các hình dưới đây quanh tâm quay màu đỏ:

::: column(width=220)

```
x-geopad.draw(width=220 height=180 grid=20 no-points): svg
  path(x="polygon(point(2,2),point(2,5),point(5,5),point(5,2))" name="from0" style="fill: rgba(34,132,213,0.4)")
  circle.red(x="point(5,6)" name="c0")
  path.finished(hidden x="from0.rotate(pi/2,c0)" name="to0" style="fill: rgba(34,132,213,0.4)")
```

{.caption} Quay 90° cùng chiều kim đồng hồ. ::: column(width=220)

```
x-geopad.draw(width=220 height=180 grid=20 no-points): svg
  path(x="polygon(point(3,2),point(8,1),point(9,4))" name="from1" style="fill: rgba(40,151,130,0.4)")
  circle.red(x="point(5,4)" name="c1")
  path.finished(hidden x="from1.rotate(pi,c1)" name="to1" style="fill: rgba(40,151,130,0.4)")
```

{.caption} Quay 180°. ::: column(width=220)

```
x-geopad.draw(width=220 height=180 grid=20 no-points): svg
  path(x="polygon(point(3,0),point(8,0),point(8,4),point(1,4))" name="from2" style="fill: rgba(46,169,46,0.4)")
  circle.red(x="point(6,3)" name="c2")
  path.finished(hidden x="from2.rotate(-pi/2,c2)" name="to2" style="fill: rgba(46,169,46,0.4)")
```

{.caption} Quay 90° ngược chiều kim đồng hồ. :::

---

> id: rotations-1

::: column(width=300)

```
x-geopad.sticky(width=300): svg
  circle.move.pulsate(name="rot" cx="150" cy="250" target="rot angle compass protractor")

  circle.reveal(name="a" x="point(270,190)" when="next-0" animation="pop" target="compass")
  circle(name="b" x="point(280,110)" hidden)
  circle(name="c" x="point(210,80)" hidden)
  circle(name="d" x="point(190,170)" hidden)
  circle(name="e" x="point(220,200)" hidden)

  circle.reveal(name="a1" x="a.rotate(-ang/18*pi,rot)" when="next-2" animation="pop" target="a1 compass")
  circle(name="b1" x="b.rotate(-ang/18*pi,rot)" hidden)
  circle(name="c1" x="c.rotate(-ang/18*pi,rot)" hidden)
  circle(name="d1" x="d.rotate(-ang/18*pi,rot)" hidden)
  circle(name="e1" x="e.rotate(-ang/18*pi,rot)" hidden)

  path.fill.green(x="polygon(a,b,c,d,e)")
  path.fill.reveal.green1(x="polygon(a1,b1,c1,d1,e1)" when="next-4")

  path.transparent.light.fill(x="arc(rot,a.rotate(pi,rot),pi)" target="protractor")
  path.reveal.light.fill(x="angle(a1,rot,a)" when="next-1" target="angle protractor")

  path.reveal(x="segment(a,rot)" when="next-0" animation="draw" delay=500 target="angle compass protractor")
  path.reveal.thin.light(x="segment(rot,b)" when="next-3" animation="draw" delay=400)
  path.reveal.thin.light(x="segment(rot,c)" when="next-3" animation="draw" delay=500)
  path.reveal.thin.light(x="segment(rot,d)" when="next-3" animation="draw" delay=600)
  path.reveal.thin.light(x="segment(rot,e)" when="next-3" animation="draw" delay=700)

  path.reveal(x="ray(rot,a1)" when="next-1" animation="draw" delay=500 target="angle l2")
  path.reveal.thin.light(x="segment(rot,b1)" when="next-3" animation="draw" delay=800)
  path.reveal.thin.light(x="segment(rot,c1)" when="next-3" animation="draw" delay=900 )
  path.reveal.thin.light(x="segment(rot,d1)" when="next-3" animation="draw" delay=1000)
  path.reveal.thin.light(x="segment(rot,e1)" when="next-3" animation="draw" delay=1100)

  path.transparent(x="segment(rot,a1)" target="compass protractor")
  path.transparent(x="circle(rot,distance(rot,a))" target="compass")
```

::: column.grow Việc vẽ các phép quay không ở góc 90° hay 180° sẽ khó hơn nhiều. Hãy cùng thử quay hình này theo góc ${10*ang}{ang|6|-18,18,1}° quanh [tâm quay](target:rot).

{.r} Cũng giống như phép đối xứng trục, chúng ta phải tìm ảnh của từng đỉnh của hình ban đầu. [Tiếp tục](btn:next)

{.r.reveal(when="next-0")} Chúng ta bắt đầu bằng việc chọn một đỉnh của hình và vẽ một đường thẳng nối đỉnh vừa chọn đến tâm quay. [Tiếp tục](btn:next)

{.r.reveal(when="next-1")}  Chúng ta có thể dùng [thước đo độ](target:protractor) để đo một [góc ${ang*10}°](target:angle) quanh tâm quay. Hãy vẽ một [đường thẳng thứ hai](target:l2) ở số đo góc này. [Tiếp tục](btn:next)

{.r.reveal(when="next-2")} Chúng ta có thể dùng [com-pa](target:compass) hoặc thước để tìm một [điểm](target:a1) có cùng khoảng cách đến tâm quay trên đoạn thẳng mới này. [Tiếp tục](btn:next)

{.r.reveal(when="next-3")} Bây giờ chúng ta sẽ lập lại các bước trên cho tất cả các đỉnh của hình [Tiếp tục](btn:next)

{.reveal(when="next-4")} Và cuối cùng, cũng như trước, chúng ta nối tất cả các điểm ảnh theo đúng thứ tự để lấy được ảnh của hình ban đầu. :::

---

> id: composition-1

Phép biến hình là một khái niệm quan trọng không những trong ngành trong toán học chứ không chỉ riêng hình học. Ví dụ, bạn có thể biến đổi [*các hàm số*](gloss:function) bằng cách dịch chuyển hoặc xoay [đồ thị](gloss:function-graph) của hàm. Bạn cũng có thể dùng các phép biến hình để xác định xem hai hình có [đồng dạng](gloss:congruent) không.

---

## Sự tương đẳng

> section: congruence sectionStatus: dev

TODO

---

### Phép biến hình hợp

Tất nhiên, chúng ta có thể kết hợp nhiều phép tịnh tiến, đối xứng trục và xoay để tạo nên các phép biến hình phức tạp hơn

{.todo} TODO Ví dụ

Tuy vậy, hóa ra rằng kết hợp bao nhiêu phép biến hình cũng như nhau: bạn luôn có thể tìm một phép biến hình để thực hiện nó ngay trong một lượt!

{.todo} TODO Máy tính phép biến hình hợp

Combining two reflections is particularly interesting. There are two different cases we need to consider:

::: column.grow Nếu hai trục đối xứng song song với nhau, kết quả sẽ tương đương với một phép tịnh tiến. Hướng của phép tịnh tiến sẽ vuông góc với các trục đối xứng, và khoảng cách là gấp đôi khoảng cách giữa hai trục.

{.todo} TODO Animation ::: column.grow Nếu hai trục đối xứng giao nhau, kết quả sẽ tương đương một phép quay. Tâm quay sẽ là giao điểm của hai trục, và góc quay sẽ là gấp đôi góc tạo bởi hai trục

{.todo} TODO Animation :::

---

## Tính đối xứng

> id: symmetry goals: play-0 play-1 section: symmetry

[**Tính đối xứng**](gloss:symmetry) hiện diễn ở mọi nơi xung quanh ta, và là một khái niệm trực quan: các bộ phận khác nhau trên cùng một vật nhìn *giống nhau* theo một cách nào đó. Bằng cách dùng các phép biến hình, chúng ta có thể đưa ra một định nghĩa Toán học cho tính đối xứng:

{.definition} Một vật có *tính đối xứng* nếu vật đó không thay đổi sau một phép biến hình nào đó.

::: column.grow

```
.symmetry
  img(src="images/symmetry-1.png" width=320 height=240)
  img(src="images/symmetry-1.png" width=320 height=240)
  x-play-btn
```

{.text-center} Chúng ta có thể lật con bướm này, và kết quả vẫn sẽ nhìn giống con bướm ban đầu. Ta gọi đây là **đối xứng trục**.

::: column.grow

```
.symmetry
  img(src="images/symmetry-2.jpg" width=320 height=240)
  img(src="images/symmetry-2.jpg" width=320 height=240)
  x-play-btn
```

{.text-center} Ta có thể xoay bông hoa này, và kết quả vẫn sẽ nhìn giống bông hoa ban đầu. Ta gọi đây là **đối xứng quay**. :::

---

> id: reflectional-symmetry

### Đối xứng trục

Một hình có tính [**đối xứng trục**](gloss:reflectional-symmetry) nếu hình này không thay đổi sau phép đối xứng trục. Đường thẳng được dùng chính là [**trục đối xứng**](gloss:axis-of-symmetry), và nó chia hình thành hai nửa [[tương đẳng|bằng nhau|gần giống nhau]]. Một số hình có thể có nhiều hơn một trục đối xứng.

---

> id: reflectional-symmetry-1 goals: r0 r1 r2 r3 r4 r5

Hãy vẽ tất cả các trục đối xứng cho sáu ảnh và hình sau:

::: column(width=220)

```
x-geopad.draw.reflection(width=220 height=180 grid=20 no-points)
  x-img.background(src="images/lake.jpg" width=220 height=180 alt="Lake")
  svg
    path(hidden name="line0" x="line(point(-1,4),point(11,4))")
```

::: column(width=220)

```
x-geopad.draw.reflection(width=220 height=180 grid=20 no-points)
  x-img.background(src="images/beijing.jpg" width=220 height=180 alt="Forbidden City in Beijing")
  svg
    path(hidden name="line1" x="line(point(5,-1),point(5,9))")
```

::: column(width=220)

```
x-geopad.draw.reflection(width=220 height=180 grid=20 no-points)
  x-img.background(src="images/blue-butterfly.jpg" width=220 height=180 alt="Butterfly")
  svg
    path(hidden name="line2" x="line(point(1,-1),point(11,9))")
```

::: column(width=220)

```
x-geopad.draw.reflection(width=220 height=180 grid=20 no-points): svg
  path(x="polygon(point(2,2),point(5,1),point(8,2),point(9,4),point(8,6),point(5,7),point(2,6),point(1,4))" style="stroke: #363644; stroke-width: 3px; fill: rgba(255,148,31,0.4)")
  path(hidden name="line3a" x="line(point(-1,4),point(11,4))")
  path(hidden name="line3b" x="line(point(5,-1),point(5,9))")
```

{.caption} Hình này có [[2]] trục đối xứng. ::: column(width=220)

```
x-geopad.draw.reflection(width=220 height=180 grid=20 no-points): svg
  path(x="polygon(point(3,2),point(7,2),point(7,6),point(3,6))" style="stroke: #363644; stroke-width: 3px; fill: rgba(242,124,43,0.4)")
  path(hidden name="line4a" x="line(point(-1,4),point(11,4))")
  path(hidden name="line4b" x="line(point(5,-1),point(5,9))")
  path(hidden name="line4c" x="line(point(0,-1),point(10,9))")
  path(hidden name="line4d" x="line(point(10,-1),point(0,9))")
```

{.caption} Hình vuông có [[4]] trục đối xứng. ::: column(width=220)

```
x-geopad.draw.reflection(width=220 height=180 grid=20 no-points): svg
  path(x="polygon(point(3,1),point(9,3),point(8,6),point(2,4))" style="stroke: #363644; stroke-width: 3px; fill: rgba(230,100,56,0.4)")
  path(hidden name="line5a" x="line(point(-2,1),point(13,6))")
  path(hidden name="line5b" x="line(point(7,-1),point(3,11))")
```

{.caption} Hình này có [[2]] trục đối xứng. :::

---

> id: alphabet

Nhiều kí tự trong bảng chữ cái cũng có tính đối xứng trục. Hãy chọn tất cả các chữ cái như vậy dưới đây:

```
x-picker.letters
  - let c = ['#D92120', '#E6642C', '#E68E34', '#D9AD3C', '#B5BD4C', '#7FB972', '#63AD99', '#55A1B1', '#488BC2', '#4065B1', '#413B93', '#781C81']
  for l, i in 'ABCDEFGHIJKLMNOPQRSTUVWXYZ'.split('')
    if 'FGJKLNPQRSZ'.indexOf(l) < 0
      .item(style=`color: ${c[i%12]}`)= l
    else
      .item(data-error="letter-not-symmetric" style=`color: ${c[i%12]}`)= l
```

---

> id: reflectional-symmetry-2 goals: r0 r1 r2

Dưới đây là thêm một vài hình. Hãy hoàn thiện chúng sao cho chúng có tính đối xứng trục:

::: column(width=220)

```
x-geopad.draw(width=220 height=180 grid=20 no-points): svg
  path.fill.finished(hidden x="polygon(point(8,5),point(9,3),point(9,2),point(8,1),point(6,1),point(5,2),point(4,1),point(2,1),point(1,2),point(1,3),point(2,5),point(5,7))" style="fill: rgba(179,4,105,0.4)")
  path(x="polyline(point(5,2),point(4,1),point(2,1),point(1,2),point(1,3),point(2,5),point(5,7))" name="from0")
  path.red(x="line(point(5,-1),point(5,9))" name="line0")
  path(hidden x="from0.reflect(line0)" name="to0")
```

::: column(width=220)

```
x-geopad.draw(width=220 height=180 grid=20 no-points): svg
  path.fill.finished(hidden x="polygon(point(1,5),point(1,3),point(6,3),point(4,1),point(5,0),point(9,4),point(5,8),point(4,7),point(6,5))" style="fill: rgba(154,24,130,0.4)")
  path(x="polyline(point(1,4),point(1,3),point(6,3),point(4,1),point(5,0),point(9,4))" name="from1")
  path.red(x="line(point(-1,4),point(11,4))" name="line1")
  path(hidden x="from1.reflect(line1)" name="to1")
```

::: column(width=220)

```
x-geopad.draw(width=220 height=180 grid=20 no-points): svg
  path.fill.finished(hidden x="polygon(point(2,1),point(8,1),point(9,2),point(9,6),point(8,7),point(2,7),point(1,6),point(1,2))" style="fill: rgba(130,43,155,0.4)")
  path(x="polyline(point(5,1),point(8,1),point(9,2),point(9,4))")
  path.red(x="line(point(5,-1),point(5,9))")
  path.red(x="line(point(-1,4),point(11,4))")
  path(hidden x="polyline(point(5,1),point(2,1),point(1,2),point(1,6),point(2,7),point(8,7),point(9,6),point(9,4))" name="to2")
```

:::

---

> id: palindromes goals: p0 p1 p2
<<<<<<< Updated upstream

Các hình, chữ và ảnh có thể có tính đối xứng, và các con số, các từ và các đoạn văn cũng vậy!

Ví dụ như “25352” và “ANNA” khi đọc xuôi và đọc ngược đều giống nhau. Các con số và các từ như vậy được gọi là [**Palindrome**](gloss:palindrome). Bạn có thể nghĩ ra thêm các palindrome khác không?

=======

Các hình, chữ và ảnh có thể có tính đối xứng, và các con số, các từ và các đoạn văn cũng vậy!

Ví dụ như “25352” và “ANNA” khi đọc xuôi và đọc ngược đều giống nhau. Các con số và các từ như vậy được gọi là [**Palindrome**](gloss:palindrome). Bạn có thể nghĩ ra thêm các palindrome khác không?

>>>>>>> Stashed changes
```
form.palindromes.text-center.form-field
  input(type="text")
  span.check(when="p0")
  input(type="text")
  span.check(when="p1")
  input(type="text")
  span.check(when="p2")
```

---

> id: palindromes-1

Nếu chúng ta bỏ qua khoảng cách và dấu câu, các câu ngắn dưới đây cũng có tính đối xứng trục. Bạn có thể tự nghĩ ra một câu như vậy không?
<<<<<<< Updated upstream

{.text-center} Never odd or even.<br> A [[nut]] for a jar of tuna.<br> Yo, banana [[boy]]!

=======

{.text-center} Never odd or even.<br> A [[nut]] for a jar of tuna.<br> Yo, banana [[boy]]!

>>>>>>> Stashed changes
{.reveal(when="blank-0 blank-1")} Tuy nhiên các Palindrome không chỉ để cho vui, chúng có vai trò quan trọng trong thực tế. Vài năm trước, các nhà khoa học phát hiện ra rằng [DNA](gloss:dna) của chúng ta có tính palindrome. Điều này giúp chúng ta chống chịu các sự đột biến và tổn thương tốt hơn – bởi mỗi mảnh DNA có một bản sao dự phòng.

---

> id: rotational-symmetry

### Đối xứng quay

::: column.grow Một hình có tính [**đối xứng quay**](gloss:rotational-symmetry) nếu nó nhìn giống ban đầu sau khi bị xoay (bởi một góc ít hơn 360°). [Tâm quay](gloss:center-of-rotation) thường sẽ chỉ là ở giữa hình.

[**Bậc đối xứng**](gloss:order-of-symmetry) là số các hướng riêng biệt mà hình này trông giống chính nó. Bạn cũng có thể nghĩ khái niệm này giống như *số lần mà bạn có thể quay hình*  trước khi quay về hình ban đầu. Ví dụ, bông hoa tuyết này có bậc đối xứng là [[6]].

{.reveal(when="blank-0")} Góc của mỗi lần quay bằng `"360°"/"bậc đối xứng"`. Đối với hình bông hoa tuyết này, góc quay bằng `"360°"/6 = input(60)°`.

::: column(width=240)

```
include svg/snowflake.svg
```

:::

```
// Maybe have another alphabeth to select all letters with rotational symmetry?
```

---

> id: rotational-symmetry-1

Tìm bậc đối xứng và góc quay của các hình sau đây:

::: column(width=220)

```
img(src="images/clover.jpg" width=200 height=200)
```

{.caption} Bậc [[4]], góc quay [[90]]°

::: column(width=220)

```
img(src="images/playing-card.jpg" width=200 height=200)
```

{.caption} Bậc [[2]], góc quay [[180]]°

::: column(width=220)

```
img(src="images/flower.jpg" width=200 height=200)
```

{.caption} Bậc [[8]], góc quay [[45]]°

:::

---

> id: rotational-symmetry-2 goals: r0 r1 r2
<<<<<<< Updated upstream

Giờ hãy hoàn thiện các hình sau sao cho chúng có tính đối xứng quay:

::: column(width=220)

=======

Giờ hãy hoàn thiện các hình sau sao cho chúng có tính đối xứng quay:

::: column(width=220)

>>>>>>> Stashed changes
```
x-geopad.draw(width=220 height=180 grid=20 no-points): svg
  circle.red(x="point(5,4)")
  path.fill.finished(hidden x="polygon(point(5,0),point(6,3),point(9,4),point(6,5),point(5,8),point(4,5),point(1,4),point(4,3))" style="fill: rgba(56,102,230,0.4)")
  path(x="polyline(point(5,0),point(6,3),point(9,4))")
  path.red(x="segment(point(5,-1),point(5,4))")
  path.red(x="segment(point(5,4),point(11,4))")
  path(hidden x="polyline(point(9,4),point(6,5),point(5,8),point(4,5),point(1,4),point(4,3),point(5,0))" name="to0")
```

{.caption} Bậc 4 ::: column(width=220)

```
x-geopad.draw(width=220 height=180 grid=20 no-points): svg
  circle.red(x="point(5,4)" name="c1")
  path.fill.finished(hidden x="polygon(point(6,2),point(1,2),point(1,4),point(4,6),point(9,6),point(9,4))" style="fill: rgba(40,151,130,0.4)")
  path(x="polyline(point(5,2),point(1,2),point(1,4),point(4,6),point(5,6))" name="from1")
  path.red(x="segment(point(5,-1),point(5,9))")
  path(hidden x="from1.rotate(pi,c1)" name="to1")
```

{.caption} Bậc 2 ::: column(width=220)

```
x-geopad.draw(width=220 height=180 grid=20 no-points): svg
  circle.red(x="point(5,4)")
  path.fill.finished(hidden x="polygon(point(4,4),point(2,6),point(3,7),point(5,5),point(7,7),point(8,6),point(6,4),point(8,2),point(7,1),point(5,3),point(3,1),point(2,2))" style="fill: rgba(83,174,9,0.4)")
  path(x="polyline(point(5,3),point(3,1),point(2,2),point(4,4))")
  path.red(x="segment(point(5,-1),point(5,4))")
  path.red(x="segment(point(5,4),point(-1,4))")
  path(hidden x="polyline(point(4,4),point(2,6),point(3,7),point(5,5),point(7,7),point(8,6),point(6,4),point(8,2),point(7,1),point(5,3))" name="to2")
```

{.caption} Bậc 4 :::

---

## Các nhóm đối xứng và Hoa văn đối xứng trong Mỹ thuật

> id: groups section: symmetry-groups

```
// HINT: To recognise different configurations, we need to highlight the
// four corners in different colours.
```

Một số hình có hơn một tính đối xứng - [hình vuông](gloss:square) là một ví dụ điển hình.

::: column(width=400 parent="padded-thin")

```
.cubes
  img.cube.reveal(src="images/cube-0.svg" width=80 height=80 when="blank-1 blank-2 blank-3" delay=1000 animation="pop")
  img.cube.reveal(src="images/cube-1.svg" width=80 height=80 when="blank-1" animation="pop")
  img.cube.reveal(src="images/cube-2.svg" width=80 height=80 when="blank-2" animation="pop")
  img.cube.reveal(src="images/cube-3.svg" width=80 height=80 when="blank-3" animation="pop")
  img.cube.reveal(src="images/cube-4.svg" width=80 height=80 when="blank-0" animation="pop")
  img.cube.reveal(src="images/cube-5.svg" width=80 height=80 when="blank-0" delay=200 animation="pop")
  img.cube.reveal(src="images/cube-6.svg" width=80 height=80 when="blank-0" delay=400 animation="pop")
  img.cube.reveal(src="images/cube-7.svg" width=80 height=80 when="blank-0" delay=600 animation="pop")
```

::: column.grow(width=200) Bạn đã chỉ ra rằng hình vuông có [[4]] trục đối xứng ở phần trước.

{.reveal(when="blank-0")} It also has rotational symmetry by [[90]]°, [[180]]° and [[270]]°.

{.reveal(when="blank-1 blank-2 blank-3")} Cuối cùng, chúng ta có thể nghĩ rằng “không làm gì cả” cũng là một dạng đặc biệt của tính đối xứng – vì kết quả mà ta nhận được (hiển nhiên) cũng chính là hình ban đầu. Đây được gọi là **phép đồng nhất**.

{.reveal(when="blank-1 blank-2 blank-3" delay=1000)} Tổng cộng, chúng ta đã tìm được [[8]] “phép đối xứng khác nhau cho một hình vuông”. :::

---

> id: add-symmetries goals: sum-0 sum-1

Bây giờ, chúng ta có thể thực hiện một vài phép Toán Số học với các phép đối xứng này. Ví dụ, chúng ta có thể *cộng* hai phép đối xứng để tạo ra một phép đối xứng mới:

::: column(width=260)

```
.text-center
  img.cube(src="images/cube-1.svg" width=54 height=54)
  mo +
  img.cube(src="images/cube-1.svg" width=54 height=54)
  mo =
  span.sym-sum.pending(tabindex=0): img.cube(src="images/cube-2.svg" width=54 height=54)
x-gesture(target=".sym-sum")
```

::: column(width=260)

```
.text-center
  img.cube(src="images/cube-2.svg" width=54 height=54)
  mo +
  img.cube(src="images/cube-6.svg" width=54 height=54)
  mo =
  span.sym-sum.pending(tabindex=0): img.cube.ani-sym(src="images/cube-4.svg" width=54 height=54)
```

:::

---

> id: calculator title: Symmetry Calculator goals: calculate

Bất cứ khi nào bạn cộng hai phép đối xứng của một hình vuông, bạn sẽ có một phép đối xứng mới. Bạn có thể dùng thử “máy tính cho phép đối xứng” dưới đây:

```
.calculator
  .display
    .operator +
    .operator =
    .clear ×
  .button(tabindex=0) + #[img.cube(src="images/cube-0.svg" width=40 height=40)]
  .button(tabindex=0) + #[img.cube(src="images/cube-1.svg" width=40 height=40)]
  .button(tabindex=0) + #[img.cube(src="images/cube-2.svg" width=40 height=40)]
  .button(tabindex=0) + #[img.cube(src="images/cube-3.svg" width=40 height=40)]
  .button(tabindex=0) + #[img.cube(src="images/cube-4.svg" width=40 height=40)]
  .button(tabindex=0) + #[img.cube(src="images/cube-5.svg" width=40 height=40)]
  .button(tabindex=0) + #[img.cube(src="images/cube-6.svg" width=40 height=40)]
  .button(tabindex=0) + #[img.cube(src="images/cube-7.svg" width=40 height=40)]
```

---

> id: symmetry-arithmetic

Hãy dành một chút thời gian để chơi với “máy tính cho phép đối xứng” này, và thử tự tìm kết quả. Bạn có thể dự đoán các kết quả cho các phép toán dưới đây không?

- Ta sẽ nhận được [[một phép quay|một phép đối xứng]] khi cộng hai phép quay (hoặc phép đồng nhất).
- Ta sẽ nhận được [[một phép quay|một phép đối xứng trục]] khi cộng hai phép đối xứng trục (hoặc phép đồng nhất).
- Giao hoán hai phép đối xứng khi thực hiện phép cộng [[đôi khi nhận được một kết quả khác|luôn luôn nhận được một kết quả khác|luôn luôn nhận được cùng một kết quả ]].
- Ta sẽ [[không nhận được gì mới|nhận được một phép đối xứng|nhận được một phép đảo ngược]] khi cộng với phép đồng nhất.

---

> id: group-axioms Bạn cũng có thể đã nhận ra rằng phép cộng của **{.m-orange}các phép đối xứng** là tương tự với phép cộng của **{.m-green}các số nguyên**:

Ở ví dụ trên, chúng ta đã bắt đầu với tám phép đối xứng của hình vuông. Thực tế, mọi hình hình học đều có **nhóm đối xứng** riêng và có thể có các phép biến hình khác nhau nhưng đều phải có ba tính chất trên.

```
ol.proof

  li.r
    | Cộng hai #[strong.m-orange phép đối xứng]/#[strong.m-green số nguyên] ta luôn nhận được một #[strong.m-orange phép đối xứng]/#[strong.m-green số nguyên] khác:
    .text-center.axiom
      img.cube(src="images/cube-2.svg" width=32 height=32)
      mo +
      img.cube(src="images/cube-6.svg" width=32 height=32)
      mo(value="=") =
      img.cube(src="images/cube-4.svg" width=32 height=32)
    .text-center.axiom
      mn 12
      mo +
      mn 7
      mo =
      mn 19
    .next-step Continue

  li.r.reveal(when="next-0")
    span.md Phép cộng của #[strong.m-orange các phép đối xứng]/#[strong.m-green các số nguyên] là [có tính kết hợp](gloss:associative):
    .text-center.axiom
      mfenced
        img.cube(src="images/cube-1.svg" width=32 height=32)
        mo +
        img.cube(src="images/cube-4.svg" width=32 height=32)
      mo +
      img.cube(src="images/cube-3.svg" width=32 height=32)
      mo(value="=") =
      img.cube(src="images/cube-1.svg" width=32 height=32)
      mo +
      mfenced
        img.cube(src="images/cube-4.svg" width=32 height=32)
        mo +
        img.cube(src="images/cube-3.svg" width=32 height=32)
    .text-center.axiom
      mfenced #[mn 4]#[mo +]#[mn 2]
      mo +
      mn 5
      mo =
      mn 4
      mo +
      mfenced #[mn 2]#[mo +]#[mn 5]
    .next-step Continue

  li.r.reveal(when="next-1")
    | Mọi #[strong.m-orange phép đối xứng]/#[strong.m-green số nguyên] đều có một #[strong nghịch đảo], là một #[strong.m-orange phép đối xứng]/#[strong.m-green số nguyên] khác mà khi thực hiện phép cộng, ta nhận được phép đồng nhất:
    .text-center.axiom
      img.cube(src="images/cube-1.svg" width=32 height=32)
      mo +
      img.cube(src="images/cube-3.svg" width=32 height=32)
      mo(value="=") =
      img.cube(src="images/cube-0.svg" width=32 height=32)
    .text-center.axiom
      mn 4
      mo +
      mn –4
      mo(value="=") =
      mn 0
    .next-step Continue
```

---

> id: groups-1

In mathematics, any collection that has these properties is called a [**group**](gloss:group). Some groups (like the **{.m-orange}symmetries** of a square) only have a finite number of elements. Others (like the **{.m-green}integers**) are infinite.

::: column.grow Ví dụ, nhóm đối xứng của các phân tử khác nhau có thể giúp các nhà khoa học dự đoán và giải thích các tính chất của các vật liệu tương ứng.

Nhóm cũng có thể được dùng để phân tích chiến lược để chiến thắng trong các trò chơi may rủi, xu hướng của vi-rút trong y học, các cách hòa âm phối khí trong âm nhạc, và nhiều ứng dụng khác,... ::: column(width=340)

::: column.grow For example, the symmetry groups of different molecules can help scientists predict and explain the properties of the corresponding materials.

Ở [chương trước](/course/transformations/symmetry), chúng ta đã thấy hai dạng khác nhau của phép đối xứng tương ứng với hai phép biến hình: phép quay và phép đối xứng trục. Nhưng chúng ta vẫn còn một phép đối xứng nữa và cũng là phép dời hình: [[phép tịnh tiến|phép quay|phép đối xứng trục]].

```
img(src="images/molecule.jpg" width=160 height=160 style="margin-right: 20px")
img(src="images/virus.jpg" width=160 height=160)
```

{.caption} Các tính chất của phân tử CCl<sub>4</sub> (trái) và Adenovirus (phải) được xác định bởi tính đối xứng của chúng. :::

---

### Nhóm Hình họa

> id: wallpaper-groups

::: column.grow

---

> id: wallpaper-groups-1 goals: play-0 play-1

{.caption} Hình lục giác tổ ong ::: column.grow

{.caption} Hoa văn gạch ốp tường :::

```
.symmetry(style="width: 320px; height: 240px;")
  img(src="images/honeycomb.jpg" width=376 height=276 style="margin: 0 0 -36px -56px; max-width: none;")
  img(src="images/honeycomb.jpg" width=376 height=276 style="margin: 0 0 -36px -56px; max-width: none;")
  x-play-btn
```

Ngoài phép đối xứng trục, phép quay và phép đối xứng tịnh tiến, ta còn có tới bốn loại phép dời hình: [**phép đối xứng lướt**](gloss:glide-reflection). Đây là sự kết hợp của một phép đối xứng trục và một phép tịnh tiến theo cùng một hướng của trục đối xứng.

```
.symmetry(style="width: 320px; height: 240px;")
  img(src="images/tiling.jpg" width=376 height=240 style="margin-left: -56px; max-width: none;")
  img(src="images/tiling.jpg" width=376 height=240 style="margin-left: -56px; max-width: none;")
  x-play-btn
```

Một mẫu hoa văn có thể được tạo nên bởi nhiều loại phép đối xứng. Giống như đối với hình vuông, chúng ta có thể tìm [nhóm đối xứng](gloss:symmetry-group) chứa tất cả các phép đối xứng khác nhau cho một mẫu hoa văn.

---

> id: footsteps

Những nhóm đối xứng này không giúp chúng ta có được những họa tiết bắt mắt (ví dụ như màu sắc và hình dáng), mà chỉ mô tả cho chúng ta cách *lặp đi lặp lại* các họa tiết này. Nhiều họa tiết phức tạp khác nhau có thể tạo nên bởi cùng một nhóm đối xứng – miễn là được sắp xếp và lặp đi lặp lại theo cùng một cách.

```
figure
  .footsteps
     img(src="images/footsteps.svg" width=650 height=120)
     img(src="images/footsteps.svg" width=650 height=120)
  x-slider(steps=100, style="max-width: 400px; margin: 24px auto")
```

---

> id: wallpaper-groups-2

::: column.grow

{.caption} Hai họa tiết này có cùng kiểu đối xứng, cho dù trông khác nhau. Bởi vì các phép đối xứng không đề cập đến màu sắc, hoặc hình dạng cụ thể. ::: column.grow

{.caption} Hai họa tiết này cũng có cùng kiểu đối xứng – mặc dù chúng trông giống với nhóm bên trái hơn là trông giống nhau. :::

```
.text-center
  img(src="images/wallpaper-1.svg" width=150 height=150 style="margin: 0 10px")
  img(src="images/wallpaper-2.svg" width=150 height=150 style="margin: 0 10px")
```

Như vậy, chúng ta có thể tạo ra vô số các họa tiết hoa văn từ 17 nhóm đối xứng khác nhau. Đây được gọi là **các nhóm hình họa**. Mọi nhóm hình họa được xác định bằng một sự kết hợp gồm các phép tịnh tiến, phép quay, phép đối xứng trục và phép đối xứng trục lướt. Bạn có nhận ra [tâm quay](gloss:center-of-rotation) và [trục đối xứng](gloss:axis-of-symmetry) ở các ví dụ dưới đây?

```
.text-center
  img(src="images/wallpaper-3.svg" width=150 height=150 style="margin: 0 10px")
  img(src="images/wallpaper-4.svg" width=150 height=150 style="margin: 0 10px")
```

Thật không may là rất khó để giải thích cặn kẽ và chứng minh tại sao lại có *17* nhóm đối xứng như vậy, điều này đòi hỏi rất nhiều kiến thức Toán cao cấp. Thay vào đó, bạn có thể tự vẽ và thiết kế họa tiết lặp đi lặp lại cho riêng bạn với mỗi nhóm đối xứng đã được liệt kê ở trên:

---

> id: wallpaper-groups-3 goals: gallery

::: column.grow Các nhóm hình họa chỉ được xây dựng trên mặt phẳng, với các họa tiết hai chiều. Chúng ta cũng có thể làm điều tương tự dành cho các họa tiết ba chiều: đây được gọi là các nhóm tinh thể, và có tất cả 219 nhóm!

```
x-gallery(slide-width="320")
  div
    img(src="images/wallpapers/p1.svg" width=360, height=240)
    p.caption <strong>Nhóm 1 – P1</strong><br>Chỉ có các phép tịnh tiến
  div
    img(src="images/wallpapers/p2.svg" width=360, height=240)
    p.caption <strong>Nhóm 2 – P2</strong><br>Phép quay bậc 2, phép tịnh tiến
  div
    img(src="images/wallpapers/p3.svg" width=360, height=240)
    p.caption <strong>Nhóm 3 – P3</strong><br>Phép quay bậc 3 (120°), phép tịnh tiến
  div
    img(src="images/wallpapers/p4.svg" width=360, height=240)
    p.caption <strong>Nhóm 4 – P4</strong><br>Bốn phép quay bậc 2 (180°), phép tịnh tiến
  div
    img(src="images/wallpapers/p6.svg" width=360, height=240)
    p.caption <strong>Nhóm 5 – P6</strong><br>Phép quay bậc 2, 3 và 6 (60°), phép tịnh tiến
  div
    img(src="images/wallpapers/pm.svg" width=360, height=240)
    p.caption <strong>Nhóm 6 – PM</strong><br>Các trục đối xứng song song, phép tịnh tiến
  div
    img(src="images/wallpapers/pmm.svg" width=360, height=240)
    p.caption <strong>Nhóm 7 – PMM</strong><br>Phép đối xứng trục vuông góc, phép quay bậc 2, phép tịnh tiến
  div
    img(src="images/wallpapers/p4m.svg" width=360, height=240)
    p.caption <strong>Nhóm 8 – P4M</strong><br>Phép quay (bậc 2 + 4), phép đối xứng trục, phép đối xứng trục lướt, phép tịnh tiến
  div
    img(src="images/wallpapers/p6m.svg" width=360, height=240)
    p.caption <strong>Nhóm 9 – P6M</strong><br>Phép quay (bậc 2 + 6), phép đối xứng trục, phép đối xứng trục lướt, phép tịnh tiến
  div
    img(src="images/wallpapers/p3m1.svg" width=360, height=240)
    p.caption <strong>Nhóm 10 – P3M1</strong><br>Phép quay 3, phép đối xứng trục, phép đối xứng trục lướt, phép tịnh tiến
  div
    img(src="images/wallpapers/p31m.svg" width=360, height=240)
    p.caption <strong>Nhóm 11 – P31M</strong><br>Phép quay 3, phép đối xứng trục, phép đối xứng trục lướt, phép tịnh tiến
  div
    img(src="images/wallpapers/p4g.svg" width=360, height=240)
    p.caption <strong>Nhóm 12 – P4G</strong><br>Phép quay (bậc 2 + 4), phép đối xứng trục, phép đối xứng trục lướt, phép tịnh tiến
  div
    img(src="images/wallpapers/cmm.svg" width=360, height=240)
    p.caption <strong>Nhóm 13 – CMM</strong><br>Phép đối xứng trục vuông góc, phép quay bậc 2, phép tịnh tiến
  div
    img(src="images/wallpapers/pmg.svg" width=360, height=240)
    p.caption <strong>Nhóm 14 – PMG</strong><br>Phép đối xứng trục, phép đối xứng trục lướt, phép quay 2, phép tịnh tiến
  div
    img(src="images/wallpapers/pg.svg" width=360, height=240)
    p.caption <strong>Nhóm 15 – PG</strong><br>phép đối xứng trục lướt song song, phép tịnh tiến
  div
    img(src="images/wallpapers/cm.svg" width=360, height=240)
    p.caption <strong>Nhóm 16 – CM</strong><br>Phép đối xứng trục, phép đối xứng trục lướt, phép tịnh tiến
  div
    img(src="images/wallpapers/pgg.svg" width=360, height=240)
    p.caption <strong>Nhóm 17 – PGG</strong><br>Phép đối xứng trục lướt vuông góc, phép quay bậc 2, phép tịnh tiến
```

---

> id: drawing title: Drawing Wallpaper Symmetries goals: draw-1 draw-2 switch

Ngoài các phép tịnh tiến, phép đối xứng trục, phép quay, và phép đối xứng trục lướt, các nhóm tinh thể này còn bao gồm thêm các phép đối xứng như **mặt phẳng lướt** và **trục vít**  (hãy nghĩ đến chuyển động khi mở nắp chai). ::: column(width=300)

```
figure: x-wallpaper
.other-students.reveal(when="draw-1 switch")
  h4 Một số sản phẩm của các bạn học sinh
  .row.padded-thin
    div(style="width: 224px"): img(src="images/user/wallpaper-1.png" width=240 height=160)
    div(style="width: 224px"): img(src="images/user/wallpaper-2.png" width=240 height=160)
    div(style="width: 224px"): img(src="images/user/wallpaper-3.png" width=240 height=160)
```

---

> id: crystallographic-groups

{.caption} Các phân tử của Boron-Nitride được sắp xếp trong mạng tinh thể này có một nhóm đối xứng ba chiều. :::

Cho đến nay, tất cả các nhóm đối xứng mà chúng ta thấy đều mang tính *trực quan* theo một nghĩa nào đó gồm các hình dạng, hình ảnh hoặc hoa văn. Thực tế, tính đối xứng còn có thể là một khái niệm rộng và trù tượng hơn: *tính bất biến*.

```
img(src="images/crystal.jpg" width=300 height=240)
```

Ví dụ, nếu như bạn thích nước ép táo như nước ép cam, thì khi đó sở thích của bạn là “đối xứng” dưới tác động của phép biến hình biến táo thành cam.

---

## Tính đối xứng trong Vật lý

> id: planets sectionBackground: dark stars section: physics

Vào năm 1915, nhà Toán học người Đức [Emmy Noether](bio:noether) đã quan sát thấy rằng một "điều gì đó tương tự" là đúng với [quy luật tự nhiên](gloss:laws-of-nature).

::: column.grow Ví dụ, kinh nghiệm của chúng ta chỉ ra rằng các định luật Vật lý là giống nhau ở mọi nơi trong vũ trụ. Không quan trọng nếu bạn tiến hành một thí nghiệm ở London, New York hoặc trên Sao Hỏa – các định luật Vật lý phải luôn giống nhau. Theo một cách nào đó, chúng ta có [[tính đối xứng tịnh tiến|tính đối xứng trục]].

{.reveal(when="blank-0")} Tương tự, không quan trọng nếu chúng ta tiến hành một thí nghiệm khi hướng về phía Bắc, phía Nam, phía Đông hoặc phía Tây: các định luật tự nhiên cũng có [[tính đối xứng quay|tính đối xứng trục lướt]].

{.reveal(when="blank-1")} Và cuối cùng, không quan trọng nếu chúng ta tiến hành một thí nghiệm trong hôm nay, ngày mai, hoặc trong cả một năm. Các định luật tự nhiên cũng có “tính đối xứng thời gian”. ::: column(width=300)

:::

Các “tính đối xứng” này thoạt đầu có vẻ khá vô nghĩa, nhưng chúng thực sự có thể cho chúng ta biết rất nhiều điều về vũ trụ. Emmy Noether đã cố gắng chứng minh mọi tính đối xứng đều tương ứng với một đại lượng Vật lý nhất định được *bảo toàn*.

```
include svg/planets.svg
```

Ví dụ, tính đối xứng thời gian hàm ý rằng **Năng lượng** phải được bảo toàn trong vũ trụ của chúng ta: bạn có thể chuyển đổi năng lượng từ dạng này sang dạng khác (ví dụ: ánh sáng thành điện), nhưng bạn không thể tạo ra hoặc triệt tiêu năng lượng. Tổng lượng năng lượng trong vũ trụ sẽ không đổi.

---

> id: planets-1

::: column(width=220)

::: column.grow Hóa ra, chỉ với các kiến thức về tính đối xứng, các nhà Vật lý có thể suy ra hầu hết các định luật tự nhiên chi phối vu trụ của chúng ta – mà không cần thực hiện bất kì một thí nghiệm hay quan sát gì cả.

```
figure
  x-img(src="images/cern.jpg" width=760 height=400 credit="© CERN" alt="Large Hadron Collider in CERN")
  p.caption CERN là máy gia tốc hạt lớn nhất thế giới. Các nhà khoa học phá vỡ các hạt cơ bản với tốc độ cực lớn, để có thể nghiên cứu thêm các tính chất của chúng. Bạn có thể hình dung được kích cỡ của máy này khi so sánh với người đang đứng ở phía dưới bức tranh.
```

Tính đối xứng thậm chí có thể dự đoán sự tồn tại của các hạt cơ bản. Một ví dụ nỗi tiếng là sự tồn tại của hạt **Higgs Boson**: nó được các nhà Vật lý lý thuyết dự đoán vào những năm 1960, nhưng chưa từng được quan sát thực tế cho mãi đến năm 2012 :::

```
x-img(src="images/higgs.png" width=220 height=150 alt="Particle Fragments")
p.caption Các đường đi của các mảnh hạt sau khi va chạm.
```

Đến bây giờ, chúng ta chỉ mới nghiên cứu về các [[phép dời hình|phép đồng dạng|phép trực quan]]. *{span.reveal(when="blank-0")} Giờ đây, chúng ta sẽ tiếp tục nghiên cứu về [**phép vị tự**](gloss:dilation): phép biến hình thay đổi kích thước của hình ban đầu bằng cách phóng to hoặc thu nhỏ hình đó.*

::: column.grow

---

## Dilations

> id: dilations section: dilations

Phép vị tự có một [**tâm vị tự**](target:center) và một [**tỉ số vị tự**](-%3E.scale-target). Tâm vị tự là một điểm tham chiếu cho phép vị tự và tỉ số vị tự cho ta biết mức độ kéo dài hoặc thu nhỏ.

---

> id: dilations-1

Nếu [tỉ số vị tự](gloss:scale-factor) nằm giữa khoảng 0 đến 1, ảnh nhận được sẽ [[nhỏ|lớn]] hơn hình ban đầu. Nếu tỉ số vị tự lớn hơn 1, ảnh nhận được sẽ [[lớn|nhỏ]] hơn hình ban đầu.

::: column(width=300)

{.text-center.scale-target} Tỉ số vị tự: ${s}{s|2|0,3,0.1} :::

{.todo} Các phần tiếp theo về phép vị tự sẽ được đưa đến quý bạn đọc sớm nhất có thể.

```
x-geopad(width=300 height=240): svg
  circle.move(name="C" cx=40 cy=35 target="center")

  circle(hidden name="a" x="point(140,55)")
  circle(hidden name="b" x="point(160,115)")
  circle(hidden name="c" x="point(60,130)")

  circle(hidden name="a1" x="a.subtract(C).scale(s).add(C)")
  circle(hidden name="b1" x="b.subtract(C).scale(s).add(C)")
  circle(hidden name="c1" x="c.subtract(C).scale(s).add(C)")

  path.fill.green(x="polygon(a,b,c)" label="A" label-class="white")
  path.fill.blue(x="polygon(a1,b1,c1)" label="A’" label-class="white")

  path.light.thin(x="segment(C,s<1?a:a1)")
  path.light.thin(x="segment(C,s<1?b:b1)")
  path.light.thin(x="segment(C,s<1?c:c1)")
```

::: column.grow For rigid transformations, the image is always [[congruent|larger|smaller]] to the original – but this is [[no longer|still]] true for dilations. Instead, we say that two shapes are [**similar**](gloss:similar). They have the same overall shape, but not necessarily the same size.

The symbol for similarity is `?` (similar to the symbol for congruence, which was `?`). In this example, we would write `A ? A'`.

```
// Here is how we can construct the dilation of a geometric shape:
//
// ::: column(width=300)
// {.todo} COMING SOON – Animation
// ::: column.grow
// First we draw rays from the center of dilation to every point in the shape.
//
// Now let’s measure the distance of all these points from the center of dilation.
// Then we can multiply the distance by the scale factor, and the measure the
// image of the point along the same ray.
//
// All that’s left is to connect the transformed points in the image … all done!
// :::
```

---

## Phép vị tự

> section: similarity sectionStatus: dev id: similarity

::: column(width=240) {.todo} COMING SOON – Illustration :::

You might have noticed that these dilations with the connecting rays almost look like **perspective drawings**. The center of dilation is called the **vanishing point**, because it looks like this is where everything is “vanishing in the distance”.

Find the vanishing point in the figure below:

---

> id: perspective

### Perspective Drawings

{.todo} COMING SOON – Interactive

Now can you draw another house that matches the existing ones?

Similarity can tell us a lot about shapes. For example, [circles](gloss:circle), [squares](gloss:square) and [equilateral triangles](gloss:equilateral-triangle) are [[always|sometimes|never]] similar. They might have different sizes, but always the same general shape.

::: column.grow The two quadrilaterals on the right are similar. Our first important observation is that in similar polygons, all the matching pairs of angles are [congruent](gloss:congruent-angles). This means that

---

> id: similar-polygons

### Similar Polygons

{.text-center} [*{.m-red}?ABC* ? *{.m-red}?A'B'C'*](target:a)*{.space}* [*{.m-blue}?BCD* ? *{.m-blue}?B'C'D'*](target:b) [*{.m-green}?CDE* ? *{.m-green}?C'D'E'*](target:c)*{.space}* [*{.m-yellow}?DEA* ? *{.m-yellow}?D'E'A'*](target:d)

The second important fact is that in similar polygons, all sides are scaled **proportionally** by the scale factor of the corresponding dilation. If the scale factor is ${k}{k|1.5|0.5,2,0.1}, then

{.text-center} `abs(AB) ×` ${k} `= abs(A'B')`*{.space}*`abs(BC) ×` ${k} `= abs(B'C')` `abs(CD) ×` ${k} `= abs(C'D')`*{.space}*`abs(DE) ×` ${k} `= abs(D'E')`

We can instead rearrange these equations and eliminate the scale factor entirely:

{.text-center} `abs(AB)/abs(A'B') = abs(BC)/abs(B'C') = abs(AB)/abs(A'B') = abs(AB)/abs(A'B')`

We can use this to solve real life problems that involve similar polygons – for example finding the length of missing sides, if we know some of the other sides. In the following section you will see a few examples. ::: column(width=240)

:::

```
// This proportional relationship is true not just for the sides of the
// polygon, but also for properties like diagonals.
```

The concept of similarity is particularly powerful with triangles. We already know that the corresponding internal angles in similar polygons are equal.

```
x-geopad.sticky(width=240 height=360): svg
  - var x = ['a', 'b', 'c', 'd']
  - var initial = {a:[50,70], b:[160,50], c:[200,110], d:[150,160]}
  - var next = {a:'b', b:'c', c:'d', d:'a'}
  - var prev = {a:'d', b:'a', c:'b', d:'c'}
  - var classes = {a:'red', b:'blue', c:'green', d:'yellow'}
  each l in x
    circle(name=l x=`point(${initial[l][0]},${initial[l][1]})` r=4 target=l)
    path(x=`angle(${prev[l]},${l},${next[l]})` target=l class=classes[l])
    path(x=`segment(${l},${next[l]})` target=`${l} ${next[l]}`)
    circle(name=l+'1' r=4 x=`${l}.subtract({x:120,y:90}).scale(k).rotate(3).add({x:120,y:270})` target=l)
    path(x=`angle(${prev[l]}1,${l}1,${next[l]}1)` target=l class=classes[l])
    path(x=`segment(${l}1,${next[l]}1)` target=`${l} ${next[l]}`)
```

For triangles, the opposite is also true: this means that if you have two triangles with the same three angle sizes, then the triangles must be similar.

---

> id: similar-triangles

### Similar Triangles

And it gets even better! We know that the internal angles in a triangle always add up to [[180]]°. This means that if we know two angles in a triangle, we can always work out the third one.

For similarity, this means that we also just need to check *two angles* to determine if triangles are similar. If two triangles have two angles of the same size, then the third angle must also be the same in both.

This result is sometimes called the [**AA Similarity Condition**](gloss:triangle-aa) for triangles. (The two *As* stand for the two *angles* we compare.)

::: .theorem If two angles in one triangle are congruent to two angles in another triangle, the two triangles are similar. :::

Let’s have a look at a few examples where this is useful:

::: column(width=320) {.todo} COMING SOON – Animation

---

> id: similar-triangles-1

::: column.grow Here you can see the image of a large lighthouse. Together with a friend, you want to measure the height of the lighthouse, but unfortunately we cannot climb to the top.

It turns out that, very well hidden, the diagram contains two similar triangles: one is formed by the lighthouse and its shadow, and one is formed by your friend and her shadow.

Both triangles have one right angle at the bottom. The sun rays are parallel, which means that the other two angles at the bottom are corresponding angles, and also equal. By the AA condition for triangles, these two must be similar.

We can easily measure the length of the shadows, and we also know the height of your friend. Now we can use the proportionality of sides in similar triangles to find the height of the lighthouse:

{.todo} COMING SOON – Equation

Therefore the lighthouse is 1.5m tall. :::

::: column(width=320) {.todo} COMING SOON – Animation ::: column.grow We can use the same technique to measure distances on the ground. Here we want to find the width of a large river. There is a big tree on one side of the river, and I’ve got a stick that is one meter long.

Try drawing another two similar triangles in this diagram.

---

> id: similar-triangles-2

You can mark the point along the side of the river, that lies directly on the line of sight from the end of the stick to the tree. Then we can measure the distances to the stick, and to the point directly opposite the tree.

Once again, these two triangles are similar because of the AA condition. They both have a right angle, and on pair of opposite angles.

According to the proportionality rule, this means that

{.todo} COMING SOON – Equation

Therefore the width of the river is 45 meters. :::

Theorem: If a ray bisects an angle of a triangle, then it divides the opposite side into segments that are proportional to the lengths of the other two sides.

We can extend this theorem to a situation outside of triangles where we have multiple parallel lines cut by transverals.

---

### Similarity on Rays

Theorem: If three or more parallel lines are cut by two transversals, then they divide the transversals proportionally.

Think about a midsegment of a triangle. A midsegment is parallel to one side of a triangle and divides the other two sides into congruent halves. The midsegment divides those two sides proportionally.

Triangle Proportionality Theorem: If a line parallel to one side of a triangle intersects the other two sides, then it divides those sides proportionally.

Triangle Proportionality Theorem Converse: If a line divides two sides of a triangle proportionally, then it is parallel to the third side.

There are some curious mathematical shapes that are similar to a smaller part *of themselves*. An example is the **Sierpinksi Triangle**: the entire triangle is similar to any one of the smaller triangles it consists on. You could zoom in and infinitely many smaller and smaller triangles.

Triangle Proportionality Theorem Converse: If a line divides two sides of a triangle proportionally, then it is parallel to the third side.

---

### Self Similarity

There are some curious mathematical shapes that are similar to a smaller part *of themselves*. An example is the **Sierpinksi Triangle**: the entire triangle is similar to any one of the smaller triangles it consists on. You could zoom in and infinitely many smaller and smaller triangles.

Shapes with this property are called **Fractals**. They have some surprising and truly XXX properties, which you will learn about more in the future.

---

<<<<<<< Updated upstream
Triangles are not just useful for measuring distances. In the next course we will learn a lot more about triangles and their properties.
=======
Triangles are not just useful for measuring distances. In the next course we
will learn a lot more about triangles and their properties.
>>>>>>> Stashed changes
