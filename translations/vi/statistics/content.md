# Thống kê và dữ liệu

## Toán học Casino 

> id: roulette
> sectionBackground: dark casino
> goals: rotate
> section: casino
> color: "#BA1778"
> level: Intermediate 
> next: graph-theory

    .roulette-wheel
      .layer-2.wheel
      .layer-3
      .layer-4.wheel
      .layer-5
      .ball
      svg(width=380 height=380): circle(cx=190 cy=190 r=190)
    x-gesture(target=".roulette-wheel" offset="-90,-100" slide="0,200")


Ngay sau khám phá ban đầu của họ, các nhà toán học bắt đầu áp dụng các định luật
xác suất đến nhiều phần khác nhau của cuộc sống - bao gồm cả các trò chơi cờ bạc.

Một trong những nhà toán học này là [Karl Pearson] (bio: pearson), người đã phân tích
kết quả của trò chơi Roulette được công bố trên tờ báo Pháp _Le Monaco_.

Roulette bao gồm một bánh xe với các số từ 1 đến 36 được tô màu
__ {. red} đỏ__ và __ {. black} đen__, và cả màu xanh lá cây 0. Một quả bóng lăn xung quanh bên ngoài và hạ cánh ngẫu nhiên vào một trong các con số. Người chơi bạc có thể đặt cược vào một số, một tập hợp nhiều số hoặc chỉ một màu. Tiềm năng chiến thắng của họ
phụ thuộc vào khả năng xảy ra của mỗi kết quả.

---
> id: roulette-1

Đây là một trong hàng trăm trích đoạn báo chí mà Pearson đã thu thập
và phân tích. Ngay từ cái nhìn đầu tiên, nó trông khá ngẫu nhiên:
      
    include mixins
    .newspaper
      p  Kết quả Roulette ngày 19 tháng 8 năm 1823, Bảng 5
      div
        for x in [13, 12, 30, 33, 3, 12, 29, 5, 8, 22, 23, 13, 5, 18, 14, 31, 36, 15, 18, 28, 32, 29, 11, 34, 23, 36, 8, 16, 2, 3, 9, 20, 16, 14, 15, 26, 31, 21, 15, 3, 33, 22, 12, 14, 9, 6, 30, 13, 33, 5, 28, 17, 27, 6, 5, 34, 11, 18, 32, 6, 9, 31, 29, 2, 18, 35, 6, 1, 34, 28, 1, 10]
          span(class=colour(x))= x

Một bánh xe roulette có cùng số lượng các con số màu đỏ và màu đen. Nếu chúng ta bỏ qua
màu xanh lá cây 0 (có nghĩa là sòng bạc thắng), chúng tôi mong đợi số lượng màu đỏ và
số màu đen là [[gần bằng nhau |  bằng nhau]]. Hãy kiểm tra xem
đây thực sự là trường hợp của tập hợp các kết quả ở trên.

    include mixins
    +barchart([['Red', 37, 'r'], ['Black', 35, 'b']])

---
> id: roulette-2

Trông có vẻ như sự phân phối này khá đồng đều - có một sự khác biệt nhỏ giữa
số kết quả màu đỏ và đen, nhưng điều đó luôn được mong đợi trong
xác suất.

Tuy nhiên, Pearson không dừng lại ở đây. Ông  ấy nhận ra rằng nếu kết quả
hoàn toàn ngẫu nhiên, sau đó mỗi cặp trong số bốn cặp có thể có của bộ 2 màu liên tiếp
 cũng phải có khả năng như nhau. Một lần nữa, chúng ta có thể đếm số lần xuất hiện trong ví dụ của chúng tôi:
    include mixins
    +barchart([['RR', 14, 'r'], ['RB', 24, 'rb'], ['BR', 24, 'rb'], ['BB', 9, 'b']])

---
> id: roulette-3

