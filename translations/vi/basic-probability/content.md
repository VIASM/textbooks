# Giới thiệu về xác suất

## Giới thiệu

> section: introduction
> sectionStatus: dev
> id: intro
> color: "#CD0E66"
> level: Foundations

Ở phần trước của khóa học, chúng ta đã được thấy cách sử dụng khoa học và toán học dự đoán tương lai.
Ví dụ, chúng ta có thể dự đoán khi nào thì một ô tô đến địa điểm định trước nếu nó đi với tốc độ không đổi.

Tuy nhiên, rất nhiều ví dụ trong đời sống không thể dự đoán được chính xác điều gì sẽ xảy ra. Điều này có thể lý giải là do chúng ta không có tất cả những thông tin chúng ta cần, vì những quyết định 
bởi những người khác có thể ảnh hưởng tới kết quả, hay đơn giản là vì nó vô cùng phức tạp.

::: column(width=200)

    // https://depositphotos.com/43434771/stock-photo-fragments-of-the-planet-earth.html
    x-img(src="images/weather.jpg" width=200 height=180 lightbox)

{.caption} Khí quyển chứa hàng tỷ phân tử tương tác với nhau.
Vì vậy, dự đoán chính xác thời tiết là việc không thể.

::: column(width=200)

    // https://depositphotos.com/89420986/stock-photo-ballot-box-with-man-casting.html
    x-img(src="images/election.jpg" width=200 height=180 lightbox)

{.caption} Bạn không biết cách mỗi người bỏ phiếu trong một cuộc bầu cử.
Vì vậy, việc dự đoán chính xác kết quả là không thể.

::: column(width=200)

    // https://depositphotos.com/8537251/stock-photo-queen-of-hearts.html
    x-img(src="images/cards.jpg" width=200 height=180 lightbox)

{.caption} Bạn không biết được thứ tự của các quân bài trong bộ bài sau khi xáo.
Vì vậy, dự đoán chính xác màu của quân bài tiếp theo là việc không thể.

:::

[Continue](btn:next)

---
> id: buckets
> goals: buckets

Ngôn ngữ của chúng ta có rất nhiều từ có thể dùng để miêu tả câu trả lời cho những câu hỏi này 
mà không cần biết chính xác điều gì sẽ xảy ra. Di chuyển từng sự kiện này theo mô tả phù hợp nhất: 

    x-buckets.likelihoods
      .inputs
        .input(bucket="3").md Ngày mai mặt trời mọc.
        .input(bucket="2").md LIKELY
        .input(bucket="1").md Tung đồng xu xuất hiện mặt số 6.
        .input(bucket="0").md Một con voi ma mút xuất hiện trên đường.
        .input(bucket="0").md IMPOSSIBLE
        .input(bucket="3").md CERTAIN
        .input(bucket="1").md Bạn trúng xổ số.
        .input(bucket="2").md LIKELY
      .buckets
        .bucket
          .title Impossible
        .bucket
          .title Unlikely
        .bucket
          .title Likely
        .bucket
          .title Certain

---
> id: dartboard

{.fixme} Bạn có thể nhận thấy rằng một số mô tả hơi "không được chính xác" lắm.
Ví dụ, nếu bạn tung một con xúc xắc chỉ một lần thì không chắc nó sẽ rơi vào mặt số 6 - nhưng 
bạn chắc chắn sẽ không ngạc nhiên nếu nó xảy ra. Việc thắng xổ số cũng không chắc chắn - nhưng rõ ràng là
khó dự đoán hơn tung được mặt số 6!

{.fixme} Thật không may, bốn từ dùng làm thang điểm để mô tả sự hợp lý hay khả năng sự kiện xảy ra của chúng ta lại không hữu ích.

::: column.grow

{.fixme} Một cách để xác định chính xác hơn khả năng xảy ra của một kết quả nào đó là xem xét tần suất nó xảy ra trong quá khứ. Lấy ví dụ, tưởng tượng bạn đang chơi trò phi tiêu với bạn mình - và bạn muốn biết số khả năng bạn của mình phi trúng hồng tâm. Bạn có thể thử tạo ra một số mô hình đo kỹ năng và tìm hiểu xem anh ấy "giỏi" như nào - nhưng phương pháp dễ dàng hơn là lắng nghe quá khứ của anh ấy. Trong trường hợp này, bạn của bạn đã ném ${20} phi tiêu, ${5} trong số đó vào trúng hồng tâm.

