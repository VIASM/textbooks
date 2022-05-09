# Polygons and Polyhedra

## Polygons

> section: polygons
> id: polygons
> description: Hình học ở mọi nơi xung quanh chúng ta. Ở khóa học này, bạn sẽ học về góc, đa giác, tessellation, đa diện và hình khai triển.
> color: "#4757D3"
> level: Intermediate
> next: circles

Một [__đa giác__](gloss:polygon) là một hình phẳng, đóng, chỉ có chứa các cạnh thẳng. Đa giác có thể có nhiều cạnh và góc, nhưng không có cạnh cong. Hình nào dưới đây là đa giác?

    x-picker
      .item#item1: include svg/polygons/polygon-1.svg
      .item(data-error="not-a-polygon-1"): include svg/polygons/polygon-2.svg
      .item(data-error="not-a-polygon-2"): include svg/polygons/polygon-3.svg
      .item: include svg/polygons/polygon-4.svg
      .item(data-error="not-a-polygon-3"): include svg/polygons/polygon-5.svg
      .item: include svg/polygons/polygon-6.svg

    x-gesture(target="#item1")

---
> id: polygons-1

Chúng ta đặt các tên khác nhau cho đa giác, dựa vào số cạnh của chúng:

    .row.padded-thin
      div(style="width: 100px")
        include svg/polygons/number-3.svg
        p.caption #[strong Triangle]#[br]3 sides
      div(style="width: 100px")
        include svg/polygons/number-4.svg
        p.caption #[strong Quadrilateral]#[br]4 sides
      div(style="width: 100px")
        include svg/polygons/number-5.svg
        p.caption #[strong Pentagon]#[br]5 sides
      div(style="width: 100px")
        include svg/polygons/number-6.svg
        p.caption #[strong Hexagon]#[br]6 sides
      div(style="width: 100px")
        include svg/polygons/number-7.svg
        p.caption #[strong Heptagon]#[br]7 sides
      div(style="width: 100px")
        include svg/polygons/number-8.svg
        p.caption #[strong Octagon]#[br]8 sides

---
> id: angles-0

### Angles in Polygons

Mỗi đa giác có _n_ cạnh thì cũng có _n_ [góc trong](gloss:internal-angle).
Chúng ta biết rằng tổng các góc trong của một tam giác luôn luôn bằng [[180]]°, thế còn đối với các đa giác khác thì sao?

---
> id: angles
> goals: angle-0 angle-1

::: column.grow(width=300)

    x-geopad(width=300 height=300): svg
      circle.move(name="a" cx=40 cy=40)
      circle.move(name="b" cx=260 cy=80)
      circle.move(name="c" cx=240 cy=220)
      circle.move(name="d" cx=80 cy=260)
      path.fill.red(x="angle(b,a,d)" label="${a1[0]}°")
      path.fill.blue(x="angle(c,b,a)" label="${a1[1]}°")
      path.fill.green(x="angle(d,c,b)" label="${a1[2]}°")
      path.fill.yellow(x="angle(a,d,c)" label="${360-a1[0]-a1[1]-a1[2]}°")
      path(name="p1" x="polygon(a,b,c,d)")

{.text-center.var} _{span.circled.red}${a1[0]}°_ +
_{span.circled.blue}${a1[1]}°_ + _{span.circled.green}${a1[2]}°_ +
_{span.circled.yellow}${360-a1[0]-a1[1]-a1[2]}°_ &nbsp;=&nbsp; _{x-anibutton(text="???")}_

    x-gesture(target="x-anibutton")

::: column.grow(width=300)

    x-geopad(width=300 height=300): svg
      circle.move(name="e" cx=120 cy=30)
      circle.move(name="f" cx=270 cy=100)
      circle.move(name="g" cx=220 cy=270)
      circle.move(name="h" cx=80 cy=240)
      circle.move(name="i" cx=30 cy=150)
      path.fill.red(x="angle(f,e,i)" label="${a2[0]}°")
      path.fill.blue(x="angle(g,f,e)" label="${a2[1]}°")
      path.fill.green(x="angle(h,g,f)" label="${a2[2]}°")
      path.fill.yellow(x="angle(i,h,g)" label="${a2[3]}°")
      path.fill.purple(x="angle(e,i,h)" label="${540-a2[0]-a2[1]-a2[2]-a2[3]}°")
      path(name="p2" x="polygon(e,f,g,h,i)")

{.text-center.var} _{span.circled.red}${a2[0]}°_ +
_{span.circled.blue}${a2[1]}°_ + _{span.circled.green}${a2[2]}°_ +
_{span.circled.yellow}${a2[3]}°_ +
_{span.circled.purple}${540-a2[0]-a2[1]-a2[2]-a2[3]}°_ &nbsp;=&nbsp; _{x-anibutton(text="???")}_
:::

---
> id: angles-1

Có vẻ như tổng các góc trong của tứ giác luôn bằng [[360]]°
– chính xác [[gấp đôi|gấp ba|một nửa]] tổng các góc trong một tam giác.
_{span.reveal(when="blank-0 blank-1")} Nó không bị trùng vào nhau: mỗi tứ giác có thể được chia thành hai tam giác._

    .row.padded-thin
      .reveal(when="blank-1" style="width: 140px"): include svg/polygons/triangles-4.svg
      .reveal(when="blank-2" style="width: 140px"): include svg/polygons/triangles-1.svg
      .reveal(when="blank-4" style="width: 140px"): include svg/polygons/triangles-2.svg
      .reveal(when="blank-4" delay=500 style="width: 140px"): include svg/polygons/triangles-3.svg

{.reveal(when="blank-0 blank-1")} Điều này cũng đúng cho các đa giác lớn hơn.
Chúng ta có thể chia một ngũ giác thành [[3]] tam giác, vì thế tổng các góc trong của nó là
`3 × 180° =` [[540]]°. _{span.reveal(when="blank-2 blank-3")} Và chúng ta có thể chia một lục giác thành [[4]] tam giác, vì thế tổng các góc trong của chúng là `4 × 180° =` [[720]]°._

---
> id: internal-angle-sum

Một đa giác có ${x}{x|7|3,15,1} cạnh sẽ có tổng các góc trong 
180° × ${x-2} = ${(x-2)*180}°. Hơn thế nữa, một đa giác có _n_ cạnh có thể được chia thành [[n – 2|n – 1|n]] tam giác. Vì vậy,

{.text-center.reveal(when="blank-0")} Tổng các góc trong trong một hình có n cạnh _n_-gon
`= (n - 2) × 180°`.

    x-gesture(target="#internal-angle-sum x-var" slide="100,0")

---
> id: concave

### Convex and Concave Polygons

::: column.grow
Chúng ta nói một đa giác là [__lõm__](gloss:concave) nếu như nó có một phần là
“Các điểm hướng vào trong”. Chúng ta có thể tưởng tượng phần này có [“caved in”](target:cave).
Các đa giác mà _không_ lõm thì được gọi là [__lồi__](gloss:convex).

Có hai cách dễ dàng giúp chúng ta xác định một đa giác lõm: chúng có [ít nhất một góc trong](target:angle) lớn hơn 180°. Chúng cũng có [ít nhất một đường chéo](target:diagonal) nằm _ngoài_ đa giác.

Ở đa giác lồi, thì lại khác, tất cả các góc trong đều nhỏ hơn
[[180]]°, và tất cả các đường chéo đều nằm [[bên trong|bên ngoài]] đa giác.
::: column(width=240)

    x-geopad(width=240): svg
      circle(hidden name="a" x="point(40,70)")
      circle(hidden name="b" x="point(60,170)")
      circle(hidden name="c" x="point(160,200)")
      circle(hidden name="d" x="point(150,130)")
      circle(hidden name="e" x="point(190,40)")
      path.fill.blue(x="polygon(a,b,c,d,e)" target="cave diagonal angle")
      path.transparent.red.fill(x="polygon(c,d,e)" target="cave")
      path.red.fill.transparent(x="angle(c,d,e)" target="angle")
      path.transparent(x="segment(a,c)" target="diagonal" style="stroke: #f7f7f8")
      path.transparent(x="segment(a,d)" target="diagonal" style="stroke: #f7f7f8")
      path.transparent(x="segment(b,d)" target="diagonal" style="stroke: #f7f7f8")
      path.transparent(x="segment(b,e)" target="diagonal" style="stroke: #f7f7f8")
      path.transparent.red(x="segment(c,e)" target="diagonal")
:::

---
> id: concave-1

Đa giác nào sau đây là lõm?

    x-picker
      .item(data-error="not-concave-1"): include svg/polygons/concave-1.svg
      .item(data-error="not-concave-2"): include svg/polygons/concave-2.svg
      .item: include svg/polygons/concave-3.svg
      .item: include svg/polygons/concave-4.svg
      .item(data-error="not-concave-3"): include svg/polygons/concave-5.svg
      .item: include svg/polygons/concave-6.svg

---
> id: regular-polygons

### Regular Polygons

Chúng ta nói một đa giác là [__đều__](gloss:regular-polygon) nếu tất cả các cạnh của chúng cùng độ dài, và tất cả các góc có cùng kích thước. Hình nào dưới đây là đa giác đều?

    x-picker
      .item: include svg/polygons/regular-1.svg
      .item(data-error="not-regular-1"): include svg/polygons/regular-2.svg
      .item: include svg/polygons/regular-3.svg
      .item(data-error="not-regular-2"): include svg/polygons/regular-4.svg
      .item(data-error="not-regular-3"): include svg/polygons/regular-5.svg
      .item: include svg/polygons/regular-6.svg

---
> id: regular-1

Đa giác đều có thể có kích cỡ khác nhau – nhưng tất cả các đa giác đều mà có cùng số cạnh thì [[đồng đạng|bằng nhau|có cùng diện tích]]!

---
> id: regular-2

Chúng ta đã biết tổng tất cả [các góc trong](gloss:internal-angle) trong đa giác. Với đa giác đều, tất cả các góc [[có chung kích thước|là các góc so le nhau]],
vì thế chúng ta có thể tính cụ thể góc trong đa giác đều:

{.text-center.reveal(when="blank-0")} `"angle" = blank("sum of all angles","number of angles")/
blank("number of angles","sum of all angles")`
_{span.reveal(when="blank-1 blank-2")} = `(180° × (x-2))/x = 180° - (360°)/x`._

{.reveal(when="blank-1 blank-2" delay=1000)} Nếu `n=3` chúng ta sẽ tính được góc trong của tam giác đều – chúng ta đã biết rằng góc đó là
[[60]]°. _{span.reveal(when="blank-3")} Trong đa giác đều với ${x}{x|6|3,12,1}
cạnh, mọi góc trong đều là 180° – `"360°"/var("x")` = ${round(180-360/x)}°._

---
> id: regular-area

### The Area of Regular Polygons

::: column(width=320)

    x-geopad.sticky(width=320 height=320): svg
      circle.reveal(name="m" x="point(160, 160)" when="blank-0" animation="pop")
      path(name="p" x="regular(m, 140, n)")
      circle(name="p0" x="p.points[0]")
      circle(name="p1" x="p.points[1]")
      circle(name="k" x="segment(p1,p0).midpoint" hidden)

      path.blue.fill.light.transparent(x="polygon(p0,m,p1)" target="isosceles-triangle")
      path.blue.fill.light.transparent(x="polygon(p0,m,k)" target="right-triangle")
      path.blue.fill.transparent(x="angle(m,k,p0)" size=15 target="right-triangle")
      path.blue.fill.reveal(when="blank-1 blank-2" x="angle(k,p0,m)" size=25 target="base-angle right-triangle alpha isosceles-triangle" label="α")
      path.blue.fill.reveal(when="blank-1 blank-2" x="angle(m,p1,k)" size=25 target="base-angle isosceles-triangle")

      for i in [0,1,2,3,4,5,6,7,8,9,10,11]
        path.thin.reveal(when="blank-0" delay=i*150 x=`segment(p.points[${i}%n],m)` animation="draw")

      path.yellow.reveal(when="blank-2" x="segment(m,k)" target="apothem" label="apothem" animation="draw")
      path.green(x="segment(p1,p0)" target="base" label="s = 1m")
      path.green(x="segment(k,p0)" target="base half-base")

      for i in [0,1,2,3,4,5,6,7,8,9,10,11]
        path.red.fill.transparent(x=`angle(p.points[${i+2}%n],p.points[${i+1}%n],p.points[${i}%n])` size=18 target="int-angle")

