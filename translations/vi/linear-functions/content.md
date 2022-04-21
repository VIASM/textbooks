# Hàm tuyến tính

## Đầu vào, đầu ra và đồ thị 

> section: graphs
> sectionStatus: dev
> color: "#F15E19"
> level: Foundations

TODO

---

## Độ dốc và giao điểm

::: .theorem
__Common Core Standard 8.EE.6__<br>
Sử dụng tam giác đồng dạng để giải thích tại sao độ dốc _m_ giống nhau giữa hai
điểm phân biệt trên một đường thẳng nằm trên mặt phẳng tọa độ; lấy phương trình 
`y=mx` đi qua gốc tọa độ và phương trình `y=mx+b`cắt trục tung tại _b_.

:::

Tại đây bạn có thể thấy [hệ tọa độ](gloss:coordinate-system), với một đường thẳng đi qua [gốc tọa độ](gloss:coordinate-system-origin). 
Để bắt đầu, chọn một điểm bất kỳ trên đường thẳng.

::: column(width=360 parent="padded-thin")

    x-coordinate-system.c-system(width=360 height=440 x-axis="-5,5,1" y-axis="-6,6,1" crosshairs="no" padding=5)
    x-gesture(target="#slope x-coordinate-system" offset="63,-107")

::: column.grow

{.reveal(when="make-point")} Ta có thể vẽ một tam giác vuông giữa điểm này
và gốc tọa độ.

{.reveal(when="make-point" delay=1500)} Thử di chuyển điểm này dọc theo đường thẳng:
chú ý các điểm khác nhau tạo thành các tam giác có kích thước khác nhau, nhưng chúng đều
[[đồng dạng|tương đẳng|đều]]. _{.lgrey.reveal(when="blank-0")} Các tốt nhất để nhận ra điều này
là quan sát hai góc dọc theo trục x. Chúng luôn có kích thước bằng nhau, 
vì vậy [điều kiện góc-góc (g.g)](gloss:triangle-aa) giữa hai tam giác thỏa mãn._

{.reveal(when="blank-0" delay=1500)} Giờ ta có thể sử dụng một trong những kết quả mà ta biết
về hai tam giác đồng dạng: tỷ số giữa hai cạnh luôn không đổi. Di chuyển điểm trên đường thẳng một lần nữa, và xem điều gì xảy ra:

{.reveal.text-center(when="blank-0" delay=3000)}
`pill(var("p.y"),"green","dy")/pill(var("p.x"),"blue","dx") = var("p.y/p.x || '???'")`

{.reveal(when="slide-point")} Điều ngược lại cũng đúng: bất kỳ điểm nào (_x_, _y_)
thỏa mãn phương trình trên cũng nằm trên đường thẳng. Vì vậy ta có "phương trình" cho đường thẳng:

{.text-center.reveal(when="slide-point" delay=1000)} `pill(y,"green","dy") / pill(x,"blue","dx") = 1.5`

{.r.text-center.reveal(when="slide-point" delay=2000)}
`⇔ pill(y,"green","dy") = 1.5 pill(x,"blue","dx")`
[Continue](btn:next)

:::

---
> id: questions-1

Điều này chứng tỏ rằng _mọi đường thẳng_ đi qua gốc tọa độ 
đều có cùng một phương trình dạng `y = mx`, trong đó _m_ được gọi là
[__độ dốc__](gloss:line-slope).

Cho một đường thẳng, bạn có thể tìm được giá trị _m_ tương ứng bằng cách chọn 
bất kỳ điểm nào nằm trên đường thẳng và đơn giản chia giá trị _y_ cho giá trị _x_ của nó.
Dưới đây là một vài ví dụ:

::: column(width=230 parent="padded-thin")

    x-coordinate-system(width=230 height=180 x-axis="-5,5,1" y-axis="-4,4,1" labels="no" padding=5 crosshair-grid=1)

{.text-center} _m_ = [[0.5]]

::: column(width=230)

    x-coordinate-system(width=230 height=180 x-axis="-5,5,1" y-axis="-4,4,1" labels="no" padding=5 crosshair-grid=1)

{.text-center} _m_ = [[3]]

::: column(width=230)

    x-coordinate-system(width=230 height=180 x-axis="-5,5,1" y-axis="-4,4,1" labels="no" padding=5 crosshair-grid=1)

