# Hàm số mũ

## Định tuổi bằng đồng vị carbon

> section: carbon-dating
> id: egypt
> color: "#EF551E"
> level: Intermediate
> next: probability

::: column.grow

Một nhóm các nhà khảo cổ học đã phát hiện ra một ngôi mộ mới trên sa mạc Ai Cập. Họ cẩn thận mở lối vào đã bị ẩn đi, leo qua một số căn phòng chứa đầy những kho báu cổ xưa, cho đến khi họ đến nơi chôn cất. Quan tài vẫn được niêm phong và chứa xác ướp của một Pharaoh.

Sau khi lập danh mục mọi vật dụng trong lăng mộ và cẩn thận vận chuyển chúng đến một
bảo tàng gần đó, họ cố gắng trả lời câu hỏi cấp bách nhất của họ: Pharaoh này là ai ?, và ông ấy chết khi nào?

::: column(width=300)

    x-img(src="images/egypt.jpg" alt="Egyptian Tomb" lightbox width=300 height=312)

:::

Thật không may, dường như không có hình vẽ và chữ khắc nào trên tường của lăng mộ
chứa bất kỳ cái tên hoặc ngày tháng nào. Tuy nhiên, có một phương pháp khéo léo để
xác định chính xác tuổi của các đồ tạo tác cổ đại như xác ướp hoặc hóa thạch,
chỉ dựa vào vật lý và toán học: __Định tuổi bằng đồng vị carbon__.
[Continue](btn:next)

---
> id: carbon-1

    figure: x-img(src="images/sarcophagus.jpg" alt="Egyptian Sarcophagus" width=600 height=180)

Tất cả các sinh vật sống trên Trái đất - thực vật, động vật và con người - đều chứa carbon
[nguyên tử] (gloss:atom). Thông thường, lõi của một nguyên tử carbon bao gồm sáu
[proton](gloss:proton) và sáu [notron](gloss:neutron), nhưng một lượng nhỏ tỷ lệ nguyên tử carbon chứa thêm notron. “Các biến thể” khác nhau này của carbon được gọi là __isotopes__:

::: column(width=170)

    x-atom(protons=6 neutrons=6 size=150)

{.text-center} __Carbon-12__<br>
6 protons, 6 neutrons<br>
98.8%

::: column(width=170)

    x-atom(protons=6 neutrons=7 size=150)

{.text-center} __Carbon-13__<br>
6 protons, 7 neutrons<br>
1.1%

::: column(width=170)

    x-atom(protons=6 neutrons=8 size=150)

{.text-center} __Carbon-14__<br>
6 protons, 8 neutrons<br>
0.1%

:::

[Continue](btn:next)

---
> id: carbon-2

Tỷ lệ mà các đồng vị này xảy ra gần như hoàn toàn giống nhau, ở khắp mọi nơi trên Trái đất - và điều này sau này sẽ rất quan trọng. Trong ví dụ của chúng ta, chúng ta
đặc biệt quan tâm đến carbon-14, được viết tắt là <sup> 14 </sup> C.
Nó chứa 6 proton và 8 notron, và nó được tạo ra khi các tia vũ trụ tới
từ không gian bên ngoài va vào các hạt cao trong bầu khí quyển của chúng ta.

Bất kỳ mẫu nguyên tử cacbon nào cũng chứa [[0,1]]% trong số các nguyên tử <sup> 14 </sup> C đặc biệt này. Bạn có thể nghĩ rằng đây là một lượng không đáng kể, nhưng cơ thể bạn chứa khoảng `8 × 10 ^ 26` nguyên tử cacbon, có nghĩa là bạn cũng chứa khoảng -14 `8 × 10 ^ 23` nguyên tử cacbon. Đó gần như là một triệu triệu triệu triệu triệu nguyên tử!

    // Carbon là một phần thiết yếu của cơ thể chúng ta, vì nó có thể hình thành,
    // các phân tử phức tạp và dài.

---
> id: radioactive-1
> goals: decay