::: column.grow
Ở đây chúng ta có thể nhìn thấy một [đa giác đều](gloss:regular-polygon) với ${n}{n|5|4,12,1}
cạnh. Mỗi cạnh đều có một độ dài [{.green} 1m](target:base). Chúng ta sẽ đi tính diện tích của nó.

Đầu tiên, chúng ta chia đa giác thành ${toWord(n)},
tam giác [[cân|đều|vuông]] bằng nhau.

{.reveal(when="blank-0")} Chúng ta đã biết [[cạnh đáy|chiều cao|diện tích]] của các tam giác này, nhưng chúng ta cũng cần biết [[chiều cao|các cạnh góc vuông|các đường trung tuyến]] để có thể tính được diện tích của nó. _{span.reveal(when="blank-2")} Trong một đa giác đều, chiều cao này cũng có thể được gọi là [{.yellow}apothem](target:apothem)._

{.reveal(when="blank-1 blank-2" delay=1000)} Chú ý rằng có một[{.blue} tam giác vuông](target:right-triangle) được tạo ra bởi chiều cao này và một nửa cạnh đáy của tam giác cân. Điều này có nghĩa là chúng ta có thể sử dụng lượng giác!

{.reveal(when="blank-1 blank-2" delay=2000)} [{.blue} Các góc ở đáy](target:base-angle)
của tam giác cân (giả sử chúng ta đặt tên là góc α) là [[một nửa|bằng|gấp hai lần]]
kích thước của [{.red} góc trong](target:int-angle) của đa giác:

{.text-center.reveal(when="blank-3")} `pill(α, "blue", "alpha") = 1/2 (180° -
(360°)/var("n")) = var("round(90-180/n,2)")`

{.reveal(when="blank-3")} Để tính chiều cao này, chúng ta cần sử dụng định nghĩa của hàm [[tangent|sine|cosine]]:

{.text-center.reveal(when="blank-4")} `tan pill(α, "blue", "alpha") =
pill("opposite", "yellow", "apothem") / pill("adjacent", "green", "half-base") =
blank("apothem", "s", "s/2") / blank("s/2", "s", "apothem")`

{.text-center.reveal(when="blank-5 blank-6")} `⇒ pill("apothem", "yellow",
"apothem") = 1/2 pill(s, "green", "base") × tan pill(α, "blue", "alpha") =
var("round(tan(pi/2-pi/n)/2,2)")"m"`

{.reveal(when="blank-5 blank-6" delay=2000)} Bây giờ, diện tích của
[{.blue}tam giác cân](target:isosceles-triangle) là

{.text-center.reveal(when="blank-5 blank-6" delay=2000)} `1/2 "base" × "height"
= 1/2 pill("1m", "green", "base") × pill(var("round(tan(pi/2-pi/n)/2,2)"),
"yellow", "apothem") = var("round(tan(pi/2-pi/n)/4,2)") "m"^2`

{.reveal(when="blank-5 blank-6" delay=4000)} Đa giác bao gồm ${toWord(n)}
của các tam giác cân này, tất cả chúng có cùng diện tích. Vì vậy, tổng diện tích của đa giác là

{.text-center.reveal(when="blank-5 blank-6" delay=4000)} `A = var("n") ×
var("round(tan(pi/2-pi/n)/4,2)") = var("round(n×tan(pi/2-pi/n)/4,2)")
"m"^2`
:::

---

## Quadrilaterals

> section: quadrilaterals
> id: quadrilaterals

Ở [khóa học trước](/course/triangles) chúng ta đã tìm hiểu rất nhiều tính chất khác nhau của tam giác. Bây giờ chúng ta sẽ tìm hiểu về tứ giác.

Một _tứ giác đều_ là một [[hình vuông|hình chữ nhật|tứ giác có các cạnh bằng nhau]].
Tất cả các cạnh của nó có cùng độ dài, và tất cả các góc của nó bằng nhau.

::: column.quadrilateral.reveal(when="blank-0")

    x-geopad(width=210 height=120): svg
      circle.move(name="a" cx=60 cy=15)
      circle.move(name="b" cx=60 cy=105)
      circle(name="c" x="a.rotate(pi/2,b)")
      circle(name="d" x="b.rotate(-pi/2,a)")
      path.fill.yellow.light(x="polygon(a,b,c,d)")
      path.blue(x="angle(a,b,c)" target="angle")
      path.blue(x="angle(b,c,d)" target="angle")
      path.blue(x="angle(c,d,a)" target="angle")
      path.blue(x="angle(d,a,b)" target="angle")
      path.red(x="segment(a,b)" target="side" mark="bar")
      path.red(x="segment(b,c)" target="side" mark="bar")
      path.red(x="segment(c,d)" target="side" mark="bar")
      path.red(x="segment(d,a)" target="side" mark="bar")

{.caption} Một __hình vuông__ là một tứ giác với [{.red} có bốn cạnh bằng nhau](target:side)
và [{.blue} bốn góc bằng nhau](target:angle).
:::

---
> id: quadrilaterals-1

Với các tứ giác “ít đều” hơn, chúng ta có hai lựa chọn. Nếu chúng ta muốn
_các góc_ bằng nhau, chúng ta có [__hình chữ nhật__](gloss:rectangle). Nếu chúng ta muốn _các cạnh_ bằng nhau, chúng ta có [__hình thoi__](gloss:rhombus).

::: column.quadrilateral

    x-geopad(width=210 height=120): svg
      circle.move(name="a" cx=40 cy=15)
      circle.move(name="b" cx=40 cy=105)
      circle.move(name="c" cx=180 cy=105 project="line(a,b).perpendicular(b)")
      circle(name="d" x="c.add(a).subtract(b)")
      path.fill.yellow.light(x="polygon(a,b,c,d)")
      path.blue(x="angle(a,b,c)" target="angle")
      path.blue(x="angle(b,c,d)" target="angle")
      path.blue(x="angle(c,d,a)" target="angle")
      path.blue(x="angle(d,a,b)" target="angle")
      path.red(x="segment(a,b)")
      path.red(x="segment(b,c)")
      path.red(x="segment(c,d)")
      path.red(x="segment(d,a)")

{.caption} Một __Hình chữ nhật__là một tứ giác với [{.blue} bốn góc bằng nhau](target:angle).
::: column.quadrilateral

    x-geopad(width=210 height=120): svg
      circle.move(name="e" cx=50 cy=60)
      circle.move(name="f" cx=105 cy=15)
      circle.move(name="h" cx=105 cy=105 project="circle(e,distance(e,f))")
      circle(name="g" x="h.add(f).subtract(e)")
      path.fill.yellow.light(x="polygon(e,f,g,h)")
      path.red(x="segment(e,f)" target="side" mark="bar")
      path.red(x="segment(f,g)" target="side" mark="bar")
      path.red(x="segment(g,h)" target="side" mark="bar")
      path.red(x="segment(h,e)" target="side" mark="bar")

{.caption} Một __Hình thoi__ là một tứ giác với [{.red} bốn cạnh bằng nhau](target:side).
:::

---
> id: quadrilaterals-2

Có một vài loại tứ giác khác, thậm chí còn “ít đều” hơn nhưng chúng cũng có những tính chất đặc biệt:

::: column.quadrilateral

    x-geopad(width=210 height=120): svg
      circle.move(name="a" cx=20 cy=20)
      circle.move(name="b" cx=160 cy=20)
      circle.move(name="c" cx=50 cy=100)
      circle(name="d" x="b.add(c).subtract(a)")
      path.fill.yellow.light(x="polygon(a,b,d,c)")
      path.red(x="segment(a,b)" mark="arrow")
      path.red(x="segment(c,d)" mark="arrow")
      path.blue(x="segment(a,c)" mark="arrow2")
      path.blue(x="segment(b,d)" mark="arrow2")

{.caption} Nếu hai cặp cạnh _đối_ là [song song](gloss:parallel), chúng ta có __Hình bình hành__.
::: column.quadrilateral

    x-geopad(width=210 height=120): svg
      circle.move(name="e" cx=20 cy=60)
      circle.move(name="f" cx=140 cy=15)
      circle.move(name="g" cx=190 cy=60)
      circle(name="h" x="f.reflect(line(e,g))")
      path.fill.yellow.light(x="polygon(e,f,g,h)")
      path.red(x="segment(e,f,)" mark="bar")
      path.blue(x="segment(f,g)" mark="bar2")
      path.blue(x="segment(g,h)" mark="bar2")
      path.red(x="segment(h,e,)" mark="bar")

{.caption} Nếu hai cặp cạnh _kề nhau_ có cùng độ dài, chúng ta có __Hình chiếc diều__.
::: column.quadrilateral

    x-geopad(width=210 height=120): svg
      circle.move(name="i" cx=60 cy=15)
      circle.move(name="j" cx=20 cy=105)
      circle.move(name="k" cx=190 cy=105)
      circle.move(name="l" cx=160 cy=15 project="line(j,k).parallel(i)")
      path.fill.yellow.light(x="polygon(i,j,k,l)")
      path(x="segment(i,j)")
      path.red(x="segment(j,k)" mark="arrow")
      path(x="segment(k,l)")
      path.red(x="segment(i,l)" mark="arrow")

{.caption} Nếu có ít nhất một cặp cạnh đối song song, chúng ta có
__Hình thang__.
:::

---
> id: quadrilaterals-venn

Các tứ giác có thể được chia thành nhiều loại. Chúng ta có thể hình dung hệ thống cấp bậc các loại tứ giác giống như [Sơ đồ Ven](gloss:venn-diagram):

    figure: include svg/venn.svg

Ví dụ, mỗi một hình chữ nhật là một [[hình bình hành|hình thoi|hình vuông]], và mỗi [[hình thoi|hình thang|hình bình hành]] lại là hình chiếc diều. Một hình thoi 
[[đôi khi|luôn luôn|không bao giờ]] là hình vuông và một hình chữ nhật [[luôn luôn|đôi khi|không bao giờ]] là hình thang.

{.reveal(when="blank-0 blank-1 blank-2 blank-3")} Để tránh gây hiểu lầm, chúng ta thường xuyên sử dụng tên gọi điển hình nhất cho mỗi một hình cụ thể.

---
> id: midsegments

::: column(width=300)

    x-geopad.sticky(width=300 height=300): svg

::: column.grow
Bây giờ hãy lấy bốn điểm, ở vị trí nào cũng được trong chiếc hộp màu xám.
_{span.reveal(when="points")} Chúng ta có thể nối chúng lại để tạo thành một tứ giác._

{.reveal(when="points" delay=1000)} Chúng ta sẽ đi tìm trung điểm của mỗi cạnh. Nếu chúng ta nối các trung điểm lại với nhau, chúng ta sẽ được [[một tứ giác khác|một tam giác|một hình chữ nhật]].

{.reveal(when="blank-0")} Hãy thử di chuyển các đỉnh của tứ giác bên ngoài và quan sát những gì xảy ra với tứ giác bên trong. Có vẻ như nó không giống_bất kì_
tứ giác bình thường nào, nhưng nó luôn luôn là một [[hình bình hành|hình thang|hình chữ nhật]]!

{.reveal(when="blank-1")} Nhưng tại sao nó lại thế? Tại sao kết quả cho _bất kì_ tứ giác nào lại nên luôn luôn kết thúc là hình bình hành? Để giúp chúng ta giải thích điều này,
Chúng ta cần vẽ một [đường chéo](gloss:polygon-diagonal) của hình tứ giác ban đầu.

{.reveal(when="diagonal")} Đường chéo sẽ chia tứ giác thành [hai hình tam giác](target:triangle). Và bây giờ bạn có thể nhìn thấy [hai trong số các cạnh](target:midsegment) của tứ giác bên trong thực sự là [[đường trung bình|trung tuyến|đường trung trực]] của các tam giác này.

