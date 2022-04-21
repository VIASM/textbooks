# Thuyết Hỗn Loạn

## Introduction

> section: introduction
> id: pendulum
> goals: play
> color: "#009EA6"
> level: Advanced

Vào đầu thế kỷ thứ 18, các nhà vật lý như [Isaac Newton](bio:newton)
cho rằng vũ trụ là một cỗ máy đồng hồ khổng lồ. Nếu ta có thông tin
chính xác về mọi đối tượng ở thời điểm hiện tại, ta có thể sử dụng các định luật vật lý để
dự đoán những gì sẽ xảy đến trong tương lai.

::: column(width=320)

    x-geopad.sticky.simulation(width=320 height=320)
      canvas(width=640 height=640)
      svg
        circle(x="point(160,160)" name="c")
        circle.move.red(name="p")
        path.thick.red(x="segment(c,p)")
      x-play-toggle

::: column.grow

Một ví dụ điển hình chính là chuyển động của con lắc. Bạn hẳn đã quen thuộc với cách dùng
phương trình vi phân để tìm ra một phương trình có thể tính toán vị trí của
con lắc tại bất kỳ thời điểm nào trong tương lai.

Ta vẫn hay nói với nhau rằng chuyển động của con lắc là __tất định__:
tuân theo chuẩn xác định luật vạn vật hấp dẫn của Newton và ở đó không có tính ngẫu nhiên hay xác suất nào.
Vậy hãy quan sát một con lắc dao động qua lại và thử đoán xem chuyện gì sẽ xảy ra tiếp theo nhé!

:::

---
> id: double-pendulum
> goals: play1 play2

::: column(width=320)

    x-geopad.sticky.simulation(width=320 height=320)
      canvas(width=640 height=640)
      svg
        circle(x="point(160,160)" name="c")
        path.thick.yellow(x="polyline(c,a1,a2)" style="stroke-width: 7px; display: none")
        path.thick.green(x="polyline(c,b1,b2)" style="stroke-width: 6px; display: none")
        path.thick.blue(x="polyline(c,c1,c2)" style="stroke-width: 5px; display: none")
        circle.move.red(name="d1")
        circle.move.red(name="d2")
        path.thick.red(x="polyline(c,d1,d2)")
      x-play-toggle

::: column.grow

Bây giờ để thêm phần thú vị ta hãy đính kèm một
con lắc thứ hai vào con lắc ban đầu - đây được gọi là một __con lắc đôi__.

Một lần nữa, hãy theo dõi chuyển động của nó và cố gắng dự đoán xem chuyện gì sẽ xảy ra. Bạn thậm chí có thể
nhắm mắt trong vòng vài giây... dự đoán của bạn vừa rồi có chính xác?

{.reveal(when="play1")} Con lắc đôi vẫn tuân theo định luật vạn vật hấp dẫn tất định của Newton, 
nhưng chuyển động dường như [[hoàn toàn không theo quy luật|như thể
không có trọng lực nào|chuyển động lặp đi lặp lại]].

{.reveal(when="blank-0")} Điều này càng trở nên rõ ràng hơn nếu ta quan sát
nhiều con lắc cùng chuyển động. Hãy thêm vào con lắc ban đầu ba con lắc nữa, mỗi
con lắc ta thay đổi góc ban đầu khác đi một chút mà mắt không thể quan sát thấy (nhỏ hơn 0.1°).
Nhấn bắt đầu lại và xem chuyện gì sẽ xảy ra!

{.reveal(when="play2")} Ban đầu thì cả bốn con lắc đều cùng chuyển động
theo một quỹ đạo giống nhau – nhưng sau vài giây chúng [[tách ra|hợp lại|thay đổi]]
_{span.reveal(when="blank-1")} và cuối cùng chúng dao động theo các quỹ đạo hoàn toàn khác nhau._

:::

---
> id: double-pendulum-1

