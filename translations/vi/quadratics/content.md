# Phương trình bậc hai

## Giới thiệu

> id: intro
> section: introduction
> color: "#F6700F"
> level: Intermediate
> next: graph-theory

    img.text-wrap(src="images/skater-1.jpg" style="shape-outside: url(images/skater-1-mask.png)" width=300 height=393)

Chào mừng bạn đến với SkateSum, một công ty nhỏ sản xuất ván trượt. Các kỹ sư ở đây đang phát triển một mô hình sản phẩm mới tên là _SquareBoard_ và nó đã sẵn sàng để bước vào giai đoạn sản xuất. Bạn được giao trách nhiệm tìm giá bán tối ưu cho chiếc ván trượt này - và giá thành sản xuất chúng không hề rẻ: 

* Các công cụ và máy móc cần thiết để chế tạo các ván trượt có giá \$5,000. Loại chi phí này 
thường được gọi là _chi phí cố định_.
* Mỗi ván trượt tốn thêm \$30 cho gỗ, các vật liệu khác, và tiền lương cho nhân viên. Loại chi phí này thường được gọi là _chí phí khả biến_.

Nói cách khác, _giá thành_ sản xuất _n_ ván trượt là

{.text-center.no-voice} [cost](pill:orange) = _{x-equation(solution="5000+30×n")}_.

---
> id: demand


Sản phẩm ván trượt mới nhận được rất nhiều sự mong đợi, nhưng nếu giá thành quá cao thì sẽ chỉ có rất ít người mua. Điều này được hiển thị qua biểu đồ với trục _x_ là giá thành của một ván trượt, và trục _y_ là số lượng người tương ứng muốn mua một ván trượt (_nhu cầu_).

Biểu đồ nào sau đây thể hiện mối tương quan giữa giá thành và nhu cầu phù hợp nhất?
 
    x-picker.wrap
      .item(data-error="wrong-chart-1" style="width: 220px")
        x-coordinate-system(width=220 height=180 x-axis="0,10,2" y-axis="0,10,2" axis-names="price,demand" crosshairs="no" labels="no" fn="0.6x + 2")
      .item(style="width: 220px")
        x-coordinate-system(width=220 height=180 x-axis="0,10,2" y-axis="0,10,2" axis-names="price,demand" crosshairs="no" labels="no" fn="8 - 0.6x")
      .item(data-error="wrong-chart-2" style="width: 220px")
        x-coordinate-system(width=220 height=180 x-axis="0,10,2" y-axis="0,10,2" axis-names="price,demand" crosshairs="no" labels="no" fn="2.5 * sqrt(x)")

---
> id: demand-1

Giá thành càng cao đồng nghĩa với càng ít người mua ván trượt, vì thế đồ thị hàm số có hướng đi xuống. Sau khi thực hiện một số nghiên cứu thị trường, các nhà kinh tế đã đưa ra phương trình sau:

{.text-center} [demand](pill:teal) = 2800 – 15 × [price](pill:purple)

Ví dụ, nếu một ván trượt có giá \$80 thì nhu cầu sẽ là [[1600]] đơn vị.

---
> id: intro4

    //- img.text-wrap.s-hide(src="images/skater-3.jpg" style="shape-outside: url(images/skater-3-mask.png)" width=280 height=480)

_Doanh thu_ của công ty là tổng tiền đi vào chúng ta tạo ra. Giá trị này bằng số ván trượt đã bán (_nhu cầu_) nhân với giá thành của mỗi ván trượt: 

{.text-center} [revenue](pill:green) = [demand](pill:teal) × [price](pill:purple)

Nhưng chúng ta quan tâm nhiều hơn tới _lợi nhuận_ thu được: tức là doanh thu từ việc bán các ván trượt trừ cho chi phí sản xuất chúng. Bạn có thể tìm một phương trình toán học thể hiện [lợi nhuận](pill:yellow) theo [giá](pill:purple) của mỗi ván trượt không?

    x-equation-system(steps="demand*price-(5000 + 30*demand) | (2800-15*price)*price-5000-30*(2800-15*price)" hints="intro-1|intro-2|intro-3")
      table
        tr
          td: em.pill.yellow profit
          td= '='
          td #[em.pill.green revenue] − #[em.pill.orange cost]
        tr
          td
          td= '='
          td: x-equation(solution="-15 × price^2 + 3250 × price - 89000" substitutions="cost: 89000 - 450 price | demand: 2800 - 15 price | revenue: 2800 price - 15 price^2")

---
> id: intro-table

Lưu ý rằng phương trình này bao gồm [giá](pill:purple) cũng như [`giá^2`](pill:purple). Đây được 
gọi là một [__phương trình bậc hai__](gloss:quadratic-equation), được đặt tên dựa trên tiếng Latin của từ bình phương là “quadratus”.

Để tìm cách tối đa lợi nhuận của chúng ta, hãy tính thử lợi nhuận thu được từ các giá bán khác nhau:

::: .overflow-wrap.overflow-table

| [price/$](pill:purple)  | 20   | 40   | 60  | 80  | 100 | 120 | 140 | 160 | 180 |
| [profit/$](pill:yellow) | –30k | 17k | [[52]]k | [[75]]k | [[86]]k | [[85]]k | _{span.reveal(when="blank-3")}72k_ | _{span.reveal(when="blank-3" delay=400)}47k_ | _{span.reveal(when="blank-3" delay=800)}10k_ |
{.grid}

:::

---
> id: intro-chart

Bây giờ, chúng ta có thể chấm các điểm này trong một hệ tọa độ và nối các điểm này lại với một đường: 

    x-coordinate-system(width=640 height=400 x-axis="-20,200,20" y-axis="-100000,100000,20000" axis-names="price/$,profit/$" padding=10 animate)
      .region.r1(style="top: 48%; height: 46%; left: 6%; width: 6%;")
      .region.r2(style="top: 26%; height: 40%; left: 79%; width: 21%;")


Bạn nhớ là đồ thị của [hàm số tuyến tính](gloss:linear-function) luôn luôn là dạng đường thẳng. Tuy nhiên, như bạn đã thấy ở trên, đồ thị của [hàm số bậc hai](gloss:quadratic-function) là đường cong. Và đường này có tên gọi cụ thể là: [__Parabol__](gloss:parabola).

Nếu [giá thành bằng 0](->.r1), lợi nhuận của chúng ta là số âm, bởi vì chúng ta chỉ tặng miễn phí các ván trượt mắc tiền. Khi giá thành tăng lên, lợi nhuận của chúng ta cũng sẽ tăng theo. Tuy nhiên, nếu giá của ván trượt [quá đắt](->.r2), mọi người không còn muốn mua nữa thì lợi nhuận của chúng ta lại giảm xuống.

Chúng ta có thể tối đa hóa lợi nhuận của mình bằng cách định giá các ván trượt xấp xỉ
\$[[108 ± 10]].

---
> id: intro-final

    figure: x-img(src="images/skater-2.jpg" alt="Skateboarder" width=400 height=352)

Trong thực tế, các công ty có thể gặp khó khăn trong việc xác định phương trình chính xác cho lợi nhuận của họ - và chúng có thể còn phức tạp hơn nhiều so với ví dụ này.

Tuy nhiên, phương trình bậc hai xuất hiện ở khắp nơi trong tự nhiên, kỹ thuật và kinh tế. Trong khóa học này, bạn sẽ được học các cách khác nhau để giải phương trình bậc hai và hiểu rõ đồ thị của dạng này.



--------------------------------------------------------------------------------



## Biểu thức nhị thức

> section: binomials
> sectionStatus: dev

TODO



--------------------------------------------------------------------------------



## Giải phương trình bậc hai

> id: definitions
> section: solving
> sectionStatus: dev

Bạn đã biết cách giải [_phương trình tuyến tính_](gloss:linear-equation): các phương trình này có dạng `ax + b`, với _x_ là một [biến số](gloss:variable), và 
_a_ và _b_ là các giá trị số cụ thể.

Bây giờ, chúng ta nghĩ về một dạng phương trình phức tạp hơn cũng có chứa `x^2`. [__Phương trình bậc hai __](gloss:quadratic-equation) là một phương trình của dạng này

{.text-center} `ax^2 + bx + c = 0`,

Trong đó, _x_ là một biến số và _a_, _b_, và _c_ là các giá trị số cụ thể (được gọi là _hệ số_). Cả `b` và `c` có thể bằng 0, nhưng `a` không thể bằng 0 vì khi đó chúng ta sẽ chỉ có [[một phương trình tuyến tính|không|vô nghiệm]].

---
> id: parabola

Giống như bạn đã thấy trong phần [giới thiệu](/course/quadratics/introduction), vẽ đồ thị của một hàm số bậc hai trong một hệ trục tọa độ sẽ cho dạng đường cong, được gọi là __Parabol__:

    x-coordinate-system(x-axis="-5,5,1" y-axis="-3,5,1")

{.text-center} `y =`${a}{a|1|-5,5,0.1} `x^2+`${b}{b|0|-5,5,0.1} `x+`${c}{c|0|-5,5,0.1}

Hãy thử thay đổi các giá trị _a_, _b_ và _c_, và quan sát đường parabol thay đổi như thế nào.

{.reveal(when="var-0 var-1 var-2")} Để giải phương trình bậc hai, chúng ta phải tìm các điểm mà `y = 0`. Đây là những điểm mà đồ thị phương trình bậc hai [[giao với trục x|giao với trục y|quay đầu]].

{.reveal(when="blank-0")} Trong khi các phương trình tuyến tính chỉ có một nghiệm duy nhất, chúng ta có thể thấy từ đồ thị là phương trình bậc hai đôi khi có [vô nghiệm](action:set(1,-2,2)),
[một nghiệm](action:set(1,2,1)), hoặc [hai nghiệm](action:set(1,-4,2)).

Trong các phần tiếp theo, chúng ta sẽ tìm hiểu tại sao lại như vậy, học một số phương pháp khác nhau để tìm các nghiệm của một phương trình bậc hai.

---

### Cấp độ 0: Lấy căn bậc hai

Khi giải phương trình bậc hai, chúng ta thường sử dụng _phép đối _ của các phép tính toán học. Ví dụ, phép cộng và phép trừ là hai phép đối nhau, và phép nhân và [[phép chia | phép cộng | căn bậc hai]] thì đối lập nhau. Phép đối của bình phương một số là lấy căn bậc hai. Ví dụ, `5^2 = 25`, nên `sqrt(25) = 5`.

Cách này có thể giúp chúng ta giải được một số phương trình bậc hai đơn giản:

{.text-center} `x^2 - 25 = 0`

Đầu tiên, chúng ta tách `x^2` về một vế của phương trình:

{.text-center} `x^2 = 25`

Bây giờ, chúng ta lấy căn bậc hai của cả hai vế, và lưu ý thêm ký hiệu ±:

{.text-center}
`x = +- sqrt(25)`
`x = +- 5`

Đôi khi, chúng ta cần phải thực hiện nhiều bước để tách `x^2`:

* Với mọi giá trị của `x^2`, có [[hai | ba | một]] giá trị có thể có của` x`: một giá trị dương và một giá trị âm. Ví dụ, nếu `x^2=`${x*x}{x|4|2,10,1}, chúng ta không biết liệu `x=`${x} hay `x=`${'–'+x}. Trong trường hợp này, phương trình bậc hai này có hai nghiệm.

* {.reveal(when="blank-0")} Các giá trị bình phương luôn dương. Điều này có nghĩa là [[không có giá trị nào|có nhiều giá trị]] của `x` có thể thỏa mãn phương trình `x^2 = -9`. 
Phương trình này __vô nghiệm__.

{.eqn-system}
| `3` | `x^2` | `-11` | `=` | `7`           | {.eqn-comment} add 11 to both sides |
| `3` | `x^2` |       | `=` | `18`          | {.eqn-comment} divide both sides by 3 |
|     | `x^2` |       | `=` | `6`           | {.eqn-comment} take square roots of both sides |
|     | `x`   |       | `=` | `+-sqrt(6)` |
|     |       |       | `=` | `+-2.45`     |

{.todo} Một vài lưu ý về độ chính xác và cách trình bày nghiệm của phương trình bậc hai

Như một cách viết tắt, chúng ta đôi khi viết `x = +-`${x} (“_x_ bằng cộng-trừ ${x}”).

VÍ DỤ 11: Giải `x^2=100`.
Đáp án: Dễ. `x=10` hoặc `x=−10`.

Khó khăn duy nhất có thể gặp ở đây là học sinh thường quên là trong đại số, hầu hết các số đều có hai giá trị căn bậc hai.

VÍ DỤ 12: Giải `w^2=36`.
Đáp án: Dễ. `w=6` hoặc `w=−6`.

VÍ DỤ 13: Giải `x^2=17`.
Đáp án: Okay, không dễ nhìn lắm nhưng vẫn dễ: `x=sqrt(17)` hoặc `x=−sqrt(17)`.

VÍ DỤ 14: Giải `x^2=0`.
Đáp án: Số không là số duy nhất có một giá trị căn bậc hai: x=0

VÍ DỤ 15: Giải:
a) x^2=121.
b) p^2=40.
c) y^2+5=14.
d) 2x^2=50.
e) x^2=−6.

---

### Cấp độ 1:

VÍ DỤ 17: Giải `(x+3)^2=100`.

Đáp án: Một chút phức tạp hơn nhưng vẫn dễ dàng. Bài toán được đưa ra là: "Một số nào đó bình phương bằng 100." Vậy thì số đó phải là 10 hoặc -10. Đó là:

