# Số phức

## Giới thiệu

> section: introduction
> sectionStatus: dev
> id: timeline
> color: "#6D3BBF"
> level: Advanced


 Mặc dù ngày nay, có rất nhiều điều tồn tại như một lẽ “ hiển nhiên”,  nhưng thực ra những khám phá trong toán học đã mất hàng thế kỉ, trước khi chúng được công nhận như bây giờ. Chúng ta có thể thấy điều này khi đề cập đến một  khái niệm cơ bản nhất trong toán học: các loại số.

Con người đã đếm bằng việc dùng [natural numbers](gloss:natural-numbers) ít nhất 20,000 năm.

Nhiều nhà toán học ở Ai Cập cổ đại đã phát triển phân số và các học trò của Pythagoras ở Hy Lạp cổ đại cũng lần đầu phát hiện ra  [irrational number](gloss:irrational-numbers): `§sqrt(2)`. 
Ban đầu, họ hoảng sợ bởi phát hiện này, và- theo truyền thuyết- họ đã cố che giấu sự tồn tại của nó vì nó không phù hợp với mô hình hoàn hảo của họ. 


    .timeline
      a.timeline-item(style="left: 80px" href="/timeline/ishango"): .timeline-panel
        img(src="images/ishango.jpg")
        p #[strong Natural Numbers]#[br]Prehistory#[br]20,000 BCE
      a.timeline-item(style="left: 230px" href="/timeline/rhind"): .timeline-panel
        img(src="images/egypt.jpg")
        p #[strong Fractions]#[br]Ancient Egypt#[br]2000 BCE
      a.timeline-item(style="left: 380px" href="/timeline/elements"): .timeline-panel
        img(src="images/greece.jpg")
        p #[strong Irrational Numbers]#[br]Ancient Greece#[br]400 BCE
      a.timeline-item(style="left: 530px" href="/timeline/bamboo-strips"): .timeline-panel
        img(src="images/china.jpg")
        p #[strong Negative Numbers]#[br]China#[br]100 BCE
      a.timeline-item(style="left: 680px" href="/timeline/kmer"): .timeline-panel
        img(src="images/khmer.jpg")
        p #[strong Zero]#[br]Khmer#[br]700 CE


Để chứng minh số âm và số 0 còn khó hơn. Ở Hy Lạp cổ đại, các con số được định nghĩa về mặt hình học. Những con số không thể được đo hay biểu thị trực tiếp bằng các đường thẳng, đường cong, hình khối sẽ không được xét đến. 

Trong hơn 1000 năm tiếp theo, các nền văn minh châu Á và Ả Rập khác nhau đã phát triển các hệ thống số bao gồm số 0 và số âm, nhưng khoảng thế kỷ 16, một số nhà toán học người châu Âu đã gọi các phương trình có nghiệm âm là “sai” hoặc “vô lý”.

[Continue](btn:next)

---
> id: cardano

::: column.grow

Đó là khoảng thời gian mà nhà toán học người Ý [Girolamo Cardano](bio:cardano) viết một luận án về lĩnh vực toán học, _Ars magna_ của ông. Đó là một trong những vấn đề mà ông ấy cố gắng giải quyết:
{.quote} “Chia 10 thành hai phần, sao tích của chúng là  40.”

Bây giờ, chúng ta có thể thử _”tìm hai số mà tổng của chúng là 10, tích của chúng là 40”. 
Bạn có thể nghĩ ra hai số thỏa mãn các điều kiện này không?

    x-free-text(placeholder="Câu trả lời của bạn…") X

::: column(width=240)

    // https://www.maa.org/press/periodicals/convergence/mathematical-treasure-cardanos-ars-magna
    x-img(src="images/cardano.jpg" width=240 height=356)

{.caption} Trang tiêu đề Ars Magna của Cardano_, xuất bản năm 1545

:::

---

Dường như không có bất kì giải pháp rõ ràng nào, nhưng Đại số đã được nghiên cứu ra chỉ vài thế kỉ trước khi Cardano ra đời. Hãy thử viết vấn đề dưới dạng phương trình:

::: x-algebra-flow

`x + y = 10 x * y = 40`

*Cho hai số là x và y, từ dữ liệu bài toán, chúng ta có thể viết hai phương trình.
* Chúng ta sẽ sắp xếp lại phương trình một, chuyển x sang vế trái.
* {.new-row} Bây giờ chúng ta có thể thay thế giá trị x vào phương trình hai.
* {.new-row} Sau khi có một nhân thức trong dấu ngoặc, chúng ta sẽ có phương trình bậc hai.

:::

---

{.fixme} Ở giai đoạn này, đa số các nhà toán học đã dừng bước, bởi bạn  [[bạn không thể tính căn bậc hai của số âm| luôn có hai kết quả | cần giải phương trình cho x, không phải y]].

{.fixme} Bạn có thể thấy căn bậc hai của (-15) là một số lạ.  Khi ta tính căn bậc hai của một số dương như căn bậc hai của 9 hay của 5, chúng ta cần tìm một số mà khi bình phương lên sẽ cho kết quả là 9 hay 5. Nhưng không có số nào trên trục số cho kết quả khi bình phương lên bằng -15. Nếu là số dương, nhân số đó với chính nó thì kết quả là số [[dương| âm]]. Nếu là số âm, nhân số đó với chính nó thì kết quả cũng là số  [[dương| âm]]. Như nhà toán học Hindu Bhaskara II đã nói: "Không có căn bậc hai của một số âm, bởi vì một số âm không phải là một bình phương."

{.fixme}  Các quy tắc cơ bản được thiết lập về các con số khiến việc giải phương trình dường như không thể. Nhưng cái khó không chỉ nằm ở vấn đề này. Vấn đề lấy căn bậc hai của một số âm xuất hiện khắp nơi với  Cardano và những người cùng thời với ông.Nó xuất hiện trong các phương trình bậc ba và bậc bốn phức tạp mà họ đang nghiên cứu, cũng như xuất hiện trong các phương trình bậc hai đơn giản như x2 + 1 = 0. Điều khiến Cardano trở nên đặc biệt là thay vì dừng lại và bỏ cuộc, ông ấy đã tìm được một hướng tiếp cận khác.  Ông ấy là người đầu tiên nói: _Có lẽ điều này dường như là không thể. Có thể chúng tôi không nghĩ rằng có những con số để giải quyết vấn đề này, nhưng chúng tôi thực sự đã làm được ._ Nói cách khác, Cardano đã tiến hành giải quyết vấn đề như thể căn bậc hai (-15) tồn tại, bất chấp mọi bằng chứng đi ngược. Cách làm của ông ấy, đã dùng để sử dụng ký hiệu hiện đại, được hiển thị bên dưới:

{.fixme} algebra flow
y-5= ± sqrt(-15)
y=5 ± sqrt(-15)
Tiếp tục,  chúng ta có thể giải phương trình của y
If y=5+sqrt(-15)
x+5+sqrt(-15)=10
x=5-sqrt(-15)
Tiếp đó, chúng ta tìm x, dùng logic hoặc thay thế một trong các giá trị của y.
1.
Tương tự, nếu y=5-sqrt(-15), x=5+sqrt(-15)
Có nghĩa là cả hai số  5+sqrt(-15) và 5-sqrt(-15).
 (5+sqrt(-15))(5-sqrt(-15))
25+5sqrt(-15)-5sqrt(-15)+(sqrt(-15))^2
Để chắc đó là cách làm đúng,  hãy nhân x và y để xem tích của chúng là 40 hay không. Thử dùng cách phân phối mở rộng 25-(sqrt(-15))^2
Chúng ta sẽ đơn giản hóa bằng cách thêm một số bất kì để vế kia bằng 0.
25-(-15)
Để xác định (sqrt(-15))^2, sẽ tính sqrt(-15) . Theo định nghĩa, nếu bình phương sqrt(-15), ta được -15.
40
Sau đó, chúng ta tính được 40, điều này chứng tỏ: sqrt(-15) tồn tại!

---

{.fixme} Điều đầu tiên và quan trọng nhất cần lưu ý về cách làm này là, với một trường hợp ngoại lệ, Cardano  đã xử lí sqrt(-15) giống cách mà ông ấy xử lí các con số khác.Theo cách tính của ông ấy, ông ấy vẫn tuân theo các quy tắc số học đã biết, chẳng hạn như sử dụng cách tính phân phối khi nhân. Chỉ khi xem xét biểu thức (sqrt (-15)) ^ 2, ông ấy đã làm điều mà trước đây chưa từng làm. Tuy nhiên cách tính của ông ấy cũng có nghĩa: nếu sqrt (-15) tồn tại, nó phải là một số mà khi bạn bình phương nó, bạn tính được -15.
---

{.fixme} Nếu cách này vẫn khó hiểu, hãy nhìn tiếp. Bản thân Cardano đã nói rằng việc dùng -15 theo cách này là “tinh vi mà vô dụng”. Tuy nhiên, Cardano và những người cùng thời với ông đã không đã cố gắng để số -15 chúng liên tục xuất hiện trong các phương trình mà họ đang cố gắng giải. Một nhà toán học người Ý khác, Rafael Bombelli, đã sử dụng căn bậc hai của các số âm để giải một số phương trình bậc ba và bậc bốn quan trọng mà không giải được trước đây. Mỗi khi những con số mới kỳ lạ này được sử dụng trong các giải pháp của các vấn đề thực tế, chúng lại trở nên hợp lý hơn một chút.

{.fixme} Tuy nhiên, hầu hết các nhà toán học thời đó vẫn xem chúng là vô nghĩa, không thể hiểu được hoặc không thể thực hiện được. Nhà triết học - toán học Rene Descartes đã tìm thấy chúng quá xa vời, ông gọi chúng là số ảo, và nhận định  tất cả những con số khác là số thực. Mặc dù nhiều nhà toán học trong tương lai sẽ phản đối việc này, nhưng các thuật ngữ cuối cùng vẫn được giữ nguyên và chúng ta vẫn sử dụng chúng cho đến ngày nay.