Các nhà toán học gọi hành vi này là [__hỗn loạn__](gloss:chaos): ngay cả khi ta biết
về các quy luật vật lý của cả hệ thống thì việc dự đoán tương lai vẫn là
bất khả thi. Những thay đổi dù rất nhỏ ở điều kiện ban đầu cũng sẽ nhanh chóng được khuếch đại lên và 
dẫn đến một chuyển động hoàn toàn khác.

Điều quan trọng là ta phải nhận ra rằng _hỗn loạn_ rất khác với _tính ngẫu nhiên_. Con 
lắc đôi không chứa yếu tố may rủi hay xác suất. Nó tuân theo
định luật vạn vật hấp dẫn chuẩn xác, tất định, tuy nhiên chuyển động của nó là hoàn toàn
không thể dự đoán được.

{.r} Trong tự nhiên và trong cả toán học, tính hỗn loạn nhiều khi 
xuất hiện ở những nơi không ngờ tới. Trong học phần
này, ta sẽ cùng đi tìm hiểu những ví dụ và phám phá ra làm cách nào
toán học có thể giúp chúng ta hiểu được chúng.
[Continue](btn:next)

---
> id: butterfly

### Hiệu Ứng Cánh Bướm

::: column.grow

Năm 1962, nhà toán học [Edward Lorenz] (bio:lorenz) đang làm việc tại MIT, nơi
ông đang phát triển các mô phỏng máy tính về bầu khí quyển nhằm dự báo thời tiết.

Lorenz đã phát triển một thuật toán lấy dữ liệu đầu vào là 
thời tiết hiện tại như nhiệt độ, độ ẩm và tốc độ gió. Rồi sau đó tính toán cách mà những giá trị sẽ
thay đổi như thế nào trong vòng vài phút tới. Bằng cách lặp đi lặp lại
quy trình này, ông có thể dự đoán được thời tiết của nhiều ngày, thậm chí nhiều tuần
sau.

::: column(width=320)

    x-img(src="images/lgp30.jpg" width=320 height=280 alt="Computer used by Edward Lorenz")

{.caption} Edward Lorenz sử dụng LGP-30, một trong những máy tính 
thương mại đầu tiên.

:::

Một ngày nọ, Lorenz quyết định chạy các phần mô phỏng của mình lần thứ hai, cùng một
dữ liệu đầu vào. Ngạc nhiên thay, hai lần dự báo thời tiết ấy
lại ra kết quả hoàn toàn khác nhau.

{.r} Đầu tiên, Lorenz cho rằng hẳn là dòng lệnh đã bị lỗi - nhưng ông nhanh chóng
tìm hiểu ra được chuyện gì đang thực sự xảy ra. Khi chạy mô phỏng lần thứ hai,
ông đã làm tròn về ít chữ số ở hàng thập phân hơn (lấy ví dụ là làm tròn
thành 0.506 thay vì 0.506127). Mặc dù sự khác biệt là rất nhỏ, dưới 0,1%,
nó dường như đã đủ để làm cho mô phỏng này đưa ra những dự đoán 
hoàn toàn khác nhau.
[Continue](btn:next)

---
> id: butterfly-1
> goals: flap

::: column(width=280)

    .r
      x-water-canvas(width=280 height=380 src="images/america.jpg")
      .butterfly
      .tornado
    x-gesture(target=".butterfly")

::: column.grow

Lorenz gọi hiện tượng này là __hiệu ứng cánh bướm__: chỉ cần một con bươm bướm
đập cánh ở Brazil cũng có thể làm thời tiết thay đổi đủ để gây ra một cơn bão 
tại Texas, tại một thời điểm nào đó trong tương lai.

Thường thì bạn vẫn hay nghĩ một thay đổi nhỏ ở thông số đầu vào sẽ chỉ dẫn tới
một thay đổi nhỏ ở kết quả đầu ra. Nhưng với những hệ thống hỗn loạn, như thời tiết hay con lắc
đôi, thì sự thật thường đi ngược lại. Kể cả những thay đổi rất nhỏ cũng sẽ phát triển lên nhanh chóng, 
từ đó dẫn tới sự khác biệt to lớn.