`x+3=10`   hoặc   `x+3=−10`
thu được:
`x=7`    hoặc   `x=−13`.

---

::: tab

#### Ví dụ

__Giải `(y−4)^2=25`__

Đáp án: Ta có:
y−4=5    hoặc    y−4=−5
thu được:
y=9    hoặc   y=−1.

CẢNH BÁO!!   Nhiều học sinh thích trình bày câu trả lời bằng cách sử dụng kí hiệu ±. Tuy nhiên, điều này lại tiềm ẩn vấn đề. Một số bạn trình bày như sau:

`(y−4)^2=25`
`y−4=±5`
`y=±9`

::: tab

#### Ví dụ 2

__Giải 4(p+2)2−16=0__

Đáp án: Cộng 16:

4(p+2)2=16.

Chia 2 vế cho 4:

(p+2)2=4.

Do đó

p+2=2   hoặc   p+2=−2
thu được:
p=0    hoặc    p=−4.

::: tab

#### Ví dụ 3

__Giải (x+7)2+9=0__

Đáp án: Ta có (x+7)2=−9. Trong tập hợp số thực, không tồn tại một đại lượng bình phương là số âm. Vì thế, phương trình này không có nghiệm.

::: tab

#### Ví dụ 4

Giải (x−1)2=5__

Đáp án: Ta có:

x−1=√5    hoặc    x−1=−√5
Từ đó
x=1+√5    hoặc   x=1−√5.

::: tab

#### Ví dụ 5

Giải (x+3)2=49__

Đáp án: Ta có:

x+3=7    hoặc    x+3=−7
Thu được:
x=4    hoặc    x=−10.

:::

---

BÀI TẬP 23: Giải:

a) (x−1)^2=64
b) (p−3)^2=16
c) (y+1)^2−2=23
d) 3(x−900)^2=300
e) (x−√2)^2=5

BÀI TẬP 24:

a) Phương trình (x+7)^2=0 có bao nhiêu nghiệm? Các nghiệm này bằng bao nhiêu?
b) Phương trình (x+7)^2=−2 có bao nhiêu nghiệm? Các nghiệm này bằng bao nhiêu?
---

### Cấp độ 2:

VÍ DỤ 25: Giải `x^2 + 6x + 9 = 49`.

Đáp án: Nếu bạn nhạy bén, bạn có thể nhận ra rằng phương trình này đang lặp lại ví dụ 22:

Phương trình `x2+6x+9=49` diễn ra tương tự `(x+3)^2`.

Để kiểm tra điều này, thử trình bày `(x+3)×(x+3)` ra như chia diện tích của một hình vuông thành 4 phần:

|     | `x`   | 3    |
| `x` | `x^2` | `3x` |
| 3   | `3x`  | 9    |
{.q-grid}

Đấy, chúng ta thấy rằng (x+3)2 bằng x2+6x+9. Do đó, câu hỏi:
Giải x2+6x+9=49 thực tế chính là:
Giải (x+3)2=49 một cách trá hình.

Ta có:
x+3=7    hoặc    x+3=−7
x=4    hoặc    x=−10.

Vì vậy, vấn đề của cấp độ 2 là nhận ra các biểu thức phức tạp hơn là các bài toán dễ ở cấp độ 1 ngụy trang.

---

Thêm một vài ví dụ

::: tab

#### Ví dụ 2

__Giải `x2+4x+4=25`.__

Đáp án: Hãy vẽ hình vuông cho `x^2+4x+4`.

Có một mảnh `x2` xuất phát từ `x×x`.

Bởi vì chúng ta muốn một hình vuông hoàn toàn đối xứng (hình vuông ứng dụng tốt cho cấp 1) “4x” phải xuất phát từ hai mảnh đối xứng: 2x and 2x.

Điều này có nghĩa chúng ta phải có các số 2 và 2 trên các cạnh của hình vuông, và
mảnh cuối cùng tương úng là 4.

|     | `x`   | 2    |
| `x` | `x^2` | `2x` |
| 2   | `2x`  | 4    |
{.q-grid}

Do đó chúng ta thấy `x^2+4x+4` thật sự là `(x+2)^2` theo một cách khác, và chúng ta cần giải:

`(x+2)^2=25`.

Ở đây thì dễ rồi:

x+2=5    hoặc    x+2=−5
x=3    hoặc    x=−7.

::: tab

#### Ví dụ 2

__Giải x2−10x+25=169.__

Đáp án: Hãy vẽ hình vuông cho x2−10x+25.

Có một mảnh x2 xuất phát từ x×x . Và chúng ta cần hai mảnh (đối xứng) mà cộng lại =10x.

Nó có nghĩa là cần các số −5 and −5, để phù hợp với phần cuối cùng của hình vuông là 25.

|     | `x`   | -5    |
| `x` | `x^2` | `-5x` |
| -5  | `-5x` | 25    |
{.q-grid}

`x^2−10x+25=169`
`(x−5)2=169`
`x−5=13`    hoặc    `x−5=−13`
`x=18`   hoặc   `x=−8`

::: tab

#### Ví dụ 3

__Giải x2−20x+100=7.__

Đáp án: Ta có:

|     | `x`    | -10    |
| `x` | `x^2`  | `-10x` |
| -10 | `-10x` | 100    |
{.q-grid}

x2−20x+100=7
(x−10)2=7
x−10=7–√    hoặc   x−10=−7–√
x=7–√+10    hoặc   x=−7–√+10  □

::: tab

#### Ví dụ 4

__Giải x2+25–√x+5=4.__

Đáp án: Đừng lo lắng vì các con số. Chỉ cần theo lộ trình như trước.

Bạn có thấy chúng ta có hình vuông này không?

|           | `x`        | `sqrt(5)`  |
| `x`       | `x^2`      | `sqrt(5)x` |
| `sqrt(5)` | `sqrt(5)x` | 5          |
{.q-grid}

x2+25–√x+5=4
(x+5–√)2=4
x+5–√=2    hoặc    x+5–√=−2
x=2−5–√    hoặc    x=−2−5–√  □

:::

---

BÀI Tập 30: Giải:

a) x2+40x+400=100
b) p2−6p+9=9
c) x2−4x+4=1
d) 3x2−18x+27=12
e) x2−22–√x+2=19

BÀI TẬP 31: Giải phương trình x2+2Bx+B2=D2 theo B và D.

---

### Cấp độ 3

VÍ DỤ 32: Giải phương trình x2+8x+15=80.

Đáp án: Hãy áp dụng kỹ thuật trong cấp độ 2 và vẽ hình vuông. 

Mảnh x2 là từ x×x. Và vì chúng ta muốn một chính phương,
8x phải được chia thành hai phần 4x:

|     | `x`   | `4`  |
| `x` | `x^2` | `4x` |
| `4` | `4x`  | 16   |
{.q-grid}

Điều này có nghĩa là chúng ta cần cạnh của hình vuông có các giá trị 4 và 4, với điều kiện phần còn lại của hình vuông là 16. GIÁ TRỊ NÀY LẠI KHÔNG TƯƠNG THÍCH VỚI SỐ 15 TRONG PHƯƠNG TRÌNH.

Có vẻ như phương pháp cái hộp không giúp giải phương trình này. Chúng ta có hai lựa chọn sau:

1. Từ bỏ vậy và khóc.
2. Trưởng thành lên và giải quyết nó nào!

Chọn cách 2 thôi nào - nghe theo một lời khuyên tích cực: Nếu có điều gì đó trong cuộc sống không đi theo hướng bạn mong muốn, hãy thay đổi nó!

Đối với vấn đề này, chúng ta muốn con số 15 trong x2+8x+15 trở thành con số 16. Vậy thì cộng thêm 1 và biến nó thành 16!

Dĩ nhiên, để đảm bảo phương trình vẫn cân bằng, nếu chúng ta cộng 1 vào một vế của phương trình, chúng ta cũng cần cộng thêm 1 vào vế còn lại:

x2+8x+15+1=80+1.

Thế là, ta có:

x2+8x+16=81.

Và cái hộp cho ta thấy nó trở thành:

(x+4)2=81
và tất cả được lắp vào vị trí:

x+4=9    hoặc    x+4=−9
x=5     hoặc    x=−13

---

Thêm một vài ví dụ:

::: tab

#### Ví dụ 1

__Giải x2−6x+11=27.__

Cái hộp cho chúng ta biết rằng 2 mảnh x2 và -6x cần số 9 cho phù hơp, không phải là số 11:

|     | `x`   | `-3`  |
| `x` | `x^2` | `-3x` |
| `-3` | `-3x`  | 9   |
{.q-grid}

Vậy thì hãy làm cho nó khả thi. Trừ 2 cho cả hai vế:

x2−6x+9=25
(x−3)2=25
x−3=5    hoặc    x−3=−5
x=8    hoặc    x=−2  □

::: tab

#### Ví dụ 2

__Giải x2−10x+3=0.__

Đáp án: Cái hộp cho chúng ta biết rằng 2 mảnh x2 và -10x cần số 25 cho phù hợp, không phải là số 3:

|      | `x`   | `-5`  |
| `x`  | `x^2` | `-5x` |
| `-5` | `-5x` | 25    |
{.q-grid}

Vậy thì cộng 22 vào cả 2 vế và tiến hành!

x2−10x+3=0
x2−10x+25=22
(x−5)2=22
x−5=2–√2    hoặc    x−5=−2–√2
x=5+2–√2    hoặc    x=5−2–√2

::: tab

#### Ví dụ 3

__Giải x2−6x=55.__

Đáp án: Để có được biểu thức chính phương thì cộng 9 cho cả hai vế.

|     | `x`   | `-3`  |
| `x` | `x^2` | `-3x` |
| `-3` | `-3x`  | 9   |
{.q-grid}

x2−6x+9=64
(x−3)2=64
x−3=8    hoặc    x−3=−8
x=11    hoặc    x=−5

::: tab

#### Ví dụ 4

__Giải w2+90=22w−31.__

Đáp án: Hãy mang tất cả các số hạng có chứa biến sang vế trái của phương trình:

w2−22w+90=−31.

|     | `x`   | `-11`  |
| `x` | `x^2` | `-11x` |
| `-11` | `-11x`  | 121   |
{.q-grid}

Cái hộp cho thấy cần cộng 31 vào mỗi vế:

w2−22w+121=0
(w−11)2=0
w−11=0
w=11   □

:::

---

Bây giờ đến lượt bạn! Hãy thử giải các bài luyện tập sau đây:

::: .box
#### Bài toán

Hãy giải các phương trình sau đây:

a) x2+12x−5=40
b) z2+2z+3=11
c) x2−40x+300=69
d) 2f2−16f+30=48
e) x2+100x+2=3

Giải x2+3x+1=5. Đừng sợ các phân số. Bạn có thể giải quyết chúng!

:::

---

### Cấp độ 4

VÍ DỤ 39: Giải x2+3x+1=5.

Đáp án: Để giải phương trình này thật sự cần sử dụng dạng phân số:

|       | `x`    | `3/2`  |
| `x`   | `x^2`  | `3/2x` |
| `3/2` | `3/2x` | `9/4`  |
{.q-grid}

Cộng `9/4` vào hai vế cho thấy:

x2+3x+94=5+114
(x+32)2=614
(x+32)2=254
x+32=52    hoặc    x+32=–52
x=1    hoặc    x=−4
Tuy nhiên, hầu hết mọi người đều không muốn giải bằng phân số.

Vấn đề ở đây là số hạng chính giữa, 3x, có hệ số lẻ. Do đó … Nếu bạn không thích thì hãy thay đổi nó!

Có lẽ cách dễ dàng nhất là tạo một số chẵn ở số hạng ở giữa để bằng cách nhân 
tất cả với 2, do đó x2+3x+1=5 trở thành:

2x2+6x+2=10.

NHẬN XÉT: Một số học sinh có thể cho rằng cách đơn giản hơn là cộng 2 vào cả hai vế để 
có thể thu được x2+4x+1=5+x. Nhưng sau đó chúng ta có biến x ở cả 2 vế, rất khó nhằn.

Okay … Hãy thử phương pháp hộp vào phương trình 2x2+6x+2=10.

|      | `x`    |  |
| `2x` | `2x^2` |  |
|      |        |  |
{.q-grid}

Nhưng chúng ta bây giờ có một vấn đề với phần đầu tiên của phương trình: Chúng ta cần 
hai số hạng đối xứng mà nhân với nhau tạo thành 2x2. Phần lớn học sinh sẽ đề nghị 2x và x, nhưng điều này ngay lập tức phá hỏng phương pháp hình vuông mà chúng ta sử dụng ở các mức độ 1, 2, và 3. 

MỘT Ý TƯỞNG KHÁC: Thay vì nhân tất cả với 2, chúng ta nhân với 4.

Một lần nữa, số hạng ở giữa chẵn VÀ giải vấn đề về số hạng đầu tiên. Hãy xem vì sao:

Bắt đầu: x2+3x+1=5.

Nhân tất cả với 4:

4x2+12x+4=20.

Bây giờ áp dụng phương pháp hộp:

|      | `2x`   | `3`  |
| `2x` | `4x^2` | `6x` |
| `3`  | `6x`   | `9`  |
{.q-grid}

Chúng ta thấy rằng 4x2 là từ 2x nhân với 2x để giữ tính đối xứng.

Lưu ý rằng số hạng ở giữa, 12x, được chia thành 2 phần bằng nhau, 6x cộng 6x, như đã dự tính. Điều này có nghĩa chúng ta cần các con số 3 và 3 ở hai vế ( 2x nhân BA cho ra 6x) 