{.fixme} Trong các số ảo, có một số đặc biệt: -1. Nó giống như số 1 trong hệ thống số thực: mọi số ảo đều là -1 như một[[nhân tố | nhiều]]. Để đơn giản phép tính về các số ảo, Leonhard Euler đã đặt cho -1 một cái tên đặc biệt: i, đơn vị ảo. Trong hầu hết mọi khía cạnh, i như một số thực, với một ngoại lệ (quan trọng): khi nhân i với chính nó, bằng  [[-1]]. Được quy ước sẵn. 

{.fixme} Để xem vai trò đặc biệt của i, hãy thử nghĩ đến số ảo -28. Chúng ta có thể để nguyên hoặc viết lại như sau:

{.fixme} algebra flow
-1 * 28
Tách -28 thành hai phần số ảo và số thực.
i28
Với i=-1
i4 * 7
2i7
Cuối cùng tìm ra số lớn nhất mà bình phương của nó bằng 28.

{.fixme} Cách này dường như đang phức tạp hóa số ảo, nhưng chúng ta thấy,  nó đã đơn giản hóa các số thực và các số ảo. Hãy thử viết vài số ảo bằng i:
{.fixme} -36 = 6i
-48 = 4i3
-14 = i14
-49 = 7i
-50 = 5i2

---

{.fixme} Mặc dù sự tồn tại của số ảo dường như có tính khả thi hơn một chút sau công trình nghiên cứu của Cardano và Bombelli, nhưng phải mất khoảng  200 năm nữa,số ảo mới được các nhà khoa học và toán học trên khắp thế giới chấp nhận hoàn toàn. Điều nên hỏi làm thế nào và tại sao điều này xảy ra. Làm thế nào những con số này, trong suốt lịch sử và thậm chí vào cuối những năm 1700 được coi là không thể, sai và vô lý, cuối cùng lại được coi là có sức thuyết phục và đáng tin cậy.

{.fixme} Để trả lời cho câu hỏi này,  hãy xem xét chính xác điều gì không thể xảy ra với những loại số này. Đến thế kỷ 18, chúng ta không còn chỉ dùng các con số qua các phép đếm, đo lường hoặc hình học, mà thay vào đó chúng ta xếp chúng trên trục có số âm, số 0 và số dương. Ngay cả những con số vô tỉ cũng có vị trí, mặc dù phải thừa nhận rằng khó để xác định vị trí chính xác của nó. Nhưng số ảo đã không được tìm thấy ở đâu cả. Chúng không phải số  dương, cũng không phải số âm, và đương nhiên không phải là số không. Nếu chúng không tồn tại ở bất kỳ đâu trên trục số, thì chúng tồn tại ở đâu?
---

{.fixme} Có 3 người đưa ra các câu trả lời khác một nhà khảo sát người Na Uy tên là Caspar Wessel, một nhân viên kế toán người Paris tên là Jean-Robert Argand, và một trong những nhà toán học vĩ đại nhất mọi thời đại, Carl Friedrich Gauss.Để thấy logic phía  sau cách giải thích các số phức của chúng, và cách tính của phép nhân, hiểu theo phương diện hình học.
{.fixme} Một cách trình bày các phép nhân là thể hiện chúng bằng các vector. Xem ví dụ sau:

{.fixme} Nếu chúng ta nó với một số dương, độ dài vector có thể bị thu nhỏ hoặc kéo dài nhưng  hướng không thay đổi.

{.fixme} Nếu chúng ta nhân nó với một số âm, độ dài vector bị thu nhỏ hoặc kéo dài, hướng vector bị quay ngược 180 độ. Lưu ý, chúng ta cũng có thể coi sự thay đổi theo hướng như một phản xạ, nhưng như chúng ta sẽ thấy, nghĩ về nó như một phép quay sẽ hữu ích hơn khi chúng ta bắt đầu xem xét các số ảo.
{.fixme} Nó giống như ta nhân nó với -1 vậy.

---

{.fixme} Vậy trong hình học, những con số ảo được thể hiện như thế nào,chúng ta biết bình phương i= -1. Để hiểu số ảo là gì, chúng ta hãy như nó như một phép biến đổi. Cách biến đổi nào mà chúng ta có thể áp dụng hai hai lần, bắt đầu từ 1, đến -1?
::: column.grow

{.fixme} Phép trừ -1 hai lần.
Khi nhấp vào: Điều này thực sự mang lại cho chúng ta –1, nhưng “phép trừ” không phải là một phép biến đổi hợp lệ. Chúng ta có thể kéo dài 1 thành 0, nhưng không có cách nào kéo dài 0 để trở thành –1.

{.fixme} Xoay 180 ° hai lần.
Khi nhấp vào: Không phải,  nó không đúng. Xoay hai lần 180 ° sẽ đưa chúng ta trở lại vị trí ban đầu: +1, không phải –1.

{.fixme} Xoay 90 ° hai lần.
Khi nhấp vào: Cách này đúng! Nếu chúng ta xoay số 1 hai lần, một góc 90 °, chúng ta sẽ đến –1. Tuy nhiên, có một vấn đề khác:  chúng ta không còn trên trục số, điều này có nghĩa là gì?
::: column.grow

{.fixme} Có 3 sơ đồ để mọi người chọn nhấp chuột.

:::

{.fixme} Đến nay, các nhà toán học vẫn luôn nghĩ đến trục số một chiều: một trục số từ số âm đến số dương. Và không có con số nào có thể thỏa mãn i² = –1.
{.fixme}Vào khoảng năm 1797, các nhà toán học như Gauss và Argand nhận ra rằng để tìm ra những số ảo mới này, chúng ta phải tìm ra cách nghĩ mới. Họ phát hiện ra rằng các con số tạo thành một mặt phẳng 2 chiều, không chỉ là một đường thẳng.

::: column.grow
{.fixme} Đến đây, bài toán về phép biến hình của chúng ta trở nên dễ dàng: trên một mặt phẳng, chúng ta có thể dễ dàng tìm thấy một phép biến hình thỏa mãn các yêu cầu của chúng ta. Chúng tôi chỉ cần xoay 180 độ hai lần, và chúng tôi sẽ có –1. Điều này có nghĩa là số i nằm cách 0 một khoảng [[trên | dưới | trái | phải]] 0.

{.fixme} Chúng ta có thể coi mặt phẳng số này như một hệ tọa độ: trục hoành chứa tất cả các dấu [[thật| hợp lý | số ảo]], trong khi trục tung chứa tất cả các số [[ảo | thật |]] số phức.



::: column.grow
{.fixme} Sơ đồ mặt phẳng khá phức tạp. Ban đầu, chỉ có trục x được nhìn thấy, cũng như các mũi tên cho hai phép quay 90 °.

{.fixme} Sau khi học sinh hoàn thành [[ở trên]] chỗ trống, một điểm có nhãn “i” sẽ xuất hiện tại (0, 1).

{.fixme} Sau khi học sinh hoàn thành ô trống [[tưởng tượng]], trục y (và tất cả các đường lưới khác) sẽ xuất hiện.

:::

---

{.fixme} Đây là một khám phá tuyệt vời! Thay vì tồn tại dọc theo trục số, các số ảo thể hiện vuông góc với các số thực. Đối với bất kỳ số thực nào, bạn có thể biến nó thành một số ảo bằng cách nhân nó với i. Về mặt trực quan, bằng cách xoay nó [{90 °]] vào cái mà ngày nay chính là  đường số ảo. Tương tự, đối với bất kỳ số ảo nào, bạn có thể nhân nó với i một lần nữa, và nó sẽ xoay [[90 °]] một lần nữa và quay trở lại một vị trí dọc theo trục số thực.

{.fixme} Khi chúng ta kết hợp các trục số thực và ảo, chúng ta sẽ có một mặt phẳng. Ngoài việc xác định vị trí các số hoàn toàn thực và hoàn toàn ảo, chúng ta có thể xác định vị trí các tổ hợp số thực và số ảo, mà chúng ta gọi là số phức, tại các điểm khác nhau trong mặt phẳng. Bạn có thể viết bất kỳ số phức nào dưới dạng a + bi, trong đó a được gọi là phần thực và bi được gọi là phần ảo. Đôi khi, phần thực được viết là Re (z) và phần ảo là Im (z), trong đó z = a + bi. Ví dụ, số phức -2 + 3i có thể được viết dưới dạng Re (z) = [[- 2]] và Im (z) = 3. Đối với mỗi số cho dưới đây, hãy đặt nó vào vị trí thích hợp của nó trên mặt phẳng phức.

    // Interactive here:
    // Students should be given complex numbers and have to plot them at points on the plane.
    // Should include (irrational, purely real, purely imaginary, and complex). Should be at least 1 in each quadrant.

{.fixme} Với ví dụ này, bạn có thể viết ngay cả số thực hoàn toàn (như sqrt (5)) hoặc số thuần túy tưởng tượng (như -3i) dưới dạng số phức. Theo đó, số phức gồm số thực, số ảo và phép tính kết hợp.

---

{.fixme} Thật khó để đánh giá quá cao tầm quan trọng của những khám phá này. Những con số từng có vẻ giống như những ký hiệu trống rỗng, vô nghĩa đã được chứng minh là có cách giải thích cụ thể và có ý nghĩa, vừa phù hợp với vừa mở rộng các quy tắc hình học và số học đã biết. Như Tobias Danzig đã nói một cách đáng nhớ, việc phát hiện ra chiếc máy bay phức tạp “đã thổi hồn cho chúng.  Nó đã lấy hình ảnh tưởng tượng ra khỏi khu phức hợp và thay thế nó bằng một hình ảnh ”. Cũng giống như trước đây chúng ta đã mở rộng khái niệm số để nhường chỗ cho phân số, số thập phân, số vô tỷ, số 0 và số âm, thì giờ đây chúng ta phải mở rộng nó một lần nữa để nhường chỗ cho các số ảo và phức.

{.fixme} Với một chiều số hoàn toàn mới được phát hiện, các thế giới mới đã được mở ra. Số phức được phát minh để giải các phương trình đa thức nhất định, nhưng chúng thực sự có những ứng dụng quan trọng trong nhiều lĩnh vực kỹ thuật và công nghệ:

{.fixme} Kĩ sư điện
Sử dụng số phức khi tính toán dòng điện, điện áp và trường điện tử.
// https://en.wikipedia.org/wiki/Electrical_engineering#/media/File:Silego_clock_generator.JPG