Đó là lí do tại sao ta chỉ có thể dự báo thời tiết trong phạm vi vài ngày. Vì sau đó,
chỉ một chút sai số trong dữ liệu thời tiết sẽ dẫn tới những dự báo khác biệt 
hoàn toàn.

:::

---
> id: butterfly-2
> goals: video

Có một sự khác biệt quan trọng giữa việc _ nắm được các quy luật vật lý_ của một 
hệ thống và khả năng _ dự đoán hành vi của nó_. Định luật hấp dẫn của Newton cho chúng ta
biết chính xác con lắc đôi đáng lẽ nên chuyển động ra sao. Về nguyên tắc, các phương trình vi phân của 
động lực học chất lỏng cho phép chúng ta tính toán thời tiết tại bất kỳ 
thời điểm nào trong tương lai.

Không may thay, để lý thuyết này thành công trong thực tế thì chúng ta sẽ phải tính được
trạng thái ban đầu của con lắc với độ chính xác vô hạn, hoặc biết vị trí chính xác 
của mọi hạt trong khí quyển - đây rõ ràng là điều không thể.
Theo thời gian, những sai số đo lường dù rất nhỏ sẽ khiến những dự đoán của ta thành vô giá trị.
Nói cách khác thì chúng ta _không bao giờ_ có thể dự đoán được chính xác tuyệt đối thời tiết.

::: figure

    x-video(src="https://static.mathigon.org/videos/weather.mp4" poster="images/weather.jpg" width=640 height=360 controls credit="© NASA")
    // source: https://svs.gsfc.nasa.gov/12163

{.caption} NASA sử dụng vệ tinh, máy bay và hàng nghìn trạm khí tượng trên
mặt đất để bắt được nhanh "ảnh chụp" của bầu khí quyển: đo lường các chỉ số quan trọng
như tốc độ gió, lượng mưa, độ ẩm, áp suất không khí và các dòng hải lưu.

:::

    //- TODO Tổng hợp các dự báo, một sơ đồ "spaghetti" về thời tiết

---
> id: dominoes
> goals: video

Tất nhiên, một con bướm không thực sự gây ra cơn bão - nhưng 
nó có thể thay đổi điều kiện của bầu khí quyển vừa đủ để gây ra một cơn bão ở _hiện tại_ 
thay vì xảy ra ở một thời điểm nào khác trong tương lai.

Có thể liên tưởng tới một chuỗi domino với kích thước ngày càng tăng. Một cử động nhỏ làm 
chao đảo quân domino đầu tiên sẽ dẫn đến quân cờ domino lớn nhất đổ:

::: figure

    x-video(src="images/dominoes.mp4" poster="images/dominoes.jpg" width=480 height=270 controls credit="© Gerrydomino, YouTube")

{.caption} Dãy Domino lớn nhất thế giới.

:::

---
> id: applications
> goals: video

### More Applications

Bạn đã chứng kiến con lắc đôi và thời tiết hoạt động một cách hỗn loạn,
nhưng cũng có vô số các ví dụ khác trong tự nhiên và trong công nghệ:

::: column(width=200)

    x-video(src="images/reaction.mp4" poster="images/reaction.jpg" width=200 height=200 credit="© Tim Kench, YouTube")
    // source: https://www.youtube.com/watch?v=PpyKSRo8Iec

{.caption} The __Belousov–Zhabotinsky__ reaction occurs when you mix _bromate_
with an acid. (Shown at 20x speed, © Tim Kench)

::: column(width=200)

    x-img(lightbox src="images/finance.jpg" width=200 height=200 alt="Stock Market Charts")

{.caption} __Thị trường chứng khoán__, lạm phát và nhiều yếu tố khác
gây rất nhiều khó khăn cho ta trong việc dự đoán nền kinh tế.

::: column(width=200)

    x-img(lightbox src="images/heart.jpg" width=200 height=200 alt="Heart")