Vì một số lý do, có vẻ như __ {. Red} RR__ và __ {. Black} BB__ xảy ra nhiều
[[ít thường xuyên hơn | thường xuyên hơn]] so với __ {. red} R __ ** {. black} B ** và
__ {. red} B __ ** {. black} R **, mặc dù tất cả chúng phải có cùng xác suất.
Tất nhiên, chúng ta có thể đã _không may mắn_ trong dãy kết quả cụ thể này - nhưng Pearson đã thử nghiệm hàng nghìn kết quả và luôn luôn tìm thấy giống nhau.
---
> id: roulette-4

Nó thậm chí còn tồi tệ hơn nếu chúng ta nhìn vào bộ ba kết quả. Mỗi cái trong số 8 bộ ba màu sắc có thể sẽ có khả năng như nhau, nhưng điều đó rõ ràng không phải là trường hợp
ở đây:

    include mixins
    +barchart([['RRR', 3, 'r'], ['RRB', 10, 'rrb'], ['BRR', 10, 'rrb'], ['RBR', 15, 'rrb'], ['BRB', 14, 'bbr'], ['RBB', 8, 'bbr'], ['BBR', 8, 'bbr'], ['BBB', 2, 'b']])

Có vẻ như trong sòng bạc cụ thể này, các màu sắc xen kẽ thường xuyên nhiều
hơn người ta mong đợi. Hầu như không có bất kỳ dãy dài nào cùng màu
(__ {. Red} RRR__ hoặc __ {. Black} BBB__).

Pearson đã tính toán rằng xác suất nhìn thấy kết quả sai lệch này
nhỏ hơn 1 trên 100.000.000! Ông ta cho rằng các bánh xe Roulette đã bị gian lận
để tạo ra lợi nhuận cao hơn cho Sòng bạc - và đã viết nhiều bức thư tức giận để vạch trần
lừa đảo này.
---
> id: roulette-5

::: column(width=300)

    x-img(src="images/cocktails.jpg" alt="Cocktail Bar" width=300 height=185)

::: column.grow
Cuối cùng khi đi du lịch đến Monte Carlo, anh ấy phát hiện ra rằng lý do
kết quả sai lệch có một bản chất rất khác: các nhà báo được đề nghị ghi lại kết quả thay vì chỉ ngồi trong quầy bar của sòng bạc, uống và tạo ra màu sắc ngẫu nhiên…
:::

---
> id: random-sequence
> goals: random

Câu chuyện này cho thấy rằng con người chúng ta có xu hướng khá tệ trong việc tìm ra 
dữ liệu nhìn có vẻ ngẫu nhiên: chúng tôi thường đánh giá quá thấp các sự kiện không chắc chắn ( dãy dài cùng màu) và đánh giá quá cao những màu có khả năng xảy ra (các màu xen kẽ). Điều này có thể được sử dụng hiệu quả để phát hiện gian lận trong lĩnh vực ngân hàng và bảo hiểm.

Ở đây bạn có thể tự thử nếu bạn giỏi hơn các nhà báo: viết
xuống một dãy các chữ R và các chữ B, và tìm hiểu xem nó thực sự ngẫu nhiên như thế nào:
    label.newspaper: input(type="text", placeholder="RBBRRBBBRRRBRBRRB")
    p.text-center(style="margin-top: -1em; font-family: monospace") Randomness Score: #[span.score 100]/100

---
> id: dealer

::: column.grow
Trong khi Pearson chỉ phân tích các kết quả Roulette trước đó, những người khác đã cố gắng sử dụng toán học để tăng cơ hội chiến thắng trong các sòng bạc. Một trong số này là
[Edward Thorp] (bio: thorp), người đã phát minh ra _đếm thẻ_ - một kỹ thuật
cho phép anh ta đánh bại các sòng bạc tại [Blackjack] (gloss: blackjack).

Sau đó, anh ấy tập trung vào trò chơi Roulette: Với niềm tin rằng, nếu bạn biết chính xác
vị trí và tốc độ của bóng trong bánh xe Roulette, bạn sẽ có thể sử dụng
Vật lý để dự đoán gần đúng kết quả. Sau khi người điều khiển quay bánh xe roulette
, chỉ có vài giây khi bạn vẫn được phép đặt cược mới. Thật không may, khoảng thời gian này là quá ngắn để con người có thể tính toán kết quả trong đầu của họ.
::: column(width=150)
    .book: img(src="images/beat-the-dealer.jpg" width=150 height=250)

