# Tam giác và lượng giác

## Giới thiệu

> id: intro
> section: introduction
> description: "Triangles are some of the most important shapes in geometry: they have countless interesting properties and appear everywhere in engineering and technology."
> color: "#3566DE"
> level: Intermediate
> next: polyhedra

::: column.grow
Vào đầu thế kỷ 19, các nhà thám hiểm đã khám phá hầu hết thế giới. Hoạt động giao thương  và vận tải  bùng nổ giữa các quốc gia xa xôi và điều này tạo ra nhu cầu về  bản đồ tổng hợp  của toàn thế giới.

Ngày nay chúng ta có các vệ tinh có thể chụp ảnh từ trên cao, nhưng cách đây 200 năm  việc lập bản đồ là một công việc khó khăn và tốn nhiều thời gian. Nó được thực hiện bởi các nhà toán học như [Radhanath Sikdar] (bio: sikdar), người đã làm việc trong _Great Trigonometrical Survey_: một dự án  hàng thế kỷ để khảo sát toàn bộ Ấn Độ, bao gồm cả dãy  Himalaya.

::: column(width=240)

    x-img.shift-1(src="images/theodolite.jpg" width=240 height=320 credit="Science & Society Picture Library")

{.caption} The _theodolite_, a surveying instrument
:::

       Mối quan tâm đặc biệt là tìm kiếm được ngọn núi cao nhất trên Trái đất. Có một vài ứng cử viên khác nhau, tuy nhiên  từ cách xa hàng trăm km, rất khó để phân biệt ngọn núi nào là cao nhất.
       Vậy làm cách nào để có thể đo được chiều cao của một ngọn núi?
 
   figure.mountain: include svg/mountain.svg

{.r}  Ngày nay chúng ta có thể sử dụng vệ tinh để đo chiều cao của các ngọn núi trong phạm vi vài cm - nhưng chúng không tồn tại khi Radhanath khảo sát Ấn Độ.[Tiếp tục](btn:next)

{.r.reveal(when="next-0")}  Những người leo núi sử dụng _ altimeter _ để xác định độ cao của những ngọn núi. Các thiết bị này sử dụng sự chênh lệch áp suất không khí ở các độ cao khác nhau. Tuy nhiên, điều này sẽ đòi hỏi người đo phải thực sự leo lên [đỉnh của mọi ngọn núi] (->. Mountain-top) - một kỳ tích cực kỳ khó khăn mà mãi một thế kỷ sau mới đạt được. [Tiếp tục](btn:next)

{.r.reveal(when="next-1")} Bạn cũng có thể thử sử dụng các tam giác đồng dạng, giống như chúng ta đã làm trong [khóa học trước] (/ khóa học / phép biến đổi / phép tương tự). Phương pháp này yêu cầu biết [khoảng cách] (->. Núi-khoảng cách) đến [chân núi] (->. núi-base): điểm ở mực nước biển nằm ngay dưới đỉnh của nó. Chúng ta có thể áp dụng cách  này đối với cây cối hoặc nhà cao tầng, nhưng đối với những ngọn núi, điểm này nằm khuất bên dưới những tảng đá hàng trăm mét.
[Tiếp tục](btn:next)

---
> id: intro-2

::: column(width=320)

    x-img(src="images/hillary.jpg" width=320 height=190)

{.caption} Edmund Hillary and Tenzing Norgay were the first to reach the top of
Mount Everest, in 1953.

::: column.grow

     Có những kỹ thuật hình học tiên tiến hơn, mà [Radhanath] (sinh học: sikdar) đã sử dụng để khám phá ngọn núi cao nhất trên Trái đất: hiện nay ngọn núi đó  được gọi là _ Núi Everest_. Số đo của anh ấy chỉ chênh lệch vài mét so với chiều cao chính thức của ngày hôm nay là 8848 mét.
    Trong khóa học này, bạn sẽ tìm hiểu về những đặc điểm và tính chất khác nhau của hình tam giác. Chúng sẽ cho phép bạn đo chiều cao của núi. Những đặc điểm, tính chất đó cũng đóng vai trò quan trọng cơ bản trong nhiều lĩnh vực toán học, khoa học và kỹ thuật khác.