{.fixme} Xử lí các tín hiệu
Số phức thường được sử dụng trong các công nghệ phân tích, chỉnh sửa và thậm chí tạo ra âm thanh, hình ảnh, v.v. thông tin.
// https://entertainment.howstuffworks.com/sound-editing4.htm

{.fixme} Kỹ thuật dân dụng và cơ khí 
Các kỹ sư dân dụng và cơ khí sử dụng các số phức để lập mô hình rung động của các tòa nhà, cầu, đường và thậm chí cả máy bay.

{.fixme} Quantum Physics
// https://phys.org/news/2019-06-quantum-physics-heisenberg-uncertainty.html
Các số phức (và một số những con số khác ) được sử dụng bởi các nhà vật lý để cố gắng giải thích bản chất của các hạt cơ bản tạo nên các khối cấu tạo của vật chất và các lực giữa chúng.

{.fixme} Số phức đã đóng một vai trò trong một số đột phá khoa học quan trọng nhất của thế kỷ 19 và 20. Số phức đã cách mạng hóa toán học. Họ đã mở ra cánh cửa cho các loại hình học mới và mở rộng hiểu biết của chúng ta về không gian, và họ mở đường cho những câu trả lời sáng tạo hơn cho câu hỏi: số là gì và chúng có thể được sử dụng để làm gì?

{.fixme} Theo nhiều cách, ý tưởng về số phức là điểm khởi đầu cho hàng nghìn câu hỏi và khám phá khác. Nhưng quan trọng, đó là phần cuối của một chương trong lịch sử toán học. Như chúng ta sẽ thấy, đối với một số loại phương trình, cuối cùng chúng ta có thể nói rằng chúng ta đã có tất cả các số cần thiết để giải bất kỳ phương trình nào chúng ta muốn. Hơn nữa, chúng ta biết chắc chắn chính xác mỗi phương trình này sẽ có bao nhiêu nghiệm. Theo nghĩa này, thật phù hợp khi cuộc hành trình đi tìm lời giải cho những phương trình này, một cuộc hành trình trải qua rất nhiều khúc quanh, rất nhiều lần bắt đầu, kết thúc bằng những con số mà chúng ta gọi là tưởng tượng. Đó là minh chứng cho vai trò của trí tưởng tượng, trực giác và phỏng đoán trong việc khám phá toán học.

----------------------------------------------------------------------------------------------------


## Số phức học

> section: arithmetic
> sectionStatus: dev

{.fixme} Bây giờ chúng ta biết số phức tồn tại, tự nhiên sẽ đặt câu hỏi: chúng ta có thể làm gì với chúng? Vì chúng là số, ta hi vọng có thể thực hiện các phép toán với  chúng: ít nhất là cộng, trừ, nhân và chia. Nhưng nó dùng như thế nào? Làm thế nào chúng ta có thể hiểu được cộng hai số phức hoặc nhân chúng?