Chúng ta cũng thấy rằng con số chúng ta cần từ cái hộp là 9. Cộng 5 vào hai vế của phương trình 4x2+12+9=20 thu được:

4x2+12x+9=25.

Cái hộp cho thấy 4x2+12x+9 thật sự là (2x+3)2, vì thế chúng ta bây giờ đang có vấn đề cấp độ 1:

(2x+3)2=25
2x+3=5    hoặc    2x+3=−5
2x=2    hoặc    2x=−8
x=1    hoặc    x=−4  □

NẾU SỐ HẠNG Ở GIỮA CÓ TÍNH LẺ, NHÂN HẾT VỚI 4 LÀ MỘT CÁCH THÔNG MINH!

---

::: tab

#### Ví dụ 4

__Giải x2−5x+6=2.__

Đáp án: Hãy nhân hết với 4:

4x2−20x+24=8

|      | `2x`   | `-5`   |
| `2x` | `4x^2` | `-10x` |
| `-5` | `-10x` | `25`   |
{.q-grid}

Cộng 1 vào cả 2 vế cho ra:

4x2−20x+25=9
(2x−5)2=9
2x−5=3    hoặc    2x−5=−3
2x=8    hoặc    2x=2
x=4    hoặc    x=1  □

::: tab

#### Ví dụ 4

__Giải x2+x=34.__

Đáp án: Hãy nhân hết với 4:

4x2+4x=3

|      | `2x`   | `1`  |
| `2x` | `4x^2` | `2x` |
| `1`  | `2x`   | `1`  |
{.q-grid}

Cộng 1 vào hai vế cho ra:

4x2+4x+1=4
(2x+1)2=4
2x+1=2    hoặc    2x+1=−2
2x=1    hoặc    2x=−3
x=12  hoặc  x=−32  □

::: tab

#### Ví dụ 4

__Giải p2+7p−2=5__

Đáp án: Hãy nhân hết với 4:

4p2+28p−8=20

|      | `2p`   | `7`   |
| `2p` | `4p^2` | `14x` |
| `7`  | `15x`  | `49`  |
{.q-grid}

Cộng 57 vào hai vế cho ra:

4p2+28p+49=77
(2p+7)2=77
2p+7=7–√7    hoặc    2p+7=−7–√7
2p=7–√7–7    hoặc    2p=−7–√7–7
p=7√7–72    hoặc    p=−7√7–72  □

:::

---

BÀI TẬP 43: Giải:

a) x2+11x−5=7
b) z2−3z+1=−1
c) x2−x−1=234
d) x2+5x+12=70
e) x2+3=9

---

### Cấp độ 5 Phương trình bậc hai

VÍ DỤ 45: Giải 3x2+5x+1=9.

Đáp án: Đây là lần đầu tiên chúng ta gặp dạng với số hạng đầu tiên phức tạp hơn so với chỉ x2. Chúng ta có thể chia tất cả với 3 và giải phương trình x2+13x+13=3 và sử dụng phương pháp hộp - và cách này sẽ ổn (thử xem?) - nhưng chúng ta sẽ rơi vào một đống phân số.

Ở cấp độ trước, chúng ta đã nhân hết với 4 và có thể giải được 4x2 như 2x×2x. Cách này ổn vì 4 là một số chính phương.

Vì thế ở vấn đề này, hãy thử biến 3x2 thành một số chính phương bằng cách nhân 
tất cả với 3.

9x2+15x+3=27.

Số hạng đầu tiên là 3x×3x nhưng chính giữa là 15x - là một hệ số lẻ. Để tránh đụng phân số, hãy nhân hết với 4.

36x2+60x+12=108.

Việc này chuyển số hạng đầu tiên thành chính phương - chúng ta có 36x2=6x×6x - và có 
số hạng thứ hai chẵn. Có vẻ như chúng ta đã ổn để tiếp tục!

|      | `6x`    | `5`   |
| `6x` | `36x^2` | `30x` |
| `5`  | `30x`   | `25`  |
{.q-grid}

Cái hộp cho thấy chúng ta cần sự xuất hiện của 25. Thế nên cộng 13 vào cả hai vế:

36x2+60x+25=121
6x+5)2=121
6x+5=11    hoặc    6x+5=−11
6x=6    hoặc    6x=−16
x=1    hoặc    x=−83
Hoàn thành!     □

---

Ví dụ trên cho thấy …

PHƯƠNG PHÁP HỘP TỐI ƯU
Để giải phương trình có dạng:

ax2+bx+c=d
i) NHÂN TẤT CẢ VỚI a (để chuyển số hạng đầu tiên thành chính phương)
ii) NHÂN TẤT CẢ VỚI 4 (để tránh gặp phân số)
iii) VẼ HỘP

và cứ thế tiếp tục!

PHƯƠNG PHÁP HỘP SẼ KHÔNG BAO GIỜ LÀM BẠN THẤT VỌNG!

---

::: tab

#### Ví dụ 1

Giải 7x2−x+1=9.__

Đáp án: Nhân tất cả với 7 để chuyến số hạng đầu tiên thành bình phương:

49x2−7x+7=63
và nhân với 4 để chuyển số hạng thứ hai thành giá trị chẵn (và bảo toàn tính chính phương):

196x2−28x+28=252

|      | `14x`    | `-1`   |
| `14x` | `169x^2` | `-14x` |
| `-1`  | `-14x`   | `1`  |
{.q-grid}

Trừ 27 cho mỗi vế và chúng ta có thể tiếp tục rồi!

196x2−28x+1=225
(14x−1)2=225
14x−1=15    hoặc    14x−1=−15
14x=16    hoặc    14x=−14
x=87    hoặc    x=−1   □

::: tab

#### Ví dụ 2

__Giải  2x2+3x−3=5.__

Đáp án: Hãy nhân hết với 2 để số hạng đầu tiên thành chính phương:

4x2+6x−6=10.

Nhân với 4 cho tất cả và chúng ta thấy các phân số được loại bỏ:

16x2+24x−24=40.

|      | `4x`    | `3`   |
| `4x` | `16x^2` | `12x` |
| `3`  | `12x`   | `9`  |
{.q-grid}

Cộng 33 cho mỗi vế:

16x2+24x+9=73
(4x+3)2=73
4x+3=73−−√    hoặc    4x+3=−73−−√
4x=−3+73−−√    hoặc    4x=−3−73−−√
x=−3+73√4    hoặc    x=−3−73√4
Mấy con số không đươc đẹp lắm, nhưng phương pháp này dễ.    □

::: tab

#### Ví dụ 2

__Giải −2x2+3x+7=1.__

Đáp án: Nhân tất cả với −2 và tiếp tục nhân với 4. Có nghĩa, hãy nhân tất cả cùng lúc với -8.

16x2−24x−56=−8

|      | `4x`    | `-3`   |
| `4x` | `16x^2` | `-12x` |
| `-3`  | `-12x`   | `9`  |
{.q-grid}


16x2−24x+9=−8+9+56
(4x−3)2=57
4x−3=±5–√7
x=3±5√74
Xong!    □   (CÂU HỎI: Việc sử dụng kí hiệu ± ở đây có nguy hiểm không?)

::: tab

#### Ví dụ 2

__Giải 11x2−x+5=0__

Đáp án: Nhân với 11 ban đầu và nhân với 4, tức là, cần nhân tất cả với 44:

484x2−44x+220=0.

|      | `22x`    | `-1`   |
| `22x` | `484x^2` | `-22x` |
| `-1`  | `-22x`   | `1`  |
{.q-grid}

Trừ hai vế cho 219 ta được:

484x2−44x+1=−219
(22x−1)2=−219
Nhưng không có số nào mà bình phương là số âm!

Phương pháp hộp cho chúng ta thấy phương trình này không có nghiệm! □

:::

---

BÌNH LUẬN: Mọi ví dụ cho đến bây giờ đều có một nghiệm, nhưng điều này 
không phải lúc nào cũng vậy. Ví dụ:

x2=9 có chính xác hai nghiệm.

x2=0 có duy nhất một nghiệm.

x2=−9 không có nghiệm nào.

Phương pháp hộp chuyển mọi phương trình bậc hai thành dạng:

(something)2=A.

Nếu A là giá trị dương, phương trình sẽ có hai nghiệm; nếu A bằng không, phương trình sẽ chỉ có một nghiệm; và nếu A là giá trị âm, phương trình đó sẽ không có nghiệm.

---

### Bài toán

BÀI TẬP 50: Giải:

a) 3x2+7x+5=1
b) 5x2−x−18=0
c) 3x2+x−2=2
d) 2x2−3x=5
e) 10x2−10x=1
f) 2x2−3x+2=0
g) 2x2=9
h)   4−3x2=2−x


a) Một hình chữ nhật có chiều dài gấp đôi chiều rộng. Diện tích của nó là 30 inch vuông. Tìm chiều dài và chiều rộng của hình chữ nhật?

b) Một hình chữ nhật có chiều dài dài hơn chiều rộng 4 inch. Diện tích của nó là 30 inch vuông. Tìm chiều dài và chiều rộng của hình chữ nhật?

c) Một hình chữ nhật có chiều dài dài hơn chiều rộng 5 inch. Diện tích của nó là 40 inch vuông. Tìm các kích thước của hình chữ nhật?


BÀI TẬP 54: Giải các phương trình bậc hai sau đây:

a) v2−2v+3=27
b) z2+4z=7
c) w2−6w+5=0
d) α2−α+1=74
Cũng lưu ý là x=(x−−√)2. Giải các phương trình bậc hai trá hình dưới đây.

e) x−6x−−√+8=0
f) x−2x−−√=−1
g) x+2x−−√−5=10
CẨN THẬN! Giải thích vì sao chỉ có một đáp án có giá trị ở câu g).

h) 3β–2β−−√=7
i) 2u4+8u2−5=0


BÀI TẬP 55:

a) Chứng minh rằng phương trình 2(x−4)2+6 là phương trình bậc hai.

b) Giải 2(x−4)2+6=10.

c) Cho là y=2(x−4)2+6. Giá x bằng bao nhiêu để giải trị y đạt giá trị nhỏ nhất?

1. Câu hỏi
Cách nào giải phương trình (2x+3)2=19 tốt nhất?

Giải (x+1)3=27.

Giải −3x2+5x+2=1 bằng phương pháp hộp.

Tính chu vi của hình chữ nhật có diện tích bằng 25 inch vuông và một cạnh dài hơn cạnh còn lại 2 inch?

Giải (x−a)(x−b)=0  dĩ nhiên cho ra x=a  hoặc x=b. Nhưng nếu chúng ta triển khai phương trình đó, cho ra: x2−(a+b)x+ab=0. Áp dụng phương pháp hộp vào x2−(a+b)x+ab=0. Liệu cách này cũng cho ra nghiệm x=a hoặc x=b?

---

### Nhân tử hóa (Phân tích thành thừa số)

Hãy nhìn vào một phương trình hơi phức tạp

{.text-center} `x^2 - 4x = 0`

Phương trình này chứa số hạng x (đáp án cần tìm) và cả số hạng x^2, 
tức là cách cũ mà chúng ta tách x^2 qua một vế của phương trình 
và sau đó lấy căn bậc hai không sử dụng được nữa.

Nhưng có một thủ thuật khác giúp chúng ta - chúng ta có thể lấy một "x" 
của cả hai `x^2` và `4x` làm thừa số chung:

{.text-center} `x (x - 4) = 0`

Bây giờ chúng ta có thể sử dụng tính chất của phép nhân: nếu tích của 
hai thừa số bằng 0, tức là một trong hai thừa số đó phải bằng 0. Không có 
cách nào để có tích bằng 0 từ hai thừa số _không bằng 0_.

{.todo} Hình ảnh

Quay về ví dụ của chúng ta, điều này có nghĩa `x = 0`, hoặc `(x-4) = 0`. Vì thế,
phương trình bậc hai này có hai nghiệm: `x=0` và `x=`[[4]].

{.todo} Luyện tập

Đây là một phương trình bậc hai khác có thể giải bằng cách phân tích thành thừa số:

{.text-center} `x^2 - 6x + 5 = 0`

Khác với lần trước, chúng ta không thể lấy _x_ ra làm thừa số chung, vì chúng ta vẫn còn có 
5 còn dư lại ở cuối. Giải pháp của chúng ta cần phải thông minh hơn một chút:

{.text-center} `(x - 3)(x - 2) = 0`

Nếu bạn triển khai các dấu ngoặc đó, bạn sẽ thấy là chúng ra hoàn toàn giống nhau.
Nhưng bây giờ chúng ta có thể sử dụng cách thức tương tự khi tích bằng 0, từ đó tìm ra 
phương trình bậc hai này có hai nghiệm:`x=`[[3]] hoặc `x=`[[2]].

Thật không may, điều này không giải thích được tại sao chúng ta có số 2 và 3 _phù hợp_ để giải phương trình trên. Để diễn giải ra, chúng ta có thể làm ngược lại:

{.eqn-system}
| `(x - P)(x - Q)` | `= 0` |
| `x^2 - Qx - Px + P*Q` | `= 0` |
| `x^2 - (P+Q)x + P*Q` | `= 0` |

{.todo} Hãy bắt đầu bằng việc xem lại cách để rút gọn các số hạng bằng dấu ngoặc. Ví dụ thủ thuật đơn giản là cộng tất cả cặp số có thể có, và để ý tới các dấu trừ:

