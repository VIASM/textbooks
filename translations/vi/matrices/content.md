# Matrices

## Transformations

> section: transformations
> sectionStatus: dev
> id: rocket
> goals: projectile
> color: "#5A49C9"
> level: Advanced

::: column.grow

Khi chúng ta chơi trò chơi điện tử với đồ họa 3D, cái mà chúng ta thực sự nhìn thấy là hàng triệu triệu tam giác siêu bé. Mọi thứ từ những ngọn núi cho tới những ngọn cỏ tạo nên môi trường sống, đến những con yêu tinh canh giữ kho báu quý giá, con tàu vũ trụ mà bạn lái qua vành đai tiểu hành tinh, được tạo thành từ nhiều tam giác nhỏ. Chiếc máy tính trong bảng điều khiển trò chơi của bạn chạy hàng nghìn tỉ phép tính để tìm ra cách mỗi hình dạng sẽ được hiển thị trên màn hình.

::: column.fit

    x-geopad(width=400 x-axis="-18,18,5" y-axis="-18,18,5" padding=5): svg
      - var path = "point(0,3),point(2,0),point(2,-2),point(0,-1),point(-2,-2),point(-2,0)"
      path.fill.green(x=`polygon(${path}).rotate(th)`)

:::

Máy tính của chúng ta đang thực hiện loạt những tính toán nào? Trước khi thử hiện thị các nhân vật hoặc phong cảnh ba chiều phức tạp, hãy tưởng tượng chúng ta muốn vẽ một con tàu vũ trụ 2D mà chúng ta có thể xoay để bắn các tiểu hành tinh đang đi đến. 
---

Đây là con tàu vũ trụ khiêm tốn của chúng ta. Giống như các hình dạng hiển thị trong trò chơi điện tử, chúng ta có thể thể hiện con tàu vũ trụ của mình như một tập hợp các điểm, với các đường nối chúng. Chúng ta có thể vẽ nó trên mặt phẳng tọa độ xy, có tâm là điểm gốc, với mỗi điểm được gắn nhãn là một giá trị (x,y). 

::: column(width=400)

    x-geopad(width=400 x-axis="-5,5,1" y-axis="-5,5,1" axes grid padding=5): svg
      circle.green(name="a" x="point(0,3)" label="A" target="a")
      circle.green(name="b" x="point(2,0)" label="B")
      circle.green(name="c" x="point(2,-2)" label="C")
      circle.green(name="d" x="point(0,-1)" label="D")
      circle.green(name="e" x="point(-2,-2)" label="E")
      circle.green(name="f" x="point(-2,0)" label="F")

      path.green(x="segment(a,b)")
      path.green(x="segment(b,c)")
      path.green(x="segment(c,d)")
      path.green(x="segment(d,e)")
      path.green(x="segment(e,f)")
      path.green(x="segment(f,a)")

:::

Đây là điểm [{.green} A](target:a) có tọa độ ([[0]], [[3]]).

---

Chúng ta muốn cung cấp cho con tàu vũ trụ của mình khả năng xoay tại chỗ, để người chơi có thể chỉ nó vào các tiểu hành tinh đang đến. Vòng quay này là thứ mà chúng ta gọi là [phép biến hình](gloss:transformation). Hãy thông báo sự quay của tàu vũ trụ thông qua góc θ as `R_"θ"`.

{.text-center} `{P_"1", P_"2", P_"3", P_"4", P_"5", P_"6"}` --- `R_"θ"` ---> `{P_"1"', P_"2"', P_"3"', P_"4"', P_"5"', P_"6"'}`
{.fixme} Có thể tốt với các điểm di chuột vào đồ họa.

Mỗi điểm `P_"n"` được áp dụng phép biến hình`R_"θ"` , điều này xoay điểm xung quanh gốc tọa độ để có điểm `P_"n"'` (được phát âm là "P n prime").

Đây là một con tàu vũ trụ chúng ta có thể xoay bởi ${phi + 'º'}{phi|60|10,350,10} xung quanh gốc tọa độ.

::: column(width=400)

    x-geopad(width=400 x-axis="-5,5,1" y-axis="-5,5,1" axes grid padding=5): svg
      circle.green(name="a" x="point(0,3)" label="A" target="a")
      circle.green(name="b" x="point(2,0)" label="B")
      circle.green(name="c" x="point(2,-2)" label="C")
      circle.green(name="d" x="point(0,-1)" label="D")
      circle.green(name="e" x="point(-2,-2)" label="E")
      circle.green(name="f" x="point(-2,0)" label="F")

      circle.blue(name="ap" x="a.rotate(phi/180*pi)" label="A'")
      circle.blue(name="bp" x="b.rotate(phi/180*pi)" label="B'")
      circle.blue(name="cp" x="c.rotate(phi/180*pi)" label="C'")
      circle.blue(name="dp" x="d.rotate(phi/180*pi)" label="D'")
      circle.blue(name="ep" x="e.rotate(phi/180*pi)" label="E'")
      circle.blue(name="fp" x="f.rotate(phi/180*pi)" label="F'")

      path.green(x="segment(a,b)")
      path.green(x="segment(b,c)")
      path.green(x="segment(c,d)")
      path.green(x="segment(d,e)")
      path.green(x="segment(e,f)")
      path.green(x="segment(f,a)")

      path.blue(x="segment(ap,bp)")
      path.blue(x="segment(bp,cp)")
      path.blue(x="segment(cp,dp)")
      path.blue(x="segment(dp,ep)")
      path.blue(x="segment(ep,fp)")
      path.blue(x="segment(fp,ap)")

:::

Và đây là một vài điều chúng ta có thể nói về hình dạng của con tàu vũ trụ khi nó xoay:
- Con tàu vũ trụ sẽ giữ nguyên hình dạng. 
- Con tàu vũ trụ sẽ giữ nguyên kích thước. 
- Con tàu vũ trụ sẽ không di chuyển lên hoặc xuống.

Chúng ta muốn có một công thức để chuyển đổi mọi điểm `P` thành điểm `P'` qua phép quay.

Hãy bắt đầu tính công thức này cho hai điểm khác nhau. 

[Continue](btn:next)

---
> id: two-points

### Tính phép quay với hai điểm khác nhau.

Với 2 điểm của chúng ta, hãy lấy [{.green} A](target:a) = `(0,3)` và [{.green} B](target:b) = `(2,0)`. Chúng ta có thể xác định công thức cho phép quay của chúng [{.purple} θ](target:theta) xung quanh gốc tọa độ cùng một lúc.

::: tab
#### (0,3)