{.fixme} Như chúng ta đã biết từ chương trước, khi Cardano và Bombelli giải các phương trình bằng cách sử dụng số phức, họ đã cố gắng hết sức có thể để xử lý các số phức giống như cách chúng với các số thực. Ngoại lệ duy nhất đối với quy tắc này là thực tế là `i ^ 2 = input (-1) ', nhưng nếu không thì họ giả định rằng các quy tắc số học tương tự mà họ áp dụng cho số thực sẽ áp dụng cho số ảo và số phức.
---

### Cộng và trừ

{.fixme} Chúng ta có thể cộng và trừ các số phức giống như bất kỳ biểu thức đại số nào, bằng cách cộng hoặc trừ riêng phần thực và phần ảo của chúng. Bạn sử dụng “_i_” giống như bất kỳ hằng số hoặc biến toán học nào khác, chẳng hạn như _π_ hoặc _x_. Với ý nghĩ đó, chúng ta hãy thử cộng và trừ một số số phức:

::: column.grow

{.fixme} (3 + 5i) + (2 + 3i)
(2 + 3i) + (2 – 2i)
(3 – 2i) – (4 + 2i)
(2 + 4i) + (1 – 4i)

::: column(width=300)

{.fixme} Hệ tọa độ

:::

---

{.fixme} Bạn có thể nhận thấy rằng số phức khá giống với vectơ 2 chiều. Trên thực tế, ta có thể biểu diễn mỗi số phức dưới dạng một vectơ trong mặt phẳng phức, với thành phần nằm ngang tương ứng với [[phần thực | phần ảo]] và thành phần thẳng đứng tương ứng với [[phần ảo | phần thực]]. Sau đó, chúng ta có thể cộng hoặc trừ các số phức giống như cách chúng ta cộng hoặc trừ các vectơ. Chúng ta có thể nghĩ về việc cộng hoặc trừ các số phức là [[dịch | xoay | phản xạ]], hoặc chuyển dịch, các điểm trong mặt phẳng phức.

---

{.fixme} Khi xem cách chúng ta có thể cộng và trừ các số phức, chúng ta có thể thấy một trong những lý do tại sao số phức lại hữu ích: giống như vectơ, chúng có thể được sử dụng để biểu diễn các đại lượng 2 chiều như chuyển động, vận tốc và lực. Nhưng, lại có câu hỏi: tại sao không chỉ sử dụng vectơ nếu cả hai đều có thể được sử dụng theo những cách tương tự? Điều gì khiến các số phức trở nên hữu ích đặc biệt đối với các nhà toán học, nhà khoa học và kỹ sư khi họ tìm cách hiểu, phân tích?

{.fixme} Câu trả lời nằm ở phép toán cơ bản thứ ba: phép nhân. Không thể nhân hai vectơ - chúng ta đã thấy các phép toán như dấu chấm và tích chéo, nhưng đây không thực sự là "phép nhân". Tuy nhiên, chúng tôi đã nói rằng các số phức phải hoạt động giống như các số thực mà chúng ta đã biết, có nghĩa là chúng ta phải có thể nhân chúng.

---

### Nhân các số phức

{.fixme} Để xem cách chúng ta có thể nhân các số phức theo phương pháp đại số, hãy xem xét một ví dụ đơn giản: (2 + i) (1-i). Chúng ta có thể nhân các số phức giống như cách chúng ta nhân các số thực. Chúng ta có thể sử dụng [[phân phối | liên kết | kết hợp]] và sau đó chúng ta có thể kết hợp tất cả các phần thực và tất cả các phần ảo một cách riêng biệt, lưu ý rằng i ^ 2 = [[- 1]]. Nó có thể trông giống như thế này.

{.fixme} algebra flow
(1+i)(1-i)
1 (1 + i) -i (1 + i)  Có thể phân chia như sau:
1 + i-i-i ^ 2 Nhân phá ngoặc
1 + 0i-i ^ 2 Kết hợp các phần ảo.
1 - (- 1) Thực tế là i ^ 2 = -1 để đơn giản hóa.
2

---
> id: multiplication

{.fixme} Điều này có ý nghĩa về mặt đại số, nhưng nó có ý nghĩa gì về mặt hình học? Hãy thử tưởng tượng một vật thể đơn giản được tạo thành trong mặt phẳng phức tạp. Lấy ví dụ một hình vuông có các đỉnh là bốn điểm sau: 1 + i, 2 + i, 1 + 2i và 2 + 2i. Điều gì sẽ xảy ra nếu chúng ta nhân tất cả các điểm này với một số phức khác, chẳng hạn như 1-i? Chúng ta đã nhân (1 + 2i) (1-i). Bây giờ chúng ta hãy lấy các điểm khác trên hình vuông và nhân chúng với 1-i:
::: column.grow

{.fixme} (3 + 5i) + (2 + 3i)
(2 + 3i) + (2 – 2i)
(3 – 2i) – (4 + 2i)
(2 + 4i) + (1 – 4i)

    // Học sinh phải điền ít nhất một phép nhân vào chỗ trống. Khi họ nhập câu trả lời đúng, điểm sẽ xuất hiện trên sơ đồ. Khi tất cả các điểm xuất hiện, chúng sẽ kết nối với nhau để tạo thành một hình vuông.

::: column(width=300)

    x-geopad(width=300 height=300 x-axis="-1,5,1" y-axis="-2,4,1" padding=5 complex): svg
      circle.blue(name="a" x="point(1,1)")
      circle.blue(name="b" x="point(2,1)")
      circle.blue(name="c" x="point(2,2)")
      circle.blue(name="d" x="point(1,2)")
      path.blue(x="polygon(a,b,c,d)")
      circle.red(name="a1" x="complexProduct(a,q)")
      circle.red(name="b1" x="complexProduct(b,q)")
      circle.red(name="c1" x="complexProduct(c,q)")
      circle.red(name="d1" x="complexProduct(d,q)")
      path.blue(x="polygon(a1,b1,c1,d1)")
      circle.green.move(name="q" x="point(1,-1)")

:::

{.fixme} húng ta hãy nghĩ về những gì đã xảy ra với hình vuông, một cách trực quan, vì mỗi điểm được nhân với 1-i. Chúng ta có thể thấy rằng nó đã được xoay một góc [[45]] theo chiều kim đồng hồ bởi một hệ số của [[sqrt (2)]]. Bạn có thể hiểu thêm về cách hoạt động của phép nhân phức tạp một cách trực quan bằng cách tính với sơ đồ trên. Chọn một hình dạng bạn chọn, sau đó kéo vectơ được hiển thị. Nó sẽ cho bạn biết điều gì sẽ xảy ra khi bạn nhân tất cả các điểm tạo nên hình dạng của bạn với số phức được biểu thị bằng vectơ.
---

{.fixme} Khi bạn dùng sơ đồ, hãy ghi lại những gì bạn thấy và những điều bạn thắc mắc.

    x-free-text

---

{.fixme} Bạn có thể nhận thấy rằng khi bạn xoay một thứ gì đó xung quanh mặt phẳng, hình ảnh cũng sẽ xoay theo nó. Nói cách khác, khi bạn thay đổi góc quay của từng yếu tố, điều đó làm cho tích cũng quay một lượng bằng nhau. Tương tự, nếu bạn kéo căng hoặc thu nhỏ một trong các yếu tố, tích của chúng cũng giãn ra hoặc co lại theo tỷ lệ thuận. Để thấy rõ điều này nhất, chúng ta có thể xem điều gì sẽ xảy ra nếu chúng ta chỉ thay đổi góc hoặc chỉ thay đổi độ lớn của mỗi yếu tố. Hãy thử xem sơ đồ bên dưới để hiểu cách làm của nó.
---
{.fixme} Chúng ta  thấy rằng phép nhân phức tạp gây ra các phép quay và phóng to hình, nhưng hãy tự hỏi: Tại sao nhân mỗi số với 1 - ta lại xoay hình vuông chính xác 45 hoặc mở rộng nó theo hệ số 2? Để hiểu chính xác lý do tại sao những phép biến đổi cụ thể đó lại xảy ra, chúng ta cần xem xét kỹ hơn chính số 1-i và hiểu nó khác một chút.

{.fixme} Cho đến nay chúng ta đã biểu diễn số phức dưới dạng điểm hoặc vectơ trong mặt phẳng phức. Chúng ta đã lưu ý rằng phần thực của mỗi số phức tương ứng với thành phần ngang của vectơ biểu thị nó, và thành phần ảo tương ứng với thành phần dọc. Mặc dù đây là một cách để mô tả số phức, nhưng nó không phải là cách duy nhất.

{.fixme} Chúng ta cũng có thể mô tả chúng theo góc mà chúng tạo ra với trục x dương và khoảng cách của chúng từ điểm gốc. Chúng tôi thường gắn nhãn góc này và gọi nó là đối số của một số phức. Chúng tôi gọi khoảng cách của một số phức từ điểm gốc là r và gọi nó là môđun của số đó. Đôi khi môđun cũng được viết là z, - đó là phiên bản 2 chiều của giá trị tuyệt đối, khoảng cách của các số từ gốc. Để thấy điều này một cách trực quan, hãy xem xét trục tọa độ dưới đây, cho thấy cách bất kỳ điểm nào trong mặt phẳng phức có thể được biểu diễn theo định nghĩa và r.

{.fixme} Muốn thể hiện bất kì số phức nào, a + bi, theo môđun r và đối số của nó, chúng ta có thể sử dụng kiến thức về lượng giác để giải a và b theo r. Chúng ta có thể viết a = [[r cos () | r sin () | r tan ()]], và b = [[r sin () | r cos () | r tan ()]]. Kết hợp tất cả lại với nhau, chúng ta có thể viết toàn bộ số phức dưới dạng:

{.fixme} biểu đồ

{.fixme} Đây được gọi là dạng cực của một số phức. Nếu điều này có vẻ quen thuộc với bạn khi học về tọa độ cực, thì bạn đã đúng khi nhận thấy nhiều điểm tương đồng giữa cách chúng ta biểu diễn tọa độ ở dạng cực và cách chúng ta biểu diễn số phức ở dạng cực.

{.fixme} Để viết1-i ở dạng cực, hãy thể hiện nó trong mặt phẳng phức được hiển thị ở trên, sau đó cố gắng tìm các giá trị của r và tương ứng với điểm đó. Chúng ta có thể tìm r bằng cách sử dụng Định lý Pythagoras, và điều này cho chúng ta r = [[sqrt (2)]]. Trong trường hợp này, chúng ta có thể tìm thấy chỉ bằng cách kiểm tra, nhưng chúng ta cũng có thể sử dụng hàm tiếp tuyến nghịch đảo và thực tế là điểm nằm trong [[Góc phần tư IV | Góc phần tư I | Góc phần tư II | Góc phần tư III]]. Ta có  = [[-45]]. Gộp lại, chúng ta có thể viết 1-i ở dạng cực là [[sqrt 2 (cos (-45) + i * sin (-45))]].

{.fixme} Một khám phá tuyệt vời. Theo một nghĩa nào đó, việc nhân một số phức với 1-i làm cho số đó quay 45 theo chiều kim đồng hồ và mở rộng theo sqrt (2) được tích hợp vào chính số 1-i. Nếu chúng ta nhân với một số phức khác, chúng ta sẽ tạo ra một tổ hợp hoàn toàn khác về phép quay và độ giãn. Các phép biến đổi này có thể được dự đoán trước, và chúng có thể được nhìn thấy rõ ràng hơn nhiều khi chúng ta viết các số phức ở dạng cực.

{.fixme} Thêm phần luyện tập ngắn để học sinh chuyển đổi giữa dạng cực và dạng Cartessian.

---

{.fixme} Ngay cả khi đã hiểu dạng cực, bạn vẫn thắc mắc cách nhân số phức chính xác như thế nào.Chúng ta có thể hiểu và hình dung phép nhân phức theo nhiều cách khác nhau, ba cách trong số đó được hiển thị trong các tab bên dưới. Khi bạn xem,  hãy để ý những gì mà mỗi hình ảnh tiết lộ về các số phức có thể bị thiếu (hoặc ít rõ ràng hơn) so với các số khác.
::: tab
#### x

{.fixme} Cho phép kéo một trong hai vector và hiện thị cách mà nó biến đổi tích.(Các góc được thể hiện rõ ràng và phần “ thêm góc” dễ thấy)
https://www.geogebra.org/m/fRcnfgDW
Hướng dẫn: Kéo số phức và quan sát cách số phức thay đổi, tích thay đổi
::: tab
#### x

{.fixme} Một đoạn video liên kết mỗi vectơ với một tam giác, sau đó yêu cầu học sinh thực hiện thay đổi  tam giác đầu tiên bằng cách căn chỉnh nó với tam giác thứ hai và kéo dài nó sao cho đáy của nó giống với cạnh huyền của tam giác thứ hai.
Ví dụ: https://www.youtube.com/watch?v=-dhHrg-KbJ0&t=667s
Hướng dẫn: Sử dụng các phép biến đổi để xoay một tam giác sao cho đáy của nó hoàn toàn giống với cạnh huyền của các tam giác khác.
::: tab
#### x

{.fixme} Một giao thức cho thấy toàn bộ mặt phẳng phức được xoay và kéo dài khi bạn nhân hai số phức.
Ví dụ: https://www.youtube.com/watch?v=5PcpBw5Hbwo&t=1896s (Start at 24:40 OR 30:40)
Hướng dẫn: Kéo điểm tại 1 vào tọa độ cho một trong các số phức bạn đang nhân. Xem cách mặt phẳng biến đổi, và cụ thể là cách biến đổi số phức khác để ra tích.



:::

---

{.fixme} Mỗi hình ảnh thể hiện một khía cạnh của phép nhân số phức. Đầu tiên, chúng ta thấy rằng chúng ta có thể tìm đối số của sản phẩm bằng cách đơn giản [[cộng | trừ  | nhân  | chia]] đối số của hai yếu tố. Tương tự, chúng ta có thể tìm môđun (r) của tích bằng [[nhân | cộng | trừ  | chia]] moduli của hai yếu tố đó.

{.fixme} Tiếp đó, chúng ta có thể thấy rằng phép nhân với một số phức không chỉ biến đổi số khác khi được nhân; nó còn biến đổi toàn bộ mặt phẳng. Mỗi số phức mô tả một tập hợp các phép quay và độ phóng đại duy nhất xảy ra với bất kỳ điểm nào trong mặt phẳng khi nó được nhân với số phức cụ thể đó.
---

### Chia số phức

{.fixme} Bây giờ chúng ta đã hiểu đầy đủ hơn về phép nhân phức, cuối cùng chúng ta hãy xem xét ý nghĩa của phép chia hai số phức. Lấy ví dụ, thương số sau:

{.fixme} 1-2i3+4i=?

{.fixme}Việc này dường như phức tạp hơn so với phép nhân. Trong phép nhân, chúng ta chỉ sử dụng thuộc tính phân phối như chúng ta làm với các biến hoặc số nguyên. Làm thế nào chúng ta có thể sử dụng những gì chúng ta biết về phép chia để tìm cách thực hiện nó trên các số phức?

{.fixme}Chúng ta biết rằng phép chia là "nghịch đảo" của phép nhân, vì vậy có vẻ hợp lý khi để chia hai số phức, chúng ta [[trừ]] các đối số của chúng, thay vì cộng chúng và [[chia]] modulo của chúng , thay vì nhân chúng lên. Điều này hóa ra đúng, nhưng quá trình chuyển đổi giữa các dạng tọa độ Descartes và tọa độ cực khá phức tạp. Nếu số phức đã ở dạng Descartes thì có một phương pháp đơn giản hơn nhiều.


{.fixme} Bạn có thể nhận thấy trong một số ví dụ ở trên rằng đôi khi nhân hai số phức cho ra một số hoàn toàn thực. Hóa ra, có một cách để biến bất kỳ số phức nào thành một số thực thuần túy bằng phép nhân. Nó dựa trên một khái niệm được gọi là liên hợp phức tạp. Chúng tôi sử dụng ký hiệu z * để biểu diễn liên hợp phức của một số z. Với mọi số phức z = a + bi, liên hợp phức của nó, z * = a - bi. Ví dụ, liên hợp phức của 3 + 4i là [[3-4i]], và liên hợp phức của -2-2i là [[-2 + 2i]].

{.fixme} Để hiểu tại sao liên hợp phức lại hữu ích ở đây, trước tiên chúng ta hãy nghĩ về nó về mặt hình học. Trong sơ đồ bên dưới, hãy kéo hai số phức để chúng liên hợp của nhau. Cố gắng tìm các liên hợp của các số trong mỗi góc phần tư khác nhau và nghĩ về những gì bạn nhận thấy về từng cặp liên hợp và tích của chúng.

{.fixme}Biểu đồ

---

{.fixme} Về mặt hình học, liên hợp phức phản ánh về:  [[trục x | y - trục | dòng y = x]]. Có [[giống | dối]] như là số phức ban đầu, nhưng [[đối | giống]] đối số. Bởi vì các đối số là đối lập nhau, khi hai liên hợp được nhân với nhau, số phức tạo thành có đối số là [[0]] và nằm dọc theo trục số thực. Điều này chứng tỏ rằng nhân một số phức với liên hợp của nó luôn cho kết quả là một số thực.

{.fixme} Ta có thể thắc mắc về phép chia và đặc biệt là với vấn đề ban đầu của ta:: 1-2i3 + 4i. Ở đây sẽ có ích khi coi phép chia là "nghịch đảo" của phép nhân. Lấy một phép chia cơ bản, như 15/5 = 3. Tại sao sự thật này lại đúng? Chúng ta có thể đưa ra nhiều lý do, nhưng tất cả về cơ bản đều đi đến thực tế là 5 nhóm 3 và 3 nhóm 5 đều là 15. Nói cách khác, phép chia được xác định theo mối quan hệ của nó với phép nhân, và tất cả các bài toán chia đều có thể được coi là những câu hỏi về phép nhân. Ví dụ, 15/5 có thể được coi là một câu hỏi: Số nào, khi nhân với 5, cho 15? Tương tự, 1-2i3 + 4i có thể được coi là hỏi: số nào, khi nhân với 3 + 4i, thu được 1-2i?

{.fixme} Bởi vì chia cho số thực dễ hiểu hơn nhiều so với chia cho số phức, một cách  chúng ta có thể sử dụng là lấy biểu thức 1-2i3 + 4i và biến nó thành một biểu thức tương đương trong đó mẫu số là một số thực . Đây là nơi xuất hiện của liên hợp phức: nếu chúng ta nhân mẫu số với liên hợp phức của nó, chúng ta sẽ nhận được một số thực . Để giữ các biểu thức tương đương, chúng ta phải nhân cả tử số và mẫu số với liên hợp của mẫu số. Đối với vấn đề này, chúng sẽ như sau:

{.fixme} algebra flow
Toán
Viết
1-2i3+4i3-4i3-4i
Phương pháp này tương đương với việc nhân phân số ban đầu của chúng ta với [[1]].
(1-2i) (3-4i) (3 + 4i) (3-4i)
Ta nhân tử số và mẫu số riêng với nhau.
[[-5 + 10i25]]
Chúng ta có thể rút gọn tử và mẫu số. Lưu ý rằng mẫu số bây giờ là một số hoàn toàn thực.
-15-25i
Chúng đã được rút gọn . Đây là thương số mà ta cần tìm.
---

{.fixme} Tiếp đó, hãy chắc rằng chúng ta đang chia đúng. Nếu 1-2i3 + 4i = -15-25i, thì (3 + 4i) (- 15-25) = [[1-2i]]. Để khẳng định điều này đúng cần thời gian để xem xét và đánh giá.

{.fixme} Có lẽ bạn sẽ thắc mắc tại sao phương pháp này lại đúng: nó liên quan đến tính chất liên hợp số phức. Để khiến câu chuyện đơn giản hơn,  bất kì số nào cũng có cùng một modun,  ngược lại với các liên hợp của chúng, liên hợp phù hợp với phép chia như hành động quay ngược của phép nhân. Chúng ta thử thực hành thêm về phép chia số phức bằng cách giải cách bài toán sau:
---

{.fixme} Ví dụ
Câu hỏi
Cách giải
2i1+i
1+i
-4i
4i
4-2i-3+2i
-16-2i13
2+2i2-i2
i

---

{.fixme} Nên chúng ta có, giống như với số thực, chúng ta có thể cộng, trừ, nhân và chia bất kỳ cặp số phức nào. Chúng ta có thể làm điều này,hầu như tất cả, bằng cách tuân theo các quy tắc tương tự mà chúng ta sử dụng để hoạt động trên số thực: thuộc tính phân phối, kết hợp và giao hoán. Và chúng ta  đã tìm ra một cách để hiểu các phép toán số phức về mặt hình học; bằng cách coi chúng là các vectơ trong mặt phẳng phức. Ở một khía cạnh nào đó,chúng ta nhận thấy tác dụng số phức còn tốt hơn vector.  Đặc biệt, khi chúng ta viết các số phức ở dạng cực, nó cho chúng ta một cách hiểu đơn giản và dễ hiểu về phép quay và sự giãn nở 2-D.

{.fixme} Sự phức tạp của số phức; ta có thể miêu tả nó được mở rộng, rút gọn và xoay. Trong khóa học về lượng giác, có mối liên hệ giữa chuyển động tròn và sóng.Thường thì khi các nhà khoa học xử lí các vấn đề về sóng dù là sóng vô tuyến từ điện thoại di động, sóng cơ học lượng tử mô tả sự chuyển động của các hạt nguyên tử hay song xung kích như sóng vật lí sau các trận động đất- số phức là số giải pháp để biểu thị các loại sóng này. Trong các chương tới, chúng ta sẽ cùng khám phá thêm các vào việc ứng dụng số phức để giải quyết các vấn đề không chỉ về sóng mà còn những vấn đề khác về khoa học, toán học từ xưa đến nay.
----------------------------------------------------------------------------------------------------


##  Công thức Euler
> section: euler
> sectionStatus: dev

{.fixme} Nhiều nhà khoa học tin rằng cách tốt nhất để tìm hiểu các hạt hạ nguyên tử nhỏ nhất
đến các thiên hà lớn nhất, là thông qua toán học. Phương trình có thể giúp chúng  giải thích các mẫu phức tạp, XXX hoặc hỗn loạn.

{.fixme} Nhưng toán học không chỉ là cách tuyệt vời để giải quyết các ứng dụng trong cuộc sống thực.

{.fixme} Như chúng ta đã thấy, nhiều nhà khoa học hiện đại tin rằng thế giới tự nhiên, từ thiên hà nhỏ nhất đến rộng nhất, chỉ có thể hiểu được bằng toán học. Họ tin rằng toán học không chỉ vô cùng hữu ích; nó cho phép chúng ta nhìn rõ cấu trúc và vẻ đẹp nằm bên dưới bề mặt thế giới của chúng ta. Nó cho phép chúng ta xem xét kỹ lưỡng và hiểu những thứ thoạt nhìn có vẻ khó hiểu: quá rộng lớn, quá nhỏ bé hoặc quá hỗn loạn.
Bạn có nghĩ đến phương trình nào không? Bạn thích định lí Py-ta-go không


In this chapter we will learn about another equation that is not just XXXX, but has also inspired
countless mathematics by its "beauty". In fact, the physicist and Nobel Laureate Richard Feynman
called it “one of of the most remarkable, almost astounding formulas, in all of mathematics”! But
first, we have to think about complex exponents.

Trong chương này, chúng ta sẽ tìm hiểu về các phương trình khác không chỉ XXX,  nhưng nó cũng đã truyền tải được vẻ đẹp vô cùng tận của toán học. Thực tế, nhà vật lý và người đoạt giải Nobel Richard Feynman đãgọi nó là “một trong những công thức đáng kinh ngạc nhất, gần như đáng kinh ngạc, trong tất cả toán học”! Nhưng trước tiên, chúng ta phải bàn về hàm số mũ phức.
---

### Số mũ phức tạp

Trong chương trước, (/ course / complex / arithmetic), ta sử dụng quy tắc của số phức để tìm hiểu ý nghĩa của cộng, nhân hay chia số phức. Nếu chúng ta muốn lũy thừa một số phức, ta có thể nhân nó nhiều lần, ví dụ:
`(2 + 3i) ^ 3 = (2 + 3i) * (2 + 3i) * (2 + 3i)`.

Nhà toán học [Leonard Euler] (chú thích: euler) đã hỏi điều gì sẽ xảy ra nếu thay vào đó chúng ta đặt một số phức vào _hàm mũ_ - ví dụ: `2 ^ (2 + 3i) 'là gì?