{.caption} Các nhà khoa học hy vọng rằng việc giải thích nguồn gốc của loạn
__nhịp tim__  (_ rung thất_) có thể giúp ta tìm ra cách chữa trị.

    // Nhịp tim bất thường thường có thể đe dọa đến tính mạng con người sau cơn đau tim. Có khả năng
    // thuyết hỗn loạn có thể dự đoán và giúp thiết kế những máy tạo nhịp tim hiệu quả hơn.

    // Lợi ích chủ yếu của loạn nhịp tim là một biến số rất nhỏ trong
    // cách hàng triệu tế bào co bóp để phân phối tải đồng đều
    // hơn, giảm thiểu sự hao mòn cho trái tim của bạn và cho phép nó hoạt động
    // dài hơn mấy thập kỷ so với khả năng cho phép.

::: column(width=200)

    x-img(lightbox src="images/city.jpg" width=200 height=200)

{.caption} __Biến động quần thể__ thường là dạng hỗn loạn – từ số người sống
trong một thành phố, đến quần thể động vật gặm nhấm, cá hoặc côn trùng.

::: column(width=200)

    x-img(lightbox src="images/stars.jpg" width=200 height=200 credit="Hubble/ESO")

{.caption}__Sao biến quang_ phát xung bằng cách thay đổi độ sáng của chúng theo thời gian.
Một số ngôi sao dao động theo một nhịp độ hỗn loạn.

    // https://en.wikipedia.org/wiki/Stellar_pulsation

::: column(width=200)

    x-img(lightbox src="images/code.jpg" width=200 height=200)

{.caption} Máy tính có thể sử dụng các hệ thống hỗn loạn để tạo ra các __ số 
ngẫu nhiên__  giả hoặc để mã hóa bảo mật hình ảnh.

:::

---
> id: applications-1

Hành vi hỗn loạn cũng đã được tìm thấy trong các mạch điện tử, tiến hóa 
sinh học cũng như từ vòi nước nhỏ giọt, và các nhà khoa học trên thế giới 
đang nghiên cứu thêm nhiều ứng dụng khác.

    // https://en.wikipedia.org/wiki/Chua%27s_circuit
    // https://www.quantamagazine.org/can-scientists-predict-the-future-of-evolution-20140717/

Nhưng trong tất cả các ví dụ này, sự tồn tại của tính hỗn loạn có nghĩa là có những
giới hạn cơ bản trong độ chính xác mà chúng ta có thể dự đoán tương lai. Điều này thường được gọi là
 __chân trời dự đoán__, ngoài giới hạn này ta sẽ không thể nào đưa ra bất kỳ dự báo 
chính xác nào.

::: column(width=300)

    x-img(src="images/forecast.jpg" width=300 height=280)

::: column.grow

Dự báo thời tiết hiện có đường chân trời dự đoán xấp xỉ một
tuần và thậm chí với công nghệ tốt hơn nhiều trong tương lai, có lẽ chúng ta cũng không bao giờ vượt qua
được mốc hai tuần mà vẫn giữ được tính chính xác.

{.r} Thay vào đó, các nhà khoa học có thể sử dụng xác suất để dự đoán _giá trị trung bình_: ví dụ
như tần suất họ mong đợi các sự kiện thời tiết nhất định (như bão) sẽ xảy ra trong một 
năm. Các giá trị trung bình này có thể rất chính xác, ngay cả khi chúng ta không biết _ thời điểm chính xác_
một cơn bão có thể xảy ra.
[Continue](btn:next)

:::

---
> id: definitions

Hãy cùng điểm lại các đặc tính của _hỗn loạn_ mà chúng ta đã cùng tìm hiểu:

::: .theorem

* Một __hệ thống hỗn loạn__ tuân theo chính xác những quy luật [[tất định|có tính xác suất|không thể dự đoán]]
  thường được mô tả bằng một hoặc nhiều phương trình vi phân.
* {.reveal(when="blank-0")} Hệ thống hỗn loạn rất __nhạy cảm với sự thay đổi__.
  Những sai khác rất [[nhỏ|lớn]] ở dữ liệu ban đầu sẽ thay đổi theo thời gian và có thể dẫn tới
  những khác biệt [[rất lớn|nhỏ|ngẫu nhiên]] trong kết quả.