::: column(width=300)

    .decay-box
      x-atom(protons=6 neutrons=8 size=68 style="cursor: pointer;")
      x-atom(hidden protons=7 neutrons=7 size=68 style="left: 100px")
      x-atom(hidden protons=1 color="fd8c00" size=68 style="left: 178px")
      x-atom(hidden protons=1 color="22ab24" size=68 style="left: 244px")
      .label #[strong Carbon-14]#[br]6 protons#[br]8 neutrons
      .label(hidden style="left: 100px") #[strong Nitrogen]#[br]7 protons#[br]7 neutrons
      .label(hidden style="left: 178px"): strong Antineutrino
      .label(hidden style="left: 244px"): strong Electron
      .operator(hidden style="left: 76px") →
      .operator(hidden style="left: 176px") +
      .operator(hidden style="left: 240px") +
    x-gesture(target=".decay-box x-atom")

{.caption}

::: column.grow

Carbon-14 rất hữu ích vì nó [__có tính phóng xạ__](gloss:radioactive). Các
nguyên tử không ổn định và nó có thể __phân rã__ thành các nguyên tố khác, ổn định hơn. Thực tế là chúng ta được bao quanh bởi nhiều vật liệu phóng xạ, nhưng nồng độ của chúng
không đủ cao để gây nguy hiểm.

:::

---
> id: radioactive-2

::: column.grow

Trong suốt cuộc đời, khi chúng ta ăn và thở, cơ thể chúng ta hấp thụ nguyên tử C <sup> 14 </sup>.
Khi chúng ta chết đi, chúng ta ngừng hấp thụ các nguyên tử C <sup> 14 </sup> mới và những nguyên tử trong cơ thể chúng ta từ từ bắt đầu [[phân rã | sinh sôi | biến mất]].

{.reveal(when="blank-0")} Tất cả các nguyên tố phóng xạ đều phân rã ở một mức rất dễ đoán trước tỷ lệ - điều này được xác định bởi  __chu kỳ bán rã__. Carbon-14, chẳng hạn, có chu kỳ bán rã xấp xỉ 6.000 năm. Điều này có nghĩa là nếu bạn có một khối nguyên tử C <sup> 14 </sup>, sẽ mất 6.000 năm để một nửa trong số chúng phân rã. Sau 6.000 năm nữa, một nửa số nguyên tử còn lại cũng sẽ bị phân hủy, vì vậy bạn chỉ còn lại [[một phần tư | một phần ba | 1/8 | không]] so với số lượng ban đầu.

::: column(width=220)

    x-img(src="images/atom.jpg" alt="Atom" width=220 height=310)

:::

---
> id: radioactive-table-1

Giả sử chúng ta bắt đầu với một khối 1.200 nguyên tử cacbon-14. Sử dụng chu kỳ bán rã,
chúng ta có thể tính lượng nguyên tử C <sup> 14 </sup> còn lại theo thời gian:

::: .overflow-wrap.overflow-table

|            | _{div.col}_ | _{div.col.c1}_ | _{div.col.c2}_ | _{div.col.c3}_ | _{div.col.c4}_ |
| __Years__  | 0           | 6000           | 12,000         | 18,000         | 24,000         |
| __Amount__ | 1200        | [[600]]        | [[300]]        | [[150]]        | [[75]]         |
{.grid.col-grid}

:::

---
> id: radioactive-table-2

Như bạn có thể thấy, chúng ta đang nhân với `§1 / 2` ở mỗi bước, giống như
Dãy [[hình học | số học | Fibonacci]].

---
> id: radioactive-equation

Sử dụng số mũ, chúng ta có thể viết ra phương trình cho số lượng còn lại sau `t` năm:

{.text-center} `§"amount" = 1200 × (1/2)^(t/6000)`

[Continue](btn:next)

---
> id: radioactive-equation-1

Tất nhiên, 1200 và 6000 chỉ là những con số tùy ý. Một phương trình tổng quát hơn là:

::: x-algebra-flow

`"amount" = "initial" × (1/2)^(t/"half-life")`

* Sử dụng luật số mũ, chúng ta có thể chuyển phân số `1 / 2` thành 2, nếu chúng ta
  nhân số mũ với `–1`.
* {.new-row} Phương trình này mô tả số nguyên tử còn lại sau _t_ năm.

:::

---
> id: radioactive-chart