{.reveal(when="blank-2")} Ở [khóa học trước](/course/triangles/properties)
chúng ta đã chứng minh được rằng đường trung bình](gloss:triangle-midsegment) của tam giác luôn song song với cạnh đáy. Trong trường hợp này, điều đó có nghĩa [cả hai cạnh này](target:parallel) song song với đường chéo – vì thế chúng cũng phải [[song song với nhau|có cùng độ dài|vuông góc với nhau]].

{.reveal(when="blank-3" delay=2000)} Chúng ta có thể làm điều tương tự với [đường chéo thứ hai](target:other) của tứ giác, để chỉ ra rằng hai cặp cạnh đối song song. Và đó là tất cả những gì chúng ta cần làm để chứng minh rằng tứ giác bên trong là [hình bình hành](gloss:parallelogram). _{span.qed}_
:::

---
> id: parallelograms

### Parallelograms

Điều đó chứng tỏ rằng hình bình hành có rất nhiều tính chất thú vị khác, hơn là việc các cặp cạnh đối song song. Khẳng định nào trong sáu khẳng định dưới đây là đúng?

::: column.grow

    x-picker.list
      .item.md Các cạnh đối là [bằng nhau](gloss:congruent).
      .item(data-error="parall-error-1") Các góc trong luôn luôn nhỏ hơn 90°.
      .item.md(data-error="parall-error-2") Các đường chéo [chia đôi](gloss:angle-bisector) các góc trong.
      .item Các góc đối bằng nhau.
      .item(data-error="parall-error-3") Hai đường chéo bằng nhau.
      .item(data-error="parall-error-4") Cách cạnh kề nhau có cùng độ dài
      .item Hai đường chéo cắt nhau tại trung điểm mỗi đường.

::: column(width=300)

    x-geopad(width=300 height=240): svg
      circle.move(name="a" cx=80 cy=50)
      circle.move(name="b" cx=20 cy=190)
      circle.move(name="c" cx=220 cy=190)
      circle(name="d" x="b.rotate(pi,line(a,c).midpoint)")

      path.red(x="segment(a,b)")
      path.red(x="segment(c,d)")
      path.blue(x="segment(b,c)")
      path.blue(x="segment(a,d)")
      path.thin.light(x="segment(a,c)")
      path.thin.light(x="segment(b,d)")

      path.thin.light(x="angle(a,b,c).sup")
      path.thin.light(x="angle(b,c,d).sup")
      path.thin.light(x="angle(c,d,a).sup")
      path.thin.light(x="angle(d,a,b).sup")

:::

---
> id: parallelograms-proof

Dĩ nhiên, việc chỉ đơn giản “quan sát” các tính chất là không đủ. Để chắc chắn rằng chúng _luôn luôn_ đúng, chúng ta cần _chứng minh_ chúng:

::: tab
#### Opposite Sides and Angles _{span.check(when="diagonal blank-0 blank-1")}_

::: column(width=300)

    x-geopad.sticky(width=300 height=300): svg
      circle.move(name="a" cx=80 cy=80)
      circle.move(name="b" cx=20 cy=220)
      circle.move(name="c" cx=220 cy=220)
      circle(name="d" x="b.rotate(pi,line(a,c).midpoint)")

      path.reveal.fill.red(when="diagonal" x="angle(a,o?c:b,d).sup" target="red-angle")
      path.reveal.fill.red(when="diagonal" x="angle(c,o?a:d,b).sup" target="red-angle")
      path.reveal.fill.blue(when="diagonal" x="angle(d,o?a:b,c).sup" target="blue-angle")
      path.reveal.fill.blue(when="diagonal" x="angle(b,o?c:d,a).sup" target="blue-angle")

      path.fill.yellow.transparent(x="polygon(a,b,o?c:d)" target="triangles")
      path.fill.green.transparent(x="polygon(o?a:b,c,d)" target="triangles")
      path(x="polygon(a,b,c,d)")

      path.green.transparent(x="segment(a,b)" target="sides")
      path.green.transparent(x="segment(c,d)" target="sides")
      path.yellow.transparent(x="segment(b,c)" target="sides")
      path.yellow.transparent(x="segment(a,d)" target="sides")
      path.fill.green.transparent(x="angle(a,b,c).sup" target="angles")
      path.fill.green.transparent(x="angle(c,d,a).sup" target="angles")
      path.fill.yellow.transparent(x="angle(b,c,d).sup" target="angles")
      path.fill.yellow.transparent(x="angle(d,a,b).sup" target="angles")

::: column.grow
{.task} Chúng ta sẽ đi chứng minh các cạnh đối và các góc đối của hình bình hành bằng nhau.

Bắt đầu bằng việc vẽ một trong các đường chéo của hình bình hành.

{.reveal(when="diagonal")} Đường chéo tạo ra bốn góc mới với các cạnh của hình bình hành. Hai góc [{.red} màu đỏ](target:red-angle) và hai góc
[{.blue} màu xanh](target:blue-angle) là [góc so le](gloss:alternate-angles),
vì thế chúng [[bằng nhau|kề nhau|bù nhau]].

{.reveal(when="blank-0")} Bây giờ nếu chúng ta nhìn vào [hai tam giác](target:triangles)
được tạo ra bởi đường chéo, chúng ta sẽ thấy chúng có hai góc bằng nhau,
và [một cạnh bằng nhau](target:diagonal). Bằng trường hợp bằng nhau[[góc cạnh góc|góc góc cạnh|góc góc]], cả hai tam giác sẽ phải bằng nhau.

{.reveal(when="blank-1")} Điều này có nghĩa là những phần tương ứng khác của hai tam giác cũng sẽ bằng nhau: cụ thể, [các cặp cạnh đối](target:sides) bằng nhau, và [các cặp góc đối](target:angles) bằng nhau. _{span.qed}_
:::

{.reveal(when="blank-1")} Nó cũng chỉ ra rằng điều ngược lại luôn đúng: nếu cả hai cặp cạnh đối (hoặc góc đối) trong một tứ giác bằng nhau, thì tứ giác đó phải là hình bình hành.

    //- Các góc kề nhau sẽ bù nhau.

::: tab
#### Diagonals _{span.check(when="diagonal blank-2 blank-3")}_

::: column(width=300)

    x-geopad.sticky(width=300 height=300): svg
      circle.move(name="a1" cx=80 cy=80 label="A")
      circle.move(name="b1" cx=20 cy=220 label="B")
      circle.move(name="c1" cx=220 cy=220 label="C")
      circle(name="d1" x="b1.rotate(pi,line(a1,c1).midpoint)" label="D")
      circle(name="m1" x="polygon(a1,b1,c1,d1).centroid" label="M")

      path.fill.yellow.light(x="polygon(b1,m1,c1)" target="triangles1")
      path.fill.yellow.light(x="polygon(a1,m1,d1)" target="triangles1")

      path.fill.red(x="angle(c1,a1,d1).sup" target="anglesR")
      path.fill.red(x="angle(b1,c1,a1).sup" target="anglesR")
      path.fill.blue(x="angle(a1,d1,b1).sup" target="anglesB")
      path.fill.blue(x="angle(d1,b1,c1).sup" target="anglesB")

      path(x="polygon(a1,b1,c1,d1)")
      path(x="segment(a1,c1)")
      path(x="segment(b1,d1)")
      path.green(x="segment(a1,d1)" target="side1")
      path.green(x="segment(b1,c1)" target="side1")

      path.yellow.tick.transparent(x="segment(a1,m1)" target="AM")
      path.yellow.tick.transparent(x="segment(b1,m1)" target="BM")
      path.yellow.tick.transparent(x="segment(c1,m1)" target="CM")
      path.yellow.tick.transparent(x="segment(d1,m1)" target="DM")

::: column.grow
{.task} Bây giờ chứng minh rằng hai đường chéo trong một hình bình hành cắt nhau tại trung điểm mỗi đường.

Hãy nghĩ về hai tam giác màu vàng được tạo ra bởi hai đường chéo:

* Chúng ta vừa mới chứng minh được [{.green} hai cạnh màu xanh lá cây](target:side1) là bằng nhau, bởi vì chúng là các cạnh đối của hình bình hành.
* [{.red} hai góc màu đỏ](target:anglesR) và [{.blue} hai góc màu xanh](target:anglesB) là bằng nhau, bởi vì chúng là [[các góc so le|các góc đối|các góc vuông]].

{.reveal(when="blank-2")} Bằng trường hợp [[góc cạnh góc|cạnh cạnh cạnh|góc góc cạnh]], cả hai tam giác màu vàng vì vậy mà bằng nhau.

{.reveal(when="blank-3")} bây giờ chúng ta có thể sử dụng tính chất các phần tương ứng của hai tam giác bằng nhau thì bằng nhau, để kết luận rằng [{.yellow} `bar(AM)`](target:AM) = [{.yellow} `bar(CM)`](target:CM)
và [{.yellow} `bar(BM)`](target:BM) = [{.yellow} `bar(DM)`](target:DM). Hay nói cách khác, hai đường chéo cắt nhau tại trung điểm mỗi đường. _{span.qed}_
:::

{.reveal(when="blank-3")} Giống như trước đó, điều ngược lại cũng đúng: nếu hai đường chéo trong một tứ giác cắt nhau tại trung điểm mỗi đường, thì tứ giác đó là hình bình hành.
:::

---
> id: kites

### Kites

::: column.grow
Chúng ta đã chứng minh được rằng là hai cặp cạnh [[đối nhau|kề nhau]] của một hình bình hành là bằng nhau. Trong hình chiếc diều, hai cặp cạnh_kề nhau_là bằng nhau.

Tên gọi _Hình chiếc diều_ rõ ràng xuất phát từ hình dáng của nó: trông nó giống như chiếc diều bay lên trên bầu trời. Tuy nhiên, hình chiếc diều là một trong những tứ giác mà chúng ta đã nhìn thấy cho đến nay, là hình duy nhất [lõm](gloss:concave): nếu như nó giống phi tiêu hoặc mũi tên:
::: column(width=320)

    x-img(src="images/kites.jpg")

:::

::: column(width=240)

    x-geopad(width=240 height=180): svg
      circle(name="a" x="point(20,90)")
      circle(name="b" x="point(90,20)")
      circle.move(name="c" cx=200 cy=90 project="segment(point(100,90),point(220,90))")
      circle(name="d" x="point(90,160)")
      path.fill.yellow.light(x="polygon(a,b,c,d)")
      path.red(x="segment(a,b)")
      path.red(x="segment(a,d)")
      path.blue(x="segment(b,c)")
      path.blue(x="segment(d,c)")

{.caption} A convex kite
::: column(width=240)

    x-geopad(width=240 height=180): svg
      circle(name="a1" x="point(20,90)")
      circle(name="b1" x="point(220,20)")
      circle.move(name="c1" cx=150 cy=90 project="segment(point(70,90),point(210,90))")
      circle(name="d1" x="point(220,160)")
      path.fill.green.light(x="polygon(a1,b1,c1,d1)")
      path.red(x="segment(a1,b1)")
      path.red(x="segment(a1,d1)")
      path.blue(x="segment(b1,c1)")
      path.blue(x="segment(d1,c1)")

{.caption} Hình chiếc diều lõm trông giống như một mũi tên.
:::

---
> id: kites-1