Bây giờ, nếu chúng ta có phương trình bậc hai tương tự `x^2-8x+15=0`, chúng ta chỉ việc so sánh các hệ số để nhận ra chúng ta muốn P+Q=8 và P*Q=15. Sau đó, phỏng đoán một chút và thử các khả năng khác nhau, chúng ta có thể tìm ra được một kết quả khả thi là P=3 và Q=5. Vì thế,

{.eqn-system}
| `x^2-8x+15` | `= 0` |
| `(x-3)(x-5)` | `= 0` |
| `x-3=0` or `x-5` | `= 0` |
| `x=3` or `x` | `= 5` |

Quá trình đi tìm các giá trị P và Q luôn cần một chút phỏng đoán, nhưng trong 
các ví dụ dưới đây thì chúng khá dễ.

{.todo} Bài tập!

Cố gắng tìm số còn thiếu trong các ví dụ nhân tử hóa:

{.text-center}
x^2 + 3x + 2 = (x+1)(x+[[1]])
x^2 + 5x + 4 = (x+4)(x+[[1]])
x^2 - 8x + 15 = (x-3)(x-[[1]])
x^2 - 5x - 14 = (x+2)(x-[[1]])

{.todo} Một số phương trình bậc hai trông có vẻ hoàn toàn rất bình thường, nhưng khi chúng phân tích chúng thành nhân tử, chúng ta chỉ thu được một dấu ngoặc:
Trong những trường hợp này, phương trình bậc hai này chỉ có một nghiệm duy nhất.

{.todo} Và cuối cùng, một số phương trình bậc hai có hệ số ở đằng trước. Điều này dẫn tới việc nhân tử hóa có một chút khó khăn, nhưng chúng vẫn có thể giải quyết theo cùng một cách:



--------------------------------------------------------------------------------



## Công thức bậc hai

> section: formula
> sectionStatus: dev

    // https://betterexplained.com/articles/quadratic-formula/

Phần bù bình phương có thế đòi hỏi sự cẩn thận, và nó dễ mắc lỗi sai trong quá trình giải bài.

Hãy thử theo các bước trên để thực hiện phần bù bình phương, nhưng sử dụng với _a_, _b_ và _c_ như các hệ số của phương trình bậc hai, thay vì các con số cụ thể:

Phương thức phần bù bình phương thì dài và phức tạp, và rất dễ mắc lỗi sai. 
May thay, có một đường tắt để qui trình đơn giản hơn nhiều!

Để tìm ra nó, chúng ta cần lặp lại phương thức phần bù bình phương, nhưng giữ các hệ số _a_, _b_ và _c_ thay vì là các con số cụ thể.

Hãy bắt đầu với một phương trình bậc hai có dạng

{.text-center} `ax^2 + bx + c = 0`.

Để chuyển số hạng đầu tiên thành dạng chính phương, chúng ta phải nhân toàn bộ phương trình với `a`. Để tránh gặp phân số, chúng ta cũng cần nhân thêm với 4. Thế là cho ra;

{.text-center} `4a2x2+4abx+4ac=0`.

Bây giờ áp dụng phương pháp hộp:

|       | `2ax`     | _b_    |
| `2ax` | `4a^2x^2` | `2abx` |
| `b`   | `2abx`    | `b^2`  |
{.q-grid}


Những bước này rất khó chịu, vật vã, và bạn không cần phải nhớ chúng (mặc dù chúng tương tự như phương thức phần bù bình phương, nhưng là với các biến số).Tuy nhiên, kết quả thì rất xứng đáng: một công thức duy nhất cho ta biết các nghiệm của _bất kì_ phương trình bậc hai nào. Nó thường được gọi là _Công thức bậc hai_: 

{.text-center#qformula} `x = (-b +- sqrt(b^2 - 4ac))/(2a)`

Để gỉải một phương trình bậc hai, chúng ta chỉ cần thay thế _a_, _b_ và _c_ bằng các con số cụ thể trong bài toán của chúng ta, và sau đó đơn giản hóa phân số.

Một số chương trình giảng dạy cảm thấy sự quan trọng trong việc lưu ý công thức
x=−b±b2−4ac√2a đại diện cho hai giá trị đối xứng qua điểm chính giữa x=−b2a.

Từ phần 4 của bài học này, chúng ta biết rằng đỉnh của parabola nằm ở giữa hai điểm đối xứng bất kì. Kĩ thuật của chúng ta đơn giản là tìm các giá trị x phù hợp để có thể định vị vị trí của đỉnh rõ ràng. Bạn không cần phải biết đến công thức này.

(Nhưng nếu bạn vẫn muốn công thức … chỉ cần viết y=ax2+bx+c thành y=x(ax+b)+c. Nó cho thấy rằng các giá trị đầu vào x=0 và x=−ba cho ra các giá trị đầu ra đối xứng. Vì thế, đỉnh nằm ở giữa những giá trị … nằm ở x=−b2a!)

---

### Biệt thức

Một phần quan trọng trong phương trình bậc hai là [biểu thức dưới căn bậc hai](->#qformula_msqrt), được gọi là _biệt thức_. Dựa vào giá trị của `b^2-4ac`, bạn có thể cho biết rất nhiều về các nghiệm của phương trình bậc hai, dù không thật sự giải nó:

* Nếu `b^2-4ac<0`, phương trình bậc hai _không có nghiệm_, bởi vì chúng ta không thể lấy căn bậc hai của một số âm. (Bạn sẽ được biết thêm về điều này sau…)
* Nếu `b^2-4ac=0`, phương trình bậc hai _có một nghiệm_. Số 0 là chữ số duy nhất 
có một giá trị căn bậc hai, bởi vì `+sqrt(0) = -sqrt(0)`.
* Nếu `b^2-4ac>0`, phương trình bậc hai _có hai nghiệm_ như trước, một nghiệm từ việc sử dụng công thức bậc hai mang dấu +, và một nghiệm sử công thức với dấu –.

{.todo} Luyện tập

Hai nghiệm thu được nằm ở vị trí đối xứng qua điểm tại `x=−b/(2a)`.

---

### Giải phương trình bậc hai – Tổng kết

Bây giờ chúng ta đã thấy được nhiều cách khác nhau để giải phương trình bậc hai 
với ưu và nhược điểm riêng:

* __Đại số Sơ cấp_
  Đây là cách dễ nhất, nhưng nó chỉ sử dụng được cho các phương trình bậc hai không có
  số hạng chứa _x_.

* __Phân tích thành nhân tử__
  Cũng khá đơn giản, nhưng cần có một chút phỏng đoán và không thể luôn áp dụng được.

* __Phần bù bình phương__
  Rất dài và phức tạp. Cách này dễ mắc lỗi sai. Bên cạnh việc đi tìm nghiệm của phương trình, cách này cũng cho chúng ta biết đỉnh của đường parabol tương ứng.

* __Công thức bậc hai
  Công thức đơn giản nhưng luôn có hiệu quả, đôi khi cảm thấy như "ma thuật" và rất dễ quên lí do tại sao và nó áp dụng như thế nào.

{.todo} Bài tập cuối



--------------------------------------------------------------------------------



## Diễn giải bậc hai bằng hình học

> id: graphing-1
> sectionStatus: dev
> section: graphs

Ở phần đầu của chương này, chúng ta đều hình dung được hình dạng của hàm số `y=x^2` khi chúng ta chấm điểm trên hệ trục tọa độ.

    x-coordinate-system(width=480 height=320 x-axis="-5,5,1")

Hàm số y=x^2 có tính đối xứng, và có dạng hình chữ U.

Lưu ý: Việc sử dụng “hình chữ U” có phải là cụm từ chính xác không? Hai nhánh của chữ U trông có vẻ thẳng đứng. Liệu các nhánh của y=x2 cũng hoàn toàn thẳng đứng? Nếu chúng ta chấm chính xác các điểm của đồ thị y=x2, nó trông giống chữ U cỡ nào?

Vị trí mà đồ thị hình chữ U giảm dần đến điểm thấp nhất, nếu đồ thị hướng lên trên, hoặc “giảm” cho đến điểm cao nhất nếu đồ thị hướng xuống dưới thì được gọi là đỉnh của đồ thị bậc hai.

### Dịch chuyển và trượt

CẦN CÓ Ví dụ để giải thích tại sao cần dịch chuyển parabol.

Tôi cao 6 feet và đang đứng ở vị trí tại x=4 trên trục nằm ngang. Liệu có thể viết được phương trình hàm số có đồ thị hình chữ U như hình y=x2 nhưng đặt ở vị trí mà để cân bằng trên đầu của tôi?

Chắc nên thử làm trước khi đọc tiếp. Hãy thử các công thức khả thi. Thế thử một số điểm và kẻ bảng giá trị. Kiểm tra xem ý tưởng của bạn có thể cung cấp bất kì gợi ý nào để giải bài toán thử thách này không.
---

#### Dịch chuyển theo Chiều dọc

Đồ thị của y=x2+3 sẽ trông như thế nào?

Lưu ý là hàm số mới cộng ba đơn vị vào mỗi giá trị đầu ra:

![](http://gdaymath.com/wp-content/uploads/2013/03/Q4_1_pic10.png)

Điều này dẫn tới việc nâng toàn bộ đồ thị lên ba đơn vị theo chiều dọc:

![](http://gdaymath.com/wp-content/uploads/2013/03/Q4_1_pic11.png)

Đồ thị của hàm số y=x2−5 vẫn là đồ thị cũ nhưng dịch chuyển xuống 5 đơn vị, và đồ thị của y=x2+3–√ là đồ thị đó khi dịch chuyển lên 3–√ đơn vị.

LUYỆN TẬP 58:

a) Phác họa y=x2−5
b) Phác họa y=x2+1/2.

---

#### Dịch chuyển theo Chiều ngang

Một điều cần lưu ý là đồ thị này có một "điểm đáy" tại x=0.

Bây giờ xét hàm y=(x−3)^2.

Lưu ý rằng khi chúng ta thế x=3 vào công thức thì thu được 02. Có nghĩa, số 3 đang “đóng vai trò” như khi x=0 trong hàm số gốc.

Trong y=(x−3)^2, chúng ta có số 3 là điểm “0 mới” cho các giá trị x.

Vì thế bất kể hàm gốc làm gì tại x=0, hàm này lặp lại như thế tại x=3.

Hàm số gốc y=x2 giảm tại x=0, vì thế đồ thị của hàm số y=(x−3)^2
giảm tại x=3.

![](http://gdaymath.com/wp-content/uploads/2013/03/Q4_1_pic5.png)

Toàn bộ đồ thị được dịch chuyển theo chiều ngang – và bạn có thể kiểm tra bằng cách kẻ bảng giá trị nếu bạn muốn:

![](http://gdaymath.com/wp-content/uploads/2013/03/Q4_1_pic6.png)

{.todo} Slider move

BÀI TẬP 57:

a) Phác họa đồ thị y=(x−4)2.

b) Phác họa đồ thị y=(x+12)2.

----

#### Kết hợp cả hai

Đây là đồ thị của y=x2:

và đây là đồ thị của y=(x−2)2.  Số “2” ở đây đang đóng vai trò là điểm 0 mới cho các giá trị của x, vì thế điểm đáy tại 0 bây giờ chuyển thành tại 2:

Bây giờ xét hàm y=(x−2)2+3 . Đây là đồ thị lúc trước được dịch lên trên ba đơn vị:

Lưu ý thứ tự dịch chuyển không quan trọng.

BÀI TẬP 59:

a) Phác họa y=(x−4)2−1.

b) Phác họa y=(x+4)2+2.

c) Phác họa y=(x+1)2−2.

---

BÀI TẬP 60: Tôi cao sáu feet và đang đứng ở vị trí tại x=4 trên trục nằm ngang. Viết hàm số có đồ thị hình chữ U với vị trí cân bằng trên đầu của tôi.