* {.reveal(when="blank-1 blank-2")} Hành vi của chúng __không thể đoán trước__ và
  không có tính lặp lại. Nó thậm chí trông _như thể ngẫu nhiên_, nhưng thực chất chỉ là nó phụ thuộc vào
  những thay đổi nhỏ tới mức không thể nhận thấy hoặc những sai số rất nhỏ trong đo lường.

:::

---
> id: definitions-1

Thuyết hỗn loạn cho chúng ta biết rằng ta không bao giờ có thể dự đoán được tương lai, hoặc biết trước
hành động của chúng ta có thể dẫn tới kết quả như thế nào. Điều này có thể đáng lo ngại nếu ta xem xét đến sự thật là 
thế giới của chúng ta phụ thuộc như thế nào vào các dự đoán toán học: từ mô hình hóa luồng gió 
quanh máy bay hoặc các tòa nhà chọc trời, đến đánh giá tác động của biến đổi 
khí hậu.

---
> id: pop-culture
> goals: video

Nhưng mặt khác, thuyết hỗn loạn và hiệu ứng cánh bướm là những ý tưởng đơn giản
mà ấn tượng, nên chúng sớm có mặt trong sách, trong lời bài hát hay
ngay cả trong những bộ phim:

::: figure

    x-video(src="https://static.mathigon.org/videos/jurassic-park.mp4" poster="images/jurassic-park.jpg" width=480 height=270 audio controls)

{.caption} Trích từ phim _Jurassic Park_ (© Universal Pictures, 1993)

:::



--------------------------------------------------------------------------------



## Toán học Bi-a

> id: pool
> section: billiard
> sectionBackground: dark casino
> sectionStatus: dev

Một trong những đặc điểm bất ngờ nhất của sự hỗn loạn là nó có thể xuất hiện trong
các hệ thống rất đơn giản. Ở phần trước bạn đã tìm hiểu về con lắc đôi.
Giờ là một ví dụ thú vị khác, bàn bi-a.

* https://plus.maths.org/content/chaos-billiard-table
* https://en.wikipedia.org/wiki/Dynamical_billiards
* http://mathworld.wolfram.com/Billiards.html
* https://www.bristol.ac.uk/media-library/sites/pace/documents/corina-powerpoint%20standard.pdf
* http://mathcircle.wustl.edu/uploads/4/9/7/9/49791831/20160306-billiards-presentation.pdf
* http://people.maths.ox.ac.uk/tanner/Prospects2010/CUlcigraiTalk.pdf

{.fixme} Hãy tưởng tượng bạn đang cố gắng dự đoán đường đi của một quả bi trên bàn bi-a
khi tác động bởi một cú hích. Quy tắc chơi khá đơn giản: gia tốc của quả bóng 
bằng lực tác dụng chia cho khối lượng của nó (định luật hai Newton) 
và khi nó tác động vào một bên, góc phản xạ bằng 
góc tới (nói đúng ra là bạn cần bao gồm cả tác động của lực 
ma sát, nhưng điều đó là đơn giản).

{.fixme} Rắc rối là trong một quán rượu thông thường, bạn không thể dễ dàng 
đo lường chính xác độ lớn một lực tác dụng vào bi, góc chính xác 
tác động vào một bên bi, v.v. Khi bạn thực hiện các tính toán của mình, ban đầu chỉ cần một sai số
không chắc chắn rất nhỏ cũng có thể khuếch đại lên và sớm thôi
dự đoán của bạn có thể trở nên vô dụng. Tính "nhạy cảm với sự thiếu thông tin" đó 
là dấu hiệu của một tính hỗn loạn toán học.

    figure.r
      svg(width=760 height=440 viewBox="0 0 760 440")
        rect.pool-table(x=15 y=15 width=730 height=410 rx=10 ry=10)
      x-play-toggle(style="position: absolute; top: 30px; left: 30px")

{.fixme} Hai bàn bi-a đạt cạnh nhau, di chuyển nhẹ một quả bóng

{.fixme} Ứng dụng trong cuộc sống thực (chất bán dẫn)

---

### Bàn Bi-a e-líp