{.text-center} _m_ = [[-1]]

:::

---
> id: intercept

Nhưng còn những đường thẳng _không_ đi qua gốc tọa độ thì sao?Trong trường hợp này
ta cần thêm một thành phần: chọn một đường thẳng có cùng độ dốc đi qua gốc tọa độ,
và dịch nó theo trục y bằng cách cộng hoặc trừ đi một giá trị:

    svg(style="width: 0; height: 0; position: absolute;"): defs
      marker#blue-arrow(refX=2 refY=2 markerWidth=4 markerHeight=4 orient="auto")
        path(d="M 0 0 L 4 2 L 0 4 z" fill="#fd8c00")
      marker#blue-circle(refX="2" refY="2" markerWidth="4" markerHeight="4" orient="auto")
        circle( cx=2 cy=2 r=1.5 fill="#fd8c00")

    x-coordinate-system(width=400 height=320 x-axis="-8,8,1" y-axis="-6,6,1" crosshairs="no" padding=5)
    x-gesture(target="#intercept x-var" slide="100,0")

{.text-center} `y = 2/3 x` ${sign(a)} ${abs(a)}{a|0|-4,4,1}

{.reveal(when="var-0")} Như bạn có thể thấy ở trên, số được thêm vào giá trị của 
_y_ bằng với khoảng cách giữa gốc tọa độ, và giao điểm giữa đường thẳng và [[trục _y_|trục _x_]].

---
> id: equation

Giờ ta có một phương trình cho _bất kỳ_ đường thẳng (không thẳng đứng) trong mặt phẳng tọa độ:

{.text-center} `y = class(m,"b orange") x + class(b,"b cyan")`,

{.r} trong đó _{.b.orange}m_ and _{.b.cyan}b_ là hai giá trị cần điền.
Bạn có thể thấy trước đó, _{.b.orange}m_ là __độ dốc {.orange}__ của đường thẳng, và
_{.b.cyan}b_ là __{.cyan}*y*- giao điểm với trục tọa độ__.
[Còn nữa](btn:next)

---
> id: equation-1

::: column(width=360 parent="padded-thin")

    x-coordinate-system(width=360 height=360 x-axis="-5,5,1" y-axis="-4,6,1" no-crosshairs padding=5)

::: column.grow

Cho một đường thẳng bất kỳ, ví dụ một đường thẳng ở bên trái, bạn có thể xác định được giá trị của
_{.b.cyan}b_ bằng cách quan sát giao điểm giữa đường thẳng line và trục _y_. Ở ví dụ này, _{.b.cyan}b_ = [[2]].

{.reveal(when="blank-0")} Tương tự, bạn có thể tìm được độ dốc _{.b.orange}m_ bằng cách 
vẽ bất một tam giác bất kỳ bên dưới đường thẳng và chia chiều cao cho đáy của nó. Trong ví dụ này,
độ dốc là _{.b.orange}m_ = [[0.75]].

{.reveal(when="blank-1")} Nói cách khác, phương trình của đường thẳng này là

{.text-center.reveal(when="blank-1")} `y=` _{x-equation(solution="3/4 x+2")}_

:::

---
> id: questions-2

Dưới đây là một số bài tập khác. Tìm độ dốc và giao điểm với trục tọa độ _y_
trong từng trường hợp, và viết phương trình của mỗi đường thẳng?

::: column(width=230 parent="padded-thin")

    x-coordinate-system(width=230 height=180 x-axis="-5,5,1" y-axis="-4,4,1" labels="no" padding=5 crosshair-grid=1)

{.text-center} `y=` _{x-equation(solution="3/2 x-2")}_

::: column(width=230)

    x-coordinate-system(width=230 height=180 x-axis="-5,5,1" y-axis="-4,4,1" labels="no" padding=5 crosshair-grid=1)

{.text-center} `y=` _{x-equation(solution="2x+1")}_

::: column(width=230)

    x-coordinate-system(width=230 height=180 x-axis="-5,5,1" y-axis="-4,4,1" labels="no" padding=5 crosshair-grid=1)

{.text-center} `y=` _{x-equation(solution="-1/2 x+3")}_

:::

---

## Đường thẳng song song và đường thẳng vuông góc

> section: parallel-perpendicular
> sectionStatus: dev

TODO

---

## Hệ phương trình

> section: systems
> sectionStatus: dev

TODO