::: column(width=300)

    x-geopad.sticky(width=300): svg
      circle.move(name="a" cx=30 cy=150)
      circle.move(name="b" cx=110 cy=250)
      circle.move(name="c" cx=270 cy=150)
      circle(name="d" x="b.reflect(line(a,c))")
      circle.transparent(name="m" x="line(a,c).project(b)")

      path.fill.light.blue.reveal(when="next-0" x="angle(b,a,d).sup" target="angles vAngle sas")
      path.fill.light.green.reveal(when="next-0" x="angle(b,c,d).sup" target="angles vAngle")
      path.fill.light.red.reveal(when="next-0" x="angle(a,d,c).sup" target="angles")
      path.fill.light.red.reveal(when="next-0" x="angle(a,b,c).sup" target="angles")
      path.fill.light.yellow.reveal(when="next-3" x="angle(a,m,d).sup" target="alpha" label="α")
      path.fill.light.yellow.reveal(when="next-3" x="angle(b,m,a).sup" target="beta" label="β")

      path.fill.red.transparent(x="polygon(a,b,c)" target="triangle1")
      path.fill.yellow.transparent(x="polygon(a,c,d)" target="triangle1")
      path.fill.red.transparent(x="polygon(a,m,d)" target="triangle2")
      path.fill.yellow.transparent(x="polygon(a,m,b)" target="triangle2")

      path.green(x="segment(a,b)" target="sss sas")
      path.green(x="segment(a,d)" target="sss sas")
      path.blue(x="segment(d,c)" target="sss")
      path.blue(x="segment(b,c)" target="sss")

      path.red.light.thin.reveal(when="blank-1" x="line(a,c)" target="symmetry" animation="draw")
      path.red.reveal(when="blank-1" x="segment(a,c)" target="symmetry sss d1" animation="draw")
      path.red.transparent(x="segment(a,m)" target="sas" animation="draw")
      path.red.reveal(when="next-2" x="segment(b,d)" animation="draw")

::: column.grow
Bạn nên để ý rằng tất cả các hình chiếc diều đều [[đối xứng|đồng dạng]].
_{span.reveal(when="blank-0")} [Trục đối xứng](gloss:axis-of-symmetry) là
[[một trong cách đường chéo|một trong các cạnh|một đường trung bình]]._

{.reveal.r(when="blank-1")} Đường chéo chia chiếc diều thành [hai tam giác bằng nhau](target:triangle1). Chúng ta biết rằng là chúng bằng nhau dựa trên trường hợp
[cạnh cạnh cạnh](gloss:triangle-sss): cả hai tam giác đều có [ba cạnh bằng nhau](target:sss) (đỏ, xanh lá cây và xanh da trời).
[Continue](btn:next)

{.reveal.r(when="next-0")} Using [CPOCT](gloss:cpoct), vì vậy chúng ta biết rằng
[các góc tương ứng](target:angles) phải bằng nhau.
[Continue](btn:next)

{.reveal.r(when="next-1")} Điều này có nghĩa là, ví dụ, [{.red} đường chéo màu đỏ](target:d1)
là một [[đường phân giác|vuông góc|trung tuyến]] của [hai góc](target:vAngle) tại hai đầu mút của nó.
[Continue](btn:next)

{.reveal.r(when="next-2")} Chúng ta có thể nhìn thấy xa hơn: nếu chúng ta vẽ đường chéo khác, chúng ta có [hai tam giác nữa, bé hơn](target:triangle2).Chúng cũng sẽ bằng nhau, dựa trên trường hợp [cạnh góc cạnh](gloss:triangle-sss): chúng có cùng [hai cạnh và góc xen giữa](target:sas).
[Continue](btn:next)

{.reveal(when="next-3")} Điều này có nghĩa là [{.yellow} góc α](target:alpha) bằng với [{.yellow} góc β](target:beta).Vì hai góc kề nhau,
[hai góc bù nhau](gloss:supplementary-angles) cả hai góc α và β phải bằng [[90]]°.

{.reveal(when="blank-3")} Hay nói cách khác, hai đường chéo của hình chiếc diều luôn luôn
[[vuông góc|song song]].
:::

---
> id: quadrilaterals-area
> goals: draw-1 draw-2

### Area of Quadrilaterals

Khi tính diện tích của tam giác ở khóa học trước, chúng ta sử dụng mẹo để chuyển nó thành một [[hình chữ nhật|hình vuông|hình ngũ giác]]. Điều đó có nghĩa là chúng ta cũng có thể làm tương tự cho một số tứ giác khác:

::: tab
#### Parallelogram _{span.check(when="draw-1 blank-1")}_

::: column(width=300)

    x-geopad(width=300 height=240 grid=20 no-points): svg
      circle.transparent(name="a1" x="point(4,3)")
      circle.transparent(name="b1" x="point(12,3)")
      circle.transparent(name="c1" x="point(10,9)")
      circle.transparent(name="d1" x="point(2,9)")
      path.fill.blue.light(x="polygon(a1,b1,c1,d1)")
      path.fill.red.transparent(x="polygon(point(2,3),a1,d1)" target="triangle-1")
      path.fill.green.transparent(x="polygon(point(10,3),b1,c1)" target="triangle-2")
      path.blue(x="polygon(a1,b1,c1,d1)")

::: column.grow
Ở bên trái, thử vẽ một hình chữ nhật có cùng diện tích giống như hình bình hành.

{.reveal(when="draw-1")} Bạn có thấy rằng[{.red} tam giác còn thiếu](target:triangle-1)
ở bên trái là [[bằng|nhỏ hơn|lớn hơn]] [{.green} tam giác bị chồng lên](target:triangle-2) ở bên phải?
_{span.reveal(when="blank-1")} Vì thế diện tích của hình bình hành là _

{.text-center.reveal(when="blank-1")} Area = __{.i.m-green}base__ × __{.i.m-yellow}height__

{.reveal(when="blank-1" delay=1000)} _Cẩn thận khi đo chiều cao của hình bình hành: nó thường không bằng với một trong các cạnh của hình bình hành._
:::

::: tab
#### Trapezium _{span.check(when="draw-2 blank-2 blank-3 blank-4 next-0")}_

Nhắc lại rằng hình thang là tứ giác với một cặp [{.blue} cạnh song song](target:bases).
Cặp cạnh song song này được gọi là __cạnh đáy__ của hình thang.

::: column(width=300)

    x-geopad.sticky(width=300 height=240 grid=20 no-points): svg
      circle.transparent(name="a2" x="point(4,3)")
      circle.transparent(name="b2" x="point(9,3)")
      circle.transparent(name="c2" x="point(13,9)")
      circle.transparent(name="d2" x="point(2,9)")
      path.fill.blue.light(x="polygon(a2,b2,c2,d2)")
      path.fill.red.transparent(x="polygon(a2,point(3,3),point(3,9),d2)" target="triangles-3")
      path.fill.yellow.transparent(x="polygon(b2,point(11,3),point(11,9),c2)" target="triangles-3")
      path.blue(x="polygon(a2,b2,c2,d2)")
      path.blue(x="segment(a2,b2)" target="bases base-1")
      path.blue(x="segment(d2,c2)" target="bases base-2")
      path.green.transparent(x="segment(point(2,3),d2)" target="t-height")
      path.yellow.transparent(x="segment(point(3,6),point(11,6))" target="t-width")
      circle.reveal(when="blank-3" x="line(a2,d2).midpoint" target="t-width" animation="pop")
      circle.reveal(when="blank-3" x="line(b2,c2).midpoint" target="t-width" animation="pop")

::: column.grow
Giống như trước đó, thử vẽ một hình chữ nhật có cùng diện tích với hình thang.
_{span.reveal(when="draw-2")} Bạn có biết bằng cách nào [các tam giác còn thiếc và được thêm vào](target:triangles-3) ở bên trái và bên phải bị loại bỏ?_

{.reveal(when="draw-2" delay=2000)} [{.green} chiều cao](target:t-height)
của hình chữ nhật là [[khoảng cách giữa|trung bình của|chiều dài của]] [{.blue} các cạnh song song](target:bases) của hình thang.

{.reveal.r(when="blank-2")} [{.yellow} chiều rộng](target:t-width)
của hình chữ nhật là khoảng cách giữa[[các trung điểm|các đầu mút]] của hai cạnh không song song của hình thang. _{span.reveal(when="blank-3")} Nó được gọi là__đường trung bình__ của hình thang._
_{button.next-step.reveal(when="blank-3")} Tiếp tục_

{.reveal(when="next-0")} Giống với [các tam giác](gloss:triangle-midsegment), đường trung bình của hình thang [[song song với|vuông góc với|cùng độ dài]]
với hai đáy của nó. Độ dài của đường trung bình thì bằng trung bình cộng độ dài của hai đáy: `(a+c)/2`.

{.reveal(when="blank-4")} Nếu chúng ta kết hợp chúng lại với nhau, chúng ta sẽ thu được công thức tính diện tích của hình thang với các cạnh song song [{.blue} _a_](target:base-2) và [{.blue} _c_](target:base-1), và chiều cao
[{.green} _h_](target:t-height):

{.text-center.reveal(when="blank-4")} `A = h xx ((a+c) / 2)`
:::

::: tab
#### Kite _{span.check(when="blank-5")}_

::: column(width=300)

    x-geopad(width=300 height=220 grid=20 no-points): svg
      circle.transparent(name="a3" x="point(1,5)")
      circle.transparent(name="b3" x="point(5,1)")
      circle.transparent(name="c3" x="point(13,5)")
      circle.transparent(name="d3" x="point(5,9)")

      path.fill.blue.light(x="polygon(a3,b3,c3,d3)")
      path.green(x="segment(a3,c3)" label="d1" target="diag3 d31")
      path.yellow(x="segment(b3,d3)" label="d2" target="diag3 d32")
      path(x="polygon(point(1,1),point(13,1),point(13,9),point(1,9))" target="rect4")
      path.blue(x="polygon(a3,b3,c3,d3)")

      path.fill.red.transparent(x="polygon(a3,b3,point(5,5))" target="inside")
      path.fill.blue.transparent(x="polygon(b3,c3,point(5,5))" target="inside")
      path.fill.green.transparent(x="polygon(c3,d3,point(5,5))" target="inside")
      path.fill.yellow.transparent(x="polygon(d3,a3,point(5,5))" target="inside")

      path.fill.red.transparent(x="polygon(a3,b3,point(1,1))" target="outside")
      path.fill.blue.transparent(x="polygon(b3,c3,point(13,1))" target="outside")
      path.fill.green.transparent(x="polygon(c3,d3,point(13,9))" target="outside")
      path.fill.yellow.transparent(x="polygon(d3,a3,point(1,9))" target="outside")

::: column.grow
Trong hình chiếc diều này, [hai đường chéo](target:diag3) tạo ra chiều rộng và chiều cao của một hình[chữ nhật](target:rect4) lớn hơn bao quanh hình chiếc diều.

Diện tích của hình chữ nhật này [[gấp hai lần|bằng|gấp ba lần]] diện tích của hình chiếc diều. _{span.reveal(when="blank-5")} Bạn có biết làm thế nào mà [bốn tam giác](target:inside) tạo ra hình chiếc diều lại giống
[four gaps](target:outside) với cái bên ngoài?_

{.reveal(when="blank-5")} Điều này có nghĩa là diện tích của hình chiếc diều với các đường chéo
[{.green}`d_1`](target:d31) và [{.yellow}`d_2`](target:d32) là

{.text-center.reveal(when="blank-5")} `"Area" = 1/2 pill(d_1,"green","d31") × pill(d_2,"yellow","d32")`.
:::

::: tab
#### Rhombus _{span.check(when="blank-6 blank-7")}_

::: column(width=300)

    x-geopad(width=300 height=240): svg
      circle.move(name="a4" cx=40 cy=120)
      circle.move(name="b4" cx=150 cy=50)
      circle.move(name="d4" cx=150 cy=190 project="circle(a4,distance(a4,b4))")
      circle(name="c4" x="d4.add(b4).subtract(a4)")

      path.fill.blue.light(x="polygon(a4,b4,c4,d4)")

      path.thin(x="line(c4,d4)")
      circle(name="q4" x="line(c4,d4).project(a4)")
      path.thin(x="angle(a4,q4,d4).sup" size=15)
      path.red(x="segment(q4,a4)" label="height" target="height")

      path.green(x="segment(a4,c4)" label="d1" target="d41")
      path.yellow(x="segment(b4,d4)" label="d2" target="d42")
      path.blue(x="polygon(a4,b4,c4,d4)")
      path.blue(x="segment(c4,d4)" target="base")

::: column.grow
Một [Hình thoi](gloss:rhombus) là một tứ giác có bốn cạnh bằng nhau. Bạn nên nhớ rằng mọi hình thoi đều là [[hình bình hành|hình chữ nhật|hình vuông]] – và cũng là [[hình chiếc diều|hình lục giác|hình đa giác lõm]].