{.fixme} Câu hỏi này nhìn qua có vẻ hơi xa vời.Dù sao, chúng ta đã được nói từ khi còn nhỏ rằng lũy thừa đại diện cho phép nhân lặp đi lặp lại. 2 ^ 3 có nghĩa là "nhân 2 với chính nó 3 lần." Làm thế nào chúng ta có thể hiểu "nhân 2 với chính nó i lần" hoặc "nhân 2 với chính nó 1 + 2i lần"? Tuy nhiên, nếu bạn sẽ nhớ, chúng ta đã mở rộng định nghĩa về số mũ trước đây. Yêu cầu bản thân "nhân 2 với chính nó -1 lần" hoặc "nhân 2 với chính nó ½ lần" không thực sự có ý nghĩa, nhưng chúng tôi đã tìm ra một cách để tính toán các biểu thức như 2 ^ (- 1), 2 ^ (½ ), hoặc thậm chí 2 ^ (pi).
---

{.fixme} Tức là chúng ta có thể phát triển ý tưởng về hàm mũ gồm mũ của số ảo và số thực nhưng nó đòi hỏi ta phải thay đổi hướng suy luận khác so với cách tính số mũ thông thường.Để bắt đầu, thay vì sử dụng cơ số 2,5, hoặc thậm chí 10, chúng ta sẽ sử dụng cơ số tự nhiên, e. Khi nghiên cứu các hàm số mũ, chúng ta đã biết rằng hàm e ^ x có thể được xác định theo hai cách:

::: column.frame.red.text-center(width=300 parent="padded-thin")

Tổng của một dãy số:

{.text-center} `e^x = 1 + x + x^2/(2!) + x^3/(3!) + x^4/(4!) + …`

::: column.frame.blue.text-center(width=300)

Giới hạn của biểu thức khi m tiến đến vô cùng:

{.text-center} `§e^x = lim_(x → ∞) (1+x/m)^m`

:::

---
> id: euler-approx

{.fixme} Nếu chúng ta lấy định nghĩa thứ hai của e ^ x, chúng ta có thể xem điều gì sẽ xảy ra nếu thay vì thay  một giá trị thực cho x, ta thay bằng một số ảo. Để đơn giản, chúng ta sẽ bắt đầu bằng cách tạo x = i. Để hình dung điều gì đang xảy ra, chúng ta có thể lấy một vectơ có điểm trên trục hoành (thực) là 1 và điểm trên trục tung  (ảo) là i / m, và dể xem điều gì sẽ xảy ra khi nhân vectơ đó với chính nó m lần. Sử dụng thanh trượt bên dưới để xem điều gì sẽ xảy ra khi giá trị của m ngày càng lớn hơn.