::: column(width=200)

    img(src="https://static9.depositphotos.com/1027309/1217/v/450/depositphotos_12178989-stock-illustration-dart-board.jpg")

:::

{.fixme} Từ đó, bạn có thể suy ra rằng lần ném tiếp theo có `5/20=0.25`khả năng trúng vào hồng tâm. Ta gọi giá trị 0.25 là xác suất trúng hồng tâm. 

{.fixme} Trong nhiều thế kỷ, các nhà toán học gặp khó khăn trong việc giải quyết những vấn đề không chắc chắn này- cho đến khi phát triển lý thuyết **xác suất** này. Trong khóa học này, chúng ta sẽ tìm hiểu xác suất là gì và cung cấp cho bạn những công cụ tuyệt vời để dự đoán tương lai.  

---

{.fixme} Nếu bạn di chuyển thanh trượt lên trên, bạn có thể nhận thấy rằng xác suất luôn ở giữa khoảng [[0]] (nếu bạn không bao giờ ném trúng hồng tâm) và [[1]] (nếu bạn luôn ném trúng hồng tâm).  

{.fixme}  Xác suất luông nằm giữa 0 và 1. Một sự kiện với xác suất nhỏ (ví dụ 0.2) ít có khả năng xảy ra hơn một sự kiên với xác suất lớn (ví dụ 0.8).Nếu một kết quả không có khả năng xảy ra, ta nói nó có xác suất 0. Nếu sự kiện đó chắc chắn xảy ra, ta nói nó có xác suất 1. Nếu một sự kiện có khả năng xảy ra hoặc không xảy ra như nhau, xác suất của nó chính xác ở giữa: [[0.5]].

{.fixme} Ta có thể biểu diễn xác suất sử dụng  trục số từ 0 tới 1. Thử kéo các từ và sự kiện sau lên trục số để hiện thị xác suất gần đúng của chúng:

---

{.fixme} Có một vài cách khác nhau để biểu diễn xác suất, chúng ta đã thấy hai trong số chúng. Trong ví dụ đầu tiên, 5 trong 20 lần ném phi tiêu vào trúng hồng tâm.

::: column.frame.blue.text-center(width=200 parent="padded-thin")

Ta có thể biểu diễn xác suất dưới dạng một phân số chỉ ra bao nhiêu kết quả đã thành công:

`p = blank(5)/20`

::: column.frame.green.text-center(width=200)

Ta có thể chuyển phân số thành một số thập phân giữa 0 và:

_p_ = [[0.25]]

::: column.frame.yellow.text-center(width=200)

Ta cũng có thể chuyển nó thành dạng phần trăm giữa 0% tới 100%:

_p_ = [[25]]%

:::

---

{.fixme} Chúng ta đã biết cách chuyển giữa phân số, số thập phân, và phần trăm  và ta có thể làm tương tự với xác suất. Phần trăm đơn giản có nghĩa là "trên giá trị 100" - vì vậy 30% tương đương với 30 lần trên 100, hoặc `30/100`!

{.fixme} Dưới đây là một vài dự đoán và sự kiện khác. Nối các dự đoán và sự kiện có cùng xác suất:

::: column(width=500)

{.fixme} Một người bạn mời bạn chơi một trò chơi đơn giản: tung đồng xu một vài lần. Nếu nó xuất hiện mặt ngửa, bạn phải đưa anh ấy 1, nếu nó xuất hiện mặt sấp, anh ấy phải trả bạn 1. Điều này có vẻ công bằng - bạn có khả năng thắng bằng với khả năng thua.

{.fixme} Ta biết rằng xác suất một đồng xu xuất hiện mặt ngửa là ½ = 0.5. Tuy nhiên, khi bạn bắt đầu chơi, một số sự kiện bất ngờ xảy ra: đồng xu xuấn hiện mặt ngửa 5 lần liên tiếp! 

::: column(width=200)

{.fixme} Chuyển động của đồng xu theo dõi 5 kết quả cuối cùng, cho ra tất cả là mặt ngửa.  

:::