{.reveal(when="blank-6 blank-7")} Điều này có nghĩa là để tìm diện tích của hình thoi,
chúng ta có thể sử dụng công thức tính diện tích của hình bình hành, hoặc công thức tính diện tích của hình chiếc diều:

{.text-center.reveal(when="blank-6 blank-7")} _Area_ =
[{.i.blue}base](target:base) × [{.i.red}height](target:height) = `1/2`
[{.i.green}d1](target:d41) × [{.i.yellow}d2](target:d42).

{.reveal(when="blank-6 blank-7" delay=1000)} _Trong nhiều trường hợp khác, người ta có thể cho bạn các phần khác nhau của hình thoi (các cạnh, đường cao, các đường chéo), và bạn nên chọn ra công thức nào phù hợp để tính diện tích._
:::

:::

    //- ### Cyclic quadrilaterals

    //- ### Isosceles Trapeziums
    //-
    //- Một hình thang cân là một hình thang có các cạnh không song song
    //- bằng nhau. Hinh thang thứ ba phía trên là một ví dụ của hình thang 
    //- cân. Hãy nghĩ nó như một tam giác cân bị cắt đi phần đỉnh.
    //- Hình thang cân cũng có những phần được đặt tên giống như 
    //- hình tam giác cân. Cả hai cạnh song song đều được gọi là cạnh đáy.
    //-
    //- Trong một tam giác cân, hai góc ở đáy bằng nhau. Tính chất
    //- này cũng đúng cho các hình thang cân.
    //-
    //- Điều ngược lại cũng đúng: Nếu một hình thang có hai góc ở đáy bằng nhau,
    //- thì nó là hình thang cân.
    //-
    //- Đường chéo của hình chữ nhật bằng nhau và chúng cắt nhau tại trung điểm của
    //- mỗi đường. Đường chéo của hình thang cân cũng bằng nhau, nhưng 
    //- chúng không cắt nhau tại trung điểm mỗi đường.

---

## Tessellations

> section: tessellations
> id: tessellations

[Các đa giác](gloss:polygon) xuất hiện ở khắp mọi nơi trong tự nhiên. Chúng đặc biệt hữu ích khi chúng ta muốn lát một khu vực lớn, bởi vì chúng ta có thể lát kín các đa giác mà không để lại khoảng trống hoặc chồng lên nhau. Mẫu hình như thế được gọi là 
[__tessellations__](gloss:tessellation).

::: column(width=200)

    x-img(lightbox src="images/tessellations/honeycomb.jpg", width=200 height=200)

{.caption} [[Hexagonal|Triangular|Quadratic]] honeycomb
::: column(width=200)

    x-img(lightbox src="images/tessellations/snake.jpg", width=200 height=200)

{.caption} Sinaloan Milk Snake skin
::: column(width=200)

    x-img(lightbox src="images/tessellations/leaf.jpg", width=200 height=200)

{.caption} Cellular structure of leafs
::: column(width=200)

    x-img(lightbox, credit="Chmee2, via Wikipedia", src="images/tessellations/causeway.jpg", width=200 height=200)

{.caption} Basalt columns at Giant’s Causeway in Northern Ireland
::: column(width=200)

    x-img(lightbox src="images/tessellations/pineapple.jpg", width=200 height=200)

{.caption} Pineapple skin
::: column(width=200)

    x-img(lightbox src="images/tessellations/tortoise.jpg", width=200 height=200)

{.caption} Shell of a tortoise
:::

---
> id: tessellations-1

Con người đã sử dụng rất nhiều mẫu hình tự nhiên trong nghệ thuật, kiến trúc và công nghệ - từ Roma cổ kính cho tới hiện đại. Đây là một trong số những ví dụ: 

::: column(width=200)

    x-img(lightbox src="images/tessellations/pavement.jpg", width="200", height="200")

{.caption} [[Rectangular|Quadratic|Hexagonal]] pavement pattern
::: column(width=200)

    x-img(lightbox, src="images/tessellations/greenhouse.jpg", width="200", height="200")

{.caption} Greenhouse at the Eden Project in England
::: column(width=200)

    x-img(lightbox, credit="Andrew Dunn, via Wikipedia", src="images/tessellations/alhambra.jpg", width="200", height="200")

{.caption} Mosaic at Alhambra
::: column(width=200)

    x-img(lightbox, credit="Chmee2 via Wikipedia", src="images/tessellations/museum.jpg", width="200", height="200")

{.caption} Mái nhà [[hình tam giác|hình lục giác|hình chữ nhật]] tại bảo tàng Anh ở London
::: column(width=200)

    x-img(lightbox, credit="© Patrick Boland, via archinect.com", src="images/tessellations/cellular.jpg", width="200", height="200")

{.caption} Cellular tessellation pavilion in Sydney
::: column(width=200)

    x-img(credit="© M. C. Escher", src="images/tessellations/escher.jpg", width="200", height="200")

{.caption} _Study of Regular Division of the Plane with Reptiles_, M. C. Escher
:::

    // TODO Carbon Nanotube
    // application: https://en.wikipedia.org/wiki/Carbon_nanotube
    // https://en.wikipedia.org/wiki/File:Types_of_Carbon_Nanotubes.png
    // https://commons.wikimedia.org/wiki/File:FlyingThroughNanotube.png

---
> id: tessellation-drawing
> goals: shapes0 shapes1

Ở đây, bạn cũng có thể tự tạo ra tessellation cho riêng mình sử dụng các đa giác đều. Đơn giản chỉ cần kéo thả hình mới từ khu vực sidebar vào trong canvas. Hình nào sẽ lát được tốt? Liệu có hình nào không thể sử dụng để lát? Hãy thử tạo ra những mẫu hình thú vị nào!

    figure: .tessellation
      x-polypad
      .menu
        for s in ['equ-triangle', 'square', 'reg-pentagon', 'reg-hexagon', 'reg-octagon']
          .add(data-shape=s)
      .btn-row: button.icon-btn(title="Download image"): x-icon(name="download")
      svg.overlay: g.tiles.active
    x-gesture(target=".tessellation .menu" slide="-300, 140")
    .other-students.reveal(when="shapes0")
      h4 Examples of other students’ tessellations
      .row.padded-thin
        div(style="width: 224px"): img(src="images/user/tess-1.png" width=240 height=160)
        div(style="width: 224px"): img(src="images/user/tess-2.png" width=240 height=160)
        div(style="width: 224px"): img(src="images/user/tess-3.png" width=240 height=160)

---
> id: tessellation-regular

### Tessellations from regular polygons

Bạn có thể thấy rằng có những hình [đa giác đều](gloss:regular-polygon) (giống như
[[hình vuông|ngũ giác]]) dùng để lát gạch rất dễ, trong khi có những hình (giống như
[[hình ngũ giác|tam giác|lục giác]]) thì không phải lúc nào cũng có thể dùng để lát gạch được.

---
> id: tessellation-regular-1

Chúng ta sẽ cần phải tính toán kích thước các [góc trong](gloss:internal-angle),
điều mà chúng ta đã được học trước đó. Tại mỗi[đỉnh](gloss:polygon-vertex) trong một tessellation, các góc trong của nhiều đa giác cùng loại sẽ gặp nhau. Chúng ta cần đảm bảo tất cả các góc này cộng lại bằng [[360]]°, nếu không thì chúng có thể tạo ra khoảng trống hoặc chồng lên nhau.

---
> id: tessellation-regular-2

::: column(width=160 parent="padded-thin")
    include svg/tessellations/triangles.svg

{.caption} Tam giác [[lát được|không lát được]] _{span.reveal(when="blank-0")} bởi vì 6 × 60° = 360°._
::: column(width=160)
    include svg/tessellations/squares.svg

{.caption} Hình vuông [[lát được|không lát được]] _{span.reveal(when="blank-1")} bởi vì 4 × 90° = 360°._
::: column(width=160)
    include svg/tessellations/pentagons.svg

{.caption} Hình ngũ giác [[không lát được|lát được]] _{span.reveal(when="blank-2")} bởi vì các bội số của 108°
không cộng lại bằng 360°._

    //- {.caption}3 × 108° = 324° thì quá nhỏ, trong khi 4 × 108° = 432° thì quá lớn.
::: column(width=160)
    include svg/tessellations/hexagons.svg

{.caption} Lục giác [[lát được|không lát được]] _{span.reveal(when="blank-3")} bởi vì 3 × 120° = 360°._
:::

---
> id: tessellation-regular-3

Bạn có thể kiểm tra tương tự, giống như ngũ giác, bất kì đa giác đều có 7 hoặc nhiều cạnh hơn không thể lát được. Điều này có nghĩa là chỉ có các đa giác: tam giác, hình vuông, hình lục giác là có thể dùng để lát gạch được!

Dĩ nhiên bạn có thể kết hợp nhiều loại đa giác đều khác nhau trong một tessellation, miễn là tổng các góc trong của chúng cộng lại là 360°:

    x-gallery(slide-width="520")
      div
        img(src="images/tessellations/regular-1.svg" width=360 height=240)
        p.caption Squares and triangles#[br]#[strong.m-blue 90°] + #[strong.m-blue 90°] + #[strong.m-yellow 60°] + #[strong.m-yellow 60°] + #[strong.m-yellow 60°] = 360°
      div
        img(src="images/tessellations/regular-3.svg" width=360 height=240)
        p.caption Squares and triangles#[br]#[strong.m-blue 90°] + #[strong.m-blue 90°] + #[strong.m-yellow 60°] + #[strong.m-yellow 60°] + #[strong.m-yellow 60°] = 360°
      div
        img(src="images/tessellations/regular-4.svg" width=360 height=240)
        p.caption Hexagons and triangles#[br]#[strong.m-red 120°] + #[strong.m-red 120°] + #[strong.m-yellow 60°] + #[strong.m-yellow 60°] = 360°
      div
        img(src="images/tessellations/regular-5.svg" width=360 height=240)
        p.caption Hexagons and triangles#[br]#[strong.m-red 120°] + #[strong.m-yellow 60°] + #[strong.m-yellow 60°] + #[strong.m-yellow 60°] + #[strong.m-yellow 60°] = 360°
      div
        img(src="images/tessellations/regular-2.svg" width=360 height=240)
        p.caption Hexagons, squares and triangles#[br]#[strong.m-red 120°] + #[strong.m-blue 90°] + #[strong.m-blue 90°] + #[strong.m-yellow 60°] = 360°
      div
        img(src="images/tessellations/regular-6.svg" width=360 height=240)
        p.caption Octagons and squares#[br]#[strong.m-green 135°] + #[strong.m-green 135°] + #[strong.m-blue 90°] = 360°
      div
        img(src="images/tessellations/regular-7.svg" width=360 height=240)
        p.caption Dodecagons (12-gons) and triangles#[br]#[strong.m-green 150°] + #[strong.m-green 150°] + #[strong.m-yellow 60°] = 360°
      div
        img(src="images/tessellations/regular-8.svg" width=360 height=240)
        p.caption Dodecagons, hexagons and squares#[br]#[strong.m-green 150°] + #[strong.m-red 120°] + #[strong.m-blue 90°] = 360°

---
> id: tessellation-triangles

### Tessellations from irregular polygons

Chúng ta cũng có thể thử tạo ra tessellations từ [các đa giác không đều](gloss:irregular-polygon)
– miễn là chúng ta cẩn thận khi xoay và sắp xếp chúng. 

::: column(width=360)

    x-geopad(width=360 height300): svg
      circle.move(name="a" cx=220 cy=90 target="vertex")
      circle.move(name="b" cx=145 cy=180 target="vertex")
      circle.move.pulsate(name="c" cx=225 cy=200 target="vertex")

      path.red.fill(name="x" x="polygon(a,b,c)")
      path.yellow.fill(name="y" x="x.rotate(pi,line(b,c).midpoint)")

      for x in [-5,-4,-3,-2,-1,0,1,2,3,4,5]
        for y in [-5,-4,-3,-2,-1,0,1,2,3,4,5]
          if x || y
            path.red.fill(x=`x.translate(c.subtract(a).scale(${x}).add(b.subtract(a).scale(${y})))`)
            path.yellow.fill(x=`y.translate(c.subtract(a).scale(${x}).add(b.subtract(a).scale(${y})))`)