{.fixme} Vector đại diện của biểu thức (1 + x / m) ^ m đã thể hiện phần số thực và số ảo (phụ thuộc vào x và m) cho thấy tích của biểu thức này được thể hiện bằng vector và tam giác.

{.fixme} Thêm một số chi tiết khác vào sơ đồ tam giác (xây dựng theo nhiều bước, giải thích thêm về những gì đang xảy ra, vì vậy học sinh không phải tự suy luận mọi thứ)
    figure
      p.md x = ${round(x,2)} and m = ${m+1}
      x-geopad(width=400 height=400 x-axis="-2,2,1" y-axis="-2,2,1" padding=5 complex): svg
        circle.blue(hidden x="point(1, x/(m+1))" name="p0")
        path.blue(x="segment(point(0,0),p0)")
        path.blue(x=`segment(point(1,0),p0)`)
        for i in [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30]
          circle.blue(hidden x=`m > ${i} ? complexPower(p0,${i+1}): q` name=`p${i}`)
          path.blue(x=`segment(point(0,0),p${i})`)
          path.blue(x=`segment(p${i-1},p${i})`)
        circle.red(x=`complexPower(p0,m)` name=`pm`)
        path.red(x=`segment(point(0,0),pm)`)

      x-slider(:bind="x" steps=5 continuous)
      x-slider(:bind="m" steps=29)

{.fixme} Có một số điều cần lưu ý ở đây. Đầu tiên, khi giá trị của m lớn dần, giá trị của biểu thức tổng thể càng gần một điểm trên vòng tròn đơn vị. Bạn sẽ thắc mắc tại sao biểu thức này lại tiến gần đến điểm cụ thể này. Để biết hãy thử với cả hai thanh trượt lần này. Điều gì xảy ra nếu chúng ta giữ giá trị của m càng lớn càng tốt, nhưng thay đổi giá trị của x? Điều gì xảy ra nếu chúng ta chuyển đến một giá trị khác của x và thay đổi giá trị của m? Ghi lại những gì bạn nhận thấy và thắc mắc vào khung bên dưới.

{.fixme} Ghi chú: Ghi lại những điều thắc mắc

---

{.fixme} Bạn có thể nhận thấy rằng khi giá trị của x thay đổi thành các số ảo khác nhau, giá trị của biểu thức tổng thể sẽ xoay đến các điểm khác nhau dọc theo vòng tròn đơn vị. Bạn cũng có thể nhận thấy một số giá trị thú vị của x. Nếu chưa tìm ra,  hãy lưu ý rằng điểm cuối được lấy nửa chừng khi giá trị của x là [[3,14 hoặc pi]]. Thực tế này dẫn đến một kết luận rất thú vị, rằng:

`e^(i*pi)= input(-1)`

{.fixme} Or, alternatively . . .

`e^(i*pi)+1=0`

{.fixme} Euler, là một trong những phát biểu nổi tiếng nhất trong toán học. Theo Tobias Dantzig, một số người cùng thời với Euler, coi sự đồng nhất này có “ý nghĩa thần bí”, giống như những người theo thuyết Pitago đã xem định lý Pythagoras. Trong các cuộc khảo sát của các nhà toán học và vật lý, danh tính này lặp đi lặp lại như một phương trình đẹp nhất trong toán học. Các nghiên cứu đã chỉ ra rằng khi các nhà toán học nhìn vào công thức này, nó sẽ gợi lại hình ảnh cho bạn như khi bạn nhìn một bức tranh hay nghe một bản nhạc. 

{.fixme} Dường như thật kì lạ khi phát hiện một mảnh ghép lớn và quan trong như vậy trong toán học. Euler không chỉ thú vị mà còn đẹp và sâu sắc. Nếu cảm thấy kì lạ, hãy thử xem xét các mối liên hệ của nó. Nó kết nối một điều không gì cả (0), thống nhất (1), số ảo (i) và vô hạn (e). Nó kết nối năm hằng số quan trọng nhất trong lịch sử toán học; tất cả đều có lịch sử lâu dài, hấp dẫn, và sau những cuộc công nghiệp hóa, con người dần quen với việc làm việc với các con số.
---

{.fixme} Nó đưa ra bằng chứng về định lí Euler là một trường hợp đặc biệt của một mối quan hệ sâu rộng hơn.Như bạn có thể đoán, không phải ngẫu nhiên mà khi x = i, điểm kết thúc quay chính xác một nửa xung quanh hình tròn đơn vị. Như chúng ta đã biết, một góc rađian tương ứng với một chuyển động quay [[180]]. Nếu chúng ta nhìn vào các giá trị khác của x, chúng ta thấy các mối quan hệ tương tự. Nếu bạn để giá trị của x = 2i, điểm sẽ quay [[tất cả| ba phần tư | một nửa | một phần tư]] quãng đường xung quanh vòng tròn. Để quay điểm một phần tư vòng quanh hình tròn, giá trị x cần phải là [[1,57i]], hoặc 2i.Trong tất cả các trường hợp này, hệ số của i cho chúng ta biết góc radian mà điểm đó quay . Đây là lý do tại sao chúng ta thường viết biểu thức không phải là eix, mà là ei.