[Tiếp tục](btn:next)

:::

---
> id: applications

Hình tam giác khác biệt bởi vì chúng đặc biệt _strong_. Chúng là đa giác duy nhất, khi được tạo ra từ dầm và bản lề bằng gỗ, sẽ hoàn toàn _rigid_ - không giống như hình chữ nhật, chẳng hạn, bạn có thể dễ dàng đẩy qua lại. 


{.todo} COMING SOON – Animations

---
> id: applications-1

Tính chất này làm cho hình tam giác đặc biệt hữu ích trong lĩnh vực xây dựng, nơi chúng có thể chịu được sức nặng.

::: column(width=200)
    x-img(src="images/truss-bridge.jpg" credit="© ykanazawa1999, Flickr" width=200 height=200 lightbox)

{.caption}"Cầu giàn" được hỗ trợ bởi các thanh hình tam giác
::: cột (chiều rộng = 200)
    x-img(src="images/pylon.jpg" width=200 height=200 lightbox)

{.caption}Các hình tam giác trong cột điện cao áp
::: column(width=200)
    x-img(src="images/bike.jpg" width=200 height=200 lightbox)

{.caption} Ngay cả xe đạp cũng sử dụng hình tam giác để tạo sự ổn định.
:::

---
> id: applications-2
> goals: video

Hình tam giác cũng là hình đa giác đơn giản và có ít cạnh nhất. Điều này làm cho chúng trở nên đặc biệt phù hợp với các bề mặt cong phức tạp. Chính vì vậy mà chúng được thực hiện trong tòa nhà vật lý…

::: column(width=200)
    x-img(src="images/st-mary.jpg" credit="Kunstlerbob, Wikipedia" width=200 height=200 lightbox)

{.caption} “The Gherkin”, một tòa nhà chọc trời ở London.
::: column(width=200)
    x-img(src="images/hk-bank.jpg" credit="WiNG, Wikipedia" width=200 height=200 lightbox)

{.caption} Tháp Ngân hàng Trung Quốc ở Hồng Kông
::: column(width=200)
    x-img(src="images/museum.jpg" credit="Andrew Dunn, Wikipedia" width=200 height=200 lightbox)

{.caption} Sân trong của Bảo tàng Anh ở London
:::

::: column.grow
…mà còn trong thế giới ảo. Trong đồ họa máy tính (ví dụ: phim hoặc trò chơi điện tử), tất cả các bề mặt đều được tính gần đúng bằng cách sử dụng “lưới” các hình tam giác nhỏ. Các nghệ sĩ và kỹ sư phần mềm cần phải có sự hiểu biết  về hình học và lượng giác để có thể di chuyển và biến đổi các hình tam giác này một cách thực tế, cũng như tính toán màu sắc và kết cấu của chúng.
::: column(width=220)
    x-img(src="images/dolphin.jpg" width=220 height=135)
:::

    figure: x-video(src="https://static.mathigon.org/videos/tiger.mp4" poster="images/tiger.jpg" width=480 height=270 credit="© UCTV, The STEAM Channel")
    //- src: https://www.youtube.com/watch?v=Y9PYzdFsVio

---

## Tính chất của tam giác

> id: angle-sum
> section: properties

Hãy bắt đầu đơn giản: một tam giác là một hình dạng khép kín có ba cạnh (là [đoạn thẳng] (bóng: đoạn thẳng)) và ba đỉnh ([điểm] (bóng: điểm) nơi các cạnh gặp nhau). Nó cũng có ba [góc trong] (bóng: góc trong), và chúng ta đã biết rằng tổng của chúng luôn là [[180]] °.

---
> id: classification