![](http://gdaymath.com/wp-content/uploads/2013/03/Q4_1_pic15.png)

---

### Co và Giãn

Chúng ta có thể nói gì về đồ thị y=2x2? Chắc chắn là tất cả giá trị đầu ra đều tăng gấp đôi:

![](http://gdaymath.com/wp-content/uploads/2013/03/Q4_2_pic3.png)

Điều này tạo đồ thị chữ U “dốc hơn”:

![](http://gdaymath.com/wp-content/uploads/2013/03/Q4_2_pic4.png)

---

BÀI TẬP 61:

a) Kẻ bảng giá trị của y=3x2 và phác họa đồ thị.

b) Đồ thị nào “dốc hơn,” là của hàm số y=100x2 hay của hàm số y=200x2?

---

Xét y=−x2. Các giá trị đầu ra của hàm này mang dấu ngược lại của hàm y=x2:

![](http://gdaymath.com/wp-content/uploads/2013/03/Q4_2_pic5.png)
![](http://gdaymath.com/wp-content/uploads/2013/03/Q4_2_pic6.png)

---

BÀI TẬP 62: Mô tả đồ thị của y=−2x2.

BÀI TẬP 63:

a) Quentin nói rằng đồ thị của y=110x2 sẽ có hình chữ U hướng lên trên mở rất “rộng”. Bạn ấy có đúng không? Giải thích.

b) Mô tả đồ thị của hàm  y=−11000x2.

---

#### Gôm tất cả lại:

::: tab

#### Ví dụ 1

__VÍ DỤ 64: Phân tích và phác họa nhanh y=2(x−3)2+1.__

Đáp án: Bây giờ hàm số y=2(x−3)2+1 về cơ bản là đồ thị hàm số y=x2 với “một đống lộn xộn.”
Chúng ta thấy đây là một đồ thị chữ U dốc (“độ dốc 2”) với x=3 đóng vai trò như số 0 cho tất cả giá trị x, và cả đồ thị được dịch lên trên một đơn vị.

![](http://gdaymath.com/wp-content/uploads/2013/03/Q4_2_pic7.png)

::: tab

#### Ví dụ 2

__Phân tích và phác họa nhanh y=−(x+2)2+4.__

Đáp án: y=−(x+2)2+4 là hàm  y=x2 bị xáo trộn. Nó là một chữ U bị lật ngược với
x=−2 là giá trị 0 mới và dịch chuyển lên trên bốn đơn vị.

![](http://gdaymath.com/wp-content/uploads/2013/03/Q4_2_pic8.png)

::: tab

#### Ví dụ 3

__Viết phương trình của đồ thị đối xứng hình chữ U:__

![](http://gdaymath.com/wp-content/uploads/2013/03/Q4_2_pic9.png)

Đáp án: Chúng ta thấy rằng đây là đồ thị hình chữ U với x=4 là một giá trị 0 mới. Không có sự tịnh tiến theo chiều thẳng đứng. Độ dốc của đồ thị cũng không được thể hiện rõ. Chúng ta có thể viết:

y=a(x−4)^2
và xem thử chúng ta có thể xác định độ dốc a không.

Đồ thị đi qua điểm có tọa độ x=0, y=6. Thử thế các giá trị này vào:

6=a(0−4)2
6=16a
a=616=38
Do đó

y=38(x−4)2.  □

::: tab

#### Ví dụ 4

__Viết phương trình của đồ thị đối xứng hình chữ U:__

![](http://gdaymath.com/wp-content/uploads/2013/03/Q4_2_pic10.png)

Đáp án: Đây là đồ thị của hàm số y=x2 bị xáo trộn.

Bởi vì đồ thị có tính đối xứng, chúng ta có thể thấy nó có đỉnh tại x=6. Vì thế x=6 đang đóng vai trò như điểm 0 cho tất cả giá trị x. Cũng như thế, đồ thị được dịch chuyển lên trên 40 đơn vị.

Chúng ta không biết độ dốc của đồ thị – mặc dù biết đây là giá trị âm. Chúng ta ít nhất có thể viết:

y=a(x−6)2+40
nhưng chúng ta cần thêm thông tin để xác định a.

Chúng ta có thể thử thế x=6, y=40 nhưng vẫn không thể xác định:

40=a(0)2+40
40=40
Trên thực tế, không có gì ngạc nhiên khi không thể giải được: vì chúng ta đã sử dụng giá trị x=6 và y=40 để đến bước này. Hãy thử thế tọa độ điểm mà chúng ta chưa từng sử dụng.

Đồ thị đi qua điểm x=0, y=0. Thử này xem:

0=a(−6)2+40
−40=36a
a=−3640=−910
Bingo!  Và chúng ta đã có được giá trị độ dốc âm như dự đoán.

LƯU Ý: Chúng ta cũng có thể thử x=12, y=0. Và nó cũng cho ra a=−910 . (Thử xem!)

Thế là chúng ta bây giờ đã có công thức của đồ thị hình chữ U:  y=−910(x−6)2+40   □

::: tab

#### Ví dụ 5

__Viết phương trình của đồ thị hình chữ U đi qua các điểm (3,18) và (17,18) và có giá trị nhỏ nhất là 5.__

Đáp án:

BỨC TRANH HƠN HÀNG NGÀN LỜI NÓI!
Sẽ có lợi thế khi phác họa đồ thị.

Đồ thị này cần trông như thế này:

![](http://gdaymath.com/wp-content/uploads/2013/03/Q4_2_pic11.png)

Bởi vì nó đối xứng, chúng ta thấy được một điểm nằm giữa 3 và 17, đó là x=10, là điểm 0 mới cho tất cả giá trị x. Toàn bộ đồ thị được tính tiến lên trên 5 đơn vị. Chúng ta có:

y=a(x−10)2+5
Thế x=3, y=18 cho ra:

18=49a+5
a=1349
Vì thế

y=1349(x−10)2+5.  □

:::

---

(1) Hàm số nào dưới đây phù hợp với đồ thị ở dưới?

![](http://gdaymath.com/wp-content/uploads/2013/05/Q4L2_Self11.png)

y=4/3(x−1)^2+1
y=4/3(x+1)^2+1
y=4/3(x−1)^2−1
y=4/3(x+1)^2−1
y=−4/3(x−1)^2+1
y=−4/3(x+1)^2+1
y=−4/3(x−1)^2−1
y=−4/3(x−1)^2−1

(2) Một phương trình bậc hai đối xứng qua đường thẳng x=3 và có giá trị lớn nhất là −17. Hàm số nào dưới đây phù hợp với đồ thị này?

y=200(x−3)^2+17
y=−200(x−3)^2+17
y=200(x−3)^2−17
y=−200(x−3)^2−17

(3) Nếu y=a(x+b)2+c là một phương trình bậc hai đi qua gốc tọa độ và có đỉnh (2,3), thì tổng giá trị a+b+c bằng …

1/4
1 3/4
4 1/4
5 1/4

(4) Viết phương trình của đồ thị bậc hai cắt trục x tại x=−10 và tại x=−6 và cắt trục y tại y=−20. Hãy phác họa sơ trong đầu: Đồ thị bậc hai này hướng lên hay hướng xuống?

(5) Liệu đồ thị bậc hai y=10,000,000x2+40,000,000 rất dốc và hướng lên này có
cắt đường thẳng đứng x=999,999,999,999,999?

CÓ
KHÔNG

---

### Dạng Tổng quát và dạng Đỉnh

Đây là đồ thị của y=x2:

![](http://gdaymath.com/wp-content/uploads/2013/03/Q4_3_pic1.png)

Đây là đồ thị của đường y=x:

![](http://gdaymath.com/wp-content/uploads/2013/03/Q4_3_pic2.png)

Chúng ta thu được gì nếu chúng ta “cộng” hai công thức này với nhau và vẽ đồ thị y=x2+x?

Ở vế bên phải, rõ ràng là “ x2 cộng x” tức là cộng các số dương lại với nhau: Đồ thị của y=x2+x rõ ràng là lớn và lớn hơn khi chúng ta di chuyển về phía bên phải.

Vấn đề thì kém rõ ràng hơn khi di chuyển về phía bên trái: Các giá trị x2 lớn và dương nhưng các giá trị x lớn và âm. Thế thì bên dương hay bên âm có giá trị lớn hơn? Liệu đồ thị của y=x2+x ở phía bên trái sẽ dương? Hay nó sẽ âm ở bên trái? Nó sẽ biến thiên giữa các giá trị dương và âm? Nó sẽ trông như thế nào?

Câu trả lời đơn giản là quay trở về những điều cơ bản và chỉ chấm các điểm lên đồ thị. Và đây là bảng giá trị:

![](http://gdaymath.com/wp-content/uploads/2013/03/Q4_3_pic4.png)

![](http://gdaymath.com/wp-content/uploads/2013/03/Q4_3_pic5.png)

Để xem rõ điều gì đang xảy ra giữa x=−1 và x=0, hãy xem thử một vài giá trị khác:

Tại x=−12 chúng ta có y=(−12)2+(−12)=−14=−0/25.

Tại x=−34 chúng ta có y=916−34=−316=−0.1875.

Tại x=−14 chúng ta có y=116−14=−316=−0/1875
Đồ thị có vẻ đi dốc xuống tới giá trị thấp nhất là −14 tại x=−12.

Đây có phải là một đồ thị hình chữ U hoàn chỉnh, với x=−12 đóng vai trò là điểm 0 mới cho tất cả giá trị x và tịnh tiến -14 đơn vị? Theo đó, có phải chúng ta có y=a(x+12)2−14 với một vài giá trị độ dốc a?

Thật sự là … Nếu  y=a(x+12)2−14   đi qua điểm (0,0) sau đó chúng ta cần 0=14a−14 cho ra a=1.

Vậy liệu y=x2+x là một đồ thị hình chữ U dạng y=a(x+12)2−14 trá hình?

Để trả lời câu hỏi này hãy thử triển khai (x+12)2:

(x+12)2=x2+12x+12x+14=x2+x+14

và có

(x+12)2−14=x2+x+14=14=x2+x.

CHÍNH XÁC!  y=x2+x là một đồ thị bậc hai chữ U hoàn chỉnh với đỉnh tại (−12,−14).

---

Bài tập thực hành tùy chọn đã chứng minh các kết quả sau – đây là điều duy nhất chúng ta cần từ phần này:

Mỗi phương trình bậc hai y=ax2+bx+c là một dạng y=x2 với “một đống lộn xộn”.

Nó tương ứng a(x+một giá trị nào đó)2+một giá trị nào đó với độ dốc a.

Cũng vì thế, đồ thị của y=ax2+bx+c cũng là một đường cong chữ U đối xứng (với độ dốc a).

Đây là sự quan sát quan trọng để việc vẽ các dạng đồ thị bậc hai dễ dàng hơn nhiều!

---

### Sức mạnh của tính Đối xứng

Vẫn khó xác định đỉnh của đồ thị này nằm ở đâu, và vì thế nó cũng làm khó việc vẽ đồ thị.

Nếu chúng ta có thể tìm được hai điểm đối xứng và phù hợp, thì theo lẽ thường thì 
bạn sẽ có cách! Để tôi giải thích rõ ý của mình.

VÍ DỤ 76: Phác họa y=2(x−3)(x−9)+7.

Đáp án: Điều đầu tiên cần lưu lý là nếu chúng ta triển khai 2(x−3)(x−9)+7, chúng ta
sẽ thu được một biểu thức có dạng ax2+bx+c . (Thực sự là, hãy thử: Chứng minh là triển khai 2(x−3)(x−9)+7 sẽ ra 2x2−24x+34.)

Tuy nhiên, nếu không thực hiện bước triển khai, chúng ta có thể thấy rằng con số 2 dương ở
đầu sẽ cho ra vế 2x2 trong biểu thức triển khai. Từ đó, chúng ta có giá trị độ dốc dương.

Vì thế chúng ta biết được y=2(x−3)(x−9)+7 sẽ là đồ thị chữ U đối xứng hướng lên trên.

Trong y=2(x−3)(x−9)+7 có hai giá trị x đối xứng và vừa đẹp đập vào mắt của chúng ta:

Thế x=3 và chúng ta có y=0+7=7.
Thế x=9 và chúng ta có y=0+7=7.

Vì thế chúng ta bây giờ có đồ thị chữ U hướng lên trên và đi qua hai điểm đối xứng:

![](http://gdaymath.com/wp-content/uploads/2013/03/Q4_4_pic1.png)

Vì đồ thị có tính đối xứng, theo lẽ thường thì nó có đỉnh tại x=6, điểm này nằm giữa x=3 và x=9.

Vấn đề là chúng ta không biết được độ cao của điểm này trong đồ thị chữ U: Nó có nằm ở trên trục x? Ở dưới? Hay chỉ chạm vào?

![](http://gdaymath.com/wp-content/uploads/2013/03/Q4_4_pic2.png)

Vậy thì … thế x=6 vào công thức trên xem!

Khi x=6 chúng ta có y=2(3)(−3)+7=−11.

Chúng ta phải có được bức hình dưới đây:

![](http://gdaymath.com/wp-content/uploads/2013/03/Q4_4_pic3.png)

XONG!  □

LƯU Ý: Cá nhân tôi thì không băn khoăn chút nào về tỉ lệ trong bức hình cũng như lắm chi tiết rắc rối trong đồ thị. Miễn là thông tin được biểu thị trên đồ thị rõ ràng và chính xác và nêu được các đặc điểm chính cần được quan tâm, thế là ổn.

---

LÀM CÁCH NÀO CÓ THỂ XÁC ĐỊNH GIÁ TRỊ X CẦN TÌM NẾU CHÚNG KHÔNG ĐƯỢC THỂ HIỆN RÕ?

Xét y=x2+4x+5. Đây sẽ là một đồ thị chữ U hướng lên trên.

Để tìm các giá trị cần quan tâm, tập trung vào “phần x” trong công thức, ở trường hợp này, chỉ có:  x2+4x.

Điều duy nhất tôi nghĩ có thể làm được là viết nó lại thành x(x+4) và cho ra:

y=x(x+4)+5.

Bây giờ rõ ràng là cả hai điểm tại x=0 và x=−4 đều thú vị. Vì cả hai đều cho ra y=5.

Bởi tính đối xứng, chúng ta biết được đỉnh nằm ở giữa các giá trị x phù hợp, tại x=−2, và ở đây y=(−2)(2)+5=1.

Và đây là đồ thị của nó.

![](http://gdaymath.com/wp-content/uploads/2013/03/Q4_4_pic7.png)

---

::: tab

#### Ví dụ 1

__Phác họa y=−(x+2)(x−10)+1. Đỉnh của đồ thị nằm ở đâu? Các tọa độ giao điểm nằm ở đâu? Giá trị lớn nhất của đồ thị bằng bao nhiêu?__

Đáp án: Nó là một đồ thị chữ U đối xứng, hướng xuống dưới (giá trị độ dốc là −1). Thêm đó x=−2 và x=10 rất đẹp. Vì cả hai điểm đều cho ra giá trị y=−0+1=1.

![](http://gdaymath.com/wp-content/uploads/2013/03/Q4_4_pic5.png)

Đỉnh của đồ thị nằm ở x=4 và có y=−(6)(−6)+1=37.

![](http://gdaymath.com/wp-content/uploads/2013/03/Q4_4_pic6.png)

Đỉnh có tọa độ (4,37).  Giá trị lớn nhất của đồ thị là y=37. Và tung độ giao điểm tức khi x=0 thì y=−(2)(−10)+1=21. □

::: tab

#### Ví dụ 2

__Phác họa hàm số y=−3x2+6x+7. Và viết lại phương trình theo dạng “đỉnh”__

Đáp án: Đây là chữ U hướng xuống.

Tập trung vào phần x, từ −3x2+6x chúng ta có thể thấy thừa số 3x. Chúng ta có:

y=3x(−x+2)+7.

Bây giờ nó rõ ràng là x=0 và x=2 là hai điểm đẹp. Chúng đều cho ra giá trị y=7.

Đỉnh của đồ thị phải nằm giữa hai giá trị này, tức tại x=1. Ở đây, y=−3+6+7=10.

Thế là khá đủ để có thể phác họa đồ thị!

![](http://gdaymath.com/wp-content/uploads/2013/03/Q4_4_pic8.png)

Bây giờ chúng ta cần phỏng đoán một cách khôn ngoan về định nghĩa của "dạng đỉnh".

Đỉnh của đường chữ U này là (1,10) vì thế chúng ta cũng có thể viết đường cong này thành:

y=a(x−1)2+10
với độ dốc a. Đây có lẽ là “dạng đỉnh”.

Để tìm a hãy thử thế một điểm, x=0, y=7:

7=a(−1)2+10
a=−3
Vì thế chúng ta có y=−3(x−1)2+10.   □

::: tab

#### Ví dụ 3

__Phác họa đồ thị y=−2x2+3x+7. Xác định hoành độ và tung độ giao điểm?__

Đáp án: Đây là đường cong chữ U hướng úp xuống. Chúng ta có:

y=−2x2+3x+7=x(−2x+3)+7
và chũ U này có giá trị là 7 tại hai điểm x=0 và x=32. Vì đây là đồ thị đối xứng, đỉnh phải nằm ở giữa hai giá trị này, tức tại x=34. Ở giá trị này, y=34(−2⋅34+3)+7=818.

Đồ thị có dạng:

![](http://gdaymath.com/wp-content/uploads/2013/03/Q4_4_pic9.png)

Tung độ giao điểm rõ là y=7.

Hoành độ giao điểm là khi y=0. Chúng ta cần giải phương trình:

−2x2+3x+7=0
Phương pháo hộp cho thấy (KIỂM TRA LẠI!):

x=3±65√4.    □

::: tab

#### Ví dụ 4

__Tìm phương trình của đường cong dạng U:__

![](http://gdaymath.com/wp-content/uploads/2013/03/Q4_4_pic10.png)

Đáp án: Hình cho chúng ta thấy x=17 và x=27 cho ra giá trị đầu ra đối xứng. Điều này cho ra công thức:

y=a(x−17)(x−27)+13.

Chúng ta để giá trị a ở đây vì chúng ta chưa biết được giá trị độ dốc.

Tuy nhiên, chúng ta được biết khi x=30 chúng ta có y=60. Vì thế chúng ta cần:

60=a(13)(3)+13
47=39a
a=4739
Do đó y=4739(x−17)(x−27)+13 là thủ thuật!  □

:::

---

LUYỆN TẬP 81: Phác họa các phương trình bậc hai sau đây một cách hợp lí:

a) y−x2−2x+3
b) y=4x2+8x+5
c) y=−5x2−20x+10
d) y=−2(x+30)(x−50)

LUYỆN TẬP 82: Phác họa các phương trình bậc hai sau đây một cách hợp lí:

a) y=3(x−1)2+5
b) y=(x−2)(x+3)+8
c) y=−5x2−20x+10
d) y=7(x−2)(x+3)

LUYỆN TẬP 83: Một đồ thị bậc hai cắt trục x tại x=2 và tại x=8, và nó cắt trục y tại y=7. Tìm công thức của hàm số bậc hai.

GỢI Ý: Hãy phác họa các thông tin bạn đã có và dùng lập luận của bạn để xem phương trình bậc hai phải như thế nào.

LUYỆN TẬP 84: Tìm công thức của đồ thị bậc hai dưới đây:

![](http://gdaymath.com/wp-content/uploads/2013/03/Q4_4_pic11.png)

---

### Nội dung đã học

Để hiểu rõ hơn về mối quan hệ giữa phương trình bậc hai và đồ thị tương ứng, chúng ta cần nghĩ về __sự tịnh tiến__. Bất kì

Tất cả các đường parabol được xem là dạng dịch chuyển của đường parabol chuẩn có phương trình  $y=x^2$y=x2.

Nếu chúng ta so sánh $y=x^2$y=x2 (đỉnh ở đây là tại $\left(0,0\right)$(0,0)) to $y=a\left(x-h\right)^2+k$y=a(x−h)2+k, sau đó chúng ta nghĩ về phương trình bậc hai và đồ thị nó là một dạng tịnh tiến của $y=x^2$y=x2:

$h$h đại diện cho số đơn vị mà đường $y=x^2$y=x2 dịch chuyển theo chiều ngang, và $k$k đại diện cho số đơn vị mà đường $y=x^2$y=x2 dịch chuyển theo chiều dọc. Lưu ý về hướng của dịch chuyển:

nếu phương trình là $y=\left(x+1\right)^2-3$y=(x+1)2−3, 1 đơn vị sẽ dịch chuyển sang bên trái theo chiều ngang.
nếu phương trình là $y=\left(x-1\right)^2-3$y=(x−1)2−3, 1 đơn vị sẽ dịch chuyển sang bên phải theo chiều ngang.


Những dịch chuyển này được gọi là sự tịnh tiến.  Tịnh tiến có nghĩa là thay đổi, và những tịnh tiến này thay đổi phương trình bậc hai đơn giản $y=x^2$y=x2 thành một dạng phương trình bậc hai khác bằng cách dịch chuyển (tịnh tiến), lật ngược (phản chiếu) và biến đổi đồ thị ở trên dốc hơn hoặc ít hơn (co giãn).


$y=a\left(x-h\right)^2+k$y=a(x−h)2+k
Đây được gọi là dạng đỉnh.

nó cho chúng ta biết được tọa độ đỉnh ngay lập tức, và biết được đỉnh ta có thể phác họa đường cong bậc hai tốt 
nó thể hiện cho chúng ta biết số tịnh tiến cần có để có thể thu được phương trình đã cho từ dạng phương trình cơ bản $y=x^2$y=x2.
Nhận dạng các tịnh tiến

Dạng $y=a\left(x-h\right)^2+k$y=a(x−h)2+k cho biết:

Bài học này chỉ tập trung vào sự kết nối giữa phương trình bậc hai và đồ thị tương ứng của chúng, và cách chúng ta có thể vận dụng sự tịnh tiến để có thể dễ dàng nhận ra và hiểu về các phương trình này.

Độ cong của một parabol được xác định dựa vào giá trị $a$a trong phương trình $y=ax^2$y=ax2.

$y=-x^2$y=−x2 vs $y=x^2$y=x2 : Dấu của hệ số $a$a xác định là đường parabol cong lên hay cong xuống.

$y=a\left(x-h\right)^2+k$y=a(x−h)2+k

$a$a quyết định độ cong

$k$k xác định hướng dịch chuyển dọc theo chiều lên hoặc xuống (dựa vào dấu của nó để xác định hướng)

$h$h thể hiện hướng dịch chuyển ngang sang trái hoặc sang phải (dựa vào dấu của nó để xác định hướng)

Cho một hàm số bậc hai và phương trình của nó, chúng ta có thể có nhiều câu hỏi khác nhau về tính chất của nó:

* Đường parabola hướng lên hay hướng xuống?
* Tọa độ của điểm ngoặt là bao nhiêu?
* Đường cong parabola cắt trục x ở đâu (các _điểm không_)?
* Đường cong parabola cắt trục y ở đâu?
* Đường parabola bị kéo giãn hay co nhỏ lại như thế nào?

{.todo} Phác họa đường parabola của phương trình

  x-coordinate-sketch(validate="quadratic:2,-4,1")

{.todo} Suy luận phương trình từ đồ thị phác họa


Vẽ phương trình bậc hai
Hãy nhìn vào phương trình bậc hai $y=-2\left(x-3\right)^2-3$y=−2(x−3)2−3

Hình dạng - chúng ta có thể thấy rằng đồ thị bậc hai sẽ cong xuống vì $a=-2$ < $0$0

Đỉnh - chúng ta có thể thấy phương trình này có điểm ngoặt ở $\left(3,-3\right)$(3,−3).

Chỉ với hai mẩu thông tin này, chúng ta có thể phác họa sơ đường cong.

Nhưng có rất nhiều đường parabol hướng xuống và đỉnh tại $\left(3,-3\right)$(3,−3). Để có thể vẽ đồ thị một cách chính xác với đúng giá trị độ dốc, chúng ta cần thông tin thêm. Chúng ta cần một điểm khác trên đồ thị.

Điểm thông thường được sử dụng là tung độ giao điểm $y$y.

Hãy nhớ
$x$ hoành độ giao điểm xuất hiện khi giá trị $y$y bằng $0$0
$y$ tung độ giao điểm xuất hiện khi giá trị $x$x bằng $0$0

Bây giờ chúng ta có thể phác họa đường cong.

Sử dụng tọa độ đỉnh $\left(3,-3\right)$, dạng đường cong úp và giá trị tung độ giao điểm $y$y là $-21$ :

Vì là dạng phác họa, ở chứa tất cả thông tin mà chúng ta cần để phác họa phương trình bậc hai.

---

### Đặc điểm của Phương trình Bậc hai

Bạn nhớ các ván trượt chúng ta chế tạo ở đầu bài họ không? Một số bản nguyên mẫu đầu tiên đã sẵn sàng, vì thế chúng ta hãy xây dựng một công viên trượt băng nhỏ để thử chúng! Chúng ta đã có hàng rào 50m, cũng như hai dãy tường sẵn có của nhà máy chúng ta có thể sử dụng chúng để rào quanh khu vực. 

{.todo} sơ đồ tương tác

Sử dụng toán học, chúng ta có thể tìm được giá trị _x_ để diện tích của công viên trượt băng lớn nhất có thể.

Nếu ta gọi bề ngang của hàng rào là _x_, thì chiều dọc có chiều dài [{x-equation.var(vars="x", fns="+ -")}]. Tổng diện tích của công viên trượt băng là

{.text-center} `A=`[{x-equation.var(vars="x", fns="+ -")}]

Một lần nữa, chúng ta có phương trình bậc hai! Thay vì giải phương trình, chúng ta muốn tìm _giá trị lớn nhất_ của nó.

{.todo} Định nghĩa của đỉnh và điểm ngoặt

{.todo} Sơ đồ và nghiệm bằng chữ số

{.todo} Scheitelpunktform und Grundform

---

Có hai cách hay để nghĩ về đồ thị của phương trình bậc hai `y = ax^2 + bx + c`:

* __I: Như đồ thị `y=x^2` kèm với đống lộn xộn
  Ví dụ, y=−3(x+10)2+17 là một chữ U lật ngược với x=−10 đóng vai trò như giá trị 0 mới với tất cả giá trị x và đồ thị dịch chuyển hướng lên 17 đơn vị. (Tọa độ đỉnh của đồ thị là (−10,17).)

* __II: Với hai giá trị x đáng chú ý được thể hiện rõ.__
  Ví dụ, y=2(x+5)(x−17)+3 có hai điểm đối xứng rõ ràng: Cả hai x=−5 và x=17 đều cho ra y=3. Giá trị nằm ở giữa chúng, x=−5+172=6 là vị trí của đỉnh. Thế x=6 vào phương trình để tìm tọa độ y của đỉnh. Hình của đồ thị nằm ở đúng vị trí.

Nếu chúng ta viết y=3(x−2)2+5 thành y=3(x−2)(x−2)+5 thành ra nó trông giống như ví dụ được cho ở II. Giá trị x nổi bật được "lặp lại".

Vì thế … có cách nào để hiểu rõ các giá trị x nổi bật được lặp lại để chúng ta có thể không cần nghĩ về cách áp dụng số I và bằng cách nào đó chuyển mọi chuyện theo hướng II?

---

### Câu hỏi

VÍ DỤ 85: Đây là câu hỏi đại số đặc trưng II:

Xét y=2x2−8x+6.
a) Tìm tọa độ đỉnh
b) Tìm “trục đối xứng” (bất kể nó có nghĩa là gì!)
c) Trình bày lại phương trình theo “dạng đỉnh.”
d) Phác họa đồ thị của phương trình bậc hai này
e) Tìm vị trí mà đồ thị cắt trục x.
f) Tìm vị trí mà đồ thị cắt trục y.


Đáp án:

Lời khuyên đầu tiên của tôi là:
KHÔNG MỘT AI YÊU CẦU BẠN PHẢI TRẢ LỜI CÂU HỎI THEO THỨ TỰ ĐÃ ĐƯA RA!

Lời khuyên thứ hai của tôi là:
LUÔN VẼ HÌNH TRƯỚC – và tất cả phần còn lại sẽ rõ ràng.

Vì thế hãy trả lời phần d) đầu tiên.

Các giá trị x nổi bật: y=2x(x−4)+6.

Chúng ta có thể thấy x=0 và x=4 đều cho ra y=6.

Đỉnh của đồ thị phải nằm ở x=2, và tọa độ y=2(2)(−2)+6=−2.

Chúng ta có:

![](http://gdaymath.com/wp-content/uploads/2013/03/Q4_5_pic1.png)

Đây là những phần dễ để trả lời:

a) Đỉnh nằm ở (2,−2).

b) “Trục đối xứng” phải là đường đối xứng thẳng đứng tại điểm 2 trên trục x. Đường phương thẳng đứng này có phương trình: x=2.

f) Tung độ giao điểm ở y=6.

Để trả lời phần c) chúng ta cần sử dụng tọa độ đỉnh để viết lại phương trình bậc hai.

Phương trình là y=a(x−2)2−2 với độ dốc a. (Thật sự là… Vì công thức là y=2x2−8x+6, chúng ta biết độ dốc là a=2, nhưng để kiểm tra …). Hãy thử thế x=0, y=6 để tìm a:

6=a(−2)2−2
8=4a
a=2

Vậy đáp án cho phần c) là:
c) y=2(x−2)2−2.

Để trả lời phần e) chúng ta cần thế y=0 và giải 0=2(x−2)2−2