{.fixme} Ở điểm này, hãy bắt đầu nghi ngờ. Có thể người bạn này đã sử dụng **đồng xu phỉnh** (hay đồng xu thiên vị), đồng xu có một mặt nặng hơn, và vì vậy mặt đó sẽ có khả năng xuất hiện lớn hơn. Nhưng bạn có lẽ cũng thực sự không may mắn! Bạn nghĩ sao?

    p.btn-row
      button.btn.btn-blue Unlucky
      button.btn.btn-green Trick Coin

---
> id: simulation
> goals: flip

{.fixme} Xác suất có thể cho chúng ta biết khả năng xảy ra của một kết quả nhất định, nhưng chúng không thể đoán trước được tương lai. Thậm chí dự báo thời tiết nói rằng chỉ có 5% khả năng mưa, điều này vẫn có thể xảy ra. Và đồng xu của chúng ta cũng không "nhớ" kết quả trước: mọi lần tung có cùng một xác suất mặt ngửa không phụ thuộc vào số lần xuất hiện mặt ngửa trước đó. 

{.fixme} Tuy nhiên, xác suất trở lên hữu ích hơn nếu chúng ta có thể lặp lại cùng một thí nghiệm nhiều lần. Ví dụ, ta tung cùng một đồng xu 100 lần và so sánh tổng số lần mặt ngửa và mặt sấp xuất hiện.Dưới đây là 3 đồng xu khác nhau - bạn có thể tìm ra đồng xu nào là đồng xu thiên vị không?

::: column(width=320)

    x-coin-flip(size="120,200")

    p.btn-row.var
      button.btn.btn-red(@click="flip()") Flip
      button.btn.btn-red(@click="flip(100)") Flip 100 times
      button.btn.btn-red(@click="reset()") Reset

::: column(width=320)

    x-coordinate-system(width=320 height=320 y-axis="0,1.1,0.2" padding="8 8 20 28" axis-names="flips,proportion heads")

Bạn đã thực hiện ${numberOfFlips} lần tung và thấy ${numberOfHeads} mặt ngửa.

:::

---

{.fixme} Trong mô phỏng ở trên, khi ta sử dụng đồng xu đồng chất (màu xanh lam) - có xác suất mặt sấp và mặt ngửa bằng nhau. Như bạn thấy, đồ thị của đồng xu đồng chất từ từ tiến đến 0.5 khi bạn tung chúng ngày càng nhiều lần. Tuy nhiên [[15 ± 5]] lần tung đầu tiên có vẻ hoàn toàn ngẫu nhiên, đối với cả đồng xu đồng chất và đồng xu thiên vị.

{.fixme} Khi bạn thực hiện 10 lần tung, có thể 8 trong số đó xuất hiện mặt ngửa - bạn có thể nghĩ rằng đồng xu đó là đồng xu thiên vị ngay lập tức! Tuy nhiên, còn quá sớm để đưa ra kết luật - nếu bạn khởi tạo lại mô phỏng và tiếp tục tung đồng xu chỉ 10 lần, bạn sẽ thấy hình dáng đồ thị nhấp nhô, và mỗi lần lặp sẽ khác với kết quả trước đó.  

{.fixme} Tuy nhiên, nếu bạn tung đồng xu cho 100 hoặc 1000 lần tung nữa: bạn sẽ thấy tỉ lệ mặt ngửa sẽ luôn luôn gần tới 0.5, trên xác suất thực tế.

{.fixme} Trong lý thuyết xác suất, hiện tượng này được biết tới với cái tên "Luật số lớn" - Tần suất một sự kiện xảy ra trong một thí nghiệm có thể không khớp chính xác với xác suất thực của sự kiện đó, nhưng khi thí nghiệm được lặp lại nhiều lần, tần suất này tiến dần tới xác suất thực. 

{.fixme} Bất cứ khi nào thực hiện một thí nghiệm để tìm xác suất của một sự kiện, điều quan trọng là phải thực hiện đủ số lần - Nếu không, bạn có thể chọn sai đồng xu để đặt cược!


----------------------------------------------------------------------------------------------------


## Tính xác suất

> section: computing
> sectionStatus: dev

TODO


----------------------------------------------------------------------------------------------------


## Cây xác suất

> section: trees
> sectionStatus: dev

TODO


----------------------------------------------------------------------------------------------------


## Sơ đồ Venn

> section: simulations
> sectionStatus: dev

TODO