Di chuyển quả bóng màu vàng vào giữa và xem vị trí cuối cùng của nó sau 100
cú va chạm:

    figure: x-pool-table: svg(width=760 height=440 viewBox="0 0 760 440")

---

### Tán xạ hỗn loạn

{.fixme} Hệ thống Gaspard–Rice



--------------------------------------------------------------------------------



## Bài toán tam vật thể

> section: three-bodies
> id: three-bodies
> sectionStatus: dev

Poincare etc.

    figure: x-geopad.simulation.r(width=480 height=480)
      canvas(width=960 height=960)
      svg
        circle.large.move.red(name="a")
        circle.large.move.blue(name="b")
        circle.large.move.green(name="c")
        path.thin(x="segment(a, a.translate(va))" arrows="end")
        path.thin(x="segment(b, b.translate(vb))" arrows="end")
        path.thin(x="segment(c, c.translate(vc))" arrows="end")
      x-play-toggle
      button.icon-btn.restore: x-icon(name="restart")

{.fixme} Có hai hệ thống hỗn loạn ảnh hưởng lớn đến chúng ta. Đầu tiên là thời tiết. Mặc dù các phương trình thời tiết đã khá nằm lòng với chúng ta và được giải bởi máy tính mỗi ngày, nhưng không thể tính đếm hết tất cả các yếu tố ảnh hưởng đến thời tiết (hãy nhớ đến hiệu ứng cánh bướm). Không có bộ dữ liệu nào là hoàn hảo, cũng như máy tính không phải tuyệt đối trong việc giải các phương trình. Tác động của những
 lỗi nhỏ cũng có thể nhanh chóng tăng lên đáng kể. Sau khoảng mười ngày, về cơ bản là không thể dự báo thời tiết với bất kỳ mức độ chính xác nào.

{.fixme} Tính hỗn loạn cũng là chìa khóa để chúng ta tìm hiểu về hệ mặt trời. Trong khi chuyển động của các hành tinh là rất dễ đoán thì nhiều tiểu hành tinh lại không như vậy. Mặc dù các tiểu hành tinh vẫn tuân theo các định luật Newton, chúng cũng có thể chuyển động trong không gian theo những quỹ đạo thất thường. Một tiểu hành tinh thất thường như vậy được cho là đã va vào Trái đất cách đây 65 triệu năm và xóa sổ loài khủng long. Hậu quả của một vụ việc tương tự
 xảy ra ngày hôm nay là không thể tưởng tượng được; Bản chất của chuyển động hỗn loạn có nghĩa là, những sự kiện như vậy hầu như không thể đoán biết trước cho đến khi đã quá muộn.

{.fixme} Năm 1887, nhà toán học người Pháp Henri Poincaré đã chỉ ra rằng, trong khi lý thuyết hấp dẫn của Newton có thể dự đoán một cách hoàn hảo cách hai thiên thể hành tinh sẽ quay quanh dưới lực hút lẫn nhau của chúng, thì việc thêm một thiên thể thứ ba vào tập hợp sẽ khiến các phương trình là không thể giải được. Điều tốt nhất chúng ta có thể làm đối với ba thiên thể là dự đoán chuyển động của chúng theo từng thời điểm và đưa những dự đoán đó vào trở lại phương trình của chúng ta… Mặc dù vũ điệu của các hành tinh có một đường chân trời dự đoán khá dài, song không thể bỏ qua tác động của sự hỗn loạn, vì sự tương tác phức hợp của lực hấp dẫn giữa các hành tinh có ảnh hưởng lớn đến quỹ đạo của các tiểu hành tinh. Để mắt đến các tiểu hành tinh là một công việc khó khăn nhưng đáng để thực hiện, vì một ngày nào đó những hiệu ứng hỗn loạn như vậy sẽ dẫn đến một bất ngờ không mong muốn với chúng ta. Mặt khác, chúng cũng có thể chuyển hướng các bất ngờ tới từ bên ngoài chẳng hạn như chuyển hướng đi của một ngôi sao chổi ra khỏi một vụ va chạm tiềm tàng với trái đất.



--------------------------------------------------------------------------------