Nếu chúng ta quay điểm [{.green}A](target:a) tại (0,3) ${t1 + 'º'}{t1|60|10,350,10} xung quanh gốc tọa độ, nó có giá trị mới `(x,y)`. Chúng ta có thể gọi điểm quay đó [{.blue}A'](target:ap) (A prime), với tọa độ `(x', y')` (x prime and y prime).

::: column(width=400)

    x-geopad(width=400 x-axis="-5,5,1" y-axis="-5,5,1" axes grid padding=5): svg
      circle.green(name="a" x="point(0,3)" label="A" target="a")

      circle.blue(name="ap" x="a.rotate(t1/180*pi)" label="A'" target="ap tri1")

      path.green(x="segment(point(0,0),a)")

      path.blue(x="segment(point(0,0),ap)" target="tri1")
      path.red(x="segment(point(0,ap.y), point(ap.x, ap.y))" target="xp tri1" label="x'")
      path.yellow(x="segment(point(0,0), point(0, ap.y))" target="yp tri1" label="y'")

      path.purple(x="angle(ap,point(0,0),a)" target="theta tri1" round size=40)

:::

Công thức nào để tạo nên tọa độ mới của điểm A’? Chúng ta có thể gọi giá trị mới x [{.red}x'](target:xp), và giá trị mới y  [{.yellow}y'](target:yp). Cả __x'__ và __y'__ sẽ phụ thuộc vào độ dài của __A__, nó bằng 3.

Các điểm này tạo thành một [tam giác vuông](target:tri1), vì thế chúng ta có thể vẽ dựa trên hiểu biết của chúng ta về lượng giác để tìm ra công thức cho __x'__ và __y'__.

{.fixme} Điều này có lẽ sẽ hơi hoang mang khi góc theta > 90º

Giá trị của chúng ta [{.red}x'](target:xp) thì ngược lại với góc đã biết, vì thế chúng ta có thể sử dụng công thức [sine](gloss:sin) để xác định rằng:

`x' = 3 * `[[-sin(θ)|sin(θ)|cos(θ)]]

Giá trị của chúng ta [{.yellow}y'](target:yp) là cạnh kề của một tam giác vuông, vì vậy chúng ta có thể sử dụng công thức [cosine](gloss:cos) để xác định rằng:

`y' = 3 * `[[cos(θ)|sin(θ)]]


::: tab
#### (2,0)

Hãy quan sát các điểm khác:
Nếu chúng ta xoay điểm [{.green}B](target:b) tại (2,0) ${t2 + 'º'}{t2|60|10,350,10} xung quanh gốc tọa độ, nó có tọa độ mới `(x,y)` Chúng ta có thể gọi điểm được quay [{.blue}B'](target:bp) (B prime), với tọa độ `(x', y')` (x prime and y prime).

::: column(width=400)

    x-geopad(width=400 x-axis="-5,5,1" y-axis="-5,5,1" axes grid padding=5): svg
      circle.green(name="b" x="point(2,0)" label="B" target="b")

      circle.blue(name="bp" x="b.rotate(t2/180*pi)" label="B'" target="bp tri2")

      path.green(x="segment(point(0,0),b)")

      path.blue(x="segment(point(0,0),bp)" target="tri2")
      path.red(x="segment(point(0,0), point(bp.x, 0))" label="x'" target="xp tri2")
      path.yellow(x="segment(point(bp.x, 0), point(bp.x, bp.y))" label="y'" target="yp tri2")
      path.purple(x="angle(bp,point(0,0),b)" target="tri2" round size=40)


:::

Công thức nào để tạo ra tọa độ mới cho điểm [{.blue}B’](target:bp)? Chúng ta có thể gọi giá trị mới x [{.red}x'](target:xp), và giá trị mới y  [{.yellow}y'](target:yp). Cả __x'__ và __y'__ sẽ phụ thuộc và độ dài của __B__, nó bằng 2.

Các điểm này tạo thành một [tam giác vuông](target:tri2), vì vậy chúng ta có thể vẽ dựa trên hiểu biết của chúng ta về lượng giác để tìm ra công thức cho __x'__ and __y'__.

{.fixme} Điều này có thể gây hoang mang khi góc theta > 90º

Giá trị của chúng ta [{.red}x'](target:xp) là cạnh kề của góc đa biết,vì vậy chúng ta có thể sử dụng công thức [cosine](gloss:cos) để xác định rằng:

`x' = 2 * `[[cos(θ)|sin(θ)]]

Giá trị của chúng ta [{.yellow}y'](target:yp) là cạnh đối diện của góc đa biết, vì vậy chúng ta có thể sử dụng công thức [sine](gloss:sin) để xác định rằng:

`y' = 2 * `[[sin(θ)|cos(θ)]]

:::


---
> id: linear-combination

::: column

Bây giờ chúng ta có phương trình cho tọa độ `(x', y')` của hai điểm `A'` and `B'`. Chúng ta vẫn có nhiều điểm quay để tính, ví dụ như (`C'`, vân vân), nhưng liệu có con đường tắt nơi chúng ta có thể sử dụng những thứ chúng ta đã có? 

::: column


    table
      tr
        td Name
        td xy
        td Rotated
        td Rxy
      tr
        td A
        td (0, 2)
        td A'
        td (-2sin(θ), 2cos(θ))
      tr
        td B
        td (3, 0)
        td B'
        td 3cos(θ), 3sin(θ))
      each p in [['C', [2, -2]] , ['D', [0, -1]], ['E', [-2, -2]], ['F', [-2, 0]]]
        - var pp = p[0] + "'"
        tr
          td= p[0]
          td= p[1]
          td= pp
          td

:::

{.fixme} Bảng cần trông đẹp hơn chút.
[Continue](btn:next)

---

Nhớ rằng ở khóa học trước, [véc tơ](link/to/course) mà mọi véc tơ có thể được xem như [một tổ hợp tuyến tính](gloss:linear-combination) của hai véc tơ đơn vị <uv>__i__</uv> và <uv>__j__</uv>.

Khi chúng ta sử dụng các công thức này, chúng ta đã tính cho phép quay của __A__ và __B__ để tìm phép quay cho bất kì điểm nào! __A__ nằm trên trục y vì thế nó chỉ được coi là một phiên bản tỉ lệ của véc tơ đơn vị [[j|i]], và __B__ nằm trên trục x vì thế nó được coi như phiên bản tỉ lệ của véc tơ đơn vị [[i|j]].

---

Khi chúng ta chia độ dài của A và B từ tọa độ tương ứng A' và B', chúng ta có thể thu được công thức cho phép quay của các véc tơ đơn vị. 

{.fixme} Kí hiệu nào chúng ta nên sử dụng? Véc tơ đơn vị? Điểm? 

`(1, 0)` trở thành `(sinθ, -cosθ)` và `(0, 1)` trở thành `(cosθ, sinθ)`.

---

Khi chúng ta có thể viết phương trình cho __bất kì__ điểm quay bằng việc viết nó như một tổ hợp tuyến tính của các véc tơ đơn vị.
cho `x'`...

{.text-center} `x' = pill(x, "teal") * cosθ - pill(y, "purple") * sinθ`

cho `y'`...

{.text-center} `y' = pill(x, "teal") * sinθ + pill(y, "purple") * cosθ`


Chúng ta có thể viết lại cái này như một véc tơ mới.
{.text-center} `§[[x'] [y']]` = `§[[(pill(x, "teal", "x", "x") * cosθ - pill(y, "purple") * sinθ)] [(pill(x, "teal") * sinθ + pill(y, "purple") * cosθ)]]`


Chú ý rằng cả x' và y' là phụ thuộc [{.teal}x](target:x) và [{.purple}y.](target:y)

[Continue](btn:next)

---
> id: matrices

#### Matrices

Các nhà Toán học đã đưa ra một khái niệm cực mạnh được gọi là [ma trận](gloss:matrix), có thể giúp chúng ta viết nó theo cách mới. Một ma trận trông giống như một bảng có hàng và cột, và các ô sẽ chứa các con số của riêng chúng. 

Ma trận này có 2 hàng và hai cột vì thế nó là ma trận 2x2, nhưng chúng cũng có thể có nhiều kích thước. 
{.text-center}`§[[cosθ (-sinθ)] [sinθ cosθ]]`


**Chúng ta có thể viết lại các phép tính cho các tọa độ `x'` and `y'` the cách sau đây:**

{.text-center}`§[[x'] [y']]` = `§[[cosθ (-sinθ)] [sinθ cosθ]]` x `§[[pill(x, "teal")] [pill(y, "purple")]]` = `§[[(pill(x, "teal", "x", "x") * cosθ - pill(y, "purple") * sinθ)] [(pill(x, "teal") * sinθ + pill(y, "purple") * cosθ)]]`

Nó là một [phép nhân ma trận](gloss:matrix-multiplication), ở đó chúng ta nhân một ma trận với một véc tơ `(x,y)` để tạo ra một véc tơ mới `(x', y')`. [Ma trận này](target:rotation-matrix) là một phép biến hình `R_"θ"` mà chúng ta đang tìm kiếm! Khi chúng ta thay các giá trị trong ma trận này, chúng ta có thể thay đổi phép biến hình.

{.fixme} Và đây là một biểu diễn khác:

::: column(width=100)

    table.vector
      tr: td(target="feature pref-A-1"): b x'
      tr: td(target="feature pref-A-2"): b y'

::: column(width=20)

    div.op =

::: column(width=200)

    table.matrix
      tr
        td(target="feature pref-A-1"): b cosθ
        td(target="feature pref-A-2"): b -sinθ
      tr
        td.name(target="pref-A-1 pref-A-2"): b {.m-green}sinθ
        td.cell(target="pref-A-1") cosθ

::: column(width=20)

    div.op x

::: column(width=100)

    table.vector
      tr: td(target="feature pref-A-1"): b x
      tr: td(target="feature pref-A-2"): b y

::: column(width=20)

    div.op =

::: column(width=400)

    table.vector
      tr: td
          div(target="x") cosθ * x
          div.op +
          div(target="y") -sinθ * y
      tr: td
          div(target="x") sinθ * x
          div.op +
          div(target="y") cosθ * y

:::

{.fixme} Hoạt động mà ở đó học sinh có thể kéo thả trượt để điều chỉnh θ và các giá trị của ma trận được cập nhật (tới hai chữ số thập phân).

[Hover x](target:x) and [Hover y](target:y)

{.todo} Kết nối mạnh hơn giữa các ma trận và điều gì có nghĩa là "phép biến hình"

[Continue](btn:next)

---
> id: identity

#### Identity Matrix

Điều gì xảy ra nếu đối với ma trận của chúng ta, chúng ta viết điều này thay thế?

{.text-center} `§[[1 0] [0 1]]`

Điều gì xảy ra khi chúng ta áp dụng phép biến hình này cho véc tơ `§[[x] [y]]`?

{.text-center} `§[[1 0] [0 1]]` x `§[[x] [y]]` = `§[[(1*x + 0*y)] [(0*x + 1*y)]]` = `§[[x] [y]]`

{.fixme} Học sinh nên điền các giá trị này theo cách riêng của mình.

Phép biến hình này [[không có ảnh hưởng|đảo ngược|phủ định]] véc tơ `§[[x] [y]]`.

---

{.text-center}`x' = x` and `y' = y`

Với bất kì véc tơ nào, kết quả của phép biến hình sẽ giống nhau. Điều này được gọi là [ma trận đơn vị](gloss:identity-matrix), bởi vì tích của nó với bất kì véc tơ 2x1 sẽ là chính véc tơ 2x1 đó. Nó giống như `1` là hàm đơn vị cho mọi phép nhân số nguyên (`1 x n = n`) và `0` là hàm đơn vị cho phép cộng (`0 + n = n`).

[Continue](btn:next)

---
> id: basic-transformations

Chúng ta cũng vừa mới thấy cách nhân một véc tơ bởi một ma trận 2x2 để xoay ma trận đó quanh gốc tọa độ, và chúng ta đã thấy cách mà một ma trận đơn vị làm cho một vec tơ không hề thay đổi. Những phép biến hình nào khác tồn tại? 

::: tab
#### Scale

Điều gì xảy ra nếu chúng ta điều chỉnh các số trên cùng bên trái và dưới cùng bên phải của ma trận của một phép biến đổi?

<table>
<tr><td>${xscale}{xscale|1.0|-2.0,2.0,0.1}</td><td>0</td></tr>
<tr><td>0</td><td>${yscale}{yscale|1.0|-2.0,2.0,0.1}</td></tr>
</table>

    include mixins
    svg(width=220 height=220)
      +grid220
      g.var.scale(:html="polygonTransform(xscale, 0, 0, yscale)")

Thay đổi giá trị [trên cùng-bên trái](target:ma) sẽ chia tỉ lệ x' dọc theo trục x.

Thay đổi giá trị [dưới cùng-bên phải](target:md) sẽ chia tỉ lệ y' dọc theo trục y.

{.text-center} `§[[a 0] [0 d]]` x `§[[x] [y]]` = `§[[a*x + 0*y] [0*x + d*y]]` = `§[[ax] [dy]]`

{.fixme} định dạng và đầu vào.

{.fixme} Thêm một số mã code cho phép chúng ta chuyển sang x-lớn, x-thu nhỏ, x-đảo ngược, y-lớn, y-thu nhỏ, y-đảo ngược, vân vân.


::: tab
#### Reflections

Điều gì xảy ra nếu chúng ta làm giá trị trên cùng-bên trái và dưới cùng-bên phải âm hoặc dương?

Điều chỉnh ma trận để thấy nó thay đổi các tọa độ như thế nào.

<table>
<tr><td>${xreflect}{xreflect|1.0|-1,1,2}</td><td>0</td></tr>
<tr><td>0</td><td>${yreflect}{yreflect|1.0|-1,1,2}</td></tr>
</table>

    include mixins
    svg(width=220 height=220)
      +grid220
      g.var.scale(:html="polygonTransform(xreflect, 0, 0, yreflect)")


Đổi dấu giá trị [trên cùng-bên trái](target:ma) sẽ phản chiếu phép biến đổi dọc theo [[trục x|trục y]], và đổi dấu của giá trị [dưới cùng-bên phải](target:ma) sẽ phản chiếu phép biến đổi dọc theo [[trục y|trục x]].

{.text-center} `§[[a 0] [0 d]]` x `§[[x] [y]]` = `§[[a*x + 0*y] [0*x + d*y]]` = `§[[ax] [dy]]`

{.fixme} định dạng và đầu vào.

::: tab
#### Shear

Điều gì xảy ra nếu chúng ta điều chỉnh giá trị [trên cùng-bên phải](target:mb) và [dưới cùng-bên trái](target:mc) ở các góc của ma trận?

Điều chỉnh các ma trận để thấy chúng thay đổi phép biến đổi như thế nào.

::: column(width=220)

{.caption} Cắt theo hướng x.

    include mixins
    svg(width=220 height=220)
      +grid220
      g.var.shear(:html="polygonTransform(1, xshear, 0, 1)")

<table>
<tr><td>1</td><td>${xshear}{xshear|0.0|-2.0,2.0,0.1}</td></tr>
<tr><td>0</td><td>1</td></tr>
</table>

`§[[1 b] [0 1]]` x `§[[x] [y]]` = `§[[(x+by)] [y]]`

{.fixme} định dạng và các đầu vào

::: column(width=220)

{.caption} Cắt theo trục y.

    include mixins
    svg(width=220 height=220)
      +grid220
      g.var.shear(:html="polygonTransform(1, 0, yshear, 1)")

<table>
<tr><td>1</td><td>0</td></tr>
<tr><td>${yshear}{yshear|0.0|-2.0,2.0,0.1}</td><td>1</td></tr>
</table>

`§[[1 0] [c 1]]` x `§[[x] [y]]` = `§[[x] [cx+y]]`

{.fixme} định dạng và đầu vào

:::

Bây giờ, hãy thêm một số nút và mã code để có thể chạy theo tập hợp các giá trị của ma trận.

Loại phép biến đổi này được gọi là [biến đổi cắt](gloss:shear), bởi vì nó cắt hệ tọa độ theo tỉ lệ thấu kính (?phrasing?).

::: tab
#### Other

Dĩ nhiên, các ma trận có thể có bất kì giá trị nào, và vì vậy có thể biến đổi theo nhiều cách khác nhau. Trải nghiệm với các giá trị ở đây và xem cách các phép biến đổi vẫn là sự kết hợp của nhiều phép biến đổi cơ bản.

{.todo} Tự do để làm những gì họ muốn. Hoặc giữ kín điều này, như được hiển thị bên dưới. 

:::

---
> id: play-with-me

Thử điều chỉnh các giá trị trong ma trận và thấy các phép biến đổi nào bạn có thể tạo ra!

    // try w/ bật hoặc tắt ô lưới, để so sánh ô lưới bên dưới phép biến đổi w/ 
    - var GRID = 8
    x-geopad(width=400 x-axis=`-${GRID},${GRID},1` y-axis=`-${GRID},${GRID},1` grid padding=5): svg
      circle.green.move(name="ipoint" x="point(1,0)" target="i")
      circle.blue.move(name="jpoint" x="point(0,1)" target="j")
      circle(name="origin", x="point(0,0)")


        // Liệu đã đúng giá trị cho điều này? Lý tưởng nhất là chúng ta nên hiển thị đến “vô tận”, nhưng điều này có vẻ chậm?
      - var MINMAX = GRID*2
      - for (var b=-MINMAX; b <=MINMAX; ++b)
        // .fabric as in "fabric of reality"
        //cũng có thể thử lớp ".grid" cho lưới mặc định
        path.fabric(x=`line(point(${b}*jpoint.x, ${b}*jpoint.y), point(ipoint.x + ${b}*jpoint.x, ipoint.y + ${b}*jpoint.y))`)
        path.fabric(x=`line(point(${b}*ipoint.x, ${b}*ipoint.y), point(${b}*ipoint.x + jpoint.x, ${b}*ipoint.y + jpoint.y))`)

      - var DRAW_SHIP = false
      - var SPACESHIP = [[3,0], [0,3], [-3,0], [-3,-3], [0,-1], [3,-3]]
      if DRAW_SHIP
        each p,i in SPACESHIP
          circle.red(name=`s${i}` x=`point(${p[0]}*ipoint.x+${p[1]}*jpoint.x,${p[0]}*ipoint.y+${p[1]}*jpoint.y)`)
          path.red(x=`segment(s${i}, s${(i+1)%SPACESHIP.length})`)

      - var DRAW_BOAT = true
      - var BOAT_RED = [[0.25,-2.5], [6.5,-2.5], [0.25,7]]
      - var BOAT_PURPLE = [[-0.25,-1.5], [-4.25,-1.5], [-0.25,7]]
      - var BOAT_ORANGE = [[0,5], [0,7.5], [-3.75,6.25]]
      - var BOAT_GREEN = [[7, -4], [5,-6], [-5,-6], [-7,-4]]
      - var BOAT_GRAY = [[-0.25,-4],[0.25,-4],[0.25,7],[-0.25,7]]
      if DRAW_BOAT
        - var gray = BOAT_GRAY.map(p => `point(${p[0]}*ipoint.x+${p[1]}*jpoint.x,${p[0]}*ipoint.y+${p[1]}*jpoint.y)`).join(',')
        path.fill.gray(x=`polygon(${gray})` label-class="gray")
        - var red = BOAT_RED.map(p => `point(${p[0]}*ipoint.x+${p[1]}*jpoint.x,${p[0]}*ipoint.y+${p[1]}*jpoint.y)`).join(',')
        path.fill.red(x=`polygon(${red})` label-class="red")
        - var purple = BOAT_PURPLE.map(p => `point(${p[0]}*ipoint.x+${p[1]}*jpoint.x,${p[0]}*ipoint.y+${p[1]}*jpoint.y)`).join(',')
        path.fill.purple(x=`polygon(${purple})` label-class="purple")
        - var orange = BOAT_ORANGE.map(p => `point(${p[0]}*ipoint.x+${p[1]}*jpoint.x,${p[0]}*ipoint.y+${p[1]}*jpoint.y)`).join(',')
        path.fill.orange(x=`polygon(${orange})` label-class="orange")
        - var green = BOAT_GREEN.map(p => `point(${p[0]}*ipoint.x+${p[1]}*jpoint.x,${p[0]}*ipoint.y+${p[1]}*jpoint.y)`).join(',')
        path.fill.green(x=`polygon(${green})` label-class="green")


        // each p,i in BOAT_GRAY
          // circle.gray(name=`bgy${i}` x=`point(${p[0]}*ipoint.x+${p[1]}*jpoint.x,${p[0]}*ipoint.y+${p[1]}*jpoint.y)`)
          // path.gray(x=`segment(bgy${i}, bgy${(i+1)%BOAT_GRAY.length})`)

        // each p,i in BOAT_RED
          // circle.red(name=`brd${i}` x=`point(${p[0]}*ipoint.x+${p[1]}*jpoint.x,${p[0]}*ipoint.y+${p[1]}*jpoint.y)`)
          // path.red(x=`segment(brd${i}, brd${(i+1)%BOAT_RED.length})`)
        // each p,i in BOAT_PURPLE
          // circle.purple(name=`bpp${i}` x=`point(${p[0]}*ipoint.x+${p[1]}*jpoint.x,${p[0]}*ipoint.y+${p[1]}*jpoint.y)`)
          // path.purple(x=`segment(bpp${i}, bpp${(i+1)%BOAT_PURPLE.length})`)
        // each p,i in BOAT_ORANGE
          // circle.orange(name=`bor${i}` x=`point(${p[0]}*ipoint.x+${p[1]}*jpoint.x,${p[0]}*ipoint.y+${p[1]}*jpoint.y)`)
          // path.orange(x=`segment(bor${i}, bor${(i+1)%BOAT_ORANGE.length})`)
        each p,i in BOAT_GREEN
          circle.green(name=`bgn${i}` x=`point(${p[0]}*ipoint.x+${p[1]}*jpoint.x,${p[0]}*ipoint.y+${p[1]}*jpoint.y)`)
          // path.green(x=`segment(bgn${i}, bgn${(i+1)%BOAT_GREEN.length})`)

      path.green(x="segment(point(0,0),ipoint)", label="i", target="i")
      path.blue(x="segment(point(0,0),jpoint)", label="j", target="j")



Đây chúng ta hiển thị véc tơ đơn vị [i](target:i) và [j](target:j).
Bên trong ma trận chúng ta có i = (${ipoint.x}, ${ipoint.y}) và j = (${jpoint.x}, ${jpoint.y})

Chọn một trong những nút này để theo kịp các phép biến đổi khác nhau.

    .button IDENTITY
    .button SHEAR
    .button SCALE
    .button ROTATE
    .button LINE

[Continue](btn:next)

---
> id: gpu

{.todo} Vậy điều này liên quan như thế nào đến các trò chơi điện tử? 

Các trò chơi điện tử có thể thao tác và hàng triệu hình dạng mỗi giây bằng cách sử dụng __Bộ xử lý đồ họa__ (GPU). GPUs được thiết kế đặc biệt để thực hiện nhiều phép nhân ma trận cùng một lúc. 

[Continue](btn:next)

---
> id: translate

Bạn có thể nhận thấy rằng chúng ta đã không thảo luận về một loại phép biến đổi. Chúng ta không thể di chuyển hình dạng của chính mình qua không gian! Để biến đổi hình dạng của chúng ta, để chúng được căn giữa ở bất kỳ đâu trừ điểm gốc, chúng ta cần một loại ma trận đặc biệt được gọi là __Ma trận qua phép tịnh tiến__.

{.text-center} `§[[1 0 dx] [0 1 dy] [0 0 1]]`

Chúng ta thêm một hàng và một cột bổ sung cho ma trận 2x2, và chúng ta thêm một hàng bổ sung vào véc tơ của chúng ta (điều này sẽ không thay đổi).

Nhân tử [dx](target:dx) sẽ được nhân bởi [1](target:bottom1) và được cộng với giá trị cuối cùng [x'](target:xprime).
Nhân tử [dy](target:dy) sẽ được nhân bởi [1](target:bottom1) và được cộng với giá trị cuối cùng [y'](target:xprime).

{.text-center} `§[[1 0 dx] [0 1 dy] [0 0 1]]` x `§[[x] [y] [1]]` = `§[[(x + dx)] [(y + dy)] [1]]`

{.fixme} Hiệu ứng lấy nét.

{.todo} Liệu có thể là một tương tác giống như trường hợp n?

[Continue](btn:next)


---
> id: three-d

Ma trận không nhất thiết phải biểu diễn các phép biến đổi 2 chiều. Chúng cũng có thể tồn tại trong không gian 3 chiều hoặc cao hơn.

Đây là một ma trận đơn vị trong không gian 3 chiều.

{.text-center} `§[[1 0 0] [0 1 0] [0 0 1]]` x `§[[x] [y] [z]]` = `§[[x] [y] [z]]`

{.todo} Tương tác với phép biến đổi 3 chiều.

[Continue](btn:next)


---
> id: mathigon-matrix

Let's mess around with the Mathigon Logo!

    include mixins
    svg(width=220 height=220)
      +grid220
      g.var.mathigon.red(:html="polygonTransform(m1a, m1b, m1c, m1d, 'red')")
      g.var.mathigon.green(:html="polygonTransform(m2a, m2b, m2c, m2d, 'green')")
      g.var.mathigon.yellow(:html="polygonTransform(m3a, m3b, m3c, m3d, 'yellow')")
      g.var.mathigon.blue(:html="polygonTransform(m4a, m4b, m4c, m4d, 'blue')")


<table>
  <tr>
    <td>
      <table>
        <tr><td>${m1a}{m1a|1|-2.0,2.0,0.1}</td><td>${m1b}{m1b|0.0|-2.0,2.0,0.1}</td></tr>
        <tr><td>${m1c}{m1c|0.0|-2.0,2.0,0.1}</td><td>${m1d}{m1d|1|-2.0,2.0,0.1}</td></tr>
      </table>
    </td>
    <td>
      <table class="green">
        <tr><td>${m2a}{m2a|1|-2.0,2.0,0.1}</td><td>${m2b}{m2b|0.0|-2.0,2.0,0.1}</td></tr>
        <tr><td>${m2c}{m2c|0.0|-2.0,2.0,0.1}</td><td>${m2d}{m2d|1|-2.0,2.0,0.1}</td></tr>
      </table>
    </td>
  </tr>
  <tr>
    <td>
      <table class="yellow">
        <tr><td>${m3a}{m3a|1|-2.0,2.0,0.1}</td><td>${m3b}{m3b|0.0|-2.0,2.0,0.1}</td></tr>
        <tr><td>${m3c}{m3c|0.0|-2.0,2.0,0.1}</td><td>${m3d}{m3d|1|-2.0,2.0,0.1}</td></tr>
      </table>
    </td>
    <td>
      <table class="blue">
        <tr><td>${m4a}{m4a|1|-2.0,2.0,0.1}</td><td>${m4b}{m4b|0.0|-2.0,2.0,0.1}</td></tr>
        <tr><td>${m4c}{m4c|0.0|-2.0,2.0,0.1}</td><td>${m4d}{m4d|1|-2.0,2.0,0.1}</td></tr>
      </table>
    </td>
  </tr>
</table>

{.todo} Các hoạt động có thể xảy ra: chuyển đổi màu cam và xanh lá cây, phản chiếu/ chia tỉ lệ toàn bộ, tạo hình.


----------------------------------------------------------------------------------------------------


## Matrix Arithmetic

> id: multiplication
> section: arithmetic
> sectionStatus: dev

### Matrix Multiplication

Chúng ta đã học trong chương trước rằng các ma trận có thể biểu diễn các phép biến đổi tuyến tính. Tuy nhiên, có rất nhiều thứ khác mà ma trận có thể biểu diễn! Ngoài ra, ma trận không phải lúc nào cũng là [ma trận vuông](gloss:square-matrix), nhưng có thể có nhiều giá trị chiều khác nhau. Hãy cùng khám phá điều này với một kịch bản giả định. 

Bốn người bạn đang ở một thành phố mới và họ đang tìm một nhà hàng để dùng bữa cùng nhau. Một số tính năng mà họ có thể tìm kiếm trong một nhà hàng là gì?

- Chỗ ngồi ngoài trời
- Đồ ăn chay
- Giá thấp
- Thực phẩm cay
- Thực đơn cho trẻ
- Tuyển chọn rượu ngon


Mỗi người bạn có nhận định về mức độ yêu thích những thứ này, chúng ta có thể định lượng bằng giá trị 0 (không quan trọng) đến 4 (rất quan trọng). Nếu chúng ta tạo một bảng với bạn bè ở cột ngoài cùng bên trái và các đặc điểm của nhà hàng ở hàng trên cùng, chúng ta có thể điền vào các ô của bảng với nhận định của từng người cho mỗi tính năng trên.

    figure: img(src="images/proto-2/matrix-1-frn-fea.png")

Những gì chúng ta đã xây dựng ở đây là một ma trận 4 x 2. Chúng ta có bốn hàng để đại diện cho bốn [[bạn bè | tính năng | nhà hàng]] và hai cột để đại diện cho hai [[tính năng | bạn bè | nhà hàng]].

---

Những người bạn đã tìm thấy ba nhà hàng trong khoảng cách đi bộ và họ đã tìm kiếm các trang web cho mỗi nhà hàng. Thật may mắn cho họ, trang web của mỗi nhà hàng đã liệt kê chất lượng của các tính năng mà những người bạn đã nhận định: sẵn có chỗ ngồi ngoài trời và các lựa chọn ăn chay.

    figure: img(src="images/proto-2/matrix-1-fea-res.png")

Đây là ma trận 2 x 3. Có hai hàng đại diện cho hai [[tính năng | nhà hàng]] và ba hàng, một hàng đại diện cho mỗi [[nhà hàng | tính năng]].

---

{.fixme} Bắt đầu hiển thị cột cạnh nhau.

Điều chúng ta muốn làm là bằng cách nào đó tổng hợp hai bảng thông tin này để chúng ta có thể biết được mức độ yêu thích của mỗi người đối với mỗi nhà hàng. Chúng ta có thể sử dụng một thủ tục được gọi là [phép nhân ma trận](gloss:matrix-multiplication) để thực hiện việc này. Kết quả sẽ là một bảng * mới * với bạn bè là [[hàng]] và nhà hàng là [[cột]].

    figure: img(src="images/proto-2/matrix-1-frn-res-empty.png")

Chúng ta nên điền vào bảng này như thế nào? Giá trị của mỗi ô phải thể hiện mức độ mà mỗi người có thể thích mỗi nhà hàng.

Ví dụ: ô đầu tiên sẽ đại diện cho mức độ Alice có thể thích [[Gauss Grill | Laplace Lounge]].

    figure: img(src="images/proto-2/mult-alice-gauss.png")

Alice chọn 1 cho Chỗ ngồi ngoài trời và Gauss Grill có giá trị 3 cho Chỗ ngồi ngoài trời, và chúng tôi nhân chúng để có được [[3]].

Alice chọn 4 đối với Đồ ăn chay, nhưng Gauss Grill chỉ có giá trị là 1 đối với Đồ ăn chay, và chúng tôi thực hiện một cách ngẫu nhiên những giá trị này để nhận được [[4]].

Chúng ta tổng hợp tất cả các tích này lại với nhau để có được [[7]], mà chúng ta có thể viết vào ô đầu tiên.

    figure: img(src="images/proto-2/mult-bob-laplace.png")

Bob có thể thích phòng chờ Laplace đến mức nào?
[[3]]*[[1]] + [[0]]*[[4]] = [[3]].

Khi chúng ta kết thúc quá trình của mình, chúng ta nhận được một ma trận gồm 4 hàng và 3 cột. Điều này thật ý nghĩa! Chúng ta có 4 người và 3 nhà hàng, vì vậy chúng ta sẽ kết thúc với một hàng cho mỗi người và một cột cho mỗi nhà hàng.

    figure: img(src="images/proto-2/matrix-1-frn-res-full.png")

Sau đó, chúng tôi có thể tính tổng các giá trị trong mỗi cột để tìm ra nhà hàng nào được yêu thích nhất (phần này được để làm bài tập cho bạn đọc).

{.fixme} Kết thúc hiển thị cột cạnh nhau

Những gì chúng ta vừa làm là [phép nhân ma trận](gloss:matrix-multiplication).

{.fixme} Căn chỉnh chúng.

    figure: img(src="images/proto-2/matrix-1-frn-fea.png" width=100)
    div x
    figure: img(src="images/proto-2/matrix-1-fea-res.png" width=200)
    div =
    figure: img(src="images/proto-2/matrix-1-frn-res-full.png" width=200)

---
> id: formal-definition

#### Định nghĩa chuẩn của phép nhân ma trận

Định nghĩa chuẩn của phép nhân ma trận như sau:

{.text-center} Cho ma trận `A` với các chiều `[r_"A", c_"A"]`
và ma trận `B` với các chiều `[r_"B", c_"B"]`

{.text-center} Giá trị của ô `x_"ij"` trong `A × B` là:

{.text-center} `a_"i1"b_"1j"` + ... `a_"iN"b_"Nj"`

{.text-center} khi mà `N = c_"A" = r_"B"`.


Lưu ý rằng, để thuật toán này hoạt động, số lượng [[cột]] trong ma trận đầu tiên phải bằng số lượng [[hàng]] trong ma trận thứ hai.
Ví dụ: nếu trong ví dụ về nhà hàng của chúng ta, mỗi người bạn có mức độ ưa thích đối với đồ ăn cay, ma trận sở thích của chúng ta sẽ là `4x3`.

    figure: img(src="images/proto-2/matrix-1-extra.png" width=200)

Bây giờ chúng ta đang cố gắng nhân ma trận `4x3` với ma trận` 2x3`, nhưng chúng ta không có bất kỳ thông tin nào về nhà hàng có đồ ăn cay! Vì vậy, chúng ta __không thể__ nhân hai ma trận.

    figure: img(src="images/proto-2/matrix-1-extra-mult.png" width=200)

{.fixme} Có thể kết thúc phần bằng một câu trắc nghiệm có dấu tích đơn giản, từ đó có thể thực hiện phép nhân.
---
> id: matrix-factorisation

#### Matrix Factorisation

 
Loại ma trận này được sử dụng trong tất cả các loại hệ thống tư vấn trực tuyến. Phim có thể được phân loại theo thể loại như Hài, Hành động, Lãng mạn hoặc Kinh dị. Các bài hát có thể được phân loại thành các thể loại với độ đặc trưng ngày càng cao như Rock, Classical, Pop, Rap, Electro-Funk, Indie Folk hay Norwegian Black Metal. Khi bạn xem một bộ phim trên Netflix hoặc nghe một bài hát trên Spotify, có thể có một ma trận rất lớn ở đâu đó, ghi nhớ sở thích của bạn!
 Tuy nhiên, quá trình này hơi khác so với những gì chúng ta đã làm ở trên. Công ty điều hành dịch vụ phát trực tuyến * không biết * thị hiếu của người dùng là gì. Nó biết họ đã xem những bộ phim nào, và họ có thích chúng hay không. Từ thông tin này, họ cố gắng tìm ra các tùy chọn thể loại có thể có của mỗi người dùng bằng cách sử dụng một quy trình được gọi là  __phân tách ma trận__. Giống như trong [phân tích thừa số nguyên] (gloss: factorisation), trong đó một số nguyên có thể được viết dưới dạng tích của các số nguyên tố, phân tích ma trận là làm việc ngược lại từ ma trận tích không hoàn chỉnh để tìm các ma trận ưu tiên có thể có. Thuật toán này phức tạp hơn nhiều so với phân tích số nguyên, vì vậy chúng ta cần các thuật toán phân nhánh máy phức tạp để thực hiện nó.

    figure: img(src="images/proto-2/factorisation.png")

[Continue](btn:next)

---
> id: multiply-transformations

### Nhân các phép biến đổi tuyến tính

Bây giờ chúng ta đã học được hai cách khác nhau để suy nghĩ về phép nhân ma trận. Trong chương đầu tiên, chúng ta đã biết rằng nhân ma trận 2x2 với vectơ 2x1, có thể được coi như một phép biến đổi tuyến tính. Và chúng ta vừa học các quy tắc chi tiết về cách nhân ma trận với bất kỳ kích thước nào, chẳng hạn như ma trận ưu tiên. Hãy quay trở lại suy nghĩ về ma trận là phép biến đổi tuyến tính.
 Nhắc lại ma trận 2x2 biểu diễn phép quay 90º về gốc. Hãy gọi nó là  `R_"90"`.

    bao gồm mixins
    img(src="images/proto-2/rotate-90-m.png" width=100)
    +ij([0,1], [-1,0], "Rotate 90º")

Điều gì xảy ra nếu chúng ta nhân ma trận này bởi ma trận cho phép quay góc 180º, `R_"180"`?

  bao gồm mixins
    img(src="images/proto-2/rotate-180-m.png")
    +ij([-1,0], [0,-1], "Rotate 180º")

Ma trận kết quả thu được là:

   bao gồm mixins
    img(src="images/proto-2/rotate-270-m.png")
    +ij([0,-1], [1,0], "Rotate 270º")

Ma trận này là biến đổi tuyến tính cho [[phép quay góc 270º|ma trận đơn vị|phép quay góc 90º]].

---

Điều này đúng,

`R_"90"` x `R_"180"` = `R_"270"`

Trong trường hợp này, nhân hai ma trận quay cho ta một ma trận quay * mới * với một góc bằng tổng hai góc đầu tiên. Một cách tổng quát hơn để nói điều này là khi chúng ta nhân hai ma trận biến đổi, ma trận biến đổi thu được có tác dụng áp dụng trên cả hai ma trận ban đầu liên tiếp.
 Điều này hoạt động cho tất cả các giá trị của phép quay:

- `R_"90"` x `R_"90"` = `R_"80"`
- `R_"180"` x `R_"180"` = `R_"360"` = `I`

[Continue](btn:next)

---
> id: transforms-calculator
> goals: calculate

Thế còn các loại phép biến đổi khác thì sao?

{.fixme} Có lẽ để họ vẽ các điểm (giống như một con tàu vũ trụ), và sau đó các điểm được biến đổi bởi mỗi phép biến đổi?
{.fixme} Nên được hiển thị theo chiều ngang, với ma trận của chúng ở phía dưới

    include mixins
    .calculator
      .display
        .mat
          x-geopad(width=150 x-axis="-3,3,1" y-axis="-3,3,1" grid padding=5): svg
        .mat.operator x
        .mat
          x-geopad(width=150 x-axis="-3,3,1" y-axis="-3,3,1" grid padding=5): svg
        .mat.operator =
        .mat
          x-geopad(width=150 x-axis="-3,3,1" y-axis="-3,3,1" grid padding=5): svg
        .button.clear CLEAR
        .button.calc CALCULATE
      .cubes
        +ij([1,0], [0,1], "Identity")
        +ij([0,1], [-1,0], "Rotate 90º")
        +ij([-1,0], [0,-1], "Rotate 180º")
        +ij([0,-1], [1,0], "Rotate 270º")

        +ij([-1,0], [0,1], "Reflect x=0")
        +ij([0,1], [1,0], "Reflect y=x")
        +ij([1,0], [0,-1], "Reflect y=0")
        +ij([0,-1], [-1,0], "Reflect y=-x")

        +ij([1,1], [0,1], "Shear x 1")
        +ij([1,-1], [0,1], "Shear x -1")
        +ij([1,0], [1,1], "Shear y 1")
        +ij([1,0], [-1,1], "Shear y -1")

        +ij([2,0], [0,2], "Scale by 2")
        +ij([0.5,0], [0, 0.5], "Scale by 1/2")
        +ij([2,0], [0,1], "Scale x by 2")
        +ij([1,0], [0,1/2], "Scale y by 1/2")

---
> id: matrix-addition

### Phép cộng ma trận

Ma trận cũng có thể được thêm vào. Phép cộng ma trận không xảy ra thường xuyên, nhưng nó rất đơn giản để học.
 Chúng ta sẽ viết các phép toán ma trận giống như cách mà bạn có thể mong đợi:

`A + B`

* Chỉ có thể thêm hai ma trận nếu chúng có cùng kích thước.
* Ma trận kết quả sẽ có cùng thứ nguyên với ma trận được thêm vào.
* Mỗi giá trị ở vị trí (i, j) của ma trận kết quả sẽ là tổng các giá trị tại (i, j) trong hai ma trận còn lại.
 Thêm hai ma trận này!

<div class="addition">
  <table class="add">
    <tr>
      <td target="a">[1](target:a)</td>
      <td target="b">[2](target:b)</td>
    </tr>
    <tr>
      <td target="c">[3](target:c)</td>
      <td target="d">[4](target:d)</td>
    </tr>
  </table>

  <div class="add">+</div>

  <table class="add">
    <tr>
      <td target="a">[9](target:a)</td>
      <td target="b">[8](target:b)</td>
    </tr>
    <tr>
      <td target="c">[7](target:c)</td>
      <td target="d">[6](target:d)</td>
    </tr>
  </table>

  <div class="add">=</div>

  <table class="add">
    <tr>
      <td target="a">
        <strong class="pill step-target" tabindex="0" data-to="a">[[10]]</strong>
      </td>
      <td target="b">
        <strong class="pill step-target" tabindex="0" data-to="b">[[10]]</strong>
      </td>
    </tr>
    <tr>
      <td target="c">
        <strong class="pill step-target" tabindex="0" data-to="c">[[10]]</strong>
      </td>
      <td target="d">
        <strong class="pill step-target" tabindex="0" data-to="d">[[10]]</strong>
      </td>
    </tr>
  </table>
</div>

Tuyệt.

Mã code này có thể đơn giản hơn rất nhiều! Và tại sao điều này không đi dưới các bảng?

---
> id: scalar-multiplication

### Nhân vô hướng

Một phép toán khác mà chúng ta có thể thực hiện với ma trận là __phép nhân vô hướng__. Một __vô hướng__ là cái mà chúng ta gọi là một số thực trong ma trận và các phép toán với vectơ.

Chúng ta viết phép nhân vô hướng là

`sA`

Phép nhân vô hướng đơn giản như nhân mọi ô trong ma trận `A` với một` s` vô hướng.

<div class="scalar">
  <div class="scm s">2</div>

  <table class="scm">
    <tr>
      <td target="a">[3](target:a)</td>
      <td target="b">[1](target:b)</td>
    </tr>
    <tr>
      <td target="c">[-4](target:c)</td>
      <td target="d">[0](target:d)</td>
    </tr>
  </table>

  <div class="scm">=</div>

  <table class="scm">
    <tr>
      <td target="a">
        <strong class="pill step-target" tabindex="0" data-to="a">[[6]]</strong>
      </td>
      <td target="b">
        <strong class="pill step-target" tabindex="0" data-to="b">[[2]]</strong>
      </td>
    </tr>
    <tr>
      <td target="c">
        <strong class="pill step-target" tabindex="0" data-to="c">[[-8]]</strong>
      </td>
      <td target="d">
        <strong class="pill step-target" tabindex="0" data-to="d">[[0]]</strong>
      </td>
    </tr>
  </table>
</div>

Lưu ý rằng mặc dù có thể cộng hai ma trận và nhân một ma trận với một đại lượng vô hướng, thì thao tác thêm một đại lượng vô hướng vào ma trận là __không được định nghĩa__.

---
> id: arith-properties

### Tính chất các phép toán với ma trận

Nhớ lại các toán tử như phép cộng và phép nhân, cũng như các tính chất của chúng hữu ích như thế nào. Tính chất giao hoán, phân phối và kết hợp.

::: tab
#### Associative

Phép nhân ma trận có phải là [kết hợp](gloss:associative)?. Nếu đúng, thì phương trình dưới đây sẽ đúng.

`Ax(BxC) = (AxB)xC`

Một câu hỏi hay đầu tiên cần đặt ra là: liệu các kích thước của ma trận có cho phép điều này không?

Nếu `Ax(BxC)` là có thể, thì

`columns_"B" = rows_"C"`

`BxC` sẽ có `rows_"B"` số lượng hàng, và sẽ bằng `columns_"A"`. Điều này có nghĩa là khi cố gắng nhân `(AxB)xC`, chúng ta biết rằng chúng ta có thể thực hiện `AxB`. `AxB` khi đó có `columns_"B"` columns, vì vậy chúng ta có thể nhân nó với C.

Chúng ta biết rằng chúng ta có thể thực hiện phép nhân này dựa trên các kích thước, nhưng liệu chúng ta có nhận được cùng một kết quả không? Nhớ lại phần của chúng ta về phép nhân rằng nó có thể được coi là các phép biến đổi tuyến tính liên tiếp.

Nó chỉ ra rằng miễn là chúng ta giữ thứ tự của các ma trận, chúng ta sẽ nhận được cùng một kết quả. Cho dù chúng ta thực hiện BxC trước hay AxB trước, điều đó không quan trọng.

Phép nhân ma trận  __là kết hợp__.

::: tab
#### Tính giao hoán

Liệu phép nhân ma trận có [giao hoán](gloss:commutative)?. Nếu đúng, thì phương trình dưới đây sẽ đúng.

`AxB = BxA`

Nhớ lại rằng khi chúng ta nhân hai ma trận, số cột của ma trận đầu tiên phải khớp với số hàng của ma trận thứ hai. Điều này có nghĩa là nếu chúng ta có thể nhân `AxB`,` cột_ "A" = row_ "B" `, nhưng điều đó không nhất thiết phải đúng với` row_ "A" = column_ "B" `. Do đó, không tuân theo việc chúng ta có thể nhân `BxA`, và phép nhân ma trận __không giao hoán__.
Điều gì sẽ xảy ra nếu cả hai ma trận đều là ma trận vuông? Sau đó, chúng ta có thể thực hiện cả `AxB` và` BxA`, tuy nhiên chúng ai không biết liệu chúng có bằng nhau hay không.
Nếu chúng ta coi các ma trận là các phép biến đổi, chúng ta có thể tưởng tượng các tình huống trong đó việc áp dụng hai phép biến đổi khác nhau sẽ khác nhau tùy thuộc vào hướng bạn nhân chúng.
Nếu chúng ta thực hiện Xoay 90º và sau đó là phản xạ qua trục x, thì phép biến đổi cuối cùng sẽ giống như sau:

    bao gồm mixins
    .cubes
      +ij([0,1], [-1,0], "Rotate 90º")
      .cube.op x
      +ij([-1,0], [0,1], "Reflect x=0")
      .cube.op =
      +ij([0,1], [1,0], "Reflect y=x")

Tuy nhiên, nếu chúng ta đảo ngược thứ tự của các phép biến đổi, thì phép biến đổi cuối cùng sẽ giống như thế này.

    bao gồm mixins
    .cubes
      +ij([-1,0], [0,1], "Reflect x=0")
      .cube.op x
      +ij([0,1], [-1,0], "Rotate 90º")
      .cube.op =
      +ij([0,-1], [1,0], "Reflect y=-x")

Có nhiều ví dụ khác về cách phép nhân ma trận không đáp ứng tính chất giao hoán và chúng tôi khuyến khích bạn thử nghiệm!


::: tab
#### Tính phân phối

Có phải phép nhân ma trận có tính [phân phối](gloss:distributive) đối với phép cộng ma trận?. Nếu đúng, thì phương trình dưới đây sẽ đúng.

`Ax(B+C) = AxB + AxC`

{.todo} Liệu có thể chứng minh điều này bằng cách thêm các vectơ cơ sở và áp dụng các phép biến đổi cho chúng? Hoặc bằng cách nào đó có thể để nó như một bài tập cho bạn đọc.

:::


----------------------------------------------------------------------------------------------------


## Các định thức

> section: determinants
> sectionStatus: dev
> id: determinants

Hãy xem cách mà diện tích thay đổi.

    - var GRID = 4
    x-geopad(width=400 x-axis=`-${GRID},${GRID},1` y-axis=`-${GRID},${GRID},1` grid padding=5): svg
      circle.green.move(name="ipoint" x="point(1,0)" target="i")
      circle.blue.move(name="jpoint" x="point(0,1)" target="j")
      circle(name="origin", x="point(0,0)")


        // Liệu có đúng giá trị cho điều này? Lý tưởng nhất là chúng ta hiển thị đến  “vô cực”, nhưng điều này có thể hiển thị chậm?
      - var MINMAX = GRID*2
      - for (var b=-MINMAX; b <=MINMAX; ++b)
        // .fabric as in "fabric of reality"
        // can also try class ".grid" for default grid
        path.fabric(x=`line(point(${b}*jpoint.x, ${b}*jpoint.y), point(ipoint.x + ${b}*jpoint.x, ipoint.y + ${b}*jpoint.y))`)
        path.fabric(x=`line(point(${b}*ipoint.x, ${b}*ipoint.y), point(${b}*ipoint.x + jpoint.x, ${b}*ipoint.y + jpoint.y))`)

      - var DETERMINANT = [[0,0], [1,0], [1,1], [0,1]]
      - var determinant = DETERMINANT.map(p => `point(${p[0]}*ipoint.x+${p[1]}*jpoint.x,${p[0]}*ipoint.y+${p[1]}*jpoint.y)`).join(',')
      path.fill.light.purple(x=`polygon(${determinant})` label-class="purple")

      path.green(x="segment(point(0,0),ipoint)", label="i", target="i")
      path.blue(x="segment(point(0,0),jpoint)", label="j", target="j")

Bên trong ma trận chúng ta có i = (${ipoint.x}, ${ipoint.y}) và j = (${jpoint.x}, ${jpoint.y})

Định thức là ${determinant}

Chọn một trong số những nút ở đây

    .button IDENTITY
    .button SHEAR
    .button SCALE
    .button ROTATE
    .button LINE

---
> id: examples

{.todo} Chứng minh cách các phép biến đổi cơ bản ảnh hưởng đến định thức.
{.todo} Thể hiện các giá trị có thể có: nhỏ hơn 1, lớn hơn 1, âm, không.

---
> id: zero-det

{.todo} Các ma trận có thể có định thức bằng 0, Điều này có nghĩa là gì? 

---
> id: det-formula

Công thức cho định thức của ma trận 2x2 là:

```ad - bc```

matrix:

[a](target:a), [b](target:b)

[c](target:c), [d](target:d)

Diện tích [định thức](target:determinant) bằng với diện tích [ad](target:ad) trừ đi diện tích [bc](target:bc).

Hãy xem vì sao điều này đúng về mặt hình học.

    - var GRID = 1.5
    x-geopad(width=400 x-axis=`-${GRID},${GRID},1` y-axis=`-${GRID},${GRID},1` grid padding=5): svg
      circle.green.move(name="ipoint" x="point(1,0)" target="i")
      circle.blue.move(name="jpoint" x="point(0,1)" target="j")
      circle(name="origin", x="point(0,0)")

      - var MINMAX = GRID*2
      - for (var b=-MINMAX; b <=MINMAX; ++b)
        // .fabric as in "fabric of reality"
        // can also try class ".grid" for default grid
        path.fabric(x=`line(point(${b}*jpoint.x, ${b}*jpoint.y), point(ipoint.x + ${b}*jpoint.x, ipoint.y + ${b}*jpoint.y))`)
        path.fabric(x=`line(point(${b}*ipoint.x, ${b}*ipoint.y), point(${b}*ipoint.x + jpoint.x, ${b}*ipoint.y + jpoint.y))`)

      - var DETERMINANT = [[0,0], [1,0], [1,1], [0,1]]
      - var determinant = DETERMINANT.map(p => `point(${p[0]}*ipoint.x+${p[1]}*jpoint.x,${p[0]}*ipoint.y+${p[1]}*jpoint.y)`).join(',')
      path.fill.light.purple(x=`polygon(${determinant})` label-class="purple", target="determinant")

      path.green(x="segment(point(0,0),ipoint)", label="i", target="i")
      path.blue(x="segment(point(0,0),jpoint)", label="j", target="j")

      path.red(x="segment(point(0,0), point(ipoint.x,0))", label="a", target="a")
      path.red(x="segment(point(0,0), point(0,jpoint.y))", label="d", target="d")

      path.red(x="segment(point(0,0), point(0,ipoint.y))", label="c", target="c")
      path.red(x="segment(point(0,0), point(jpoint.x,0))", label="b", target="b")

      path.fill.light.teal(x="polygon(point(0,0),point(ipoint.x,0),point(ipoint.x,jpoint.y),point(0,jpoint.y))" target="ad")

      path.fill.light.lime(x="polygon(point(0,0),point(jpoint.x,0),point(jpoint.x,ipoint.y),point(0,ipoint.y))" target="bc")


{.fixme} Các hình dạng đang chặn nhau khi được nhắm mục tiêu.

{.fixme} Có thể tạo hoạt ảnh cho thấy các tam giác khớp với nhau như thế nào, như trong định lí Py-ta-go

---
> id: nonsquare

{.todo} Các định thức chỉ tồn tại cho ma trận vuông.


----------------------------------------------------------------------------------------------------


## Matrix Inverses

> section: inverses
> sectionStatus: dev

{.todo} COMING SOON


----------------------------------------------------------------------------------------------------


## Quy tắc Cramer và phép khử Gauss

> section: systems
> sectionStatus: dev

{.todo} COMING SOON


----------------------------------------------------------------------------------------------------


## Giá trị riêng và véc tơ riêng

> section: eigenvalues
> sectionStatus: dev

{.todo} COMING SOON