NHẬN XÉT: Thay vào đó, chúng ta có thể chọn phương trình ban đầu để làm và giải ra 0=2x2−8x+6, nhưng tôi nghĩ rằng những gì tôi đã chọn sẽ nhanh hơn. Cũng không phải vấn đề gì lớn – tất cả con đường đúng đều dẫn đến cùng một kết quả!

Vậy

2(x−2)2=2
(x−2)2=1
x−2=1  hoặc  x−2=−1
x=3 hoặc x=1.

Các tung độ giao điểm là x=1 và x=3.  □

---

BÀI TẬP 86: Xét y=5x2−10x−15.

a) Tìm vị trí của đỉnh
b) Tìm “trục đối xứng.”
c) Trình bày phương trình bậc hai ở “dạng đỉnh.”
d) Phác họa đồ thị phương trình bậc hai
e) Tìm vị trí đồ thị cắt trục x.
f) Tìm vị trí đồ thị cắt trục y.
g) Giá trị nhỏ nhất của đồ thị là bao nhiêu?

---

BÀI TẬP 87: Đây là ba hàm số bậc hai:

(A) `y=3(x−3)(x+5)`
(B) `y=2x^2+6x+8`
(C) `y=2(x−4)2+7`
với bốn câu hỏi:

i) Giá trị kết quả xuất ra nhỏ nhất từ hàm số bậc hai là bao nhiêu?
ii) Đồ thị bậc hai cắt trục x ở đâu?
iii) Đồ thị bậc hai cắt trục y ở đâu?
iv) Tìm tọa độ đỉnh của phương trình bậc hai?