::: column.grow
Điều này có nghĩa là chúng ta có thể lát gạch không chỉ với tam giác đều, nhưng là _bất kì tam giác nào_! Thử di chuyển [các đỉnh](target:vertex) ở biểu đồ này.

Tổng các góc trong một tam giác là [[180]]°. Nếu chúng ta sử dụng mỗi góc [[2 lần|1 lần|3 lần]] tại mỗi đỉnh trong một tessellation, chúng ta có góc 360°:

    x-geopad.reveal(width=200 height=160 when="blank-0 blank-1"): svg
      circle(name="m" cx=100 cy=80)
      circle(name="p" cx=100 cy=150)
      circle.move(name="q" cx=175 cy=130)
      circle(name="r" x="p.rotate(pi,line(m,q).midpoint)")
      circle(name="s" x="p.rotate(pi,m)")
      circle(name="t" x="q.rotate(pi,m)")
      circle(name="u" x="q.rotate(pi,line(m,p).midpoint)")

      path.fill.red(x="angle(p,m,q).sup" size=20)
      path.fill.blue(x="angle(q,m,r).sup" size=20)
      path.fill.green(x="angle(r,m,s).sup" size=20)
      path.fill.red(x="angle(s,m,t).sup" size=20)
      path.fill.blue(x="angle(t,m,u).sup" size=20)
      path.fill.green(x="angle(u,m,p).sup" size=20)

      path.fill.red.light(x="angle(m,q,r).sup" size=20)
      path.fill.red.light(x="angle(r,s,m).sup" size=20)
      path.fill.red.light(x="angle(m,t,u).sup" size=20)
      path.fill.red.light(x="angle(u,p,m).sup" size=20)
      path.fill.blue.light(x="angle(p,q,m).sup" size=20)
      path.fill.blue.light(x="angle(m,r,s).sup" size=20)
      path.fill.blue.light(x="angle(s,t,m).sup" size=20)
      path.fill.blue.light(x="angle(m,u,p).sup" size=20)
      path.fill.green.light(x="angle(m,p,q).sup" size=20)
      path.fill.green.light(x="angle(q,r,m).sup" size=20)
      path.fill.green.light(x="angle(m,s,t).sup" size=20)
      path.fill.green.light(x="angle(t,u,m).sup" size=20)

      path(x="segment(m,p)")
      path(x="segment(m,q)")
      path(x="segment(m,r)")
      path(x="segment(m,s)")
      path(x="segment(m,t)")
      path(x="segment(m,u)")
      path(x="polygon(p,q,r,s,t,u)")
:::

---
> id: tessellation-quadrilaterals

::: column(width=360)

    x-geopad(width=360 height=300): svg
      circle.move(name="a" cx=100 cy=105)
      circle.move(name="b" cx=115 cy=200)
      circle.move.pulsate(name="c" cx=180 cy=170)
      circle.move(name="d" cx=200 cy=120)

      path.blue.fill(name="x" x="polygon(a,b,c,d)")
      path.green.fill(name="y" x="x.rotate(pi,line(c,d).midpoint)")

      for x in [-5,-4,-3,-2,-1,0,1,2,3,4,5]
        for y in [-5,-4,-3,-2,-1,0,1,2,3,4,5]
          if x || y
            path.blue.fill(x=`x.translate(c.subtract(a).scale(${x}).add(d.subtract(b).scale(${y})))`)
            path.green.fill(x=`y.translate(c.subtract(a).scale(${x}).add(d.subtract(b).scale(${y})))`)


::: column.grow
Ngạc nhiên hơn, _bất kì tứ giác nào_ cũng có thể lát gạch được! Tổng các góc trong của chúng là [[360]]°, vì thế nếu chúng ta sử dụng mỗi góc [[1 lần|2 lần|3 lần]] tại mỗi đỉnh trong một tessellation, chúng ta có góc 360°.

    x-geopad.reveal(width=200 height=160 when="blank-0 blank-1"): svg
      circle(name="m" x="point(100,80)")
      circle(name="p" x="point(100,150)")
      circle.move(name="q" cx=180 cy=140)
      circle.move(name="r" cx=165 cy=90)
      circle(name="s" x="p.rotate(pi,line(m,r).midpoint)")
      circle(name="t" x="q.rotate(pi,line(m,r).midpoint)")
      circle(name="u" x="r.rotate(pi,line(m,t).midpoint)")
      circle(name="v" x="q.rotate(pi,line(m,p).midpoint)")
      circle(name="w" x="r.rotate(pi,line(m,p).midpoint)")

      path.fill.red(x="angle(p,m,r).sup" size=20)
      path.fill.blue(x="angle(r,m,t).sup" size=20)
      path.fill.green(x="angle(t,m,v).sup" size=20)
      path.fill.yellow(x="angle(v,m,p).sup" size=20)

      path.fill.red.light(x="angle(m,r,s).sup" size=20)
      path.fill.red.light(x="angle(t,u,v).sup" size=20)
      path.fill.red.light(x="angle(w,p,m).sup" size=20)
      path.fill.blue.light(x="angle(q,r,m).sup" size=20)
      path.fill.blue.light(x="angle(m,t,u).sup" size=20)
      path.fill.blue.light(x="angle(v,w,p).sup" size=20)
      path.fill.green.light(x="angle(p,q,r).sup" size=20)
      path.fill.green.light(x="angle(s,t,m).sup" size=20)
      path.fill.green.light(x="angle(m,v,w).sup" size=20)
      path.fill.yellow.light(x="angle(m,p,q).sup" size=20)
      path.fill.yellow.light(x="angle(r,s,t).sup" size=20)
      path.fill.yellow.light(x="angle(u,v,m).sup" size=20)

      path(x="segment(m,p)")
      path(x="segment(m,r)")
      path(x="segment(m,t)")
      path(x="segment(m,v)")
      path(x="polygon(p,q,r,s,t,u,v,w)")
:::

---
> id: tessellation-pentagons

Hình ngũ giác thì khó hơn một chút. Chúng ra đã biết rằng là đa giác _đều_ [[không thể lát gạch được|lát gạch được]], những với những hình đa giác không đều này thì sao?

---
> id: tessellation-pentagons-1

Đây là ba ví dụ khác nhau về tessellation với các ngũ giác. Chúng không
_đều_, nhưng chúng lại là các ngũ giác hợp lí một cách hoàn hảo:

::: column(width=220)
    include svg/tessellations/pentagons-1.svg
::: column(width=220)
    include svg/tessellations/pentagons-2.svg
::: column(width=220)
    include svg/tessellations/pentagons-3.svg
:::

Qua thời gian, thì các nhà toán học đã chỉ tìm ra 15 loại tessellation với các ngũ giác (lồi)
 – loại gần đây nhất được phát hiện vào năm 2015.

---
> id: pentagons
> goals: shapes

Hai năm trước, năm 2017, _Michaël Rao_ đã công bố một bản chứng minh rằng không có khả năng khác, ngoại trừ 15 loại đã tồn tại trước đó. Liệu bạn có thể tạo ra một tessellation sử dụng chúng?

    figure
      .tessellation
        x-polypad
        .menu
          .add(data-shape="-13.9 -70.5,40.5 -70.5,40.5 24.4,13.1 70.5,-40.5 -23.5")
          .add(data-shape="-46 47.3,-1.4 47.3,46 0,-1.4 -47.3,-45.5 3")
          .add(data-shape="-28 -43.1,9.3 -43.1,59.2 43.1,-40.5 43.1,-59.2 10.8")
          .add(data-shape="-53.6 -40.2,-28.7 2.9,14.8 40.2,53.6 9,46 -40.2")
          .add(data-shape="11.5 40.5,54.6 21,19 -40.5,-52 -40.4,-54.6 -4.4")
          .add(data-shape="43.3 28.5,-4.3 43.2,-54.3 -42.9,45.3 -43.2,54.3 -20")
          .add(data-shape="-49.1 23.1,-5.4 35.5,73.4 -35.5,-32.7 -35.5,-73.4 -15.4")
          .add(data-shape="-57 -33,37.2 -33.3,57 13.7,10 33.3,-37.2 14")
          .add(data-shape="29.8 50.4,-31.5 8.2,-53.2 -50,8.9 -50.4,53.2 -7")
          .add(data-shape="-37.5 -2.8,-16.5 63.5,17.2 3,37.5 -63.5,-31.6 -63.5")
          .add(data-shape="42 -42,-42 -42,-42 42,0 42,42 0")
          .add(data-shape="-30.8 0,10.3 71.1,30.8 35.6,30.8 -71.1,10.3 -71.1")
          .add(data-shape="-36.9 -23.4,-9.9 -70.3,36.8 -43,36.9 70.2,17.4 70.3")
          .add(data-shape="-74.9 36.4,40 36.4,75.1 12.1,4.8 -36.4,-75.1 -6.3")
          .add(data-shape="-37.5 24.9,-12.4 -68,37.4 -68,37.5 -18.3,-12.4 68")
        .btn-row
          button.icon-btn(title="Flip selection"): x-icon(name="flip")
          button.icon-btn(title="Download image"): x-icon(name="download")
        svg.overlay: g.tiles.active
      .caption Shapes provided by the Math Happens Foundation

---
> id: escher

### Tessellations in Art

Rất nhiều nghệ sĩ, kiến trúc sư và nhà thiết kế sử dụng tessellation trong công việc của họ. Một trong những ví dụ nổi tiếng là nghệ sĩ người Hà Lan [M. C. Escher](bio:escher). Công việc của ông ấy bao gồm những sinh vật kì lạ, đột biến, mô hình và cảnh quan:

    .row
      div(style="width: 220px")
        x-img(credit="© M. C. Escher Foundation" src="images/escher/escher-1.jpg" width=220 height=220)
        p.caption “Sky and Water I” (1938)
      div(style="width: 220px")
        x-img(credit="© M. C. Escher Foundation" src="images/escher/escher-2.jpg" width=220 height=220)
        p.caption “Lizard” (1942)
      div(style="width: 220px")
        x-img(credit="© M. C. Escher Foundation" src="images/escher/escher-3.jpg" width=220 height=220)
        p.caption “Lizard, Fish, Bat” (1952)
      div(style="width: 220px")
        x-img(credit="© M. C. Escher Foundation" src="images/escher/escher-4.jpg" width=220 height=220)
        p.caption “Butterfly” (1948)
      div(style="width: 220px")
        x-img(credit="© M. C. Escher Foundation" src="images/escher/escher-5.jpg" width=220 height=220)
        p.caption “Two Fish” (1942)
      div(style="width: 220px")
        x-img(credit="© M. C. Escher Foundation" src="images/escher/escher-6.jpg" width=220 height=220)
        p.caption “Shells and Starfish” (1941)

Những công việc nghệ thuật này trông có vẻ vui và không cần nhiều nỗ lực, nhưng dưới các nguyên lí của Toán học như đã nêu trước đó: góc, phép quay, phép tịnh tiến và đa giác. Nếu Toán học không đúng, thì sẽ không thể tạo ra tessellation.

    .metamorph: img(src="images/escher/metamorphosis.jpg" width=3000 height=150)
    p.caption “Metamorphosis II” by M. C. Escher (1940)

---
> id: penrose

### Penrose Tilings

Tất cả các tessellation mà chúng ta quan sát có một đặc điểm chung: chúng
__tuần hoàn__. Điều này có nghĩa là chúng chứa đựng những mô hình đều nhau lặp đi lặp lại. Chúng tiếp tục mãi mãi theo mọi hướng và chúng giống nhau ở mọi nơi.
Vào những năm 1970, nhà Toán học người Anh và nhà vật lí học [Roger Penrose](bio:penrose)
đã phát hiện ra những tessellation _không tuần hoàn – chúng vẫn tiếp tục đến vô tận theo mọi hướng, nhưng _khong bao giờ_ giống nhau một cách chính xác. Chúng được gọi là __Penrose
tilings__, và bạn chỉ cần một số ít loại đa giác để tạo ra nó:

::: figure

    include svg/penrose.svg
    x-slider(steps=100, style="max-width: 400px; margin: 24px auto")