:::

---
> id: dealer-1

    img.computer(src="images/wearable-computer.png" width=275 height=364)

Tại Viện Công nghệ Massachusetts, Thorp đã thảo luận về các ý tưởng của mình với
[Claude Shannon] (bio: shannon), một nhà toán học khác và là cha đẻ của
[lý thuyết thông tin] (gloss: thông tin). Họ cùng nhau quyết định xây dựng
lần đầu tiên _ máy tính đeo được_, nhiều thập kỷ trước khi có Mắt kính Google  hoặc
Đồng hồ Apple.

Máy tính có kích thước gần bằng một bao thuốc lá và được buộc xung quanh
eo của họ. Một bộ dây chạy xuống giày của họ, họ chạm vào khi 
bóng vượt qua một điểm đánh dấu nhất định trên bánh xe roulette. Điều đó cho phép
máy tính toán tốc độ của bóng và dự đoán nó sẽ kết thúc ở đâu. Một bộ dây khác dẫn từ máy tính đến tai nghe, tạo ra các âm khác nhau dựa trên các kết quả khác nhau

---
> id: dealer-2

    figure: x-img(src="images/las-vegas.jpg" alt="Las Vegas Strip" width=760 height=345)

Vào mùa hè năm 1961, Thorp và Shannon đã thử thành công máy tính của họ
ở Las Vegas. Nhưng trong khi họ kiếm được một số tiền, thì chiếc máy tính - thứ thậm chí
chứa các bộ phận của máy bay mô hình - không đủ mạnh để sử dụng ở
quy mô lớn hơn

Thorp đã viết về kết quả của họ trong một bài báo khoa học, và tất nhiên, máy tính
sau đó đã bị cấm trong các sòng bạc. Thorp thậm chí còn bị cấm ở tất cả các sòng bạc ở Las
Vegas, nhưng sau đó anh ấy đã chuyển sang các dự án kinh doanh có lợi hơn:
sử dụng toán học và máy tính trên thị trường chứng khoán.

 // Mật mã Shannon và phá mã trong Thế chiến thứ hai, và sẽ tiếp tục
    // trở thành cha đẻ của lý thuyết thông tin - và thực sự là
    // thời đại thông tin. Shannon dạy anh ta tung hứng ba quả bóng, và anh ta
    // đi xe đạp một bánh trên sợi cáp thép được buộc giữa hai gốc cây. "Anh ta
    // sau đó đã đạt được mục tiêu, "anh ấy viết," đó là tung hứng các quả bóng trong khi
    // đi xe đạp một bánh bằng dây buộc. "

--------------------------------------------------------------------------------



## Trực quan hóa dữ liệu

> section: visualisation
> sectionStatus: dev

TODO

---

## Trung tâm và truyền dữ liệu

> section: center-and-spread
> sectionStatus: dev

TODO

---

## Lấy mẫu và ước tính

> section: sampling
> sectionStatus: dev

TODO

---

## Trí tuệ của đám đông

> section: wisdom-of-crowds
> sectionStatus: dev
> goals: guess
> id: guess-1

Trong chương này, chúng ta sẽ thử một thử nghiệm thống kê thực tế, nơi bạn có thể tham gia cùng với tất cả những người dùng Mathigon khác.
Khi bạn nhấp vào nút bên dưới, chúng tôi sẽ hiển thị cho bạn một câu hỏi đơn giản và bạn có 10 giây để gửi một câu trả lời. Đừng cố gắng tính toán câu trả lời - chỉ cần đoán bằng cảm giác của bạn:
::: box
::: column.grow

_Câu hỏi 1__
Có bao nhiêu hạt thạch trong lọ này?

    input.form-field()
    button.btn Start…
    .timer bar

::: column(width=280)

    x-img(src="" width=280 height=320)

:::
:::

---
> id: guess-2