Chúng ta có thể phân loại các hình tam giác theo kích thước các góc của chúng:

::: column(width=220)

    x-geopad(width=220): svg
      circle(name="a1" x="point(40,60)")
      circle(name="b1" x="point(40,140)")
      circle(name="c1" x="point(180,140)")
       path.fill.red(x="angle(a1,b1,c1)")
      path(x="polygon(a1,b1,c1)")

{.caption} Tam giác vuông<br>
has one [right angle](gloss:right-angle).
::: column(width=220)

    x-geopad(width=220): svg
      circle(name="a2" x="point(30,30)")
      circle(name="b2" x="point(150,60)")
      circle(name="c2" x="point(190,190)")
      path.fill.blue(x="angle(c2,b2,a2)")
      path(x="polygon(a2,b2,c2)")
{.caption}Tam giác tù [obtuse angle](gloss:obtuse-angle).
::: column(width=220)

    x-geopad(width=220): svg
      circle(name="a3" x="point(60,50)")
      circle(name="b3" x="point(30,180)")
      circle(name="c3" x="point(190,130)")
      path.fill.green(x="angle(a3,b3,c3)")
      path.fill.green(x="angle(b3,c3,a3)")
      path.fill.green(x="angle(c3,a3,b3)")
      path(x="polygon(a3,b3,c3)")
{.caption} An __acute triangle__<br>
has [[three]] [acute angles](gloss:acute-angle).
:::

---
> id: labels

::: column.grow

Để thuận tiện, chúng tôi luôn dán nhãn các hình tam giác theo cùng một cách. Các đỉnh được kí hiệu bằng chữ in hoa [_A_, _B_ and _C_](target:vertex), các cạnh được kí hiệu bằng chữ thường [_a_, _b_ and _c_](target:side), à các góc được kí hiệu bằng các chữ cái Hy Lạp [`α`, `β` and `γ`](target:angle) (“alpha”, “beta” and “gamma”).

The [side that lies _opposite_ vertex _A_](target:X) is labeled _a_, and the
[angle that lies right next to _A_](target:Y) is labelled `α`. The same pattern
works for _B_/_b_/`β` and for _C_/_c_/`γ`.
::: column(width=220)

    x-geopad(width=220 height=200): svg
      circle.move.red(name="a" cx=80 cy=30 label="A" target="vertex X Y")
      circle.move.blue(name="b" cx=30 cy=170 label="B" target="vertex")
      circle.move.green(name="c" cx=190 cy=150 label="C" target="vertex")
      path.red(x="angle(c,a,b).sup" label="α" target="angle Y")
      path.blue(x="angle(a,b,c).sup" label="β" target="angle")
      path.green(x="angle(b,c,a).sup" label="γ" target="angle")
      path.red(x="segment(b,c)" label="a" target="side X")
      path.blue(x="segment(a,c)" label="b" target="side")
      path.green(x="segment(b,a)" label="c" target="side")

:::

---
> id: medians
> goals: s0 s1 s2 move
### Medians

::: column(width=300)

    x-geopad.sticky(width=300 tools="move|line" projections="no"): svg
      circle.move(name="a" cx=75 cy=75 target="ratio")
      circle.move(name="b" cx=50 cy=250)
      circle.move(name="c" cx=250 cy=200)
      path(x="triangle(a,b,c)")

      circle.green(name="ab" x="line(a,b).midpoint")
      circle.blue(name="ac" x="line(a,c).midpoint")
      circle.red(name="bc" x="line(b,c).midpoint" target="ratio")

      circle.yellow.reveal(name="d" x="triangle(a,b,c).centroid" when="blank-0" animation="pop" target="ratio")

      path.red.transparent(x="segment(a,d)" label="2" target="ratio")
      path.red.transparent(x="segment(d,bc)" label="1" target="ratio")

::: column.grow
Ở đây bạn có thể thấy một tam giác cũng như [midpoints](gloss:midpoint) của ba cạnh của nó.