{.caption} Di chuyển thanh trượt để nhìn thấy cấu trúc nằm phía dưới tessellation này. Chú ý cách mà các mô hình giống nhau xuất hiện theo các tỉ lệ khác nhau: ngũ giác màu vàng, ngôi sao màu xanh da trời, hình thoi màu tím và
‘những con tàu’ màu xanh xuất hiện cùng kích thước với hình nguyên bản, với__{.blue} kích thước lớn hơn một chút__ và __{.red} thậm chí kích thước còn lớn hơn nữa __. Việc _tự đồng dạng_ có thể được sử dụng để chứng mình rằng một Penrose tiling luôn luôn không tuần hoàn.

:::

---
> id: penrose-1

Penrose khám phá ra tessellation chỉ đơn thuần cho vui, nhưng thú vị thay cấu trúc bên trong của một số nguyên liệu thực (giống như aluminium) lại tuân theo mẫu hình này. Mẫu hình này thậm chí còn được sử dụng trong giấy vệ sinh, bởi vì các nhà sản xuất nhận thấy rằng một mẫu hình không tuần hoàn có thể được cuộn lại mà không bị phồng lên. 

---

## Polyhedra

> section: polyhedra
> id: polyhedra

Cho tới tận bân giờ, chúng ta mới chỉ chứng kiến những gì chúng ta có thể là với đa giác trong một bề mặt phẳng, thế giới 2 chiều. Một [__đa diện__](gloss:polyhedron) là một vật thể ba chiều được tạo ra từ các đa giác. Và đây là một số ví dụ:

::: column.padded-thin(width=220)
    x-polyhedron#poly1(size=220 shape="PentagonalPrism")
::: column(width=220)
    x-polyhedron(size=220 shape="Hebesphenorotunda")
::: column(width=220)
    x-polyhedron(size=220 shape="StellatedDodecahedron")
:::

Hình đa diện không chứa mặt cong - ví dụ, hình cầu và hình trụ không phải hình đa diện.

Các đa giác được dùng để tạo ra đa diện được gọi là [__các mặt__] của đa diện (gloss:polyhedron-face).
Đường thẳng nơi mà hai mặt được nối lại với nhau được gọi là [__các cạnh__](gloss:polyhedron-edge),
và các vị trí nơi mà các cạnh gặp nhau được gọi là [__các đỉnh__](gloss:polyhedron-vertex).

---
> id: euler

Hình đa diện có thể có nhiều hình dạng và nhiều kích thước - từ những hình đơn giản như hình lập phương hay hình chóp chỉ với một vài mặt, cho tới những hình phức tạp hơn như hình ngôi sao ở bên trên, có tới 60 mặt đều là tam giác. Điều này, tuy nhiên, rằng _tất cả_ các đa diện đều có chung một tính chất quan trọng: 

::: .theorem
__Euler’s Polyhedron Formula__<br>
Ở mọi đa diện, số lượng mặt (_F_) cộng với số lượng đỉnh (_V_)
Nhiều hơn số lượng cạnh là 2 (_E_). Hay nói cách khác,

{.text-center} `F + V = E + 2`
:::

Ví dụ, nếu một đa diện có 12 mặt và 18 đỉnh, chúng ta biết rằng nó phải có [[28]] cạnh.

---
> id: euler-1

Phương trình này được phát hiện bởi một nhà Toán học nổi tiếng người Thụy Sĩ [Leonard
Euler](bio:euler). Điều này đúng cho mọi đa diện, miễn là nó không chứ bất kì 
lỗ hổng nào. 

Nếu bạn muốn thử các đa diện khác, giống như những cái phía trên, bạn sẽ thấy rằng công thức Ơ-clit luôn đúng. Trong [một khóa học sau](/course/graph-theory/planar-graphs)
bạn sẽ học cách chứng minh nó.

---

## Nets and Cross Sections

> section: nets-cross-sections
> sectionStatus: dev

Dưới đây là một ví dụ minh họa cho phần giao nhau của một đa diện và một mặt phẳng:

    figure.var
      x-select.tabs(:bind="poly")
        div(value="tetrahedron") Tetrahedron
        div(value="cube") Cube
        div(value="octahedron") Octahedron
        div(value="dodecahedron") Dodecahedron
        div(value="icosahedron") Icosahedron
      x-polyhedron-slice(:shape="poly" :opacity="opacity")

---

Thế giới của chúng ta là không gian 3 chiều – nhưng chúng ta lại thường dễ vẽ hoặc hình dung những đồ vật trong không gian hai chiều. Và có một số cách khác để quan sát các hình đa diện ba chiều trong không gian 2 chiều.

    //- x-folding(shape="Tetrahedron" size=400)
    //- x-folding(shape="Cube" size=400)
    //- x-folding(shape="Octahedron" size=400)
    //- x-folding(shape="Dodecahedron" size=400)
    //- x-folding(shape="Icosahedron" size=400)

Hình khai triển nào tạo ra hình lập phương
Nối hình khai triển với đúng vật thể
https://github.com/polymake/matchthenet
Vẽ hình khai triển

Mô tả mặt cắt được tạo ra bởi phần giao nhau của mặt phẳng và một khối hình.

Mặt cắt là phần giao nhau giữa một mặt phẳng và một khối hình. 
Một cách khác để biểu diễn hình khối trong mặt phẳng 2 chiều là sử dụng hình khai triển. Hình khai triển là một biểu diễn phẳng, không bị gấp của các cạnh của một hình 3 chiều.

Xoay hình lập phương để tạo ra một mặt cắt có dạng hình lục giác

    // ---

    // ## Scaling Shapes and Solids

    // > section: scaling
    // > sectionStatus: dev

    // TODO

---

## Platonic Solids

> section: platonic
> id: platonic

Ở phần đầu của khóa học chúng ta đã định nghĩa [đa giác đều](gloss:regular-polygon)
Cũng như hình đa giác đối xứng đặc biệt, nơi mà tất cả các cạnh và các góc bằng nhau.
Chúng ta có thể làm tương tự với hình đa diện.

Trong một hình _đa diện đều_ tất cả [các mặt](gloss:polyhedron-face) sẽ cùng
một loại đa giác đều, và cùng số lượng mặt gặp nhau tại mỗi
[đỉnh](gloss:polyhedron-vertex). Hình đa diện với hai tính chất này được gọi là 
[__Khối Platonic __](gloss:platonic-solid), được đặt tên theo 
nhà triết học người Hy Lạp [Plato](bio:plato).

    //- Hình chóp ở bên phải không phải là khối Platonic. Nó chứa 2
    //- loại đa giác khác nhau (hình vuông và hình tam giác), và nó có [[4]]
    //- mặt gặp nhau tại đỉnh phía trên, nhưng chỉ có [[3]] ở các đỉnh phía dưới.

Vậy thì khối Platonic trông như thế nào – và có tất cả bao nhiêu khối như thế? Để tạo ra một hình khối, chúng ta cần ít nhất [[3]] mặt gặp nhau tại mỗi đỉnh. Hãy cùng bắt đầu một cách hệ thống với hình đa giác đều nhỏ nhất: tam giác đều:
---
> id: platonic-tetrahedron

::: column(width=120 parent="padded-thin")

    x-polyhedron(size=120 shape="Tetrahedron")

::: column(width=200)

    img(src="images/platonic/tetrahedron.svg" width=200 height=120)

::: column.grow
Nếu chúng ta tạo ra một đa diện nơi mà ba [tam giác đều](gloss:equilateral-triangle)
gặp nhau tại mỗi đỉnh, chúng ta sẽ có hình bên trái. Nó được gọi là
__Tetrahedron__ và nó có [[4]] mặt. _{.reveal(when="blank-0")}(“Tetra” means
“four” in Greek)._
:::

---
> id: platonic-octahedron

::: column(width=120 parent="padded-thin")

    x-polyhedron(size=120 shape="Octahedron")

::: column(width=200)

    img(src="images/platonic/octahedron.svg" width=200 height=120)

::: column.grow
Nếu bốn tam giác đều gặp nhau tại mỗi đỉnh, chúng ta sẽ có một khối Platonic
khác. Nó được gọi là __Octahedron__ và nó có [[8]] mặt.
_{.reveal(when="blank-0")}(“Octa” means “eight” in Greek. Cũng giống như “Octagon”
có nghĩa là hình có 8 cạnh, “Octahedron” nghĩa là khối có 8 mặt.)_
:::

---
> id: platonic-icosahedron

::: column(width=120 parent="padded-thin")

    x-polyhedron(size=120 shape="Icosahedron")

::: column(width=200)

    img(src="images/platonic/icosahedron.svg" width=200 height=120)

::: column.grow
Nếu [[năm]] tam giác gặp nhau tại mỗi đỉnh, chúng ta có __Icosahedron__. Nó có
[[20]] mặt. _{.reveal(when="blank-1")}(“Icosa” có nghĩa là  “hai mươi” trong tiếng Hy Lạp.)_
:::

---
> id: platonic-6-triangles

::: column(width=120 parent="padded-thin")
::: column(width=200)

    img.reveal(when="blank-1" src="images/platonic/triangles-6.svg" width=200 height=120)

::: column.grow
Nếu [[sáu]] tam giác gặp nhau tại mỗi đỉnh, có một vài thứ khác xảy ra: đơn thuần chúng ta có [[một tessellation|một tứ giác|một khối Icosahedron khác]],
_{span.reveal(when="blank-1")}thay vì một khối đa diện 3 chiều._
:::

---
> id: platonic-7-triangles

::: column(width=120 parent="padded-thin")
::: column(width=200)

    img(src="images/platonic/triangles-7.svg" width=200 height=120)

::: column.grow
Và 7 hoặc nhiều tam giác hơn nữa gặp nhau tại mỗi đỉnh cũng không thể tạo ra một đa diện mới: không đủ không gian xung quanh mỗi đỉnh, để vừa khít với số tam giác đó. 
:::

Điều này có nghĩa chúng ta tìm thấy [[ba]] khối Platonic bao gồm các tam giác. Nào hãy cùng đến với một khối đa giác đều nữa: hình vuông.
---
> id: platonic-cube

::: column(width=120 parent="padded-thin")

    x-polyhedron(size=120 shape="Cube")

::: column(width=200)

    img(src="images/platonic/cube.svg" width=200 height=120)

::: column.grow
Nếu [[ba]] hình vuông gặp nhau tại mỗi đỉnh, chúng ta có __hình lập phương__. Giống như con xúc xắc, nó có [[6]] mặt. _{span.reveal(when="blank-1")} Hình lập phương đôi lúc cũng được gọi là *Hexahedron*, được đặt theo tên tiếng Hy Lạp “hexa" có nghĩ là “sáu”._
:::

---
> id: platonic-4-squares

::: column(width=120 parent="padded-thin")
::: column(width=200)

    img.reveal(when="blank-1" src="images/platonic/squares.svg" width=200 height=120)

::: column.grow
Nếu [[bốn]] tam giác gặp nhau tại mỗi đỉnh, chúng ta có [[một tessellation khác |một tứ diện đều tetrahedron|một hình lập phương khác]].
_{span.reveal(when="blank-1")} Và cũng giống như trước, năm hoặc nhiều hình vuông hơn không có nghĩa gì._
:::

---
> id: platonic-dodecahedron

Tiếp theo, hãy thử với hình ngũ giác đều:
::: column(width=120 parent="padded-thin")

    x-polyhedron(size=120 shape="Dodecahedron")

::: column(width=200)

    img(src="images/platonic/dodecahedron.svg" width=200 height=120)

::: column.grow
Nếu [[ba]] ngũ giác gặp nhau tại cùng một đỉnh, chúng ta có __Dodecahedron__. Nó có
[[12]] mặt. _{.reveal(when="blank-1")} (“Dodeca” có nghĩa “12” trong tiếng Hy Lạp.)_
:::

---
> id: platonic-4-pentagons

::: column(width=120 parent="padded-thin")
::: column(width=200)

    img(src="images/platonic/pentagons.svg" width=200 height=120)

::: column.grow
Giống như trước đó, bốn hoặc nhiều ngũ giác hơn [[không có ý nghĩa gì|có thể]] bởi vì không có đủ không gian.
:::

---
> id: platonic-hexagons

