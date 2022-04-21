# Angles and Polygons

## Angles

> section: angles
> sectionStatus: dev
> color: "#2E6AE1"
> level: Foundations

TODO

---

## Angles in Polygons

> section: angles-in-polygons
> sectionStatus: dev

TODO

---

## Drawing Triangles

> section: triangles
> id: triangle-inequality
> goals: s0 s1 s3 s5

Ở phần này, chúng ta sẽ tìm hiểu về cách vẽ các tam giác. Ví dụ, nếu chúng ta có ba số bất kì, liệu chúng ta có thể vẽ được một tam giác nhận ba số đó làm chiều dài cạnh hay không? 

Dưới đây là một số ví dụ - Di chuyển các đỉnh của tam giác cho tới khi ba cạnh thỏa mãn một trong các bộ ba ở bên tay trái. 

    .inequality.row
      div(style="width:150px")
        .item #[.t-num 5]#[.t-num 6]#[.t-num 7] #[span.check(when="s0")]
        .item #[.t-num 3]#[.t-num 9]#[.t-num 9] #[span.check(when="s1")]
        .item #[.t-num 2]#[.t-num 4]#[.t-num 8]
        .item #[.t-num 4]#[.t-num 6]#[.t-num 7] #[span.check(when="s3")]
        .item #[.t-num 1]#[.t-num 2]#[.t-num 6]
        .item #[.t-num 3]#[.t-num 5]#[.t-num 7] #[span.check(when="s5")]
      .grow
        x-geopad.label-halo(height=360): svg
          circle.move.pulsate(name="a" cx=175 cy=75)
          circle.move(name="b" cx=150 cy=250)
          circle.move(name="c" cx=350 cy=200)
          path.red(x="segment(a,b)" label="${roundD(a,b)}")
          path.blue(x="segment(b,c)" label="${roundD(b,c)}")
          path.yellow(x="segment(a,c)" label="${roundD(a,c)}")

{.reveal(when="s0 s1 s3 s5")} Có vẻ như ít trường hợp mà bộ ba số đơn giản là _không thể_ tạo nên một tam giác. Điều này đặc biệt hay xảy ra khi một cạnh [[lớn hơn nhiều|ngắn hơn nhiều|cùng độ dài]] so với hai cạnh kia.

---
> id: triangle-inequality-1

::: column.grow
Nghĩ ba cạnh của một tam giác giống như những thanh kim loại, được kết nối với nhau bằng bản lề. 
Hãy đặt [thanh kim loại dài nhất](target:long) ở giữa và [thanh ngắn hơn](target:short) ở cạnh còn lại.

{.r} Bây giờ thật đơn giản để thấy rằng không thể nối phần đuôi của các thanh ngắn hơn, nếu tổng độ dài của các đoạn được nối ngắn hơn độ dài của thanh lớn hơn. 
[Continue](btn:next)

::: column(width=300)

    x-geopad(width=300 height=180): svg
      circle(name="a" x="point(90,90)")
      circle(name="b" x="point(210,90)")
      circle.move.pulsate(name="c" cx=150 cy=50 project="circle(a,60)")
      circle.move.pulsate(name="d" cx=150 cy=50 project="circle(b,40)")

      path.blue(x="circle(a,60)" style="stroke-dasharray: 8px 10px")
      path.blue(x="circle(b,40)" style="stroke-dasharray: 8px 10px")
      path.thick(x="segment(a,b)" target="long")
      path.thick(x="segment(a,c)" target="short")
      path.thick(x="segment(b,d)" target="short")

:::

---
> id: inequality-picker

Hãy viết lại quan sát này theo thuật ngữ Toán học: 

::: .theorem
__Bất đẳng thức tam giác__<br>
Tổng độ dài hai cạnh bất kì trong tam giác phải lớn hơn độ dài của cạnh thứ ba. 
:::

Hay nói cách khác, nếu một tam giác có có các cạnh _a_, _b_ và _c_, thì chúng ta kết luận rằng `a+b>c` và `a+c>b` và `b+c>a`.

Bất đẳng thức tam giác cho phép chúng ta kiểm tra nhanh nếu ba số có thể tạo thành một tam giác. Bộ ba nào sau đây có thể tạo thành tam giác? 

    x-picker
      .item.text-center #[.t-num 4]#[.t-num 6]#[.t-num 9]
      .item.text-center(data-error="inequality-error-1") #[.t-num 1]#[.t-num 2]#[.t-num 3]
      .item.text-center #[.t-num 3]#[.t-num 7]#[.t-num 8]
      .item.text-center(data-error="inequality-error-2") #[.t-num 2]#[.t-num 4]#[.t-num 7]
      .item.text-center(data-error="inequality-error-3") #[.t-num 1]#[.t-num 5]#[.t-num 8]
      .item.text-center #[.t-num 2]#[.t-num 3]#[.t-num 4]

---
> id: triangle-inequality-2

Bất đẳng thức tam giác cũng cho phép chúng ta ước lượng độ dài của cạnh thứ ba của tam giác, nếu chúng ta biết độ dài hai cạnh kia. 

Tưởng tượng rằng nếu một tam giác có hai cạnh độ dài 4 và 6. Đặt _c_ là độ dài của cạnh thứ ba. Thì chúng ta biết rằng

{.text-center} `4+6>c`, _{span.space}_ `4+c>6` _{span.space}_ và _{span.space}_ `6+c>4`

Chúng ta có thể sắp xếp lại các bất đẳng thức từ đó ta có [[2]] `<c<` [[10]].
_{span.reveal(when="blank-0 blank-1")} Độ dài của cạnh *c* phải nằm giữa 2 và 10._

---
> id: triangle-inequality-3
> goals: target-0 target-1

::: column.grow

Một lần nữa, chúng ta có thể nghĩ điều này sử dụng các vật thể vật lý: hai cạnh của một tam giác là các thanh kim loại có độ dài 4 và 6, và thanh thứ ba là dây cao su có thể dãn ra hoặc co vào. 

Bây giờ chúng ta có thể thấy độ dài của dây cao su luôn luôn [ít nhất](action:hover(90,45,118,69,1)) `6-4=2` và [nhiều nhất](action:hover(50,127,250,127,0))
`6+4=10`.

::: column(width=300)

    x-geopad(width=300 height=200): svg
      circle(name="a" cx=170 cy=130 hidden)
      circle.move(name="b" cx=75 cy=60 project="circle(a,120)")
      circle.move(name="c" cx=300 cy=110 project="circle(a,80)")
      path.thick(x="segment(a,b)" label="6")
      path.thick(x="segment(a,c)" label="4")
      path.orange(x="segment(b,c)" label="${round(distance(b,c)/20,1)}")

:::

Chú ý rằng có các bất đẳng thức _chặt_. Nếu cạnh thứ ba _chính xác bằng_ 2 hoặc
10, chúng ta sẽ có một đường thẳng chứ không phải là tam giác. Tuy nhiên, 2.1 hoặc 9.9 cũng đủ để tạo thành tam giác.

---

{.todo} COMING SOON – Nhiều hoạt động liên quan đến vẽ hình tam giác, góc trong tam giác, tính đồng dạng và sự bằng nhau.

---

## Pythagoras’ Theorem

> section: pythagoras
> sectionStatus: dev

TODO

---

## The Coordinate Plane

> section: coordinate-plane
> sectionStatus: dev

TODO

---

## Transformations and Congruence

> section: transformations
> sectionStatus: dev

TODO