Trong ba hàm số bậc hai ở trên, hàm nào là dễ trả lời cho từng câu hỏi nhất?

---

BÀI TẬP 88:

a) Thử giải phương trình `x^2+10x+30=0`. Chuyện gì xảy ra?

b) Phác họa đồ thị của `y=x^2+10x+30`.

c) Sử dụng đồ thị để giải thích về mặt hình học tại sao phương trình `x^2+10x+30=0` không có nghiệm.

d) Theo đồ thị, liệu phương trình `x^2+10x+30=11` có nghiệm không? Nếu có, hãy xác định nghiệm.

e) Tìm một giá trị b để phương trình `x^2+10x+30=b` có duy nhất một nghiệm.

Bài tập 88 chỉ ra một kĩ thuật rất hay:
NẾU BẠN CÓ THÊ, HÃY VẼ HÌNH ĐẦU TIÊN, MỘT BỨC HÌNH CÓ GIÁ TRỊ BẰNG 1001 TỪ!

---

VÍ DỤ 89: Đồ thị của hàm `y=−x^2+4x−5` cắt trục x bao nhiêu lần?

Đáp án: Chúng ta có y=−x(x−4)−5 và vì thế x=0 và x=4 đều đáng chú ý. (Cả hai điểm đều cho ra y=−5.)

Vậy đỉnh phải nằm ở x=2 và y=−4+8−5=−1.

![](http://gdaymath.com/wp-content/uploads/2013/03/Q4_5_pic2.png)

Chúng ta thấy rằng đồ thị của hàm số này không cắt trục x. □

---

BÀI TẬP 90: Mỗi hàm số bậc hai dưới đây cắt trục x bao nhiêu lần?
a) y=x2−2x−4
b) y=3x2−12x+12
c) y=2−x2

Có bao nhiêu giá trị x cho ra y=0 trong hai hàm số bên dưới?
d) y=−500x2−200x+3000
e) 4=4x2+80x+200

BÌNH LUẬN:  Có thể bạn được dạy công thức “b2−4ac ” để có thể trả lời các kiểu câu hỏi
dạng này. Nhưng như bạn đã thấy, chúng ta cũng chẳng cần đến nó!

---

BÀI TẬP 91: Tìm một giá trị k để y=−2x2+8x+k đạt được giá trị lớn nhất là 43.

GỢI Ý: Vẽ phác họa đồ thị tốt nhất có thể, dù chưa biết giá trị k.

---

BÀI TẬP 92: Tìm một giá trị k để y=3(x−10)(x+10)+k chỉ chạm trục x.

GỢI Ý: Vẽ phác họa đồ thị tốt nhất có thể, dù chưa biết giá trị k.

---

VÍ DỤ 93: Tìm một giá trị k để y=(x−c)(x+c)+k has smallest value −2.

Đáp án: Ở đây x=c và x=−c cần được chú ý. Cả hai đều có y=k.

Vậy chúng ta cần hình chữ U hướng lên qua các điểm đối xứng mà chỉ chạm xuống tới −2. Đồ thị của hàm phải như sau:

![](http://gdaymath.com/wp-content/uploads/2013/03/Q4_5_pic3.png)

Vì đối xứng, “điều này” phải diễn ra tại x=0.

Thay x=0, y=−2 để xem chúng ta có điều gì:

−2=(−c)(c+k
−2−c2+k
Cho ra k=c2−2.  □

---

BÀI TẬP 94:

a) Tìm một giá trị k để y=5x2−10x+k chỉ chạm trục x.

b) Tìm một giá trị m để y=−2x2−18x+m có giá trị lớn nhất là 100.

c) Tìm một giá trị a để y=(x−a)(x−3a) có giá trị nhỏ nhất là −10.

---

BÀI TẬP 95: Xét y=2(x−1)(x+1)+(x−3)(x+4)+x(x−2).

a) Nếu một ai đó triển khai phương trình này, họ có thu được biểu thức y=ax2+bx+c với các giá trị a, b và c? ĐÚNG/SAI.

b) Giải thích tại sao chúng ta dễ dàng thấy được a=2+1+1=4.

c) Thế x=0 vào y=2(x−1)(x+1)+(x−3)(x+4)+x(x−2). Giải thích tại sao bây giờ chúng ta biết c=−14.

Vậy chúng ta có 2(x−1)(x+1)+(x−3)(x+4)+x(x−2)=4x2+bx−14. Chúng ta vẫn chưa biết giá trị của b.

d) Có cách nào dễ để tìm giá trị b? Giá trị này bằng bao nhiêu?

e) Phác họa đồ thị của y=2(x−1)(x+1)+(x−3)(x+4)+x(x−2).

---

BÀI TẬP 96: Một hình chữ nhật có chiều dài x+3 inch và cạnh còn lại dài 7−x inch. Tìm giá trị x để hình chữ nhật có diện tích lớn nhất?

---

BÀI TẬP 100: CÂU HỎI LÝ THUYẾT

Xét phương trình bậc hai ](y=ax^{2}+bx+c\). Viết lại phương trình theo dạng `y = x(ax+b)+c`.

a) Hai giá trị x cần được chú ý trong phương trình này là giá trị nào?

b) Giải thích tại sao đỉnh của đồ thị này ở `x=−b/(2a)`.

BÌNH LUẬN: Nhiều chương trình dạy học yêu cầu học sinh ghi nhớ lại công thức này. Ví dụ, cho `y=3x2+4x+8`, học sinh được yêu cầu có thể nêu được vị trí của đỉnh nằm ở `x=−b2a=−42*3=−23`. Nếu tốc độ đóng vai trò quan trọng, thế thì đẹp! Nhưng nếu không, sẽ không có vấn đề gì khi viết y=x(3x+4)+8 và bảo là đỉnh của đồ thị nằm ở giữa 
x=0 và x=−43.

---

BÀI TẬP 101: Đây là quyền năng của các giá trị x cần chú ý! Cân nhắc thử thách này

Phác họa đồ thị của y=(x+10)3(x+6)2(x+2)(x−3)4(x−5)(x−12)37.

Chúng ta chưa từng làm vấn đề này bao giờ vì thế phải sử dụng trực giác.

Có bất kì giá trị x cần chú ý không?

Đồ thị cắt trục x ở đâu?

Khi giá trị x là một số dương lớn thì đồ thị có tiến về giá trị lớn và dương không?

Đồ thị sẽ như thế nào nếu giá trị x là một số âm lớn như −1000000?

Giữa hai điểm mà đồ thị cắt trục x, bạn có thể cho biết là đồ thị sẽ dương hay âm?

Nếu bạn có thể trả lời những câu hỏi này tức là bạn đã có đủ thông tin để phác họa đồ thị khá hoàn chỉnh rồi!

---

CÂU HỎI:
i) Tìm tọa độ x của đỉnh của y=−4x2+10x+7?
ii) Giá trị x bằng bao nhiêu để hàm số y=2x2−8x−100 có giá trị nhỏ nhất?
iii) Tìm “trục đối xứng” của y=(x−4)2+5?

---

CÂU HỎI:
Giả sử một công ty sản xuất và bán nệm đã xác định các công thức cho doanh thu R(x) mang lại từ việc bán và chi phí C(x) để sản xuất x nệm mỗi tuần. Các công thức đó là:

R(x)=100+20x−x2
C(x)=2x+145

- Phác họa đồ thị của các hàm trên cùng một hệ trục tọa độ.
- Công ty cần phải sản xuất và bán bao nhiêu nệm mỗi tuần để có thể hòa được vốn?
- Công ty cần phải sản xuất và bán bao nhiêu nệm mỗi tuần để có thể tối ưu hóa lợi nhuận?

---

CÂU HỎI:
Tìm công thức tính k theo c để phương trình bậc hai y=x(x−2c)−k  chỉ chạm trục x.



--------------------------------------------------------------------------------



## Chuyển động đường đạn

> id: penguins
> section: projectiles
> sectionStatus: dev
> sectionBackground: projectiles

Như bạn đã biết, chim cánh cụt không thể bay - mà đôi cánh của chúng đặc biệt thích nghi để bơi. Tuy nhiên, bạn có thể giúp chúng đi bằng cú ném của bạn để vượt qua tảng băng:

    figure: x-projectile

---

Với các chương trước, bạn có thể nhận thấy rằng đường bay của chim cánh cụt trông giống như một [[parabol|e-líp|nửa đường tròn]]. _{span.reveal(when="blank-1")}Nhưng tại sao?_

---

Chúng ta hãy thử dự đoán chuyển động của chim cánh cụt bằng cách sử dụng các định luật vật lý. Quan sát chính là mấu chốt để chúng ta có thể chia chuyển động cong của chim cánh cụt thành hai phần hoàn toàn riêng biệt:

::: column.grow

* Chúng ta có thể cho rằng không có lực cản của không khí. Điều này có nghĩa là nếu chúng ta chỉ nhìn vào chiều ngang của chuyển động ("bóng" của chim cánh cụt), nó dường như chuyển động với tốc độ không đổi.

* Theo phương thẳng đứng (lên và xuống), tốc độ của chim cánh cụt thay đổi. Ban đầu nó là dương (hướng lên), sau đó nó chậm dần và chuyển sang âm (hướng xuống).

::: column(width=320)

{.fixme} Đồ thị

:::

---

Tốc độ theo phương thẳng đứng thay đổi vì lực hấp dẫn đang hút quả bóng về Trái đất. _Mức độ thay đổi_ của tốc độ thường được gọi là __gia tốc__, và trên Trái đất, nó luôn là `-10m/s^2` (chúng ta sử dụng giá trị âm vì lực hấp dẫn tác động hướng xuống).

| __Time__         |   0 |  1s |  2s |  3s |  4s |  5s |  6s |  7s |  8s |  9s |
| __Acceleration__ | -10 | -10 | -10 | -10 | -10 | -10 | -10 | -10 | -10 | -10 |
| __Speed__        |  50 |  40 |  30 |  20 |  10 |   0 | -10 | -20 | -30 | -40 |
| __Position__     |   0 |  50 |  90 | 120 | 140 | 150 | 150 | 140 | 120 |  90 |
{.grid}

---

Như bạn có thể thấy, kết quả là một hình parabol. Sử dụng Giải tích

https://nssdc.gsfc.nasa.gov/planetary/lunar/apollo_15_feather_drop.html

---

Tất nhiên, chim cánh cụt bay không phải là thứ duy nhất di chuyển có dạng đường parabol. Nếu chúng ta bỏ qua các lực khác như ma sát, sức cản của gió hoặc không khí, bất kỳ lực nào bay trong không khí và chịu tác động của trọng lực thì tất cả các vật thể mà chúng ta ném vào không khí đều theo đường parabol: bao gồm bóng rổ, tia nước, hoặc thậm chí tên lửa.

Ở đây bạn có thể xem thêm một vài ví dụ:

::: column(width=320)

{.fixme} video

::: column(width=320)

{.fixme} video

::: column(width=320)

{.fixme} video

::: column(width=320)

{.fixme} video

:::

---

Đây là một vài ví dụ:

::: tab