Chúng tôi sẽ quay lại câu hỏi này trong thời gian ngắn, để xem phỏng đoán của bạn gần với câu trả lời thực tế đến mức nào và những người khác đã làm như thế nào. Trước khi làm điều đó, chúng ta hãy thử một bài toán hơi khác.

Trong trường hợp này, bạn sẽ có một phút để ước tính chính xác hơn câu trả lời. Ví dụ: chúng tôi
có thể đoán có bao nhiêu hạt thạch có trong một "lớp" duy nhất của lọ và sau đó nhân số đó lên
bằng giá trị gần đúng [[số lớp | chiều cao của cái lọ | đường kính của cái lọ]]:
::: box
::: column.grow

Có bao nhiêu viên  M & M trong lọ này?

    input.form-field()
    button.btn Start…
    .timer bar

::: column(width=280)

    x-img(src="" width=280 height=320)

:::
:::

---
> id: guess-3

Bây giờ bạn phải đưa ra dự đoán: Bạn nghĩ cái nào nào trong hai ước tính này chính xác hơn?
::: column(width=340 tabindex="0")

(B) Các phép tính sơ bộ của bạn được thực hiện trong vòng chưa đầy một phút

::: column(width=340 tabindex="0")

(A) Giá trị trung bình của tất cả các câu trả lời cho câu hỏi đầu tiên (trong vòng chưa đầy 10 giây), do bạn và
những người dùng khác.

:::

---

Bây giờ

Câu trả lời có thể sẽ khiến bạn ngạc nhiên đấy.

SỐ TIỀN THỰC TẾ: XXX
DỰ ĐOÁN BAN ĐẦU CỦA BẠN: XXX
A: TRUNG BÌNH CỘNG CÁC DỰ ĐOÁN BAN ĐẦU CỦA NGƯỜI DÙNG: XXX
B: TÍNH TOÁN SƠ BỘ CỦA BẠN: XXX

Hóa ra giá trị trung bình (trung bình) của tất cả các dự đoán của người dùng là khá chính xác!

Mặc dù một dự đoán cá nhân có thể sai, nhưng khi chúng tôi lấy nhiều phỏng đoán từ nhiều người khác nhau và lấy trung bình cộng chúng với nhau, chúng tôi sẽ nhận được một dự đoán THỰC SỰ TỐT.
Nó giống như một phép thuật và được gọi là sự khôn ngoan của đám đông. Nó tương tự như những gì chúng ta đã đề cập trong chương trước về lấy mẫu ngẫu nhiên (liên kết) trong đó mỗi suy đoán của con người giống như một mẫu ngẫu nhiên.

Có thể có một số người thực sự 'giỏi đoán' trong đám đông, những người gần với câu trả lời hơn, nhưng phần lớn mọi người có thể sẽ khá xa: một số sẽ đánh giá quá cao số lượng hạt đậu, trong khi những người khác sẽ đánh giá thấp nó. May mắn thay, những lỗi này sẽ triệt tiêu lẫn nhau. Điều này là do đối với mỗi đánh giá quá cao có khả năng có một người nào đó đánh giá thấp hơn nhiều. Khi chúng tôi tính trung bình các giá trị này cùng với giá trị trung bình (trung bình) của chúng sẽ nằm ở giữa, gần với các dự đoán tốt.

Điều đó có nghĩa là thêm ngày càng nhiều dự đoán sẽ làm cho dự đoán của chúng tôi XXX [chính xác hơn, ít chính xác hơn].
----

Khi chúng tôi tăng số lượng người trong đám đông người đoán của chúng tôi, chúng tôi sẽ nhận được câu trả lời chính xác hơn.

Hiện tượng này được phổ biến vào thế kỷ 19 khi Francis Galton yêu cầu mọi người tại một hội chợ quận đoán trọng lượng của một con bò. Khi tính trung bình những phỏng đoán đó, anh ta thấy rằng nó chính xác hơn nhiều so với suy đoán của một chuyên gia.