Vì phương trình chứa _số mũ_ và số nguyên tử _giảm đi_,
vì vậy chúng ta gọi quá trình này là __phân rã theo cấp số mũ__.

Chúng ta có thể vẽ biểu đồ số lượng nguyên tử C <sup> 14 </sup> theo thời gian trong một hệ tọa độ. Nếu chúng ta bắt đầu với một lượng ban đầu là $ {format (x0)} {x0 | 3000 | 100,4000,100} nguyên tử, và chu kỳ bán rã là $ {format (hl)} {hl | 5000 | 200,10000,200} năm, sau đó phân rã trông như thế này:

    x-coordinate-system(width=600 height=400 x-axis="0,18000" y-axis="0,4000" axis-names="Years,Carbon-14 Atoms" padding="20 20 20 40")

---
> id: radioactive-chart-2

Các điểm trên biểu đồ cho biết khi số nguyên tử giảm đi một nửa. Chú ý rằng chúng ta có thể tính toán số nguyên tử còn lại tại _ bất kỳ thời điểm nào, không chỉ các khoảng thời gian cụ thể này. Đây là sự khác biệt chính so với cấp số nhân.

Sự phân rã của các nguyên tử phóng xạ là ngẫu nhiên, và không thể dự đoán được _khi chính xác_ một nguyên tử đơn lẻ C <sup> 14 </sup> sẽ phân rã. Biểu đồ cho thấy _trung bình cộng_ số nguyên tử mà chúng ta _ dự kiến_ sẽ còn lại tại một thời điểm cụ thể. Đó cũng là lí do tại sao số nguyên tử còn lại có thể không phải lúc nào cũng là số nguyên - mặc dù bạn không thể có "một nửa nguyên tử". Bạn sẽ tìm hiểu thêm về điều này trong [khóa học về xác suất] (/ khóa học / xác suất / ngẫu nhiên).
[Continue](btn:next)

---
> id: spectrometer

::: column.grow

Bây giờ chúng ta có tất cả thông tin cần thiết để xác định tuổi của Pharaoh. Các
các nhà khảo cổ quyết định cắt một mẫu nhỏ ra khỏi da của xác ướp. Sử dụng một
máy phức tạp được gọi là __mass spectrometer__, chúng có thể "đếm"
số nguyên tử C <sup> 12 </sup> và C <sup> 14 </sup>trong mẫu.
 
Trong ví dụ của chúng ta, họ đã tìm thấy 800 nguyên tử cacbon-14. Với tỷ lệ của
Các nguyên tử C <sup> 12 </sup> và C <sup> 14 </sup> , họ cũng ước tính rằng các mẫu giống nhau có khả năng chứa 1200 nguyên tử C <sup> 14 </sup> khi Pharaoh
vẫn còn sống.

::: column(width=320)

    x-img(src="images/spectrometer.jpg" alt="Accelerator Mass Spectrometer" lightbox width=320 height=280)

{.caption} Accelerator Mass Spectrometer in the Oxford Radiocarbon Accelerator Unit

:::

Tất cả những gì chúng ta phải làm bây giờ là tính xem mất bao lâu để 400
nguyên tử C <sup> 14 </sup> phân rã. Con số đó chính xác là [[thời gian kể từ khi
Pharaoh chết | tuổi của Pharaoh khi ông chết]].

---
> id: carbon-solver

Chúng ta có thể sử dụng phương trình chúng ta tìm thấy ở trên và điền vào các tham số cần thiết:

::: x-algebra-flow

`input(1200,"initial") × 2^((-t)/input(6000,"half-life")) = input(800,"amount")`

* Điền vào ba thông số từ trên!
* Hãy bắt đầu bằng cách chia cả hai vế của phương trình cho 1200.
* {.new-row} Chúng ta có thể tìm giá trị thập phân của phân số ở vế phải của phương trình.
* Bây giờ, chúng ta phải xử lý số mũ ở vế trái. Để làm được điều đó, chúng ta
  có thể sử dụng một hàm đặc biệt được gọi là __Logarit__, bạn sẽ tìm hiểu thêm
  về sau.
* {.new-row} Sử dụng máy tính, chúng ta có thể tìm giá trị của `log_2 (0,667)`.
* {.new-row} Phần còn lại phải đơn giản: hãy nhân cả hai vế của
  phương trình bằng 6000.