Hình đa giác đều tiếp theo là lục giác đều:

::: column(width=120 parent="padded-thin")
::: column(width=200)

    img.reveal(when="blank-0" src="images/platonic/hexagons.svg" width=200 height=120)

::: column.grow
Nếu ba lục giác gặp nhau tại mỗi đỉnh, chúng ta sẽ có ngay một [[tessellation|đa diện|đa diện có các mặt là hình lục giác]].
_{span.reveal(when="blank-0")} Vì không có không gian cho nhiều hơn 3 hình, nên cũng khó để tạo ra một hình khối Platonic bao gồm các hình lục giác._
:::

---
> id: platonic-final

Điều này cũng xảy ra với mọi đa giác đều có nhiều hơn sáu cạnh. Chúng không thể lát gạch,và chúng ta chắc chắn sẽ không thu được bất kì đa diện 3 chiều nào. 

Điều này cũng có nghĩa chỉ có [[năm]] khối Platonic! Hãy cùng nhìn chúng một lượt nữa nào. 

---
> id: platonic-overview

::: column.grow.text-center(width=120 parent="plato padded-thin")
__Tetrahedron__

    x-polyhedron.dual(size=120 shape="Tetrahedron")

_{span.dual}[[4]] Faces_<br>
_{span.dual}[[4]] Vertices_<br>
_{span.dual}[[6]] Edges_

::: column.grow.text-center(width=120)
__Cube__

    x-polyhedron.dual(target="dual1" size=120 shape="Cube")

_{span.dual(target="dual1")}[[6]] Faces_<br>
_{span.dual(target="dual1")}[[8]] Vertices_<br>
_{span.dual}[[12]] Edges_

::: column.grow.text-center(width=120)
__Octahedron__

    x-polyhedron.dual(target="dual1" size=120 shape="Octahedron")

_{span.dual(target="dual1")}[[8]] Faces_<br>
_{span.dual(target="dual1")}[[6]] Vertices_<br>
_{span.dual}[[12]] Edges_

::: column.grow.text-center(width=120)
__Dodecahedron__

    x-polyhedron.dual(target="dual2" size=120 shape="Dodecahedron")

_{span.dual(target="dual2")}[[12]] Faces_<br>
_{span.dual(target="dual2")}20 Vertices_<br>
_{span.dual}30 Edges_

::: column.grow.text-center(width=120)
__Icosahedron__

    x-polyhedron.dual(target="dual2" size=120 shape="Icosahedron")

_{span.dual(target="dual2")}[[20]] Faces_<br>
_{span.dual(target="dual2")}12 Vertices_<br>
_{span.dual}30 Edges_
:::

{.reveal(when="blank-3 blank-4 blank-6 blank-7 blank-9 blank-10")} Chú ý làm thế nào mà số lượng mặt và đỉnh [[đổi chỗ cho nhau|giống nhau]] đối với [hình lập phương và hình 8 mặt](target:dual1), cũng như [hình 12 mặt và hình 20 mặt](target:dual2), trong khi số lượng cạnh [[giữ nguyên|khác nhau]]. Cặp các khối Platonic được gọi là [__các khối đối ngẫu__](gloss:polyhedron-dual).

---
> id: platonic-dual

Chúng ta có thể xoay một hình đa diện trở thành một khối hình đối ngẫu của nó, bằng cách thay thế mỗi mặt với 1 đỉnh, và mỗi đỉnh với một mặt. Những chuyển động dưới đây sẽ cho chúng ta hình dung rõ:

::: column(width=300)

    x-solid(size=300)
    x-slider(steps=100)

::: column(width=300)

    x-solid(size=300)
    x-slider(steps=100)

:::

Hình tứ diện đối ngẫu với chính nó. Vì nó có số lượng mặt và đỉnh như nhau, việc đổi chỗ chúng cho nhau không làm thay đổi điều gì. 

---
> id: platonic-elements

[Plato](bio:plato) tin tưởng rằng mọi vật chất trong vũ trụ đều được tạo ra từ 4 nguyên tố: khí, đất, nước và lửa. Ông ấy nghĩ rằng mọi nguyên tố tương ứng với một khối Platonic, trong khi nguyên tố thứ năm có thể biểu diễn toàn bộ vũ trụ. Ngày nay, chúng ta biết rằng có nhiều hơn 100 nguyên tố khác nhau bao gồm các nguyên tử hình cầu, chứ không phải đa diện. 

    figure
      img(src="images/elements.jpg" width=600 height=153)
      p.caption Images from Johannes Kepler’s book “Harmonices Mundi” (1619)

---

### Archimedean Solids

> id: archimedean

Khối Platonic là các hình đa diện đặc biệt quan trọng, nhưng lại có vô số những thứ khác. 

Ví dụ như, [__Khối Archimedean__](gloss:archimedean-solid), vẫn phải được tạo ra bởi [các đa giác đều](gloss:regular-polygon), nhưng bạn có thể sử dụng nhiều loại khác nhau cùng lúc. Chúng được đặt tên theo một nhà Toán học người Hy Lạp, [Archimedes
of Syracuse](bio:archimedes), và có 13 khối như thế:

::: column(width=170 parent="padded-thin")
    x-polyhedron(size=170 shape="TruncatedTetrahedron")

{.caption} __Truncated Tetrahedron__<br>
8 mặt, 12 đỉnh, 18 cạnh
::: column(width=170)
    x-polyhedron(size=170 shape="Cuboctahedron")

{.caption} __Cuboctahedron__<br>
14 mặt, 12 đỉnh, 24 cạnh
::: column(width=170)
    x-polyhedron(size=170 shape="TruncatedCube")

{.caption} __Truncated Cube__<br>
14 mặt, 24 đỉnh, 36 cạnh
::: column(width=170)
    x-polyhedron(size=170 shape="TruncatedOctahedron")

{.caption} __Truncated Octahedron__<br>
14 mặt, 24 đỉnh, 36 cạnh
::: column(width=170)
    x-polyhedron(size=170 shape="Rhombicuboctahedron")

{.caption} __Rhombicuboctahedron__<br>
26 mặt, 24 đỉnh, 48 cạnh
::: column(width=170)
    x-polyhedron(size=170 shape="TruncatedCuboctahedron")

{.caption} __Truncated Cuboctahedron__<br>
26 mặt, 48 đỉnh, 72 cạnh
::: column(width=170)
    x-polyhedron(size=170 shape="SnubCube")

{.caption} __Snub Cube__<br>
38 mặt, 24 đỉnh, 60 cạnh
::: column(width=170)
    x-polyhedron(size=170 shape="Icosidodecahedron")

{.caption} __Icosidodecahedron__<br>
32 mặt, 30 đỉnh, 60 cạnh
::: column(width=170)
    x-polyhedron(size=170 shape="TruncatedDodecahedron")

{.caption} __Truncated Dodecahedron__<br>
32 mặt, 60 đỉnh, 90 cạnh
::: column(width=170)
    x-polyhedron(size=170 shape="TruncatedIcosahedron")

{.caption} __Truncated Icosahedron__<br>
32 mặt, 60 đỉnh, 90 cạnh
::: column(width=170)
    x-polyhedron(size=170 shape="Rhombicosidodecahedron")

{.caption} __Rhombicosidodecahedron__<br>
62 mặt, 60 đỉnh, 120 cạnh
::: column(width=170)
    x-polyhedron(size=170 shape="TruncatedIcosidodecahedron")

{.caption} __Truncated Icosidodecahedron__<br>
62 mặt, 120 đỉnh, 180 cạnh
::: column(width=170)
    x-polyhedron(size=170 shape="SnubDodecahedron")

{.caption} __Snub Dodecahedron__<br>
92 mặt, 60 đỉnh, 150 cạnh
:::

    // Prisms and antiprisms, và các nhóm đối xứng của chúng là các nhóm nhị diện,     
    // thường không được xem là khối Archimedean, mặt dù chúng cũng thỏa mãn    
    // các định nghĩa phía trên.

---
> id: polyhedra-applications

### Applications

Plato đã sai khi tin tưởng rằng tất cả các nguyên tố là tập hợp của các khối Platonic. Nhưng các đa diện đều có nhiều tính chất đặc biệt khiến chúng xuất hiện nhiều trong tự nhiên – và chúng ta có thể tận dụng những tính chất này trong khoa học và trong kĩ thuật. 

::: column(width=180)

    x-img(lightbox width=180 height=180 src="images/radiolaria.jpg")
    p.caption Radiolaria skeleton

::: column(width=180)

    x-img(lightbox width=180 height=180 src="images/virus.jpg")
    p.caption Icosahedral virus

::: column.grow
Nhiều __loại vi rút__, __vi khuẩn__ và những loại __sinh vật__ nhỏ khác có dạng giống như
[icosahedra](gloss:icosahedron). Ví dụ như vi rút, phải bao bọc vật chất di truyền của chúng bên trong vỏ gồm nhiều đơn vị protein giống nhau. Hình The đa diện 20 mặt hiệu quả để làm được điều đó, bởi vì nó chứa một số nguyên tố thường nhưng có dạng giống như hình cầu.
:::

::: column(width=180)

    x-img(lightbox, credit="NASA/JPL", width=180, height=180, src="images/buckyball.jpg")
    p.caption Buckyball molecule

::: column(width=180)

    x-img(lightbox, credit="Philipp Hienstorfer, via Wikipedia", width=180, height=180, src="images/biosphere.jpg")
    p.caption Montreal Biosphere

::: column.grow
Nhiều __phân tử__ có dạng giống như hình đa diện đều. Một ví dụ nổi tiếng là `C_60` chứa tới 60 nguyên tử carbon được sắp xếp dạng hình [Truncated
Icosahedron](gloss:truncated-icosahedron).

Nó được phát hiện vào năm 1985 khi một nhà khoa học nghiên cứu hạt bụi giữa các vì sao. Chúng được đặt tên là “Buckyball” (or Buckminsterfullerene) theo tên nhà kiến trúc [Buckminster
Fuller](bio:fuller), người nổi tiếng vì xây dựng những tòa nhà trông đồng dạng nhau. 
:::

::: column(width=180)

    x-img(lightbox credit="Chris Gladis via Wikipedia" width=180 height=180 src="images/crystal.jpg")
    p.caption Fluorite octahedron

::: column(width=180)

    x-img(lightbox credit="Archaeodontosaurus, via Wikipedia" width=180 height=180 src="images/rock.jpg")
    p.caption Pyrite cube

::: column.grow
Hầu hết __những viên pha lê__ có những nguyên tử được sắp xếp trong lưới đều nhau, bao gồm [hình tứ diện](gloss:tetrahedron), [hình lập phương](gloss:cube) or [hình đa diện 8 mặt](gloss:octahedron).
Khi chúng nứt hoặc vỡ, bạn có thể nhìn thấy những hình dạng này trên quy mô lớn hơn. 
:::

::: column(width=180)

    x-img(lightbox, credit="Andrew Dunn, via Wikipedia", width="180", height="180", src="images/space-frame.jpg")
    p.caption Octagonal space frames

::: column(width=180)

    x-img(lightbox width="180", height="180", src="images/louvre.jpg")
    p.caption Louvre museum in Paris

::: column.grow
Hình tứ diện và hình 8 mặt cực kì cứng và ổn định, điều này là chúng trở nên hữu ích trong __xây dựng__. _Khung không gian_ là những cấu trúc đa giác có thể nâng đỡ những mái nhà lớn và những cây cầu nặng. 
:::

::: column(width=180)

    x-img(lightbox width="180", height="180", src="images/football.jpg")
    p.caption Football

::: column(width=180)

    x-img(lightbox width="180", height="180", src="images/dice.jpg")
    p.caption Polygonal role-playing dice

::: column.grow
Các khối Platonic được sử dụng để tạo ra __xúc xắc__. Bởi vì tính chất đối xứng của chúng, mỗi cạnh có [xác suất](gloss:probability) xuất hiện như nhau – nên con xúc xắc đó là công bằng.

[Hình 20 mặt cụt](gloss:truncated-icosahedron) có lẽ là hình đa diện nổi tiếng nhất trên thế giới: nó là hình dạng của quả bóng đá.
:::