## Không gian pha và những tâm hút lạ

> section: attractors
> sectionStatus: dev

Biểu đồ pha của con lắc:
https://youtu.be/MjPFHWul2J0?t=29

những vòng tròn => cân bằng

ma sát 
xoắn ốc => lực hút ổn định

Cáo + thỏ, hệ thống động lực

Định lý Poincaré-Bendixson (trạng thái cân bằng, chu trình giới hạn)

Trường vectơ, trạng thái cân bằng
2D => đơn giản, tất định, 3D => không!

---

Cối xay nước

Sinaï-Ruelle-Bowen đo lường / thống kê / dự báo

* https://www.youtube.com/watch?v=xQ3mJxr2NAY
* https://bl.ocks.org/gcalmettes/c3363abb74fe219b283782f055b72386

{.fixme} Các nhà toán học sử dụng khái niệm "không gian pha" để mô tả các hành vi có thể có của một hệ thống về mặt hình học. Không gian pha không phải (lúc nào cũng) như không gian thông thường - mỗi vị trí trong không gian pha tương ứng với một cấu hình khác nhau của hệ thống. Hành vi của hệ thống có thể được quan sát bằng cách đặt một điểm tại vị trí đại diện cho cấu hình ban đầu và xem điểm đó di chuyển như thế nào trong không gian pha.

{.fixme} Trong không gian pha, một hệ thống ổn định sẽ di chuyển trong dự đoán, về phía một tâm hút ở mức độ rất đơn giản (như là một điểm duy nhất trong không gian pha nếu hệ thống đứng yên, hoặc là một vòng lặp đơn giản nếu hệ thống quay vòng giữa các cấu hình khác nhau một cách lặp đi lặp lại) . Một hệ thống hỗn loạn cũng sẽ di chuyển trong dự đoán về phía tâm hút của nó trong không gian pha - nhưng thay vì các điểm hoặc các vòng đơn giản, chúng ta thấy những "tâm hút lạ" xuất hiện - các hình dạng phức tạp và đẹp mắt (được gọi là Fractal - Phân dạng) ngoằn ngoèo, chi tiết, phức tạp ở tất cả các tỷ lệ cho phép.

{.fixme} Một đặc điểm khác của các hệ thống hỗn loạn là chúng có thể đột ngột chuyển từ hành vi này sang một hành vi khác rất khác biệt. Hãy nghĩ về việc một số loại vay nợ có thể đột ngột từ tài sản trở thành rủi ro đối với ngân hàng. Một sự thay đổi đột ngột như vậy được gọi là sự chuyển pha. Có một cách để quan sát quá trình chuyển pha là ta có thể thử với một vòi nước. Vặn vòi chảy thật chậm và bạn sẽ nghe thấy tiếng nhỏ giọt đều đặn, tong, tong,
 tong. Vặn vòi mạnh hơn một chút và các giọt nhỏ trở nên đều đặn hơn và không phải tất cả các giọt đều cùng một kích thước nữa. Vặn mạnh thêm chút nữa, nước nhỏ giọt sẽ trở nên hoàn toàn bất quy tắc và không thể đoán trước được: sự hỗn loạn bắt đầu. Cứ tiếp tục như vậy, nước sẽ chảy ổn định sẽ thành một cột trong suốt. Tuy nhiên đến khi bạn vặn quá mạnh, cột nước sẽ bắt đầu xoắn, sủi bọt và xoắn ốc: bắt đầu có sự nhiễu loạn. Bằng cách tăng đều đặn dòng chảy, chúng ta quan sắt được tính đều đặn
 và tính hỗn loạn mà không cần phải rời bỏ thế giới của sự tất định này.



--------------------------------------------------------------------------------



## Bản đồ Logistic

> section: logistic-map
> sectionStatus: dev

* https://www.dwitter.net/d/12018
* https://geoffboeing.com/2015/03/chaos-theory-logistic-map/
* Feigenbaum constant
* https://www.youtube.com/watch?v=ovJcsL7vyrk
* https://www.thegreatcourses.com/courses/chaos.html