* {.new-row} Chúng ta có thể đơn giản hóa vế phải của phương trình.
* Chúng ta cũng có thể loại bỏ dấu - ở cả hai vế của phương trình.
* Như vậy, chúng ta thấy rằng phải mất 3510 năm để đảm bảo số lượng
  nguyên tử C <sup> 14 </sup> phân rã.

:::

---
> id: carbon-end-1

::: column(width=280)

    x-img(src="images/mummy.jpg" alt="Egyptian Mummy" lightbox width=280 height=170)

::: column.grow

Điều này có nghĩa là Pharaoh đã chết cách đây khoảng 3510 năm, hoặc trong
[[1490 ± 10]] trước Công nguyên. Khoảng thời gian này là sự khởi đầu của _Tân Vương quốc_ ở Lịch sử Ai Cập: "thời kỳ vàng son" đánh dấu đỉnh cao quyền lực của Ai Cập. Và tất cả
những gì chúng ta cần là một mảnh mô da nhỏ, cùng với toán học!!

:::

---
> id: carbon-end-2

Các nhà địa chất và sinh vật học có thể sử dụng cùng một phương pháp để xác định tuổi của
hóa thạch. Điều này giúp họ hiểu khi nào các lớp đá nhất định trên lớp vỏ Trái đất của chúng ta
được hình thành, hoặc tổ tiên tiến hóa giữa các loài động vật đã tuyệt chủng.

Xác định niên đại bằng đồng vị carbon được phát triển vào cuối những năm 1940 tại Đại học Chicago, bởi Willard Libby, người đã nhận giải Nobel Hóa học cho công trình của mình vào năm 1960. Nó đã trở thành một phương pháp không thể thiếu trong nhiều lĩnh vực khoa học.

    figure: x-img(src="images/dinosaur.jpg" alt="Fossil" width=760, height=360)

Lưu ý rằng chúng ta đã đơn giản hóa rất nhiều quá trình xác định niên đại carbon trong
chương này. Có nhiều điều khác cần xem xét, chẳng hạn như nhiễm bẩn mẫu, hoặc nồng độ carbon-14 trong bầu khí quyển của chúng ta đã thay đổi như thế nào theo thời gian.

---

## Tăng trưởng và phân rã theo số mũ

> section: growth-decay
> sectionStatus: dev

    img.text-wrap(src="images/fossil.jpg" style="shape-outside: url(images/fossil.png)" width=320 height=295)

Trong phần trước, chúng ta đã xem xét __phân rã theo số mũ__ của các vật liệu phóng xạ và cách nó có thể giúp các nhà khoa học xác định tuổi của hóa thạch và xác ướp sử dụng niên đại carbon. Nhưng cũng có một số điều hoạt động chính xác theo cách ngược lại: chúng _ tăng trưởng theo số mũ.

{.todo} TODO

---

## So sánh các mô hình

> section: comparing-models
> sectionStatus: dev

Sự phân rã phóng xạ tuân theo một _tốc độ tương đối_: trong những khoảng thời gian bằng nhau, số nguyên tử thay đổi theo tỷ lệ __ cố định __ {.red} (e.g. 50%). Điều này dẫn tới một __mô hình số mũ__{.red}, hoặc tăng tăng trưởng hoặc phân rã theo số mũ.

Mô hình số mũ rất khác với mô hình __tuyến tính __ {.blue}, khi giá trị thay đổi bởi một __ giá trị được cố định __ {. blue} trong những khoảng thời gian bằng nhau.

diagram {.todo}

Dưới đây là một vài ví dụ về các quá trình trong tự nhiên hoặc cuộc sống hàng ngày. Cố gắng xác định những cái nào là tuân theo số mũ hoặc tuyến tính. (Lưu ý rằng một số mô hình đang tăng lên, và những cái khác đang giảm.)

{.todo} phân chia tế bào

{.todo} lãi

{.todo} tốc độ của các máy tính, Định luật Moore

---

## Lãi kép

> section: compound-interest
> sectionStatus: dev

TODO

---

## Biến động dân số

> section: population-dynamics
> sectionStatus: dev

TODO