Hãy thử điều này một lần nữa. Thay vì một con bò, hãy thử chiếc xe tải lớn nhất thế giới (BelAZ 75710). Bạn nghĩ nó nặng đến mức nào?

C U TRẢ LỜI CỦA BẠN: XXX kg
[https://upload.wikimedia.org/wikipedia/commons/thumb/e/e2/BelAZ_75710.jpg/1280px-BelAZ_75710.jpg]

------




Đây là kết quả:

TRUNG BÌNH TRẢ LỜI NGƯỜI DÙNG : _____

C U TRẢ LỜI THỰC TẾ: 360.000 kg

Không tồi, những người dùng Mathigon đã đoán khoảng X% cho câu trả lời đúng!

NGHIÊN CỨU TRƯỜNG HỢP THƯỞNG: Tai nạn kẻ thách thức

Một nơi khác mà chúng ta thấy được sự khôn ngoan của đám đông trong hành động là trên thị trường chứng khoán. Giá cổ phiếu thể hiện sự phỏng đoán về giá trị tương lai của một công ty. Chúng ta có thể nghĩ về việc mỗi nhà đầu tư mua / bán cổ phiếu dự đoán rằng giá trị nên “cao hơn” hoặc “thấp hơn”.

At first, nobody knew what caused the accident, there were many different parts that could have failed and each was made by a different company. At this time investors who held stock in companies which made these parts had to make a quick decision, to sell or not. This is because the company which caused the accident would be hit with fines & bad publicity and would drop in value immediately.

Let’s have a look at the prices of the top 4 component suppliers to the Space Shuttle within hours of the accident:

Lockheed: -5%
Marietta: -3%
Rockwell: -5%
Thiokol: -12%
Một ví dụ nổi tiếng về điều này diễn ra ngay sau vụ tai nạn thảm khốc của tàu con thoi Challenger khi nó gặp sự cố ngay sau khi cất cánh.

Lúc đầu, không ai biết điều gì đã gây ra vụ tai nạn, có rất nhiều bộ phận khác nhau có thể đã bị hỏng và mỗi bộ phận được sản xuất bởi một công ty khác nhau. Vào thời điểm này, các nhà đầu tư nắm giữ cổ phần trong các công ty sản xuất các bộ phận này phải nhanh chóng đưa ra quyết định bán hay không. Điều này là do công ty gây ra vụ tai nạn sẽ bị phạt và bị dư luận xấu và sẽ giảm giá trị ngay lập tức.

Hãy cùng xem giá của 4 nhà cung cấp linh kiện hàng đầu cho Tàu con thoi trong vòng vài giờ sau vụ tai nạn:

Lockheed: -5%
Marietta: -3%
Rockwell: -5%
Thiokol: -12%





Bạn nghĩ công ty nào đã tạo ra bộ phận gây ra vụ tai nạn? XXX

Hóa ra thị trường đã đoán đúng về Thiokol. Nhiều tuần sau, người ta xác nhận rằng thành phần do Thiokol tạo ra là nguyên nhân. Họ đã sản xuất một “seal” (niêm phong) bằng cao su mà nó đóng băng khi cất cánh khiến nó bị hỏng. Đây là một đoạn clip ngắn của nhà vật lý Richard Feynman, người đã xác định được vấn đề rất lâu sau khi thị trường dự đoán nó.

https://www.youtube.com/watch?v=8qAi_9quzUY

Vì vậy, trong khi một trong những nhà vật lý vĩ đại nhất của thế kỷ 20 tìm ra câu trả lời cho câu hỏi này trong vài tuần, thì một nhóm các nhà đầu tư đã tìm ra câu trả lời chung nhanh hơn nhiều, chỉ trong vài giờ.

Hãy nhớ sự khôn ngoan của đám đông vào lần tới khi bạn có một câu trả lời khó giải quyết ... nó có thể chỉ giúp bạn tiết kiệm một chút thời gian!
---

## Bảng tính và bảng tần suất

> section: spreadsheets
> sectionStatus: dev

TODO

---

## Mô hình tuyến tính

> section: linear-models
> sectionStatus: dev

TODO