#### Ví dụ 1

::: tab

#### Ví dụ 2

::: tab

#### Ví dụ 3

:::

---


{.fixme} Vì chúng ta biết tốc độ ban đầu của quả bóng, chúng ta có thể dễ dàng tính được tốc độ sau mỗi giây tiếp theo.

{.fixme} Mặt khác, tốc độ là tốc độ thay đổi vị trí. Quả bóng bắt đầu ở độ cao 0 khi chúng ta ném nó và chúng ta có thể tính độ cao của nó sau mỗi giây tiếp theo bằng cách cộng tốc độ tại thời điểm đó.

{.fixme} Hãy bắt đầu với một ví dụ đơn giản: một quả bóng được ném thẳng lên không trung, với tốc độ ban đầu là 50m/s. Sử dụng các định luật vật lý, chúng ta có thể dự đoán chuyển động của quả bóng, và thời gian để quả bóng rơi trở lại mặt đất.

Galileo đã sử dụng ý tưởng này để suy luận rằng bởi vì gia tốc trọng lực là không đổi, và gia tốc là một loại hiệu số kép, tất cả các vật thể đẩy trong không khí đi theo đường của đồ thị bậc hai.

BÀI TẬP 119: Lizzy ném một quả bóng vào không trung. Độ cao của nó, tính bằng feet, tại thời điểm t giây được cho bởi công thức bậc hai:

H(t)=−32t2+480t+6.

a) Tìm H(0). Giá trị này có nghĩa là gì?
b) Tại thời điểm nào thì quả bóng ở vị trí cao nhất?
c) Khi nào quả bóng rơi chạm mặt đất?

Sau khi sử dụng phương trình bậc hai để lên kế hoạch kinh doanh tối ưu cho công ty ván trượt của chúng ta, và thiết kế công viên trượt băng lớn nhất có thể, bây giờ hãy thực sự XXX.

Khi thực hành các bước nhảy và thủ thuật, điều quan trọng là phải hiểu trọng lực

{.todo} ảnh trượt ván



--------------------------------------------------------------------------------



## Các ứng dụng khác

> section: applications
> sectionStatus: dev

::: column.grow

Trong phần trước, bạn đã biết rằng mọi vật mà bạn ném vào không khí đều theo di chuyển
theo đường parabol. Nhưng điều gì sẽ xảy ra nếu quả bóng bắn ra từ một khẩu đại bác, nhanh đến mức nó bay vòng quanh toàn bộ hành tinh và quay trở lại nơi chúng ta bắt đầu?

Quả bóng đi vào một "quỹ đạo" xung quanh Trái đất, giống như Mặt trăng hoặc một vệ tinh, 
và đường đi của nó có dạng [[hình tròn|parabol|hyperbol]].

::: column(width=280)

{.fixme} diagram

:::

Nó chỉ ra rằng có một số dạng di chuyển khác nhau mà một vật thể có thể đi khi có 
trọng lực, và chúng được gọi là __đường conic__.

---

### Đường Conic

Các tia sáng phát ra từ đèn pin tạo thành một hình trụ. Nếu bạn chiếu vào một bề mặt phẳng, bạn có thể thấy các hình dạng khác nhau mà có thể được tạo ra bằng cách cắt ngang hình nón:

    x-conic-section
    .fixme labels

Nếu bạn chiếu đèn pin trực tiếp xuống mặt đất, bạn sẽ có một [[hình tròn|hình elip|hình bầu dục]]. Nếu bạn nghiêng nó một chút, hình tròn sẽ trở thành một hình elip. Nếu bạn tiếp tục xoay đèn pin, hình elip ngày càng lớn hơn, và cuối cùng biến thành hình chữ U kéo dài mãi: đây là một Parabol. Và nếu bạn tiếp tục, parabol sẽ trở thành hyperbol, một dạng hình dạng khác mà bạn sẽ được tìm hiểu thêm sau.

Hình parabol được tạo ra bằng cách cắt hình nón song song với cạnh của nó một cách chính xác. Bạn có thể chứng minh rằng hình dạng của nó khớp với hình được tạo ra bằng cách vẽ đồ thị của một phương trình bậc hai - nhưng điều đó vẫn còn hơi quá khó.

---

Chúng ta đã thấy rằng parabol mô tả đường đi của các vật thể khi bị ném vào không khí. Tất cả các hành tinh trong hệ mặt trời của chúng ta đều chuyển động trên quỹ đạo hình elip xung quanh mặt trời và XXXXX.

Khi NASA phóng những tên lửa đầu tiên vào không gian, các nhà toán học như [[Kathrine Johnson]](bio:johnson) phải tính toán đường đi chính xác của tàu vũ trụ. Những lần phóng đầu tiên là những đường parabol đơn giản chỉ diễn ra trong vài phút. Các lần ra mắt sau đó được đổi thành

https://hackaday.com/2018/02/28/katherine-johnson-computer-to-the-stars/

{.fixme} biểu đồ

---

Tính toán sự chuyển đổi giữa quỹ đạo parabol và elip là một nhiệm vụ cực kỳ khó khăn - như được giải thích ở đây trong di chuyển "Hình ẩn":

{.fixme}

Các hàm và phương trình bậc hai không chỉ xuất hiện trong chuyển động của đường đạn, mà còn có nhiều ứng dụng khác trong khoa học, kỹ thuật, kinh tế và tự nhiên. 
Chúng ta hãy xem xét thêm một vài ứng dụng.

---

### Gương và Phản chiếu

Chấm hai điểm trên một tờ giấy và tạo một nếp gấp để đưa một trong hai điểm trực tiếp đè lên trên điểm kia. Bạn có thể coi nếp gấp này là "đường phản chiếu" giữa A và B. Mọi điểm trên đường thẳng này đều có cùng khoảng cách tới A và B.

Ta có thể nói, "tập hợp các điểm cách đều A và B một cách chính xác là các điểm nằm trên đường trung trực của A và B."

![](http://gdaymath.com/wp-content/uploads/2013/04/Q6_3_pic4.png)

Lấy một tờ giấy trắng và vẽ một đường thẳng trên đó và một điểm P không nằm trên đường thẳng đó. Sử dụng bút dạ để làm cho điểm dễ thấy.

![](http://gdaymath.com/wp-content/uploads/2013/04/Q6_3_pic5.png)

Giữ tờ giấy trước ánh sáng, gấp tờ giấy sao cho điểm trên nằm đâu đó trên đường kẻ. Tạo một nếp gấp.

Mở tờ giấy và sau đó đưa điểm P đến một vị trí khác trên đường thẳng. Tạo nếp gấp thứ hai.

Lặp lại hành động này ít nhất NĂM MƯƠI lần nữa, tạo thêm 50 nếp gấp trên tờ giấy bằng cách đặt điểm P ở các vị trí khác nhau trên đường kẻ.

52 nếp gấp bạn có đã phác thảo hình dạng của một đường cong thú vị.

Dùng bút chì vẽ theo các nếp gấp để phác thảo đường cong mà bạn nhìn thấy.

Khi hoàn thành hoạt động này, bạn sẽ thấy một đường cong hình chữ U. Tất nhiên, câu hỏi đặt ra là đường cong này có phải là hình dạng của một hàm số bậc hai/parabol không?

Việc gấp trước đó yêu cầu đo khoảng cách giữa một điểm và đường thẳng. Nhớ lại rằng chúng ta đo khoảng cách của một điểm đến một đoạn thẳng thông qua độ dài của một đoạn thẳng vuông góc từ điểm đến đoạn thẳng đó:

Giả sử chúng ta được cho một đường thẳng L và một điểm F không nằm trên đường thẳng đó. Khi đó, tập hợp tất cả các điểm cách đều điểm đã cho và đoạn thẳng (xem sơ đồ dưới đây) cho một đường cong hình chữ U.

---
> id: directrix

Điểm F được gọi là trọng tâm của đường cong đặc biệt này và đường thẳng L được gọi là đường chuẩn của nó.

    x-geopad(width=300): svg
      path(x="line(point(0,280),point(300,280))" name="dir")
      circle.move(cx="30" cy="280" project="dir" name="p")
      circle(x="point(150,200)" name="f")
      circle(x="point(p.x,qy(p,d))" name="q")

![](http://gdaymath.com/wp-content/uploads/2013/04/Q6_3_pic7.png)

Đường cong này giống chữ U. Nó có phải là phương trình bậc hai?

---

Parabol có tính chất phản xạ đáng kinh ngạc, đó là khiến cho tất cả các tia sáng song song tới, vuông góc với đường chuẩn, đều hướng đến tâm của parabol.

Đĩa vệ tinh và kính thiên văn phản xạ sử dụng các đĩa có mặt cắt ngang hình parabol để hội tụ các tia sáng song song vào một điểm cố định, và ngược lại, chẳng hạn, gương phản xạ ánh sáng và gương phản xạ đèn pha ô tô là hình parabol: tất cả các tia từ bóng đèn được đặt tại tâm được phản xạ song song với trục của parabol.

![](http://gdaymath.com/wp-content/uploads/2013/04/Q6_3_pic8.png)

Trong một gương hình parabol, các tia sáng tới đều bị phản xạ vào một điểm duy nhất ở chính giữa. Tính chất thú vị này có thể được sử dụng khi xây dựng kính thiên văn vô tuyến, nơi đặt máy thu vào tiêu điểm, hoặc các nhà máy nhiệt điện mặt trời, nơi tập trung tia nắng mặt trời vào một điểm duy nhất để tạo ra nhiều nhiệt.

Hình dạng thực tế của kính thiên văn này được gọi là Paraboloid - về cơ bản nó là một phiên bản ba chiều của một parabol.

Ngay cả các đĩa TV ở nhà của bạn cũng có hình dạng parabol. Chúng tập trung các sóng vô tuyến tới vào máy thu nhỏ ở trung tâm của nó.
---

### Các cây cầu

Trong nhiều cầu treo, các dây cáp treo chính tạo thành hình parabol. Một ví dụ nổi tiếng là Cầu Cổng Vàng ở San Francisco:

Cầu treo có thể kéo dài những khoảng cách đặc biệt dài và tương đối có giá trị kinh tế để xây dựng.

Các dây cáp treo chịu tải trọng rất lớn của bản mặt cầu, cũng như tất cả các phương tiện lưu thông qua đó. Điều này gây ra lực căng và lực nén lớn, và hình parabol là hình dạng tốt nhất để cân bằng các lực này như nhau.

---

### Đường cong dây xích

Galileo nhận thấy hình dạng của một sợi dây hoặc một sợi xích treo giữa hai cực là hình chữ U và suy ra rằng nó cũng phải được tạo bởi một công thức bậc hai. (Chúng ta thấy điều này với hình dạng của các đường dây điện, hình dạng của những sợi dây thừng bao quanh các tác phẩm điêu khắc trong các bảo tàng nghệ thuật, v.v.)

Như chúng ta đã thấy ở phần I, Galileo cũng tự hỏi liệu hình dạng của dây treo có phải là 
các hình dạng của đường cong bậc hai.

![](http://gdaymath.com/wp-content/uploads/2013/04/Q6_1_pic3.png)

Hóa ra không phải vậy! Những đường cong này được gọi là đường cong dây xích (từ tiếng Latinh có nghĩa là “chuỗi”) và được đưa ra bởi một công thức phức tạp. Toán học của họ đã không được tìm ra chính xác cho đến năm 1691, khi mà nội dung giải tích được phát minh.

Tiến hành một số nghiên cứu trên internet để tìm hiểu về các đường cong dây xích, vòm dây xích, và lịch sử của chúng.

Hóa ra là Galileo đã sai lầm về hình dạng của dây treo: chúng không tuân theo công thức bậc hai. Hãy tin tưởng những gì dữ liệu của bạn đang cho bạn biết!

Hình dạng của đường cong được tạo ra bởi một chuỗi treo được gọi là một đường cong dây xích (từ catena trong tiếng Latinh có nghĩa là “dây chuyền). Mãi đến năm 1691, các nhà toán học mới tìm ra công thức chính xác cho đường cong này. (Nó rất khác với công thức bậc hai!)

HOẠT ĐỘNG MỞ RỘNG: Cổng vòm St. Louis có dạng đường cong bậc hai không? Tìm hiểu bằng cách thực hiện các phép đo trên một bức ảnh của vòm.

---

### Đường Parabola Nhân

http://demonstrations.wolfram.com/TheMultiplicationParabola/

---

### Các ứng dụng khác

https://demonstrations.wolfram.com/LiquidInARotatingCylinder/

Các giá trị lớn nhất và nhỏ nhất của phương trình bậc hai được sử dụng trong nghiên cứu chuyển động các vật thể và trong các bài toán về gia tốc và thể tích. Các mô hình kinh doanh cũng bao gồm các hàm bậc hai và được sử dụng để giúp dự đoán lãi và lỗ.

Nhiều phương trình trong vật lý hoặc kinh tế có chứa phép nhân, và những phép nhân này thường dẫn đến bình phương. Đó là lý do tại sao không có gì ngạc nhiên khi thế giới của chúng ta chứa đầy các phương trình bậc hai và các parabol.

Phương trình bậc hai ẩn chứa ở khắp mọi nơi trong thế giới của chúng ta. Bạn có thể nghĩ về bất kỳ ví dụ nào khác không?

    // solve fractional equations that result in quadratics
    // quadratic substitutions
    // quadratic inequalities
    // absolute value equations
    // systems of quadratic equations

    // Fitting data to quadratics:
    // http://gdaymath.com/lessons/quadratics1/5-1-just-do-it/