{.fixme} Mối quan hệ này kết thúc đúng với bất kỳ giá trị nào của x. Nếu chúng ta đặt `x = 2pi / 3 * i` cho x, điểm sẽ quay chính xác 2pi / 3 radian, hoặc [[120]] độ, dọc theo vòng tròn đơn vị. Điều này có nghĩa là `e ^ (2pi * i / 3) =` [[-1 / 2 + sqrt (3) / 2 * i | xxx]]. Nói một cách tổng quát hơn, chúng ta có thể nói rằng với bất kỳ giá trị ảo nào `i * theta`, chúng ta có thể coi` e ^ (i * theta) 'là quay một điểm dọc theo đường tròn đơn vị một góc bằng radian. Chúng ta có thể sử dụng những gì chúng ta biết về lượng giác để viết ý tưởng này trong một câu lệnh nhỏ gọn:

::: .theorem
_Công thức Euler__

{.text-center} `e^(i θ) = blank(cos(θ),sin(θ),tan(θ)) + i*blank(sin(θ),cos(θ),tan(θ))`
:::

---

Bây giờ chúng ta có ba cách riêng biệt để biểu thị số phức: chúng ta đã biết [__cartesian
form __] (gloss: complex-cartesian) `a + bi` và [__polar form __] (gloss: complex-polar)
` r cos (θ) + r  i  sin (θ) `từ chương trước. Công thức của Euler có thể giúp ta chuyển đổi
dạng cực thành dạng mới:
::: column.frame.blue.text-center(width=212 parent="padded-thin")

__Dạng Cartesian__<br>
`§z = a + b i`

::: column.frame.green.text-center(width=212)

__Dạng cực __<br>
`§z = r cos(θ) + r i sin(θ)`

::: column.frame.yellow.text-center(width=212)

__Dạng lũy thừa __<br>
`§z = re^(i θ)`

:::

---

{.fixme} r đặt trước đâu từ (modun), làm thế nào để chuyển từ Cartesian sang lũy thừa, đổi e ^ (a + bi) thành re ^ (bi)

{.fixme} Có phải dạng lũy thừa luôn áp dụng được? Không: như chúng ta đã thấy, để cộng và trừ các số phức, dạng Cartesian cực kỳ đơn giản và trực quan về mặt hình học. Tuy nhiên, đối với phép nhân và chia các số phức, dạng lũy thừa đơn giản hóa mọi thứ đáng kể. Để xem cách này hoạt động như thế nào, hãy coi tích hai số phức `z = 1 + i` và` w = -1 + sqrt (3) * i`. Như chúng ta đã thấy, z có môđun là [[sqrt (2)]] và đối số là [[pi / 4]]. Do đó, chúng ta có thể viết nó ở dạng hàm mũ là z = [[`sqrt (2) * e ^ (i * pi / 4)` | x]]. Tương tự, chúng ta có thể viết w là `w = 2e ^ (i * 2pi / 3)`. Nếu chúng ta muốn nhân `z * w`, chúng ta có thể viết:

{.fixme}
z=`[[sqrt(2)*e^(i*pi/4)]]`
w=`[[2e^(i*2pi/3)]]`
Chúng ta có thể tìm môđun và đối số của cả z và w và sử dụng nó để viết chúng ở dạng hàm mũ
`z*w=sqrt(2)*e^(i*pi/4)*2e^(i*2pi/3)`
`z*w=2sqrt(2)*e^(i*pi/4+i*2pi/3)`
Chúng ta có thể sử dụng quy tắc lũy thừa để nhân cả hai số phức.
`z*w=2sqrt(2)*e^(i(pi/4+2pi/3))`
`z*w=2sqrt(2)*e^(i*11pi/12)`
Chúng ta có thể thừa số i và đơn giản hóa biểu thức của mình bằng cách thêm cả hai số đối

{.fixme} Điều này không chỉ đơn giản hơn việc nhân cả hai số được biểu thị ở dạng cực; nó có lợi thế là xác nhận với cách chúng ta biết phép nhân số phức tạp được tính như thế nào. Nó cho thấy rằng để tìm tích của hai số phức, chúng ta chỉ cần [[cộng | trừ  | nhân  | chia]] đối số của họ và [[nhân | cộng | trừ  | chia]] modun của chúng. Dạng này cũng khá rõ khi chúng ta chia các số phức.
---

::: .box.blue
#### Exercises

{.fixme} Thực hành

:::

---
> id: taylor

### Phát triển công thức Euler

{.fixme} Đầu tiên, công thức này rất hữu ích. Khi các kỹ sư cần sử dụng  các số phức để phân tích điện, họ sẽ sử dụng công thức của Euler. Khi các nhà vật lý cần sử dụng số phức để giúp trả lời những câu hỏi lớn về vũ trụ, họ cũng thường dựa vào công thức của Euler. Nói chung, công thức này thường cung cấp cách đơn giản và thanh lịch nhất để thực hiện các phép tính với số phức.

{.fixme} Có rất nhiều điều chúng ta có thể làm với công thức của Euler một khi chúng ta biết nó, nhưng chúng ta hãy khám phá thêm một chút chính xác tại sao công thức của Euler hoạt động và nó đến từ đâu.

::: column.grow

Bạn có thể nhớ từ giải tích rằng mọi hàm đều có thể được biểu diễn dưới dạng đa thức với vô
số số hạng, các số hạng này càng ngày càng nhỏ - điều này được gọi là [Taylor Series] (gloss:taylor-series).

Đến đây, ta có thể thấy chuỗi [`e^x`](action:exp), [`sin(x)`](action:exp) và [`cos(x)`](action:exp).ưu ý rằng khi bạn di chuyển thanh trượt, giá trị gần đúng đa thức ngày càng gần giá trị thực của hàm.

{.fixme} Để tìm hiểu kĩ hơn về cách tính này, hãy xem chương về chuỗi công suất trong khóa học giải tích:

::: column(width=320)

    x-select.segmented
      div Exponential
      div Sine
      div Cosine
    x-coordinate-system(width=320 height=280 x-axis="-5,5,1" y-axis="-4.5,4.5,1" padding="5" axis-names="x,y")
    x-slider(steps=8)

{.fixme} Sin (x)=1-x^2/2!+x^4/4!-x^6/6! + . . .

:::

{.fixme} Ghi lại rằng chúng ta cũng có thể định nghĩa e ^ (x) là tổng của chuỗi vô hạn sau:

{.fixme} 1+x+x^2/2!+x^3/3!+x^4/4!+ . . .

{.fixme} Đây được gọi là chuỗi lũy thừa cho e ^ (x). (Để xem tóm tắt và giải thích về khái niệm chuỗi lũy thừa, hãy nhấp vào đây.) Thông thường chúng ta nghĩ về những chuỗi lũy thừa này chỉ có đầu vào số thực, nhưng nếu chúng ta chọn một số ảo (i) và thay thế nó vào phương trình tại chỗ của x, điều gì đó rất thú vị sẽ xảy ra:

{.fixme} Math
Commentary
ei=1+i+(i)22!+(i)33!+(i)44!+(i)55!+(i)66!+...

{.fixme} ei=1+i-()22!-i()33!+()44!+i()55!-()66!+...
Chúng ta có thể sử dụng hiểu biết của mình về lũy thừa của i để đơn giản hóa biểu thức này.
ei=(1-()22!+()44!-()66+....) +(i()-i()33!+i()55!+...)
Tập hợp các thuật ngữ về số ảo và số thực
ei=(1-()22!+()44!-()66+....) +i(()-()33!+()55!+...)
Loại i khỏi thuật ngữ ảo
ei=cos()+i*sin()

Lưu ý rằng các chuỗi mới này là chuỗi lũy thừa cho cos () và sin (), tương ứng!

{.fixme} Do đó, chúng ta có thể suy ra công thức của Euler trực tiếp từ chuỗi lũy thừa cho e ^ (x), sin (x) và cos (x)!

---

### Chuyển động tròn

::: column.grow

Trước đây, hàm `e ^ (ax)` luôn biểu thị sự tăng trưởng hoặc phân rã theo cấp số nhân, giống như lãi kép hoặc phân rã phóng xạ. Bây giờ chúng ta biết rằng nếu _a_ là ảo, thì hàm tương tự
cũng có thể biểu diễn __ chuyển động tròn__.

Ví dụ: chúng ta có thể sử dụng `x (t) = e ^ (it)` để biểu thị vị trí của một hành tinh tại một thời điểm _t_, khi nó quay quanh một điểm nằm tại điểm gốc.
::: column(width=320)

{.fixme} Sơ đồ quỹ đạo hành tinh

:::

{.fixme} Như bạn có thể thấy, mọi thứ có thể nhanh chóng vượt khỏi tầm kiểm soát và đây là hướng suy luận về cách tính của tăng trưởng theo cấp số nhân. Chúng ta cũng có thể áp dụng những ý tưởng này cho các hàm khác như x (t) = e ^ (2t) để xem tốc độ lũy thừa thậm chí còn nhanh hơn, hoặc x (t) = e ^ (- 0,5t) để hình dung sự phân rã theo cấp số nhân. Nhưng điều gì sẽ xảy ra nếu chúng ta đưa các số ảo vào các hàm số mũ này? Có lẽ để lấy ví dụ đơn giản nhất, những động lực học này hoạt động như thế nào nếu chúng ta tạo hàm x (t) = e ^ (i * t)?

{.fixme} Khi nghiên cứu giải tích, chúng ta đã học được rằng nếu chúng ta phân biệt chức năng của một vật, chúng ta có  [[vận tốc | chức vụ | gia tốc]], cũng là e ^ (t). Chúng ta có thể sử dụng [[quy tắc chuỗi | quy tắc sản phẩm | quy tắc thương số]] để tìm dẫn xuất của `x (t)` ở trên:

`v(t)=d/dt(e^(it))=`[[`i*e^(it)`|x]]

{.fixme}Về chuyển động của hạt, thực hiện nhân với i có nghĩa là vectơ vận tốc có cùng độ dài với vectơ vị trí, nhưng nó quay 90 ngược chiều kim đồng hồ. Nói cách khác, tại bất kỳ thời điểm nào, vectơ vận tốc sẽ là [[vuông góc | song song]] với vectơ vị trí. Nếu chúng ta tưởng tượng vectơ vị trí ban đầu của mình, vectơ vận tốc của chúng ta sẽ xuất hiện như hình dưới đây:

{.fixme} Bắt đầu từ vectơ của vị trí ban đầu nơi mà các vectơ bật lên ngay khi được nhập vào ô trống, giải thích cách chúng hoạt động.

{.fixme}  Có lẽ chúng ta đã biết về chuyển động của hạt, nhưng để làm rõ hơn, chúng ta hãy để ý đến gia tốc. Để tìm gia tốc, chúng ta có thể lấy đạo hàm của phương trình vận tốc:

`a(t)=d/dt(i*e^(i*t))=-(e^i*t)`

{.fixme} Điều này có nghĩa là vectơ gia tốc cũng sẽ có cùng độ lớn với vectơ vận tốc và vị trí, nhưng nó sẽ hướng về phía [[ngược lại | giống nhau | khác]] hướng như vectơ vị trí ban đầu. Tại bất kỳ thời điểm nào, các vectơ này sẽ giữ nguyên mối quan hệ: vectơ gia tốc hướng vào trong, vectơ vị trí hướng ra ngoài và vectơ vận tốc vuông góc với cả hai.

{.fixme} Sinh viên vật lý sẽ nhận ra những điều kiện này là điều kiện của chuyển động tròn. Nếu bạn chưa học vật lý, hãy tưởng tượng một yo-yo quay trong một vòng tròn hoặc một quả cầu tether quay trên một cực. Điều giữ cho yo-yo hoặc tetherball ở trong một đường tròn là lực hướng tâm kéo vật thể về phía tâm của vòng tròn: đây là lý do tại sao vectơ gia tốc luôn hướng vào trong. Hãy nhấn nút trên sơ đồ trên và xem hạt thực sự chuyển động như thế nào.

{.fixme} Như ta thấy, hạt vạch một đường quanh một vòng tròn bán kính [1]]. Hơn nữa: vì vectơ vận tốc và vectơ vị trí có cùng độ lớn nên hạt luôn chuyển động với tốc độ [[1]] đơn vị / giây. Điều này có nghĩa là khi t = 1, hạt sẽ di chuyển được quãng đường 1 đơn vị xung quanh chu vi của hình tròn. Khi t = pi, hạt sẽ di chuyển một quãng đường bằng đơn vị pi xung quanh vòng tròn, v.v. Điều này giải thích đầy đủ lý do tại sao công thức của Euler có hướng lí luận của nó. Bởi vì tốc độ của hạt là 1 đơn vị / giây, đầu vào, trong ví dụ này đại diện cho thời gian đã trôi qua, cũng đại diện cho khoảng cách mà hạt đi được. Bởi vì đường tròn có bán kính bằng 1, khoảng cách mà hạt di chuyển được bằng góc radian mà hạt quay qua đó, vì vậy chúng ta thực sự có thể coi đầu vào là đại diện cho góc đó, nhân với đơn vị ảo i.
---

### Chuỗi Fourier 

{.fixme} Hãy nói về mối liên hệ giữa chuyển động tròn và sóng.

{.fixme} Được phát triển bởi nhà toán học và vật lý người Pháp Joseph Fourier, và ban đầu được phát minh để giải quyết các vấn đề liên quan đến dòng nhiệt, chuỗi Fourier cũng đã mở rộng phạm vi của nó vào cuộc sống hàng ngày của chúng ta và vào hầu hết mọi lĩnh vực khoa học hiện đại. Ý tưởng chung là chúng ta có thể biểu diễn hầu hết bất kỳ hàm nào dưới dạng tổng của một chuỗi vô hạn các sóng sin. Nó tương tự như ý tưởng về chuỗi lũy thừa - rằng chúng ta có thể biểu thị một số hàm nhất định dưới dạng tổng vô hạn của các hàm khác - nhưng nó lạ hơn, bởi vì, một lần nữa, Fourier tuyên bố rằng một chuỗi vô hạn các sóng sin có thể đại diện cho hầu hết mọi hàm, mà không có gì là phức tạp hay kì lạ cả.

{.fixme} Để bắt đầu xem ý tưởng này có thể được chiếu sáng như thế nào, chưa kể là cực kỳ mạnh mẽ, chúng ta hãy xem một ví dụ. Cũng chính ví dụ đó đã thuyết phục những người theo thuyết Pitago rằng có những mối liên hệ sâu sắc giữa cấu trúc toán học, vẻ đẹp và quy luật tự nhiên: sự hài hòa âm nhạc. Khi bạn nghe bài hát yêu thích của mình trên radio, hoặc nghe một dàn nhạc biểu diễn một bản giao hưởng nổi tiếng, bạn đang nghe thấy một hỗn hợp âm thanh vô cùng phức tạp. Mỗi nốt nhạc được chơi bằng đàn violin, chẳng hạn, được tạo ra từ tần số cơ bản, xác định cao độ thực tế mà bạn nghe được và một loạt những gì được gọi là âm bội hoặc hài âm. Những âm bội này là bội số của tần số cơ bản, và sự kết hợp cụ thể của những âm bội nhẹ nhàng hơn và to hơn mang đến cho các nhạc cụ bạn nghe được âm sắc của chúng; đặc điểm hoặc chất lượng âm thanh của chúng.

---

{.fixme} Chuỗi Fourier và công thức của Euler có liên quan gì đến điều này? Thực sự,  bản chất hợp âm có thể được biểu diễn dưới dạng tổng hợp các tần số cơ bản và âm bội khác nhau dành riêng cho các nốt trong hợp âm, cũng như các nhạc cụ cụ thể đang được chơi. Các tần số và âm bội cơ bản này có thể được biểu diễn dưới dạng sóng sin, với một tần số cụ thể (chu kỳ trên giây) và cường độ (biên độ).Lấy 1 ví dụ đơn giản về cách thức hoạt động của điều này, hãy chơi một nốt trên đàn piano bên dưới. Lưu ý cả tần số cơ bản (sóng hình sin biên độ cao nhất) và các âm bội khác nhau tạo nên một nốt nhạc này.

{.fixme} Tương tác: Một cây đàn piano (ít nhất một quãng tám) mà học sinh có thể nhấp vào để chơi các nốt hoặc hợp âm.
Biến đổi Fourier tương ứng của đàn piano, cả tổng thể và chuỗi các tần số và âm bội riêng lẻ quan trọng nhất.
{.fixme} Bây giờ chơi một hợp âm. Ví dụ, chơi các nốt C, E và G cùng một lúc. Đây là một hợp âm C cơ bản. Lưu ý rằng hiện tại chúng ta có nhiều tần số cơ bản cũng như âm bội, và cách sóng đại diện cho toàn bộ hợp âm trở nên phức tạp hơn nhiều. Hợp âm mở đầu của "A Hard Day's Night" thậm chí còn phức tạp hơn; liên quan đến nhiều nốt và 4 nhạc cụ khác nhau. Nhưng nguyên tắc của chúng  giống nhau: Chúng ta có thể chia biểu đồ phức tạp, thất thường biểu thị hợp âm này thành các sóng hình sin đơn giản đại diện cho các tần số cơ bản và âm bội đang được chơi, và chúng ta có thể sử dụng thông tin này để tìm ra nhạc cụ đã chơi nốt nào. Để biết thêm về cách điều này hoạt động về mặt toán học và cách công thức của Euler phù hợp với tất cả những điều này, hãy xem video sau đây của người đam mê toán học nổi tiếng Grant Sanderson:


    figure.video-wrap
      iframe(src="https://www.youtube-nocookie.com/embed/spUNpyF58BY" frameborder=0 allow="autoplay; encrypted-media; picture-in-picture" allowfullscreen)



---

### Nhiều ứng dụng hơn

Sóng ở khắp mọi nơi xung quanh chúng ta: bạn tương tác với [sóng điện từ] (gloss:electromagnetism)
bất cứ khi nào bạn nghe đài, gọi điện thoại, kết nối với WiFi hoặc sử dụng lò vi sóng. Bạn có thể nhìn thấy các sóng cơ học khi ném một viên sỏi vào nước hoặc cảm thấy chấn động của một trận động đất.
Ánh sáng truyền đi dưới dạng sóng, và thậm chí các định luật cơ bản nhất của tự nhiên, như [lực hấp dẫn] (gloss:gravity)
hoặc các hạt hạ nguyên tử, có thể được mô tả bằng cách sử dụng sóng.

Công thức của Euler là một cách đơn giản, ngắn gọn để mô tả sóng và chuyển động tròn bằng toán học - và đó là lý do tại sao không có gì ngạc nhiên khi nó có những ứng dụng quan trọng ở khắp mọi nơi trong khoa học, công nghệ và kỹ thuật.

---

::: column(width=240)

{.fixme} Ảnh

::: column.grow
Một trong những ứng dụng này là __ tinh thể học tia X__, một kỹ thuật được sử dụng để xem cấu trúc của các phân tử cực nhỏ, quá nhỏ ngay cả đối với kính hiển vi.

{.fixme} 
Một chùm tia X chiếu vào 1 phân tử ở dạng tinh thể.Khi các tia X tương tác với phân tử, chúng sẽ phân tán và tạo thành một kiểu đốm ở phía bên kia. Mẫu này cung cấp thông tin về biên độ và tần số của các electron trong phân tử. Nói cách khác, dạng đốm đóng vai trò là phép biến đổi Fourier của riêng nó, cung cấp cho chúng ta thông tin về cấu trúc phân tử của tinh thể mà nó tương tác. Sử dụng một số công trình thám tử thông minh, cùng với toán học của phép biến đổi Fourier, chúng ta có thể suy ra cấu trúc phân tử 3D từ mô hình của các đốm.


https://en.wikipedia.org/wiki/Photo_51
https://en.wikipedia.org/wiki/DNA

{.fixme} Phương pháp này đã được sử dụng để khám phá cấu trúc của nhiều phân tử quan trọng. Nổi tiếng nhất, tinh thể học tia x đã tạo ra Ảnh 51. Bức ảnh này ban đầu được chụp bởi một nghiên cứu sinh dưới sự giám sát của nhà hóa học người Anh Rosalind Franklin, và sau đó được trao cho Watson và Crick, những người đã sử dụng nó làm bằng chứng quan trọng để hỗ trợ tuyên bố của họ rằng DNA có cấu trúc chuỗi xoắn kép.


:::

---

{.fixme} Tinh thể học tia X cũng cho phép các nhà khoa học nghiên cứu cấu trúc của các
phân tử khác , như protein phức tạp và thậm chí một số loại virus. Và nhiều kỹ thuật hình ảnh y tế khác, chẳng hạn như __ Chụp ảnh cộng hưởng từ (MRI) __ sử dụng nguyên tắc tương tự: Chúng thăm dò các cấu trúc hóa học hoặc vật lý mà chúng ta không thể nhìn thấy bằng cách sử dụng bức xạ, sau đó sử dụng phép biến đổi Fourier để giải thích và tái tạo lại các cấu trúc này từ dữ liệu chúng ta nhận được .

---

{.fixme} Công thức của Euler có thể giúp chúng ta mô tả dòng điện xoay chiều, cho phép các kỹ sư tạo ra mạng lưới điện cung cấp năng lượng cho ngôi nhà và thành phố của chúng ta. Các kỹ sư kết cấu sử dụng cả công thức của Euler để phân tích độ rung của các tòa nhà cao tầng, cầu và đường, nhằm giữ an toàn cho chúng ta khi chúng ta
bay trên máy bay hoặc khi động đất xảy ra. Và công thức của Euler thậm chí còn được sử dụng để giải phương trình __Schrodinger__, trở thành xương sống của vật lý lượng tử.


{.fixme} Thật khó để liệt kê tất cả những cách khác nhau mà số phức đã ảnh hưởng đến cuộc sống của chúng ta, và tất cả những đột phá về khoa học, công nghệ và toán học mà chúng đã tạo ra.

{.fixme} Feynman gọi công thức của Euler là “đáng kinh ngạc” và “đáng chú ý” không chỉ vì nó hữu ích - mà vì nó hay, sâu sắc .Giống như định lý Pitago, nó thể hiện một mối liên hệ đơn giản và ngắn gọn nhưng hoàn toàn mang tính đột phá giữa các lĩnh vực toán học khác nhau: giữa đại số và hình học, giữa chuyển động tròn, dao động và biến đổi theo cấp số nhân. Cũng giống như những người theo thuyết Pitago đã tìm thấy một ý nghĩa gần như thần bí trong các tỷ lệ đơn giản giúp họ khám phá ra cấu trúc của một hợp âm âm nhạc hoặc sự quay của các hành tinh, các nhà khoa học và toán học hiện đại cũng tìm thấy cảm giác bí ẩn, hài hòa và vẻ đẹp tương tự trong công thức của Euler.Mặc dù chúng ta có thể đã đưa ra đạt được những thành tựu vượt xa phạm vi trước đó của Pitago rằng “tất cả đều là số”, công thức của Euler và phép biến đổi Fourier nhắc nhở chúng ta về sức mạnh của những con số và toán học để khám phá ra cấu trúc tiềm ẩn và vẻ đẹp tiềm ẩn xung quanh chúng ta: trong âm nhạc, trong thiên nhiên, và trên thế giới nói chung.




----------------------------------------------------------------------------------------------------


## Giải các đa thức

> section: polynomials
> sectionStatus: dev

* Biết rằng các nghiệm nguyên không thực của phương trình đa thức với hệ số thực xảy ra
trong các cặp liên hợp.
* Tính toán các nghiệm phức của phương trình bậc hai bằng cách hoàn thành bình phương.
* So sánh đối chiếu phương trình bậc hai với nghiệm phức và không thực.
* Chứng minh rằng một phương trình bậc hai sẽ có nghiệm thực hoặc không thực bằng cách sử dụng suy luận đồ họa.
* Giải bất phương trình bậc hai với hệ số thực.
* Giải phương trình bậc ba hoặc bậc hai với hệ số thực (cung cấp đủ thông tin để suy ra ít nhất một căn đối với lập phương hoặc ít nhất một căn phức hoặc nhân tử bậc hai đối với tứ phân).


----------------------------------------------------------------------------------------------------


## Định lí De Moivrevà  Roots of Unity

> section: de-moivre
> sectionStatus: dev

* Tìm n gốc thứ n phân biệt của re ^ (iθ)
* Biết rằng chúng tạo thành các đỉnh của một ngọn thông thường trong biểu đồ Argand.
* Sử dụng các nghiệm nguyên phức hợp để giải các bài toán hình học

---
> id: roots

Các trục và hệ tọa độ

    figure
      x-geopad(width=600 height=400 x-axis="-6,6,1" y-axis="-4,4,1" complex padding=5): svg
        circle.move.green(name="p" cx=2 cy=2)
        path.green(x="segment(point(0,0),p)")
        circle.red(x="complexRoot(p,3,0)" name="r0")
        circle.red(x="complexRoot(p,3,1)" name="r1")
        circle.red(x="complexRoot(p,3,2)" name="r2")
        path.red(x="polygon(r0,r1,r2)")

