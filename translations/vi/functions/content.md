# Các hàm

## Quan hệ và Các hàm

> section: relations
> sectionStatus: dev
> id: sorting-hat
> color: "#FD8C00"
> level: Intermediate
> next: sequences

::: column.grow

Chào mừng đến với Trường học thần kỳ Hoctagon! Bạn đã đi tàu từ ga King’s Cross ở Luân Đôn,
một chiếc thuyền băng qua hồ lớn phía trước lâu đài, và vừa đến đại sảnh với tất cả
những học sinh khác.

Nhưng trước khi bữa tiệc chào mừng có thể bắt đầu, Chiếc mũ phân loại phải chỉ định tất cả học sinh mới vào một nhà.
Hãy thử sắp xếp từng học sinh này vào một trong bốn ngôi nhà:

::: column(width=300)

    // EDITORIAL ONLY
    // https://depositphotos.com/139592200/stock-photo-the-hogwarts-express-train.html

{.fixme} Image

:::

    x-relation
      .item(slot="domain" name="a") **Current User**
      .item(slot="domain" name="b") Phineas Lynch
      .item(slot="domain" name="c") Sturgis Switch
      .item(slot="domain" name="d") Dilys Derwent
      .item(slot="domain" name="e") Demelza Zabini
      .item(slot="domain" name="f") Bogod Clearwater
      .item(slot="range") Lionpaw
      .item(slot="range") Eaglewing
      .item(slot="range") Badgerclaw
      .item(slot="range") Serpentfang

---

Sau bữa tối, tất cả học sinh trở về phòng sinh hoạt chung của ngôi nhà mới. Mọi người ổn định về ký túc xá của mình và trở về phòng sinh hoạt chung để gặp những người bạn cùng nhà mới của họ. Chủ nhiệm nhà sử dụng thời gian này để chuyển danh sách lớp. Giống như trước, hãy kết nối từng học sinh với các lớp khác nhau:

    x-relation
      .item(slot="domain" name="a") **Current User**
      .item(slot="domain" name="b") Phineas Lynch
      .item(slot="domain" name="c") Sturgis Switch
      .item(slot="domain" name="d") Dilys Derwent
      .item(slot="domain" name="e") Demelza Zabini
      .item(slot="domain" name="f") Bogod Clearwater
      .item(slot="range") Potions
      .item(slot="range") Transfiguration
      .item(slot="range") Magical Creatures
      .item(slot="range") Broomstick Flying
      .item(slot="range") Charms

---

Ngày hôm sau, bạn và một số bạn cùng lớp đến sớm để học bài đầu tiên. Cuộc trò chuyện nhanh chóng chuyển sang về những cây đũa phép mới của bạn. Bạn trao đổi những câu chuyện về cách những cây đũa phép đã chọn bạn. Kết nối mỗi cây đũa phép này với một học sinh.

    x-relation
      .item(slot="domain")
        img(src="images/wand-1.png" width=200 height=30)
        span.caption Birch, phoenix feather, 5 3/4
      .item(slot="domain")
        img(src="images/wand-2.png" width=200 height=30)
        span.caption Oak,dragon heartstring, 6 9/16
      .item(slot="domain")
        img(src="images/wand-3.png" width=200 height=30)
        span.caption Oak, unicorn hair, 6 5/8
      .item(slot="domain")
        img(src="images/wand-4.png" width=200 height=30)
        span.caption Yew, kneazle whicker, 4 9/16
      .item(slot="domain")
        img(src="images/wand-5.png" width=200 height=30)
        span.caption Yew, unicorn hair, 5 7/8
      .item(slot="range" name="a") **Current User**
      .item(slot="range" name="b") Phineas Lynch
      .item(slot="range" name="c") Sturgis Switch
      .item(slot="range" name="d") Dilys Derwent
      .item(slot="range" name="e") Demelza Zabini

---

Trong tất cả các ví dụ trên, có hai nhóm đồ vật (như sinh viên, nhà ở hoặc cây đũa phép) mà bạn phải kết nối với nhau.

Trong toán học, ta gọi các nhóm như thế này [__tập hợp__](gloss:set). Ta có thể viết ra các phần tử của một tập hợp trong "dấu ngoặc nhọn", ví dụ: {Lionpaw, Eaglewing, Badgerclaw, Serpentfang}. Thứ tự của các phần tử trong một tập hợp không quan trọng, nhưng mỗi phần tử chỉ có thể xuất hiện một lần trong một tập.

Một kết nối giữa hai tập hợp được gọi là [__quan hệ__](gloss:relation). Các quan hệ có thể có các dạng khác nhau, và bạn có thể đã nhận thấy một số điểm tương đồng và khác biệt giữa các ví dụ trên.

| Các nhà | Các lớp | Các đũa phép |
| ------ | ------- | ----- |
|[[Nhiều]] học sinh có thể ở trong [[một]] nhà. Quan hệ này được gọi là Quan hệ nhiều-một.| [[Nhiều học sinh]] có thể ở trong [[nhiều lớp]]. Một quan hệ như thế được gọi là quan hệ nhiều-nhiều. | [[Một đũa phép]] chọn [[một học sinh]]. Một quan hệ như thế được gọi là quan hệ một-một. |

---

Có nhiều cách để chúng ta có thể biểu diễn quan hệ giống nhau giữa các tập hợp. Cho đến giờ, ta đã và đang sử dụng sơ đồ ánh xạ. Ta cũng có thể biểu diễn cùng một thông tin bằng cách sử dụng một bảng. Sơ đồ ánh xạ của Chiếc mũ phân loại được hiển thị trong bảng dưới đây.

TODO Interactive here

Ta cũng có thể sử dụng các cặp có thứ tự để thể hiện quan hệ này. Giá trị đầu tiên trong một cặp có thứ tự là từ tập hợp đầu vào (tập nguồn). Giá trị thứ hai là từ tập hợp đầu ra (tập đích).

({{Current User Name}}, Lionpaw) (Phineas Lynch, Lionpaw) (Sturgis Switch, Eaglewing) (Dilys Derwent, Badgerclaw) (Demelza Zabini, Serpentfang) (Bogod Clearwater, Serpentfang)

---

### Tập xác định và Tập giá trị

Bạn có thể coi quan hệ như một phép toán: bạn chuyển vào một phần tử từ __tập hợp__ ở bên trái và bạn nhận các phần tử từ tập hợp ở bên phải làm giá trị xuất ra. Hãy xét quan hệ này:

| Tập nguồn | | Tập đích |
| :---: | | :----: |
| 14 |  | chẵn |
| 3 |  | lẻ |
| 11 |  | lẻ |
| 6 |  | chẵn |
| -6 |  | chẵn |

Tập nguồn trong ví dụ đầu tiên là {14, 3, 11, 6, -6}. Lưu ý rằng những con số này không nhất thiết phải theo thứ tự từ nhỏ đến lớn. Tập đích cho ví dụ này là {chẵn, lẻ}. Chú ý các phần tử chẵn và lẻ không được lặp lại.

Các tập nguồn và tập đích này có tên gọi đặc biệt. Tập hợp toàn bộ tất cả các phần tử đầu vào được gọi là [__tập xác định__](gloss:domain). Tương tự,  [__tập giá trị__](gloss:range) là tập hợp tất cả các giá trị đầu ra có thể có. Ta sử dụng cùng một ký hiệu dấu ngoặc nhọn trong ví dụ trên. Đôi khi, chúng ta sử dụng các bất đẳng thức để thể hiện tập xác định và tập giá trị. Ta sẽ xem xét điều này chi tiết hơn sau. Sử dụng các tab để trả lời các câu hỏi bên dưới.

TODO Interactive here

---

### Hệ trục tọa độ

Chúng ta sử dụng các sơ đồ ánh xạ, các cặp tọa độ và bảng để biểu diễn các quan hệ. Đồ thị là một cách khác để hình dung các quan hệ. Ta có thể lưu ý một vài điều thú vị khi xem xét các quan hệ trên [__mặt phẳng tọa độ__](gloss:coordinate-system).

Hãy vẽ quan hệ {(0,0), (1,4), (-5,3), (-2,-1), (4, -3)} trên mặt phẳng tọa độ. Hai điểm đã cho trên đồ thị.

TODO Interactive here

TODO Tutor prompts here

Hãy xem xét đồ thị của các quan hệ mà ta đã nói đến. Chú ý cách sơ đồ ánh xạ liên hệ với đồ thị. Các trục trong mặt phẳng tọa độ bên dưới có tên khác với x và y, các biến mà chúng ta đã thấy trước đây. Ví dụ, đồ thị này bao gồm trục-tên và trục-nhà.

TODO Interactive here

Sử dụng hệ tọa độ, cũng rất dễ dàng để kiểm tra xem một quan hệ là quan hệ nhiều-nhiều hay quan hệ một-nhiều. Đồ thị quan hệ nhiều-một và nhiều-nhiều [[có ít nhất một | không có]] các điểm có cùng giá trị x. Đồ thị một-một và một-nhiều [[không có | có ít nhất một]] điểm có cùng giá trị x.

Đi qua hệ tọa độ từ trái sang phải và kiểm tra xem có hai điểm nào được nối với nhau bằng một đường thẳng đứng không. Điều này có nghĩa là chúng có cùng một giá trị x, vì vậy mối quan hệ không phải là nhiều-một. Đây được gọi là cách kiểm tra theo đường thẳng đứng. Các đồ thị có cùng giá trị x dường như chúng có thể một đường thẳng đứng nối [[hai hay nhiều | không có]] của nó.

TODO Interactive here

---

### Hàm số

Trong toán học, các quan hệ một-một hoặc nhiều-một đặc biệt quan trọng, và ta sẽ gặp nhiều ví dụ khác trong các chương sau. Đó là lý do tại sao chúng có một cái tên đặc biệt: Hàm số. Một [__function__](gloss:function) là một quy tắc gán mỗi phần tử trong tập nguồn với [[chính xác một | ít nhất một]] phần tử tập đích.
---

Hãy quay trở lại mối quan hệ Hoctagon. Sử dụng định nghĩa của một hàm, chọn các quan hệ là các hàm.

TODO Interactive here

---

Ta có thể coi hàm như một cỗ máy. Hãy xét xem máy mũ phân loại thực hiện như thế nào.

TODO Interactive here

---

Mọi hàm cần phải có tên. Ký hiệu hàm cho chúng ta biết tên của hàm đó, giá trị đầu vào và quy tắc xác định giá trị đầu ra.

Cho một hàm, ta sẽ gọi là f, đặt các chiếc mũ vào tập nguồn.

IMAGE

Nếu ta được cho, f(🙊),ta biết tập nguồn là INSERT IMAGE. Tương tự, nếu ta biết f(x)= INSERT IMAGE , ta biết x là 🦊.

| Tên hàm | | Tập nguồn | = | Tập đích |
| :-----------: | |:---------: | :---:| :-------: |
|      _f_      | |      _(x)_ | = | giá trị hoặc biểu thức|

Hãy sử dụng mẫu này để mô tả hàm phân loại mũ.

sortinghat(first year name) = house name

Từ ký hiệu hàm ở trên, ta biết rằng đặt mũ phân loại vào năm đầu tiên cho biết năm đầu tiên được sắp xếp vào ngôi nhà nào. Mô hình này rất quan trọng để ghi nhớ. Kí hiệu và các biểu thức đối lập với tên hàm đôi khi có thể khiến chúng ta mất tập trung nhớ cách đọc kí hiệu hàm.

sortinghat({current user name}= [[{current user house} | not {current user house}1 | not {current user house}2  |not {current user house}3 ]]

sortinghat(Sturgis Switch) = [[{Sturgis Switch’s house} | not {Sturgis Switch’s house}1  | not {Sturgis Switch’s house}2 | not {Sturgis Switch’s house}3]]

Bây giờ chúng ta hãy thử một số ví dụ với các biểu thức đại số.
Cho x=2 và f(x)=50-3x, tính f(2). [[44]]

TODO optional text for incorrect answers

Dưới đây là một số cỗ máy hàm. Bạn có thể tìm ra quy tắc trong từng trường hợp không?

TODO Interactive here

Cũng giống như trước đây, chúng ta có thể hình dung các hàm trong một hệ tọa độ. Giá trị trục hoành x đại diện cho tập nguồn và giá trị trục tung y đại diện cho tập đích.

TODO Interactive here

Tập xác định và tập giá trị có thể gồm nhiều phần tử hơn những phần tử được liệt kê. Chúng ta phải suy nghĩ về điều gì sẽ tạo nên một danh sách đầy đủ tất cả các phần tử tập nguồn hoặc phần tử tập đích. Với mỗi ví dụ sau, hãy kéo các số có thể vào nhóm “Tập nguồn” hoặc “Tập đích”.

TODO Interactive here

Nhìn vào đồ thị của các hàm. Xác định các phần tử đầu vào nào có nghĩa và lý do tại sao.

::: column(width=300)

TODO coordinate plane

::: column.grow

Đồ thị chỉ xuất hiện trong góc phần tư thứ [[1st]]. Chúng ta có thể thấy rằng tất cả các giá trị đầu ra phải [[dương | âm | bằng không]].

::: column(width=300)

TODO coordinate plane

::: column.grow

Giá trị y nhỏ nhất trên biểu đồ là khoảng [[1250+-50 tùy thuộc vào tỉ lệ]]. Hãy nghĩ về cách chúng ta sẽ tìm ra giá trị y lớn nhất. Nếu mọi học sinh tại trường mua một vé, ta sẽ nhân [[số học sinh đăng ký]] với $25 để tính giá trị y lớn nhất có thể.

:::


--------------------------------------------------------------------------------


## Đồ thị và Dịch chuyển hàm số 

> section: graphing
> sectionStatus: dev

    // NOTE
    // Local server trouble - not able to visualize design decisions. Followed the conventions I could find in terms of notes, fixme tags, image/ graph mock-ups, and targets. Targets do not have objects set, but the syntax should indicate where the target is intended to go. Worked last to first. Some of these conventions change as I learned more from other code.

    // EDITORIAL USE ONLY
    // [mock-up title image](https://drive.google.com/file/d/1P7d1Tfb7NwYLR5FM-e0zMbj5JKYgpJMJ/view?usp=sharing)

Thế vận hội Olympic có đầy những kỳ tích thể thao đáng kinh ngạc. Nó cũng chứa đầy dữ liệu thú vị. Đồ thị giúp chúng ta hình dung dữ liệu đó. Bây giờ, chúng ta sẽ xem xét các cuộc thi Olympic và phân tích đồ thị của chúng để biết thêm thông tin thú vị. Hãy đến đấu trường thể dục dụng cụ!

::: column(width=240)

![Ri](https://media.gettyimages.com/photos/derval-orourke-of-ireland-sally-pearson-of-australia-and-brigitte-of-picture-id123295200)

::: column.grow

Ri Se-gwang của Cộng hòa Nhân dân Triều Tiên sắp sửa nhảy. Anh đã giành được huy chương vàng cho môn nhảy cầu trong Thế vận hội Olympic mùa hè 2016. Cùng xem nào.

:::

    // NOTES
    // [citation](https://en.wikipedia.org/wiki/Gymnastics_at_the_2016_Summer_Olympics_%E2%80%93_Men%27s_vault)
    // Student presses play on a [video](https://www.youtube.com/watch?v=85v0Un19A94) (0:00-0:18) of Ri’s vault. Simultaneously, a distance-time graph populates in a card to the right of the animation.

[vault mock-up](https://www.desmos.com/calculator/td3fynck7q)

Có một số điều đang diễn ra ở đây. Di chuyển video qua lại để xem cách đồ thị sắp xếp theo chuyển động.

Đầu tiên, ta cần hiểu các trục đại diện cho điều gì. Trục x trong đồ thị này là khoảng cách ngang mà Ri nhảy. Nó được đo bằng đơn vị cm. Trục y là khoảng cách thẳng đứng mà Ri di chuyển được. Điều này cung cấp cho chúng tôi thông tin về vị trí của Ri giống như các quân cờ trên bàn cờ.

Đồ thị không bao gồm bất kỳ thông tin nào về thời gian. Ví dụ, chúng ta không thể nói _khi nào_ Ri hạ xuống hố. Một số đồ thị của các cuộc đấu sau này sẽ bao gồm thời gian dọc theo trục hoành.

Trên biểu đồ này, chúng ta thấy hố ở ([[3565+-5]], [[135+-5]])), có nghĩa là Ri đã di chuyển khoảng 3.5 mét trên đường chạy của mình. Điểm bắt đầu trên đường băng là ở [__gốc tọa độ__](gloss:coordinate-system-origin). Ri hạ xuống tại (3910, 30), có nghĩa là hố cao khoảng [[30]] cm

---

Hãy xây dựng một số trực quan về đồ thị của các cuộc đấu khác nhau như thế nào. Nối đồ thị với cuộc đấu. Hãy chắc chắn chú ý đến những gì các trục đại diện.

    // NOTE
    // Organized as a table in the Google Doc, so I (Dani) put it in a table here. The idea is to make it cards.
    // Match graphs to sports of time functions

    // I'm having a tough time getting the shape to work with the scale. It might be easier to get the shape then layer the axes over - make this a static image. [sketch](https://drive.google.com/file/d/1uh9_0Abfs0lYIa8q6uZxUYFoRnHeLKtr/view?usp=sharing) disegard notes dotted graph

| Cú nhảy ba lần | Cú nhảy tự do 50 M | Nhảy vượt rào 100 M | Nhảy hố | Lặn | Trượt tuyết |
| ----------- | -------------- | ------------- | ----- | ------ | ------ |
| [Graph](https://www.desmos.com/calculator/qxfugm6xpi) | [Graph](https://www.desmos.com/calculator/z07xkap2bl) | [Graph](https://www.desmos.com/calculator/fwgpfln0ne) | [Graph](https://www.desmos.com/calculator/td3fynck7q) | [Graph](https://www.desmos.com/calculator/es8ugnvxeq) | [Graph](https://www.desmos.com/calculator/x58olmjtkl) |
| ![Photo](https://thumb.spokesman.com/LzzALA-yzk6jmSOYmVPZ6rdEsbU=/1170x0/media.spokesman.com/photos/2008/08/18/triplejumppic18_08-18-2008_ILE22PC.jpg) | ![Photo](https://c7.alamy.com/comp/2A8DJYK/genova-italy-08-nov-2019-cesar-cielo-filho-brazil-during-trofeo-nicola-sapio-swimming-credit-lpsdanilo-vigoalamy-live-news-2A8DJYK.jpg) | ![Photo](https://media.gettyimages.com/photos/derval-orourke-of-ireland-sally-pearson-of-australia-and-brigitte-of-picture-id123295200?s=2048x2048) | ![Photo](https://www.gettyimages.dk/detail/news-photo/derval-orourke-of-ireland-sally-pearson-of-australia-and-news-photo/123295200) | ![Photo](https://img.washingtonpost.com/rf/image_1484w/2010-2019/WashingtonPost/2016/08/19/Production/Daily/Style/Images/2016-08-18T192657Z_01_OLYGK111_RTRIDSP_3_OLYMPICS-RIO-DIVING-W-10MPLATFORM.jpg?uuid=BvCIjGYKEeaLJ7uLo5SXog) | ![Photo](https://st.depositphotos.com/2579941/2911/i/950/depositphotos_29111391-stock-photo-fra-alpine-skiing-val-disere.jpg) |
| [Video](https://www.youtube.com/watch?v=wVqYjmK-T3w) | [Video](https://www.youtube.com/watch?v=qZvdhv9uhi0) | [Video](https://www.youtube.com/watch?v=AFNqbhJ3kmw) | [Video](https://www.youtube.com/watch?v=85v0Un19A94) | [Video](https://www.youtube.com/watch?v=wTX13JZFHd4) | [Video](https://www.youtube.com/watch?v=kU0a-kvvKW4) |
| [Françoise Mbango Etone](https://en.wikipedia.org/wiki/List_of_Olympic_records_in_athletics) của Cameroon giữ kỷ lục Olympic ở nội dung nhảy ba lần nữ với khoảng cách dài 15.39 mét. | [César Cielo](https://en.wikipedia.org/wiki/List_of_Olympic_records_in_athletics) của Brazil giữ kỷ lục Olympic nội dung 50 mét nam với thời gian 21.47 giây. | [Sally Pearson](https://en.wikipedia.org/wiki/List_of_Olympic_records_in_athletics) của Australia giữ kỷ lục Olympic ở nội dung 100 mét vượt rào nữ với thời gian 12.35 giây. | [Ri Se-gwang](https://en.wikipedia.org/wiki/Gymnastics_at_the_2016_Summer_Olympics_%E2%80%93_Men%27s_vault) của Cộng hòa Nhân dân Triều Tiên đã giành được huy chương vàng cho môn nhảy cầu trong Thế vận hội Olympic mùa hè 2016. | [Ren Qian](https://en.wikipedia.org/wiki/Diving_at_the_2016_Summer_Olympics_–_Women%27s_10_metre_platform) của Trung Quốc giành huy chương vàng môn lặn trong Thế vận hội Olympic mùa hè 2016. |
| Bắt đầu: 985m | Hoàn thành: 805m | Khoảng cách cao: 180m | Cổng: 66 | Thời gian hoàn thành: 48.33 |

Như bạn có thể thấy, có một số quan điểm khác nhau để vẽ đồ thị chuyển động. Một quan điểm là khoảng cách là một hàm của thời gian. Chọn các cuộc đấu được thể hiện với góc nhìn này.

    // NOTES
    // Multiple Select

Ta thấy hai cuộc đấu còn lại là [[độ cao | khoảng cách]] như một hàm của [[khoảng cách | độ cao]]. Chúng ta sẽ xem xét hai hàm này chi tiết hơn. Hãy đến hồ bơi.

---

Sắp diễn ra trận chung kết 50 mét tự do nam. Hãy theo dõi sát sao César Cielo Filho của Brazil. Biểu đồ thị đường bơi của anh ấy sẽ xuất hiện khi video phát.

    // NOTES
    // Student presses play on a [video](https://www.youtube.com/watch?v=qZvdhv9uhi0) (0:12-1:21) of Cielo’s record setting swim. Simultaneously, a distance-time graph populates in a card to the right of the animation.

::: column.grow

César Cielo của Brazil giữ kỷ lục Olympic nội dung 50 mét nam với thời gian 21.47 giây.

::: column(width=240)

![César Cielo](https://c7.alamy.com/comp/2A8DJYK/genova-italy-08-nov-2019-cesar-cielo-filho-brazil-during-trofeo-nicola-sapio-swimming-credit-lpsdanilo-vigoalamy-live-news-2A8DJYK.jpg)

:::
::: column.grow

Thật là một cuộc đua đầy cảm xúc đối với Cielo! Anh đã phá kỷ lục thế giới và kỷ lục olympic của môn bơi này. Đồ thị cho ta thấy lượt bơi phá kỷ lục của Cielo. Hình dạng mà chúng ta đã thấy trước đây trong [đồ thị các hàm tuyến tính] (/linear-functions/graphing-functions). Nhớ lại đồ thị này biểu diễn tất cả các cặp có thứ tự của phần tử đầu vào ứng với phần tử đầu ra. Ta có thể sử dụng thông tin từ đồ thị để viết hàm mô tả bước bơi của Cielo. Hãy gọi hàm đó là f(t).

Hãy nhớ lại mẫu chung của [__linear function__](gloss:linear-function) như dạng y=mx+c, với m là hệ số góc và c giá trị giao với trục tung. Ta thay thế y bởi tên của hàm và thay thế x bằng biến đầu vào cho hàm này.

{.text-center} `y=mx+c`
`=> f(t)=m[[t]]+c`

Điều này có nghĩa là chúng ta cần tìm [[hệ số góc {.fixme} là "m"]] và [[tung độ giao trục tung {.fixme} là "c"]] từ đồ thị.

Chú ý là [trục hoành](target:1_xAxis), trong đồ thị này cho thấy [[thời gian]] tính theo giây. [trục tung](target:1_yAxis) là khoảng cách từ khối bắt đầu đến đích đối diện của hồ bơi được tính bằng [[mét]]. Ta thấy rằng trục tung [__giao điểm__](gloss:intercept) là [[00]] mét, đại diện cho [[khoảng cách | thời gian | số vòng]] của cuộc đua.

{.text-center} `y=mx+c`
`=> f(t)=mt+[[0]]`

Chúng ta chỉ còn thiếu độ dốc. Trong hàm này, độ dốc đại diện cho [[tốc độ | khoảng cách | tốc độ đá]] của Cielo. Làm thế nào chúng ta có thể sử dụng đồ thị để xét xem anh ta bơi nhanh như thế nào?

    // NOTES
    // This might work better as an animation to keep the stairs equal distances. We won't have to worry about reducing ratios.
    // Students can click two points on the graph. These coordinates appear in a x-y table. Dashed lines with the horizontal and vertical measurements appear one unit at a time as though counting the slope. Students can choose between one and five points to see a pattern (slope).

Khi chúng ta di chuyển từ trái sang phải dọc theo đường thẳng, khoảng cách dọc đo được [[-2.35]] mét. Khoảng cách ngang đo được là [[1]] giây. Tốc độ của Cielo [[không đổi | tăng lên | giảm xuống]] trong cuộc đua này, đó là một đặc điểm chính của các hàm số tuyến tính.

Nhớ lại rằng [__hệ số góc__](gloss:line-slope) là khoảng thay đổi dọc chia cho khoảng thay đổi ngang (dọc trên ngang). Hệ số góc của f(t) là [[2.35]] mét trên giây.
y=mx+c

f(t)=[[2.35]]t+0

::: column(width=240)

[Mô hình cuộc đua Cielo](https://www.desmos.com/calculator/o3de2a7odh)

:::

Giả sử chúng ta muốn biết Cielo bơi 10 mét đầu tiên trong bao lâu. Mười mét vào cuộc đua, điều này có nghĩa là ta đang xét [f(t)=10](target:1_cieloGraph). Cụm từ “bao lâu” cho biết chúng ta đang giải tìm t.

    // NOTE
    // Algebra Flow

{.text-center} `f(t)=2.35t`
`10=2.35t`
`(10)/(2.35)=t`
`4.25=t`

Cielo bơi 10 mét đầu tiên chỉ trong hơn [[4.1+-0.1]] giây.

---

Hãy xem bốn người về đích hàng đầu trong cuộc đua này:

    // NOTES
    // Lines are labeled with the swimmer’s name and the function name. Moving the cursor along the active line show crosshairs extending to the axes. Students can also select a line, then select a value along one of the axes to lock the crosshairs to that value.
| Vận động viên bơi lội | | Tên hàm | | Màu sắc |
| :------ | | :------------ | | :---- |
| Cesar Cielo Filho | | f(t) | | xanh lá cây |
| Amaury Leveaux | | l(t) | | tím |
| Alain Bernard | | b(t) | | xanh dương |
| Ashley Callus | | c(t) | | đỏ |

::: column(width=240)

[Mô hình bơi 50 tự do](https://www.desmos.com/calculator/ahx1i7lkau)

::: column.grow

Tất cả các đường đi qua trục tung ở [[0]] mét vì đây là khoảng cách của cuộc đua. Thoạt nhìn, chúng ta nhận thấy các đồ thị gần như nằm chồng lên nhau. Điều này phải cho thấy rằng tốc độ của những người bơi gần như là tương tự nhau.

Giả sử chúng ta muốn tính xem Cielo đi trước Leveaux bao nhiêu giây sau 10 mét. Ta đã biết Cielo bơi quãng đường này trong 4.25 giây. Ta không biết quy tắc hàm cho l(t), đường bơi của Leveaux, nhưng ta có đồ thị của nó. Tìm thời gian t, với l(t) = [[10]].

    // NOTES
    // Student clicks on l(t) to make it the active function. Student clicks on 10 on the y-axis. Dotted line from y-axis to l(t) appears. Dotted line from l(t) at 10 meters to corresponding t-value appears.

Leveaux bơi 10 mét đầu tiên trong [[4.56+-.02]] giây. Điều đó có nghĩa là Cielo chỉ đi trước Leaveaux [[0.46+-0.12]] giây!

Leveaux và Bernard đã tập luyện cùng nhau, và ta thấy điều đó. Họ luôn cố gắng trong toàn bộ cuộc đua. Họ về đích chỉ cách nhau [[0.4+-.01]] giây.

Sử dụng đồ thị để tìm vị trí của mọi người ở mốc 20 giây.
f(20)=[[47+-0.1]]
l(20)=[[43+-0.1]]
b(20)=[[43.8+-0.1]]
c(20)=[[41.2+-0.1]]

Callus ở phía sau [[Cielo | Leveaux | Bernard]] 6 mét ở mốc 20 giây.

:::

Hãy đến hồ bơi lặn cho cuộc thi nhảy cầu 10 mét dành cho nữ.

---

::: column.grow

Trong khi đó, ở phía bên kia của trung tâm Aquatics, một cuộc thi lặn đang diễn ra.
Ren Qian là một trong những vận động viên đoạt huy chương Olympic trẻ tuổi nhất. Hiện giờ cô ấy đang lặn - [xem](https://www.youtube.com/watch?v=wTX13JZFHd4)

    // NOTES (0:00-0:12)!

Ren Qian từ Trung Quốc đã giành huy chương vàng môn lặn trong Thế vận hội Olympic mùa hè 2016.

::: column(width=240)

[Mô phỏng hình ảnh Ren](https://img.washingtonpost.com/rf/image_1484w/2010-2019/WashingtonPost/2016/08/19/Production/Daily/Style/Images/2016-08-18T192657Z_01_OLYGK111_RTRIDSP_3_OLYMPICS-RIO-DIVING-W-10MPLATFORM.jpg?uuid=BvCIjGYKEeaLJ7uLo5SXog)

::: column(width=240)

    // NOTES
    // make sticky
[dive mock-up](https://www.desmos.com/calculator/es8ugnvxeq)

::: column.grow

Hãy gọi hàm đại diện cho đường lặn của Ren là d(x). Các giá trị đầu vào, x, là khoảng cách ngang từ nền. Các giá trị đầu ra, d(x), là [[độ cao]] của Ren trong suốt quá trình lặn. Ngay lập tức, ta nhận thấy hình dạng của đồ thị này khác với các đồ thị đường bơi ở trên. Đồ thị này có [[2]] điểm ngoặt so với hàm tuyến tính có [[0]] điểm ngoặt.

Đồ thị với hình dạng này được gọi là hàm lập phương. Chúng ta có thể nhận được thông tin quan trọng từ đồ thị ngay cả khi không biết phương trình hàm số. Nối các mệnh đề đã cho với đồ thị.

:::

    // NOTES
    // Students cards for all of the items below, and then drag them onto the corresponding point along the graph. Let’s show all the contextual statements, but talk about one key feature at a time.

| Đặt thẻ mệnh đề trên đồ thị | | Tính năng mục tiêu chính xuất hiện khi thẻ được đặt |  | Ký hiệu hàm số khi thẻ được đặt |
| :---: | | :---: | | :---: |
| Ren vào chỗ cô ấy trên bục. | | Giao với trục tung | |    |
| Ren đạt đến điểm cao nhất trong lần lặn của cô ấy | | Giá trị lớn nhất | |    |
| Ren hoàn thành 3.5 lần nhảy | | tăng | | 0.335<x<2.556 |
| Cú nhảy của Ren gần như hoàn tất. | | Giao với trục hoành | | d(2.056)=0 |
| Ren quay người dưới nước. | | Giá trị nhỏ nhất | | d(2.556)=-1.623 |
| Ren nổi lên sau một lần lặn gần như hoàn hảo. | | Giao với trục hoành | | d(2.989)=0|

    // NOTES
    // If I read this correctly, the explanation of the various features of the graph would come up and then students would drag the corresponding ones into place? Is that correct? If so, I wonder how it would go if the order is flipped - students choose any item from the table above and then when they drag it into the correct spot, some narrative comes up explaining the math of that point. I'm only suggesting this because as I read the table without any of the text below, I found myself moving all the "cards" into the correct spot on the graph and enjoyed that. Maybe the scaffolding is needed and important tot the math here. Just sharing my 1st experience of reading the table.
Nhớ lại tung độ giao điểm với Oy đạt khi x = [[0]]. Trong ký hiệu hàm số, tức là d([[0]])=10. Dạng của d(0)= tung độ giao điểm với Oy luôn đúng với bất kỳ hàm nào.
    // That's an interesting thought. +philipp@mathigon.org can text oder be dependent on how the student uses the interactive? In this case, what order they choose to place the cards on the graph?

Tương tự, các hoành độ giao điểm với Ox là [[d(x) | x]]=0. Đồ thị này có [[2]] hoành độ giao điểm với Ox. Chúng đại diện cho bề mặt của nước trong hồ bơi.

---

Khi ta nói về giá trị lớn nhất, ta thực sự đang nói về giá trị cao nhất [[d(x) | x]]. Độ cao lớn nhất của Ren là [[10.9+-0.1]] mét. Cô ấy đạt độ cao tối đa khi cách ván [[0,3 + -0,1]] mét. Trong ký hiệu hàm, ta có [[d(0.3)=10.9 | d(10.9=0.3]].

Giá trị nhỏ nhất là độ cao thấp nhất của Ren. Trong đồ thị này, điểm thấp nhất của cô ấy là dưới nước. Vì trục hoành biểu diễn bề mặt nước nên giá trị d(x) nhỏ nhất là số [[âm | dương | không]]. Cô ấy quay lại tại [[-1.6 +-0.1]] mét dưới nước và [[2.6 +-0.1]] mét từ bục hồ lặn.

---

    // NOTES
    // +philipp@mathigon.org I pulled the intervals of increase from the cards. Do we want to pull it from the discussion, too? It gives a few more opportunities to use intevals.

Bằng trực giác, ta thấy rằng đồ thị tăng khi cơ thể của Ren đang di chuyển [[lên | xuống]]. Kí hiệu điểm tăng khác với điểm ngoặt và điểm cắt. Vì đồ thị tăng ở nhiều hơn một điểm, ta biểu diễn phần của đồ thị bằng cách sử dụng [__khoảng__](gloss:interval). Khoảng các giá trị  [[x | d(x)]] tương ứng với độ cao đang tăng dần của Ren. Lưu ý rằng có nhiều cách khác nhau để viết các khoảng, ta sử dụng các bất đẳng thức trong chương này.

Ren di chuyển lên trong khoảng:

    // NOTES
    // Multiple selector (shuffle order)

0<x<0.335		0.335<x<2.556		2.556<x<2.989

Khoảng không được kiểm tra là chỗ đồ thị [[giảm]]. Ren đang di chuyển xuống từ d(0.335)= [[10.941+-0.1]] mét tới d(2.556)=[[-1.623+-0.1]] mét.

Chú ý giá trị [[lớn nhất | nhỏ nhất]] tại nơi đường đi của Ren thay đổi từ độ cao tăng đến giảm. Giá trị nhỏ nhất là nơi đường đi của Ren thay đổi từ giảm sang tăng.

    // NOTES
    // Not sure where to put the comment, so putting it here. I like how in the 1st example, students see the graph being made as the video is playing. Maybe at the end of this section, something similar could happen? They have the graph labeled with the cards correctly. Then, the graph goes away and the cards stay in place. Then, they hit play on the video and see the graph made in real time as they watch the dive?

---

Hãy nghĩ về các giá trị đầu vào và đầu ra của hàm d(x). Nhớ lại [__tập xác định__](gloss:domain) là tập hợp tất cả các giá trị đầu vào có thể có của d(x). Một phương pháp để tìm tập xác định là bắt đầu với tập hợp các số thực và thu hẹp tập đó xuống một phạm vi phù hợp với tình huống đã cho.

Khoảng cách theo phương ngang của Ren bắt đầu từ bệ lặn và kết thúc khi cô ấy nổi lại trong hồ bơi. Ta biết bệ lặn ở x = [[0]] mét. Cô ấy nổi lên lại ở độ cao x = [[2.989]] mét. Do đó, ta có thể viết tập xác định là [[0<=x<=2.989 | 0<=x<=10.941 | 0<x<2.989]]. {.fixme} SHOW AFTER PREVIOIUS BLANKS FILLED  Lưu ý rằng các điểm mút, 0 và 2.989, được bao gồm trong tập xác định bằng cách sử dụng <= và >=.

Nhớ lại [__tập giá trị__](gloss:range) là tập hợp của tất cả các độ cao Ren đi được. Chú ý rằng Ren di chuyển dưới mặt nước. Trên thực tế, ta có thể sử dụng giá trị [[nhỏ nhất | lớn nhất | giao điểm trục hoành | giao điểm trục tung]] của hàm số để xác định giới hạn dưới của tập giá trị. Giá trị nhỏ nhất của D(x) là [[-1.623]] mét.

Tương tự, giá trị lớn nhất d(x) cho ta giới hạn trên của tập giá trị. Do đó, tập giá trị là [[-2]] <= d(x) <= [[10.941]].

---

Hãy đến bãi biển để xem trận đấu tranh huy chương vàng bóng chuyền nam giữa Brazil và Ý. Các đội tham gia vào một cuộc đấu [bóng chuyền](https://www.youtube.com/watch?v=k4ux0jau_ws) (5:56-6:01). Khi bạn xem video, hãy chú ý đến hình dạng của đồ thị. Nó có giống là những gì bạn nghĩ đến?

    // NOTES
    // Students watch the video of the volley and the graph appears simultaneously.
    // I'm thinking students can use estimates for y-values. The times should be pretty close to the video, but the heights should just be correct relative to each other (e.g. the second relative max is higher than the first and lower than the third). We can have the net height on the graph for reference.
    // We make this graph, add discussion.

[sketch](https://drive.google.com/file/d/1mrT-d6Xwunc6I6hC7y2U_38bWR1y-lF5/view?usp=sharing)

Đồ thị cho thấy đường đi của quả bóng chuyền như một hàm của [[thời gian | khoảng cách | độ cao]]. Điều đó có nghĩa là tại mỗi thời điểm, quả bóng có một vị trí được đánh dấu bởi [[(thời gian, độ cao) | (độ cao, thời gian)]]. Ví dụ, quả bóng cao [[9+-.5]] feet trong 2 giây. Ta có thể tìm thấy thông tin về _khi nào_ những điều nào đó xảy ra.

Ví dụ, quả bóng mất khoảng [[3.5+-.5]] giây trên lưới. Brazil ghi một điểm sau khoảng [[4.75+-.5]] giây. Ý có một đường chuyền đẹp vào khoảng [[3]] giây. Bóng đạt độ cao lớn nhất, khoảng [[11+-1]] feet, lệch khỏi khung.

Chú ý rằng đồ thị không hiển thị khi quả bóng đổi hướng. Điều này có thể xảy ra nếu đồ thị là một hàm của [[khoảng cách | độ cao | thời gian]]. Một đồ thị như vậy sẽ cho chúng ta biết _where_ những điều nhất định sẽ xảy ra. Nhìn vào đồ thị này, ta không thể biết được quả bóng nằm ở phía nào của lưới.

___

### Vẽ đồ thị

    // NOTES
    // From David re: diving graph. Capturing idea.
    // Great graph. I really like how you included the part under the water. That's nice to show. I wonder if before showing the graph, students could draw the shape they think the graph would be? Maybe have an image of a diving board at the 10 meter mark and they use like a "scribble" or "line" tool to draw in the line they think the graph will be. Then, when they are done, the graph you have gets superimposed on their graph and their line fades away.
    // Create videos similar to the ball bouncing activity here: https://curriculum.illustrativemathematics.org/HS/teachers/1/4/8/index.html
    // Students place a point on the coordinate plane and label it with a key feature name. The might also be able to place approximate points on the internals of increase and decrease. Students click “graph”, or some such button, to see a line connect the points according to their labels. Once students see the graph, they can choose to edit or submit for checking.
    // Alternate interactive ideas
    // Give components of this similar to the piecing it together activity. [This is the same idea](https://www.google.com/url?q=https://curriculum.illustrativemathematics.org/HS/teachers/1/4/12/index.html&sa=D&ust=1595249230079000&usg=AFQjCNFlsjZxKJ9PGN9cluHSZm-OAFBaOA) used in the next chapter for building the tri graph.

Trận đấu nhảy sào dành cho nữ sắp bắt đầu. Bạn sẽ vẽ đồ thị cho sự kiện này.

    // NOTES
    // Allow scrubbing in video. Superimpose timer on the frames to make graphing easier. [1:00 - 1:15](https://www.youtube.com/watch?v=PPaUgaBor2I)

Ta sẽ bắt đầu vẽ đồ thị bằng cách sử dụng một bảng. Điền vào bảng dưới đây. Lưu ý rằng hố nhảy cao 0.81 mét.

    // NOTES
    // Students fill in the missing values.

| Thời gian (s) | | Độ cao (m) |
| :------: | | :--------: |
| 0 | | 0 |
| 1 | | 0 |
| 4 | | [[0]] |
| 5.5 | | [[0]] |
| 6 | | [[1.5+-.2]] |
| 6.5 | | [[3.2+-.2]] |
| 7 | | [[4.85]] |
| 7.5 | | [[3.2+-.2]] |
| 8 | | [[0.81]] |

Vẽ đồ thị các giá trị này trên mặt phẳng tọa độ.

[vẽ đồ thị](https://drive.google.com/file/d/1iywz65_-0ySs5Sd6rSxWF9RN_zun7pLc/view?usp=sharing)

Đồ thị này rất thú vị vì trong khoảng từ [[0]] đến khoảng [[5.7+-0.2]] giây, đồ thị là không đổi. Độ cao tối đa của Stefanidi là [[4.85]] mét. Điểm cuối trên đồ thị là tại ([[8]], [[0.81]]) bởi vì cô ấy đáp xuống hố, không phải trên mặt đất.

---

### Hệ các hàm số / Hàm số tương đồng

Hãy bắt đầu đến với đường đua cho trận chung kết 800 mét nữ. Có vẻ như ta đến kịp thời để bắt kịp 200 mét cuối cùng của cuộc đua. [3:22-4:00](https://www.youtube.com/watch?v=h83yS9gPkA8)

    // NOTES
    // Information for the interactive:

| __Vận động viên__ | | Adelle Tracey | | Laila Boufaarirane | | Raevyn Rogers |
| :---------: | | :-----------: | | :----------------: | | :------------:|
| __Quốc gia__ | | GBR | | FRA | | USA |
| __@ 90.63 s__ | | 600 | | 598 | | 590 |
| __@ 800 m__ | | 121 | | 126 | | 120.2 |
| __màu__ | | đen | | xanh lá cây | | cam |
| __hàm số__ | | g(t)=6.58545x+3.16101 | | f(t)=5.71105x+80.4071 | | u(t)=7.10179x-53.6354 |

    // NOTES
    // Students see the graph populate in time with the video.
    // We'll need to think about where we want to place this in the coordinate plane. Floating axes are nice as seen here. We could also change it such that 90.63s is t=0, though I think that would be a higher barrier to understand than not seeing the origin on the coordinate plane.

[800 M mock-up](https://www.desmos.com/calculator/msryjohuz9)

Khi chúng ta có hai hoặc nhiều hàm số trên cùng một mặt phẳng tọa độ, ta gọi chúng là [__hệ phương trình__](gloss:system-of-equations). Các hệ như thế này bổ sung các tính năng chính giúp ta hiểu thêm những gì đang xảy ra trong cuộc đua giữa Tracey, Boufaarirane và Rogers. Ví dụ, một điều nào đó thú vị đang xảy ra khi các đồ thị giao nhau. Chọn tất cả các câu phát biểu đúng về các giao điểm của hệ này.

    // NOTES
    // Multiple select

| Tracey và Rogers ở cùng một địa điểm. | | g(t) = u(t) | | Rogers ở trước Boufaarirane. | | u(t) < f(t) |
| Boufaarirane và Rogers ở cùng một địa điểm. | | f(t) = u(t) | | Tracey ở sau Rogers. | | g(t) > u(t) |

Các đồ thị cắt nhau khi một người chạy vượt qua người khác. Khi một vận động viên chạy còn khoảng 200 mét trong cuộc đua của họ, [[Rogers | Boufaarirane | Tracey]] ở vị trí thứ ba.

---

Rogers vượt qua Boufaarirane khoảng [[96.5+-.25]] giây khi cả hai còn khoảng [630]] mét trong cuộc đua. Trong ký hiệu hàm số, ta có f([[96.5+-.25]])=u([[96.5+-.25]])=[[630]].

Khoảng [[13.5+-.25]] giây sau, [[Rogers | Boufaarirane | Tracey]] vượt qua [[Tracey | Rogers | Boufaarirane]]. Họ còn khoảng [[73+-1]] mét nữa là về đích.

---

Hệ số góc của mỗi hàm số cho ta biết [[tốc độ | khoảng cách | nhịp]] của mỗi vận động viên. Rogers đang chạy với tốc độ khoảng [[7.1+-0,2]] mét mỗi giây.

    // NOTES
    // We looked at counting slope above. This is a review of calculating slope. They need to pull the values off of the graph.
    // Algebra Flow

{.text-center} `m=(y_2 - y_1)/(x_2 - x_1)`
`m= (y_2 - 590)/(x_2 - 90.63)`
`m= (800-590)/(120.2-90.63)`
`m= (210)/(29.57)`
`m=7.1`

Tốc độ của Roger nhanh hơn so với Boufaarirane [[0.6+-0.2]] mét trên giây và nhanh hơn Tracey [[1.4+-0.2]] mét trên giây.

---

Trong hệ các hàm số này, ta có thể biết ai dẫn trước tại bất kỳ thời điểm nào trong cuộc đua. Ví dụ, ta viết f(t)> u(t) khi [[Boufaarirane vượt trước Rogers | Rogers vượt trước Boufaarirane]].

    // NOTES
    // Used both < and > to show both. Would it be better for students to see a "readable" pattern than matches the sentences, which would only use > ?

| Các học sinh gắn nhãn với các thẻ mệnh đề đã cho. | | Thông tin này xuất hiện sau khi thẻ ký hiệu hàm số được đặt chính xác. | | Thông tin bổ sung. Không phải thẻ. |
| :---: | | :---: | | :---: |
| Boufaarirane vượt trước Rogers. | | f(t) > u(t) | | 90.63=<t<96.382 |
| Rogers vượt trước Boufaarirane. | | f(t) < u(t) | | 96.382<t<=120.2 |
| Tracey vượt trước Rogers. | | u(t) < g(t) | | 90.63<=t<109.998 |
| Tracey vượt trước Boufaarirane. | | g(t) > f(t) | |   |
| Rogers vượt trước Tracey. | | g(t) < u(t) | | 109.998<t<=120.2 |

Khi ta nói về một hàm lớn hơn một hàm khác, ta đang sử dụng [[giá trị đầu ra | giá trị đầu vào]] để xác định một miền các [[đầu ra | giá trị]]. Ví dụ, ta thấy Tracey dẫn trước Boufaarirane trong toàn bộ chặng đua này. Điều này được thể hiện dưới dạng [[g(t) > f(t) | g(t) < f(t)]]. Chúng ta có thể coi đây là “khoảng thời gian mà Tracey đã chạy một khoảng cách xa hơn Boufaarirane”. Miền giá trị đó là [[90.63+-0.2]] <= t <= [[121]]. Chúng ta có thể thực hiện một phân tích tương tự cho từng cặp hàm số.

Nhìn vào ba hàm số trên mặt phẳng tọa độ, ta có thể thấy rằng quan hệ giữa u(t) và g(t) thay đổi từ g(t)>u(t) đến u(t)>g(t) khi [[Rogers vượt qua Tracey | Tracey vượt qua Rogers | Rogers vượt qua Boufaarirane | Boufaarirane vượt qua Rogers]]. Điều này có nghĩa là giới hạn trên của g(t)>u(t) khi g(t) [[= | < | >]] u(t), với t=[[110+-0.2]] giây. Giá trị t này, 110 giây, cũng là giới hạn dưới của u(t)>g(t).

----

Cuối cùng, đây là một hàm số nữa đại diện cho một môn thể thao. Bạn có thể nghĩ xem nó là gì và viết một câu chuyện ngắn giải thích các đặc điểm khác nhau của đồ thị không?

TODO: draw chart
<< free-form text input >>


--------------------------------------------------------------------------------


## Hàm cho trên từng đoạn

> section: piecewise
> sectionStatus: dev
> id: fn-sketch

Vẽ một hàm số:

    x-coordinate-sketch(width=600 height=400 x-axis="-1,10,1" y-axis="-5,5,1")
      button.btn.clear Clear

Nhập một số văn bản:

    x-free-text(placeholder="Your answer…")

    // NOTE
    // Local server trouble - not able to visualize design decisions. Followed the conventions I could find in terms of notes, fixme tags, image/ graph mock-ups, and targets. Targets do not have objects set, but the syntax should indicate where the target is intended to go. Worked last to first. Some of these conventions change as I learned more from other code.

Các cuộc đua đa môn thể thao kiểm tra sức bền của các vận động viên. Swimrun là một cuộc thi đa môn thể thao khá mới bắt đầu vào năm 2002 tại Thụy Điển. Câu chuyện kể rằng chủ khách sạn Utö Värdshus, bạn của anh ta, và hai nhân viên khách sạn đã thách đấu với nhau trong một cuộc đua hai đấu hai từ khách sạn Utö Värdshus, băng qua ba hòn đảo, đến Sandhamn. Đội thua sẽ trả tiền cho các bữa ăn sau cuộc đua của mọi người. Bạn nghĩ cuộc đua kéo dài bao lâu?

    // NOTES
    // Anders Malm - owner of Utö Värdshus, Janne Lindberg - friend, Andersson brothers - staff at Utö Värdshus
    // [citation](https://en.wikipedia.org/wiki/Swimrun)

    // Map between these two locations. Include images from each place. I like David’s map zoom effect he has mentioned in a couple of chapters. While it wouldn’t necessarily add to the math directly, it would make the story more interesting and help student intuit distance.
    // EDITOR USE ONLY
    // [Utö Värdshus](https://www.utovardshus.se/wp-content/uploads/2019/03/Liggande_VH-fr%C3%A5n-Bastun_Copyright-Ut%C3%B6-V%C3%A4rdshus-1.jpg)

    // [map view](https://www.google.com/maps/dir/Sandhamn,+Sweden/Ut%C3%B6+V%C3%A4rdshus,+Pr%C3%A4stbacken+22,+130+56+Ut%C3%B6,+Sweden/@59.1054899,18.3165704,10z/data=!4m14!4m13!1m5!1m1!1s0x46f5741069214bbf:0xbfee8fb6ece8997c!2m2!1d18.9108304!2d59.2878703!1m5!1m1!1s0x46f58b4425a902e9:0xb792bc38be8de224!2m2!1d18.329336!2d58.967417!3e4)

![Sandham](https://upload.wikimedia.org/wikipedia/commons/c/c1/Sandhamn_February_2013_04.jpg)

Cuộc đua kết thúc kéo dài hơn 24 giờ! Những người bạn đó đã thực hiện một cuộc đua giống vậy vào năm sau, và ý tưởng về ÖtillÖ (đảo này sang đảo khác) được khỏi sinh.

---

::: column(width=240)

    // NOTES
    // Something like this would be awesome. Transition from water to run. Setting. Dressed for water in Sweden.
    // EDITORIAL ONLY

![](https://live.staticflickr.com/65535/48213036251_c9ae4edc7b_b.jpg)

::: column.grow

Chúng ta đang luyện tập cho ÖtillÖ. Chúng ta cần làm quen với cảm giác bơi sau đó là chạy ngay lập tức. Chúng ta quyết định bơi 500 mét sau đó chạy 5 km. Chọn đồ thị biểu thị quãng đường của vận động viên dưới dạng một hàm số theo thời gian, d(t).

:::

    // NOTES
    // Multiple selector with one choice
    // [option 1](https://drive.google.com/file/d/1UhFc87ir21UUNnQWmJ0UhvrXn6bZu6Lo/view?usp=sharing)
    // [option 2](https://drive.google.com/file/d/1T0q0btNyuiNaOVWk6NbM8dQydXthhwtv/view?usp=sharing)
    // [option 3](https://drive.google.com/file/d/18DMyDqbjmOq7Wdou-yTuMvI0NTBfSg-T/view?usp=sharing)
    // [option 4](https://drive.google.com/file/d/1zKhk2t_V00SSEsmyXWCvohxnOyzMk0Q6/view?usp=sharing)
    // Option 2 is the object of the targets below.

Đây là một ví dụ về một [__hàm cho trên từng đoạn__](gloss:piecewise) trong đó các quy tắc khác nhau áp dụng cho các tập giá trị đầu vào khác nhau. Ta có thể thấy [first section](target:1_piecewise) của đồ thị có hệ số góc khác với [second section](target:2_piecewise).

Một trong những cách phổ biến nhất để viết các hàm số trên từng đoạn là sử dụng các trường hợp.

    // NOTES
    // It would be great to target or color code the different components of the function. Input ranges point to x-axis, rules point to graph.

`d(t)= {(1/20t,0<=t<10),(1/6 t-7/6,10<=t<=40):}`

Mỗi dòng trong hàm số này là một trường hợp. Nó bao gồm quy tắc xác định hàm số và các giá trị đầu vào tương ứng. Chúng ta đọc hàm này là “Hàm d có giá trị là (1/20)t khi t lớn hơn hoặc bằng 0 và nhỏ hơn hoặc bằng 10. Hàm d là (⅙)t-(7/6) khi t lớn hơn hoặc bằng 10 và không vượt quá 40.”

Hãy tiếp tục tìm hiểu về các hàm cho bởi từng đoạn.

---

::: column.grow

Nội dung 400 mét tiếp sức ở môn bơi lội gồm bốn vận động viên bơi lội. Mỗi vận động viên bơi 100 mét tiếp sức ở một trong bốn lượt bơi. Các đoạn dài 100 mét này được gọi là các chặng. Cuộc đua tiếp sức này bao gồm [bơi ngửa](target:1_relayGraph), [bơi ếch](target:2_relayGraph), [bơi bướm](https://www.desmos.com/calculator/y3zz7gphmo), và [bơi tự do](https://www.desmos.com/calculator/y3zz7gphmo) theo thứ tự. Đồ thị dưới đây cho ta s(d). Chú ý trục tung là [[khoảng cách | tốc độ]] tính bằng mét. Trục hoành thể hiện [[tốc độ | khoảng cách]] tính bằng mét trên giây. s(d) là hàm số phải không [__hàm số__](gloss:function)?

::: column(width=240)

    // EDITORIAL USE ONLY

![](https://depositphotos.com/stock-photos/backstroke-start.html?filter=all&qview=115180204)

    // NOTES
    // Add vertical line test tool.
    // [200 Medley Mock-up](https://www.desmos.com/calculator/y3zz7gphmo)
    // Graph above is the object of the targets in relay paragraph.

:::

Nhớ lại rằng các hàm số không thể có một giá trị đầu vào đi đến [[nhiều hơn một | chỉ một]] giá trị đầu ra. [__kiểm tra đường thẳng đứng__](gloss:vertical-line-test) là một công cụ để kiểm tra xem một quan hệ có phải là một hàm hay không. Sử dụng đường thẳng đứng ở trên để kiểm tra quan hệ này.

:::

---

Chúng ta cần chú ý đến các điểm mút của mỗi phần của miền xác định. Các điểm mút đảm bảo mỗi phần tử của miền chỉ được khớp với một phần tử của miền giá trị. Với lưu ý này, hãy chọn hàm phù hợp với đồ thị trên.

    // NOTES
    // Multiple selector with one correct answer

[option 1](s(d)={(1.3, 0<=d<=100),(1.2, 100<d<=200),(1.4, 200<d<=300),(1.5, 300<d<=400):})
[option 2](s(d)={(1.3, 0<=d<=100),(1.2, 100<=d<=200),(1.4, 200<=d<300),(1.5, 300<d<=400):})

Lưu ý rằng đồ thị hiển thị “<” dưới dạng một đường tròn mở - điều này cũng đúng với điểm mút cuối chứa “>”. Các đường tròn đóng kín nếu “<=” và “>=”.

---

Hàm s(d) là một hàm số cho trên từng đoạn được gọi là [__hàm bậc thang__](gloss:step-function). Một điểm khác biệt chính giữa s(d) và d(t) ở trên là tất cả các hệ số góc của s(d) bằng [[0]].

Chặng nhanh nhất của tiếp sức là [[bơi tự do | bơi bướm | bơi ếch | bơi ngửa]] với tốc độ [[1.5+-0.025]] mét trên giây. Chặng chậm nhất là [[bơi ếch | bơi tự do | bơi bướm | bơi ngửa]] hoàn thành trong [[1.2+-0.025]] mét mỗi giây. Mỗi chặng của cuộc đua dài [[100]] mét.

Ta đã sẵn sàng đi sâu vào vẽ đồ thị.

---

Một trong những cuộc thi đa môn thể thao phổ biến nhất là ba môn phối hợp, gồm bơi lội, chạy xe đạp và chạy bộ. Hàm l(t), cuộc đua của Lisa Laws, được đưa ra dưới đây. Sử dụng các đoạn thẳng đã cho để vẽ đồ thị l(t) trên mặt phẳng tọa độ.

    // EDITORIAL USE ONLY
    // Fun, quick [video](https://tokyo2020.org/en/sports/triathlon/) of triathlon. Nod to 2020 Olympics, especially if they don't happen. Includes map of courses.

`l(t)={(75x, 0<=t<=20),(50000, 20<t<=21),(-615.385t+63000, 21<t<=86),(10000, 86<t<=87),(-277.778t+34166.7, 87<t<=123):}`

    // EDITORIAL USE ONLY

[tiếp sức ba môn phối hợp](https://depositphotos.com/stock-photos/triathlon-competition-woman.html?filter=all&qview=111615040)

    // NOTES
    // There is a paper-based activity in the [IM chapter](https://curriculum.illustrativemathematics.org/HS/teachers/1/4/12/index.html) on piecewise functions “Students are given the equations that define two piecewise functions, along with strips of paper, each containing a part of a graph and a portion of the horizontal axis (no scale is shown). Their job is to arrange the strips, apply a scale on each axis, and add open and closed circles to the graph to accurately represent the function values at each interval of input.” - IM After building the first function, students label with the given cards.
    // Maybe shuffle order and orientation? Students can spin them as they would a paper cut out?

[Bậc 1](https://www.desmos.com/calculator/pqdjlinaf1)
[Bậc 2](https://www.desmos.com/calculator/yauvuvkbpx)
[Bậc 3](https://www.desmos.com/calculator/t9ltbpdotk)
[Bậc 4](https://www.desmos.com/calculator/zaa3wcoa05)
[Bậc 5](https://www.desmos.com/calculator/hcghou4mr7)
[Giải](https://www.desmos.com/calculator/mkyxyep0jv)

    // TUTOR PROMPTS
    // What do you remember about slope?
    // Positive slope increases from left to right.
    // Negative slope decreases from left to right.
    // What does a linear function with zero slope look like?

Lưu ý rằng mỗi hệ số góc hoặc là không đổi hoặc [[dương | âm]] giúp ta xác định hướng của từng phần của đồ thị. Hệ số góc không đổi là một đường [[ngang | đứng]]. Hệ số góc dương di chuyển [[lên | xuống]] khi chúng ta đi từ trái sang phải.

Hệ số góc cũng có thể giúp chúng ta xác định thứ tự của các đoạn từ trái sang phải. Ví dụ: chặng đua nhanh nhất của Law là [[chạy xe đạp | bơi lội | chạy bộ]]. Hệ số góc lớn nhất, [[615.4+-.1]] mét trên phút, là trường hợp thứ ba trong hàm số. Nó chạy từ [[21]] đến [[84]] phút. Bây giờ ta biết vị trí trên trục hoành để đặt phần dốc nhất của đồ thị.

---

Nhớ lại rằng đặc điểm chính của một hàm số cung cấp cho ta thông tin chi tiết về những gì đang diễn ra trong cuộc đua. Ví dụ: đường bắt đầu được biểu thị bằng {.FIXME} (multiple select) [[tung độ giao điểm Oy | hoành độ giao điểm Ox | giá trị lớn nhất | giá trị nhỏ nhất]]. Ta có thể viết điểm này trong ký hiệu hàm là l([[0]])=[[0]]. Đặt các mệnh đề còn lại trên đồ thị.

    // NOTES
    // Students label with the given cards.

| Đặt thẻ mệnh đề trên biểu đồ | | Tính năng mục tiêu chính xuất hiện khi thẻ được đặt |  |Ký hiệu hàm số xuất hiện khi thẻ được đặt |
| :---: | | :---: | | :---: |
| Law vượt qua vạch đích. | | giá trị lớn nhất | | l(123)=51500 |
| Law đang đạp xe về phía điểm chuyển tiếp. | | tăng | | 21 < t <= 86 |
| Law đang chuyển từ bơi sang đạp xe. | | không đổi | | 20 < t <= 21 |
| Law đang chuyển từ đạp xe sang chạy bộ. | | không đổi | | 86 < t <= 87 |

---

Bây giờ bạn có thể đua với Law. Một trong những điều thú vị về ba môn phối hợp là bạn không cần phải là người nhanh nhất trong ba môn thể thao, bạn chỉ cần vượt qua vạch đích trước. Tại đây, bạn có thể điều chỉnh đồ thị của mình, s(t), để xem cuộc đua thay đổi như thế nào. Giả sử chặng đua thử thách nhất của bạn trong cuộc đua này là bơi. Như bạn thấy, không thể điều chỉnh phân đoạn này. Bạn có thể đánh bại Law khi có một chặng bơi chậm hơn [[4]] phút không?

::: column.grow

    // NOTES
    // Slider in __bold__ . Like slider graphs in https://mathigon.org/course/sequences/arithmetic-geometric. Or drag endpoints along the transition lines to change slopes.
    // Adjusts to match given input _italics_.

s(t) = {(60t, 0<=t<=25),(1500, 25<t<=26.5),(_695.652_t-_16934.8_, __26.5+-0.75__<=t<__84+-0.75__),(41500, _84_<t<=_85.5_), (_298.50_t+_15977.6_, _85.5_<t<=__123+-5__):}

    // NOTES for 60t line: Actually adjusting these points in the background.
    // NOTES for 695.652 line: (__26.5+-.75__, 1500) and (__84+-.75__, 41500)
    // NOTES for 41500 line: (_84_, 41500) and (_85.5_, 41500), _84_ matches slider in last case, _85.5_ Adjusts to be lower bound + 1.5
    // NOTES for 298.50 line: (_85.5_, 41500) and (__123+-5__, 51500), _85.5_ matches previous case

---

Hãy thử điều chỉnh đồ thị để bạn bơi __và__ chạy chậm hơn Law. Bạn cần đạp xe lúc [[{.fixme} Có cách nào để chấp nhận phạm vi các hệ số góc phụ thuộc vào các giá trị thanh trượt không? ]] mét trên phút để đánh bại Law.

::: column(width=240)

    // NOTES
    // Graph: l(t) is blue, s(t) is orange
    // [mock-up triathlon graph](https://www.desmos.com/calculator/1wcntarqcv)

:::

---

::: column(width=240)

[hình ảnh Sundae](https://depositphotos.com/4537530/stock-photo-ice-cream.html)

::: column.grow

Hãy đi lấy kem để ăn mừng bạn giành chiến thắng! Ice-agon đưa ra hai phương án định giá. Bạn có thể trả theo gam hoặc mua một trong ba kích cỡ. Bạn muốn gọi món gì?

:::

    // NOTES
    // Students interact with the graph. Small, medium, and large are in orange. Price per gram is in purple.

[mô hình đồ thị](https://www.desmos.com/calculator/i0iatpatrn)

Như bạn thấy, sự lựa chọn của bạn sẽ phụ thuộc vào một vài yếu tố khác nhau. Điền vào bảng dưới đây để hiểu rõ hơn về các tùy chọn của bạn.

| Khối lượng | | Giá | | Giá |
| :---: | | :---: | | :---: |
| 50 | | [[ Không có sẵn ]] {.fixme} cũng chấp nhận không, không có sẵn | | 0.10 |
| 75 | | [[2.75]] | | [[1.50+-0.1]] |
| 125 | | [[2.75]] | | [[2.50+-0.1]] |
| 150 | | [[Không có sẵn]] | | [[3+-0.1]] |
| 175 | | [[4.25]] | | [[3.50+-0.1]] |
| 225 | | [[4.25]] | | [[4.50+-0.1]] |
| 275 | | [[Không có sẵn]] | | [[5.50+-0.1]] |
| 325 | | [[5]] | | [[6.50+-0.1]] |
| 335 | | [[Không có sẵn]] | | [[6.70+-0.1]] |

Loại kem nhiều nhất bạn có thể mua với $5 là khoảng [[300+-30]] gam với hộp đựng kích thước lớn. Loại tốt nhất nên mua nếu bạn muốn 200 gram kem là [[tính theo gram | hộp đựng loại trung]], có giá [[4]].


--------------------------------------------------------------------------------


## Hàm giá trị tuyệt đối

> section: absolute-value
> sectionStatus: dev

    // NOTE
    // Local server trouble - not able to visualize design decisions. Followed the conventions I could find in terms of notes, fixme tags, image/ graph mock-ups, and targets. Targets do not have objects set, but the syntax should indicate where the target is intended to go. Worked last to first. Some of these conventions change as I learned more from other code.

::: column.grow

Atari's Pong, được phát hành vào năm 1972, đã khởi động ngành công nghiệp trò chơi điện tử như chúng ta đã biết. Trò chơi này giống là một trò chơi bóng bàn kỹ thuật số. Pong phổ biến đến nỗi văn hóa đại chúng cho đến nay vẫn còn nhắc đến nó.

Ngày nay, các game thủ có thể chơi các biến thể dựa trên internet của trò chơi bóng bàn hoặc ghé xem một trò chơi điện tử với bàn điều khiển Atari Ping nguyên bản.

    // REFERENCE ONLY
    // [https://www.youtube.com/watch?time_continue=9&v=fiShX2pTz9A&feature=emb_logo](https://www.youtube.com/watch?time_continue=9&v=fiShX2pTz9A&feature=emb_logo)

MathiPong bày tỏ lòng kính trọng đối với trí tuệ này trong lịch sử trò chơi. Mục tiêu là hướng bóng đến đích. Chọn chế độ thông thường hoặc chế độ thử thách để bắt đầu.

::: column(width=240)

![](https://upload.wikimedia.org/wikipedia/commons/3/32/Signed_Pong_Cabinet.jpg)

    // Source: https://commons.wikimedia.org/wiki/File:Signed_Pong_Cabinet.jpg

:::

    // NOTES
    // onboard the game. User uses arrow keys to move platform. Platform is wider than the point shown.
    // User plays several rounds.

![](/content/functions/images/4/Screenshot_2020-06-29_at_13.53.44.png)

Bây giờ bạn đã chơi một vài vòng và có ý tưởng về cách trò chơi này hoạt động, chúng ta hãy nghĩ về chiến lược để bắn trúng mục tiêu. Hãy cùng nhìn lại trò chơi trên mặt phẳng tọa độ.

    // NOTES
    // The animation mock-ups are on a loop for minimal clicking in this draft. I don't think they need to be on a loop in the final. In fact, I actually envision these happening on one coordinate plane. This would make each a different state of the same interactive.
    // Left column shows states of game. Right column is the text matching the state. In final version of the chapter, this won't need to be a series of columns.

::: column(width=240)

[https://www.desmos.com/calculator/vy9nhnyp1z](https://www.desmos.com/calculator/vy9nhnyp1z)

::: column.grow

Nếu chúng ta chỉ để quả bóng rơi từ phần trên bên trái của màn hình. Đường đi của nó sẽ trông như thế nào [this](target:1_linearGraph). Ở đây chúng ta nhận ra hệ số góc của đường mô tả đường đi của bóng là [[-1]]. Cho biết đường thẳng này đi qua điểm gốc tọa độ, có hàm số là f(x)=-x.

::: column(width=240)

[https://www.desmos.com/calculator/yyoqeezli2](https://www.desmos.com/calculator/yyoqeezli2)

::: column.grow

Chúng ta biết mong muốn đường đi của quả bóng trông như thế nào [this](target:2_linearGraph) để đạt được mục tiêu. Đường mới này mô tả đường đi dự định của quả bóng là [[1]]. Thật thú vị, điều này chỉ đơn giản là ngược lại với hệ số góc ở trên. Hàm số của đường này là g(x)=x.

::: column(width=240)

[https://www.desmos.com/calculator/jr6scyqzdn](https://www.desmos.com/calculator/jr6scyqzdn)

::: column.grow

Nếu chúng ta di chuyển đến giao điểm của hai đường này, đường đi của quả bóng sẽ di chuyển từ đường ban đầu của nó đến đường đi mong muốn của chúng ta. Giao điểm tại ([[0]], [[0]]).

::: column(width=240)

[https://www.desmos.com/calculator/jjbzth2pta](https://www.desmos.com/calculator/jjbzth2pta)

::: column.grow

Trong chương về các hàm số cho trên từng đoạn, chúng ta đã thực hành viết các hàm để mô tả các tình huống như thế này. Tức là, ta muốn sử dụng một phần nào đó của một hàm số và một phần của hàm số khác. Các giá trị của tập xác định cho hàm số trên từng đoạn mô tả đường đi này là:

h(x)= \begin{matrix}-x & x [[\ge]]\ [[0]] \\x & x\ [[<]]\ [[0]]\end{matrix}

:::

Thực ra có một cách khác để thể hiện cùng một hình dạng bằng cách sử dụng một hàm số khác.

[https://www.desmos.com/calculator/vyl1ggpfxc](https://www.desmos.com/calculator/vyl1ggpfxc)

[https://www.desmos.com/calculator/ihajfmgvkl](https://www.desmos.com/calculator/ihajfmgvkl)

[v-shaped graph](target:1_absGraph) được gọi là một hàm giá trị tuyệt đối. Như bạn có thể thấy, hình dạng đồ thị của nó giống như của hàm cho trên từng đoạn. Ngoài ra để ký hiệu hàm số, ta sử dụng các thanh đứng để chỉ giá trị tuyệt đối. Nhớ lại rằng [**giá trị tuyệt đối**](gloss:absolute-value) là khoảng cách giữa số đã cho và số 0. Nói cách khác, giá trị tuyệt đối của bất kỳ số nào đều không âm. Ý tưởng tương tự cũng áp dụng cho hàm số này.

f(x)=|x|

Các hàm giá trị tuyệt đối có nhiều đặc điểm chính giống như chúng ta đã biết qua chủ đề hàm số. Một điểm quan trọng được gọi là [đỉnh](gloss:graph-vertex) của một đồ thị. Nó là điểm ngoặt trong tất cả các đồ thị hàm giá trị tuyệt đối. Đỉnh của hàm giá trị tuyệt đối này là ([[0]], [[0]]).

Bây giờ Mathipong sẽ không còn là một trò chơi nếu quả bóng luôn rơi từ cùng một vị trí và mục tiêu không bao giờ di chuyển. Tương tự như vậy, các hàm giá trị tuyệt đối sẽ không hữu ích lắm nếu chúng chỉ với quy tắc f(x)=|x|. Hãy xem cách chúng di chuyển trên mặt phẳng tọa độ.

    // NOTES
    // This section will likely work better with some animations. The graphs here can be mock-ups of key points in the animations.

Cho đến giờ, khi chúng ta vẽ đồ thị các hàm số, ta đã vẽ các điểm trên đường thẳng đó và nối chúng thành một đường thẳng, hoặc ta tìm một điểm quan trọng, như giao điểm với trục tung hoặc giao điểm với trục hoành và tính hệ số góc để vẽ đường thẳng đó. Các đồ thị và phương trình tương ứng của chúng thực sự cho chúng ta một cách hiểu mới về đồ thị trên mặt phẳng tọa độ. Ta có thể nghĩ đến việc vẽ đồ thị **[phép dịch chuyển](gloss:transformations).** Hãy xem xét điều này với một đường thẳng có đồ thị quen thuộc y=x.

::: column(width=240)

![](/content/functions/images/4/Screenshot_2020-07-10_at_15.18.28.png)

![](/content/functions/images/4/Screenshot_2020-07-10_at_14.47.44.png)

::: column.grow

Bây giờ ta vẽ đồ thị đường thẳng y=x+2.

::: column(width=240)

[https://www.desmos.com/calculator/mcwyh3toux](https://www.desmos.com/calculator/mcwyh3toux)

Lưu ý rằng đường thẳng này là y=x dịch lên 2 đơn vị. Hoặc, chúng ta có thể thấy là y = x dịch sang trái 2 đơn vị.

Sau đó, hãy lấy đối xứng nó qua trục hoành.

::: column(width=240)

![](/content/functions/images/4/Screenshot_2020-07-10_at_14.50.39.png)

![](/content/functions/images/4/Screenshot_2020-07-10_at_14.53.38.png)

::: column.grow

Phần bên phải của đồ thị ban đầu, hay phần phía trên trục hoành, vẫn không bị dịch chuyển. Phía bên trái, mọi thứ bên dưới trục hoành, ta lấy đối xứng lên phía trên trục hoành. Vị trí phía trên trục hoành giống với đồ thị của hàm số f(x)=|x+2|.

::: column(width=240)

[https://www.desmos.com/calculator/6fpbvgfrny](https://www.desmos.com/calculator/6fpbvgfrny)

::: column.grow

Chú ý y=|x+2| là y=|x| dịch sang trái 2 đơn vị.

Bây giờ, giả sử chúng ta cộng thêm một số vào y=|x| tương tự như với y=x+2. Bạn nghĩ điều gì sẽ xảy ra với đồ thị?

:::

---

::: column(width=240)

[https://www.desmos.com/calculator/aqly16ptq5](https://www.desmos.com/calculator/aqly16ptq5)

::: column.grow

Đồ thị của y=|x| chuyển lên trên.

Chú ý rằng việc dịch chuyển đồ thị sang trái và phải sẽ làm thay đổi các giá trị [[bên trong | bên ngoài]] thanh giá trị tuyệt đối. Tương tự, di chuyển đồ thị lên và xuống làm thay đổi các giá trị [[bên ngoài | bên trong]] thanh giá trị tuyệt đối. Điều này có nghĩa rằng y=|x+2|  **không** giống y=|x|+2.

Hai phép biến đổi này, mà chúng ta gọi là phép dịch chuyển hay phép tịnh tiến, rõ ràng cho ta các đồ thị khác nhau. Đồ thị bên trái cho thấy một dịch chuyển phương [[ngang | đứng]] trong khi đồ thị bên phải hiển thị một dịch chuyển theo phương [[đứng | ngang]]. Ta sẽ xem xét các phép biến đổi chi tiết hơn trong phần [Phép dịch chuyển hàm số](https://mathigon.org/course/function-transformations).

:::

---

Hãy ghép hàm số với đồ thị của nó. Hãy ghi nhớ các phép dịch chuyển f(x)=|x-h|+k với h là dịch chuyển theo phương ngang và k là dịch chuyển theo phương thẳng đứng.

    // NOTES
    // Students drag functions to their respective graphs.

    // Functions for cards.

[](https://lh6.googleusercontent.com/bjmVukpDAuueGt7ShvzlA7ciunIpVLBrQPg-WNbdw0JZSFb59imu8XM4rDi_sS1mIn8FcooZjyUbeJnj04TExksgfPn70I0CdNL6kN65eIHZ611gFplehLVgMMnl11QhTOUUl0C-)

    // Graph mock-ups for cards.

[https://lh6.googleusercontent.com/BiB7qoKIoH-Ct1EKL54qUHd5DaPt8yEC11EHxDh0NY8jv_baTSmdjCIxuT4I-bEkGIgpj_zUhe-Q-vYyURKf6rv9mWpFtkWF8ClKaPNfkle5r575c3isjwp47h8128K9Dol5Pael](https://lh6.googleusercontent.com/BiB7qoKIoH-Ct1EKL54qUHd5DaPt8yEC11EHxDh0NY8jv_baTSmdjCIxuT4I-bEkGIgpj_zUhe-Q-vYyURKf6rv9mWpFtkWF8ClKaPNfkle5r575c3isjwp47h8128K9Dol5Pael)

[https://lh5.googleusercontent.com/qDPHACr6mN2lDyvT2T4HzeV93FcMRj0yXAvctg0Wu00_WrB3VSRacBLURLB_A3VQazxfFoIjJ9mtRvZEsl9uYnPvl3zOgOOIemy6GXwziJR1A-PdxQpl2FKFJ23flqUg2rHdGTXY](https://lh5.googleusercontent.com/qDPHACr6mN2lDyvT2T4HzeV93FcMRj0yXAvctg0Wu00_WrB3VSRacBLURLB_A3VQazxfFoIjJ9mtRvZEsl9uYnPvl3zOgOOIemy6GXwziJR1A-PdxQpl2FKFJ23flqUg2rHdGTXY)

[https://lh6.googleusercontent.com/vmg68ABIbxAl6uhLVfxGs3Z0GOZqUF3LvM4hdubZ4qKBIBIyrY1fgUc9rP9oPBthfbFAyWz8Ra_8-SN2kpZMO4bONJ6Awj1V17MksaDdxQA01Xr9BoMRgTM8t-zA9BeOjID1PPyS](https://lh6.googleusercontent.com/vmg68ABIbxAl6uhLVfxGs3Z0GOZqUF3LvM4hdubZ4qKBIBIyrY1fgUc9rP9oPBthfbFAyWz8Ra_8-SN2kpZMO4bONJ6Awj1V17MksaDdxQA01Xr9BoMRgTM8t-zA9BeOjID1PPyS)

[https://lh4.googleusercontent.com/jjOSNHGZ4SyupkjyNcwV6R6SttOVaNW2Wans6ug9mOx24AXzNrUIIqIY531O1sF9tAc5kKJSV01yE6C__uy1JLKh32XFDf-jkfWJyhBAimFWGyMbP8U0_FHf--NHtqZ18dPPIqQ9](https://lh4.googleusercontent.com/jjOSNHGZ4SyupkjyNcwV6R6SttOVaNW2Wans6ug9mOx24AXzNrUIIqIY531O1sF9tAc5kKJSV01yE6C__uy1JLKh32XFDf-jkfWJyhBAimFWGyMbP8U0_FHf--NHtqZ18dPPIqQ9)

[https://lh5.googleusercontent.com/Fs4qVDVYffvrT6EWYqmwbxPiNXNQrrVHXqA3kK85-H8V1hwLoIbN59ODnXwXjRp-SW17-Y4vjMTg6mXVM8m6csg_zDb4BcptbReFnap16j7KYvF1xbuJ5tjNo0lDlmoToLS-RexU](https://lh5.googleusercontent.com/Fs4qVDVYffvrT6EWYqmwbxPiNXNQrrVHXqA3kK85-H8V1hwLoIbN59ODnXwXjRp-SW17-Y4vjMTg6mXVM8m6csg_zDb4BcptbReFnap16j7KYvF1xbuJ5tjNo0lDlmoToLS-RexU)

---

Hãy quay lại ý tưởng lấy đối xứng một đồ thị qua trục hoành. Đây thực sự không phải là một sự ngẫu nhiên mà hành động này dùng cho hàm giá trị tuyệt đối của hàm số tuyến tính ban đầu. Tính chất tương tự thỏa với giá trị tuyệt đối của các hàm số khác.

    // NOTES
    // **Slideshow** functions: https://www.desmos.com/calculator/l2lveli1ey
    // This could be a cool graph drawing interactive once your tool is done.
    // Function mock-ups. Left column is original graph. Right column is absolute value Superimposed over original.

::: column (width=240)

![](/content/functions/images/4/Screenshot_2020-07-10_at_15.27.58.png)

![](/content/functions/images/4/Screenshot_2020-07-10_at_15.30.12.png)

![](/content/functions/images/4/Screenshot_2020-07-10_at_15.29.35.png)

![](/content/functions/images/4/Screenshot_2020-07-10_at_15.28.36.png)

![](/content/functions/images/4/Screenshot_2020-07-10_at_15.31.06.png)

![](/content/functions/images/4/Screenshot_2020-07-10_at_15.29.58.png)

::: column(width=240)

![](/content/functions/images/4/Screenshot_2020-07-10_at_15.29.23.png)

![](/content/functions/images/4/Screenshot_2020-07-10_at_15.28.13.png)

![](/content/functions/images/4/Screenshot_2020-07-10_at_15.30.22.png)

![](/content/functions/images/4/Screenshot_2020-07-10_at_15.29.47.png)

![](/content/functions/images/4/Screenshot_2020-07-10_at_15.28.55.png)

![](/content/functions/images/4/Screenshot_2020-07-10_at_15.31.30.png)

:::

Chúng ta sẽ khám phá về phép đối xứng nhiều hơn trong [Hàm đối xứng](https://mathigon.org/course/function-transformations/refleticing).

---

### Sai số tuyệt đối

    // NOTES
    // This section may not work with final chapter. Editors may strike.

Hãy cùng xem ý tưởng về giá trị tuyệt đối có thể liên quan đến phân tích dữ liệu như thế nào. Có một loại phép đo được gọi là sai số tuyệt đối để định lượng sự khác biệt giữa giá trị kỳ vọng và giá trị đo được. Ví dụ, chúng ta biết nhiệt kế của chúng ta có sai số là 2 độ. Nhiệt kế cho biết hiện tại là 25°C. Chúng ta có thể sử dụng giá trị tuyệt đối để xác định nhiệt độ thấp nhất và cao nhất có thể mà không khí có thể gây ra sai số trên nhiệt kế.

Gọi x là nhiệt độ thực trong khi nhiệt độ đo được là 25. Sự sai khác của chúng cho chúng ta sai số, mà chúng ta biết là 2. Do đó, chúng ta có thể sử dụng phương trình |x-25|=2 để xác định nhiệt độ thực tế có thể.

Nhớ lại rằng giá trị tuyệt đối đo khoảng cách từ số không. Điều này có nghĩa là phép đo đó có thể đi theo hướng dương **or** theo hướng âm. Ta thực sự không biết hướng dự định khi được cho một giá trị như *sai số tuyệt đối bằng 5*. Để tính nó, ta cần xem xét cả hai trường hợp.

    // NOTES
    // Algebra Flow. Currently written step-by-step in step then description.

$|x-25|=2 $

Cho

$x-25=2 \ \text{or}\ -(x-25)=2 $

Tính giá trị trong trường hợp [hướng dương](target:1_leftEquation) và giá trị trong trường hợp [hướng âm](target:2_rightEquation).

$x=27 \ \text{or} \ x-25=-2$

Giải từng phương trình một cách bình thường.

$x=27\ \text{or}\ x=23$

Các nghiệm cho ta nhiệt độ thấp nhất và cao nhất có thể.

    // END ALGEBRA FLOW

Để biết nhiệt độ cao hơn hay thấp hơn giá trị mình đã đo, ta sẽ cần thêm thông tin như phép đo từ một nhiệt kế khác.

Nhiều loại hàm số khác nhau có những tình huống giống như vậy, chúng thực sự có thể có nhiều hơn một nghiệm cho bài toán. Chúng ta sẽ khám phá ý tưởng này sâu hơn trong phần [hàm số bậc hai](https://mathigon.org/course/quadratics/introduction).

---

Bây giờ chúng ta đã biết thêm về các hàm giá trị tuyệt đối và cách chúng hoạt động, hãy bắt đầu ở cấp độ tiếp theo của Mathipong.

    // NOTES
    // Ball comes at different locations on the upper left side of the screen. Path is at different angels (slopes).


--------------------------------------------------------------------------------


## Hàm ngược

> section: inverse
> sectionStatus: dev

    // NOTE
    // Local server trouble - not able to visualize design decisions. Followed the conventions I could find in terms of notes, fixme tags, image/ graph mock-ups, and targets. Targets do not have objects set, but the syntax should indicate where the target is intended to go. Worked last to first. Some of these conventions change as I learned more from other code.
    // Many links go to databases in Notion where design elements and texts are stored.

Môn thể thao đồng đội là thế giới của những hành động trong tích tắc và phải di chuyển thật nhanh. Đồng đội chọn nơi đặt đường chuyền. Trọng tài quyết định ai là người giành quyền sở phát bóng. Người hâm mộ theo dõi hành động từ khoảng cách rất xa. Trong tất cả những trường hợp này, màu áo thi đấu là nhân tố quyết định cách thức đưa ra những quyết định tức thời.

Chúng ta hãy nhìn vào giải thi đấu bóng đá Balligon Soccer League. Ghép mỗi đội với một màu áo để bạn có [hàm số](gloss:function).

    // NOTES
    // Same interactive as chapter 1. Links go to the databases with assets and text.

[Đội](https://www.notion.so/a89f42d0f2b447f89f0d4ae58ad565be)

[Màu áo](https://www.notion.so/e13166523b5e47ef96044c922bac940b)

Nhớ lại rằng các đội tạo nên [[tấp xác định | tập giá trị]] của hàm số,

    // NOTE hide until blank is filled

trong khi màu sắc áo thi đấu tạo nên tập giá trị. Trong ký hiệu hàm số, ta viết quan hệ này là f([[đội]])=[[màu áo]].

    // NOTE
    // also accept "domain", "mascot", "team name"; also accept "range", "colour", "color", "jersey"; OR make multi-select

Xem qua các vòng đấu cuối mùa giải.

::: column(width=240)

![](/content/functions/images/5/Screenshot_2020-07-01_at_16.50.26.png)

Ví dụ về cặp dấu ngoặc. Điền vào các đội phù hợp với màu sắc.

::: column.grow

Trò chơi giữa `team1 assigned to same color` và `team2 assigned to same color` sẽ là một thách thức đối với các cầu thủ, trọng tài và người hâm mộ. Màu sắc áo thi đấu là `{jersey colour}` cho cả hai đội. Hãy tưởng tượng bạn đạng theo dõi xem ai sở hữu bóng từ khoảng cách 30 mét. Trên thực tế, hậu quả của việc mặc đồng phục giống màu nhau gây nhiều khó khăn đến mức liên đoàn thể thao phải đưa ra những hình phạt cho các đội mặc đồng phục sai quy cách.

:::

---

Ý tưởng nhìn thấy màu áo thi đấu và biết ngay cầu thủ đó thuộc về đội bóng nào thì ngược lại với `f(team)=jersey`. Trong toán học, ta gọi quan hệ ngược này là [nghịch đảo](gloss:inverse-operation). Ta sử dụng ý tưởng này khi chúng tôi cân bằng các phương trình: phép cộng hủy bỏ phép trừ, phép nhân hủy bỏ phép chia, v.v. Đặc biệt, chúng ta đang nghĩ về một quan hệ [hàm ngược](gloss:inverse-function).

Hàm ngược mà ta đang xét xác định đội dựa trên màu áo thi đấu. Hãy xem ánh xạ của hàm trên di chuyển từ trái sang phải.

    // NOTES
    // Show mapping from above with copy of the team group to the right of colour.
    // Think about how to guide students toward adding a colour to the output. This should be integrated into the interactive design.

Ở đây ta có thể thấy rằng [quan hệ](target:1_mapping) giữa màu và đội bóng không phải là một hàm số. Điều gì sẽ khắc phục quan hệ này giữa `f(team)` và vì vậy mà `f^(-1)(colour)`  thành một hàm số?

---

    // NOTES
    // Show mapping from above with copy of the team group to the right of colour. Students can add a colour option. Change the mapping s.t. `f(team)` is one-to-one.

Giờ  `f^(-1)(colour)` là một hàm số. Thực tế, nhớ lại từ [Relations and Functions](https://mathigon.org/course/functions/relations)có một số loại hàm số. `f(team)`giờ là một tương ứng [[một-một | một-nhiều | nhiều-một | nhiều-nhiều]].

    // Decide whether or not to include all relation classificiations or just function classifications.

---

Hãy xét quan hệ ánh xạ này trong một cỗ máy hàm số. Chọn một đội để đi qua máy. Máy chỉ định cho nhóm một màu, sau đó đảo ngược nhiệm vụ. Nói cách khác, máy đã áp dụng quy tắc hàm số sau đó áp dụng quy tắc hàm ngược.

    // NOTES
    // Visual inspiration
    // Apples are team names. Lemons are jersey colours. Label the first machine with `f(team)` and the second with `f^1(colour)`.
    // EDITORIAL USE ONLY

![](https://upload.wikimedia.org/wikipedia/commons/f/fe/Fruit_function_and_inverse.PNG)

[Inspiration](https://phet.colorado.edu/sims/html/function-builder/latest/function-builder_en.html)

Mỗi khi bạn vượt qua `{team}` thông qua cả hai máy, bạn thoát khỏi [[tên | màu áo]]. Về mặt đại số, ta viết hàm này là `f(f^1(x))=x`. Chúng ta sẽ xem xét kỹ hơn tại sao điều đó lại quan trọng trong suốt chương này.

    // NOTES
    // Highlight that f^-1 is not exponent

---

### Chuyển đổi ngoại tệ

Du lịch quốc tế đạt hơn 4 triệu lượt mỗi ngày vào năm 2019. Với việc đi lại nhiều giữa các quốc gia, người dân nhận thức rõ hơn về khả năng chi tiêu của mình. Đó là, đổi một loại tiền tệ bằng một loại tiền tệ khác`{user's currency unit e.g. dollar}` ứng với `{user's home country's currency}`. Hãy cùng khám phá ý tưởng về khả năng chi tiêu này - chọn điểm đến từ các thành phố được liệt kê.

    // NOTES
    // Do not show city options located in the same country as the user.
    // Could be great to tie the conversion rate in this interactive to the daily rates. This would complicate the rest of the chapter's text and [[blanks]]. I think it could be a nice touch, though. Users who return to this chapter would see how (potentially) volatile, or at least not-static, this rate is in real life.

[Thành phố và tiền tệ](https://www.notion.so/554f2cbfc43640799fff025363f6d2fc)

    // NOTES
    // The text below is build on visiting Machu Picchu from the USA.

Trong chuyến đi của bạn, bạn sẽ tìm thấy nhiều khu chợ khác nhau chỉ thu tiền mặt. Để chuẩn bị cho chuyến đi chợ tiếp theo, bạn phải rút tiền mặt. Hàm số chuyển đổi là `{destination currency}={conversion rate}*{home currency}` . Dựa vào ngân sách của bạn, bạn có khoảng [[nội tệ]]

{.fixme} người dùng nhập bất kỳ số tiền nào họ muốn

để chi trả cho những món quà lưu niệm, bạn cần phải rút [[{destination currency}={conversion rate}*{home currency}]]

{.fixme} người dùng phải thực hiện phép tính này và nhập số tiền +- .5

Đi dạo qua chợ và quyết định thứ bạn muốn mua.

    // MOCK UP
    // Souvenir cards
    // Images have local price. Rollover shows price in `{home currency}`. Even cooler, user calculates and inputs on the back of the card.

[Figma](https://www.figma.com/embed?embed_host=notion&url=https%3A%2F%2Fwww.figma.com%2Fproto%2FAItjhFAz9DsTkH0elhIbNt%2FUntitled%3Fnode-id%3D10%253A5%26viewport%3D-720%252C470%252C0.9163351058959961%26scaling%3Dmin-zoom)

[Đồ lưu niệm](https://www.notion.so/20a2f11c078940b6ae0170578e84c4ea)

---

### Quan hệ trực quan

Chúng ta có thể thể hiện quan hệ này giữa chi phí trong `{destination currency}` và `{home currency}` cũng như (`{destination currency}`, `{user home currency}`). Quan hệ này có nghĩa là `{destination currency}` là [[đầu vào | đầu ra]] và `{user home}` là [[đầu ra | đầu vào]]. Các điểm nằm trên một đường. Hãy gọi đường thẳng này f(`{destination currency}`)=`{conversion rate}`x`{destination currency}`.

---

Nhớ lại rằng trước đó ta đã sử dụng phương trình `{destination currency}={conversion rate}*{home currency}` để tính toán số tiền cần rút từ ngân hàng trước khi đi chợ. Lưu ý rằng phương trình này rất giống với [f(x)](target:1_souvenirGraph) về đồ thị.

Trong thực tế, sự khác biệt quan trọng nhất là các giá trị đầu vào và đầu ra được chuyển đổi. Ta đã thấy quan hệ này giữa các hàm số ở trên trong ví dụ về màu áo. Theo quan sát này, ta có thể thấy rằng `{destination currency}={conversion rate}*{home currency}` là hàm ngược của f(`{destination currency}`)=`{conversion rate}`x`{destination currency}`. Điều này có nghĩa là chúng ta có thể sử dụng ký hiệu `f^(-1)({home currency})` cho hàm số đại diện cho chuyển đổi từ `{home currency}` sang `{destination currency}`.

---

Đồ thị của các hàm ngược có một số đặc điểm thú vị. Đầu tiên, ý tưởng chuyển đổi giá trị đầu vào và đầu ra này giúp ta vẽ các điểm cho `f^(-1)({home currency})`. Hãy vẽ đồ thị các điểm lưu niệm của hàm ngược.

    // NOTES
    // f(x)=3.54x where x is soles and f(x) is dollars. The souvenir labels would be stronger if they were the name of the souvenir purchased.
    // Object of f(x) target above.
[https://www.desmos.com/calculator/ff6489z9ns](https://www.desmos.com/calculator/ff6489z9ns)

[https://www.desmos.com/calculator/tlscgnsyy3](https://www.desmos.com/calculator/tlscgnsyy3)

    // Students plot these points.
[https://www.desmos.com/calculator/ccbs3quxpu](https://www.desmos.com/calculator/ccbs3quxpu)

[https://www.desmos.com/calculator/mgmj8jbz26](https://www.desmos.com/calculator/mgmj8jbz26)

---

Có một tính năng thú vị khác của hàm ngược, mặc dù nó có thể không nhìn thấy rõ ràng. Hãy thực hiện một số phép đo giữa các đường để xem có thấy thêm tính chất thú vị nào không.

Bắt đầu bằng cách đo khoảng cách thẳng đứng từ `{souvenir 1}` trong  `f^(-1)({home currency})` đến `f({destination currency})`. Khoảng cách là

    // NOTES
    // Students read this from the measurement tool on the graph. I'm not as worried about the exact measurement as I interested in their noticing the vertical and horizontal distances are the same. I also want them to eventually key into the intersection points.

[[`f({cost of souvenir 1 in destination currency})`- `f^(-1)({cost of souvenir 1 in home currency})`|xxx]]. Tương tự, đo khoảng cách ngang giữa `{souvenir 1}` trong  `f({destination currency})` đến `f^(-1)({home currency})`.

---

Khoảng cách này giống với khoảng cách đứng mà bạn đã đo được! Thực hiện các phép đo giống nhau cho từng điểm lưu niệm.

    // NOTES
    // Interactive states

![](/content/functions/images/5/Screenshot_2020-06-30_at_14.58.09.png)

![](/content/functions/images/5/Screenshot_2020-06-30_at_14.58.39.png)

![](/content/functions/images/5/Screenshot_2020-06-30_at_14.59.00.png)


Lưu ý rằng các giao điểm của mỗi phép đo này nằm trên đường riêng của chúng.

    // NOTES
    // Interactive states

![](/content/functions/images/5/Screenshot_2020-06-30_at_14.59.38.png)

![](/content/functions/images/5/Screenshot_2020-06-30_at_15.00.10.png)

![](/content/functions/images/5/Screenshot_2020-06-30_at_14.11.11.png)

Phương trình này là [đường thẳng](target:2_souvenirGraph) is y= [[1]]m+[[0]]

{.fixme} ẩn cho đến khi chỗ trống được điền

đơn giản được y=x. Lưu ý rằng nếu chúng ta gấp mặt phẳng tọa độ dọc theo đường thẳng y=x,  `f({destination currency})` và `f^(-1)({home currency})` sẽ nằm chồng lên nhau. Đường thẳng y=x sẽ vẫn ở vị trí cũ khi ta gấp như thế.

Trong thực tế, tất cả các hàm ngược đều đối xứng qua đường thẳng y=x. Các công cụ ta dùng để đưa ra quan sát này giống như cách ta sử dụng để xác định xem hai hàm số có phải là nghịch đảo hay không. Chúng ta hãy xem xét kỹ hơn điều này với một dạng đồ thị mới được gọi là parabol.

---

### Parabol

::: column(width=240)

    // NOTES
    // Interactive states - not shown: vertical line test
![](/content/functions/images/5/Screenshot_2020-06-30_at_15.29.04.png)

![](/content/functions/images/5/Screenshot_2020-06-30_at_15.33.18.png)

::: column.grow

Chúng ta gọi hình dạng này là một [parabol](gloss:parabola). [Kiểm tra](target:1_lineTest) để đảm bảo rằng nó thực sự là một hàm số.

---

Parabol thỏa thử nghiệm đường thẳng đứng, vì vậy nó là một hàm số. Chúng ta chỉ quan sát thấy rằng các hàm ngược đối xứng nhau qua đường thẳng y=x. Tạo một bản sao của parabol và xoay nó trong mặt phẳng tọa độ để làm cho nó đối xứng với parabol ban đầu qua đường thẳng y=x. Phép đối xứng trong trường hợp này có nghĩa là hai parabol đối xứng qua y=x.

:::


    // NOTES
    // New parabola can snap to inverse when user gets close.

![](/content/functions/images/5/Screenshot_2020-06-30_at_15.37.42.png)

::: column.grow

Parabol nghịch đảo có dạng phản chiếu giống như các hàm số tiền tệ. Nhớ lại các cặp có thứ tự trên đường thẳng đó đã được chuyển đổi. Đó là (`destination currency`, `home currency`) trên một đường và (`home currency`, `destination currency`) trên một đường khác. Kiểm tra để đảm bảo rằng mô hình trên thỏa với hai parabol này.

Điền vào bảng với các điểm tọa độ cho mỗi điểm chính trong parabol ban đầu. Xác định rằng nghịch đảo của nó xuất hiện trên parabol đã quay.

    // NOTES
    // All values are fill-in-the-blank. Students can indicate or track that they have found the corresponding coordinate points.

::: column(width=240)

    // NOTES
    // **Note** students should check several points to verify.

![](/content/functions/images/5/Screenshot_2020-06-30_at_15.43.10.png)

:::

[Untitled](https://www.notion.so/3c9309dafa2f4ed6b49e3d5a9cb6004a)

---

::: column(width=240)

![](/content/functions/images/5/Screenshot_2020-06-30_at_15.47.25.png)


::: column.grow

Theo tính chất của hàm ngược, đây là nghịch đảo của parabol ban đầu. Nó đối xứng qua đường y=x và các điểm trên đường cong này là phần nghịch đảo của các điểm trên parabol ban đầu. Điều cuối cùng chúng ta cần làm là kiểm tra xem nó có phải là một hàm số không.

---

Hàm ngược không thỏa bài kiểm tra đường thẳng đứng. Nó không thực sự là một hàm số! Khi ta xem xét ví dụ về áo thi đấu, ta đã thay đổi đội thành hàm số màu để mỗi đội chỉ được chỉ định một màu. Bạn có thể áp dụng ý tưởng đó ở đây không?

:::

    // NOTES
    // CTA: Use the sliders to adjust the original function so that the second parabola is a function.
    // Sliders here prototype the slider function in the chapter. They restrict the domain from each direction.

[https://www.desmos.com/calculator/ywpamz642r](https://www.desmos.com/calculator/ywpamz642r)

Khi chúng ta thay đổi [tập xác định](gloss:domain) của parabol ban đầu, ta có thể làm cho parabol nghịch đảo trở thành một hàm số. Trên thực tế, miền xác định phải được giới hạn để mỗi giá trị đầu vào chỉ được khớp với một giá trị đầu ra. Điều này có nghĩa là một số hàm số có hàm ngược và một số hàm số thì không có. Cụ thể, chỉ các hàm số một-một có hàm ngược.

---

### Quan hệ đại số

::: column(width=240)

![](/content/functions/images/5/Screenshot_2020-07-01_at_21.27.34.png)

[https://stock.adobe.com/images/beachside-hammock/328924634?prev_url=detail](https://stock.adobe.com/images/beachside-hammock/328924634?prev_url=detail)

::: column.grow

Các đảo Caribe là một địa điểm du lịch nổi tiếng khác. Những bãi biển mang tính biểu tượng của họ và làn nước trong xanh như pha lê vẽ nên một bức tranh tuyệt đẹp. Bermuda, một quốc đảo ở Caribe, là một trong số ít nơi trên thế giới sử dụng cả thang đo nhiệt độ theo độ C và độ F trong khí tượng học. Hãy cùng tìm hiểu và xem xét mối quan hệ giữa các thang nhiệt độ này.

Nhớ lại rằng việc chuyển đổi tiền tệ từ loại tiền này sang loại tiền khác là các hàm nghịch đảo. Chúng ta đã xem xét điều đó bằng cách sử dụng đồ thị. Hãy xem việc chuyển đổi nhiệt độ từ thang này sang thang khác để xem liệu đây có thực sự là một ví dụ của hàm nghược hay không.

---

Dự báo cho thấy nhiệt độ cao nhất là 27 độ C. Chúng ta đã bỏ lỡ báo cáo về nhiệt độ ở độ F, vì vậy ta đã Google chuyển đổi và tìm C(x)= $\frac{5}{9}(x-32)$. Tìm mức nhiệt độ cao nhất hôm nay ở độ F.

:::

    // NOTES
    // Algebra Flow. Written as step, description, step, description, etc.

$27=\frac{5}{9}(x-32) $

Thay thế 27 vào C(X)

$9*27=[\frac{5}{9}(x-32)]x9$

Sử dụng phép toán nghịch đảo để di chuyển 9

$\frac{9}{5}x27=\frac{5*(x-32)}{5}$

Sử dụng phép toán nghịch đảo để di chuyển 5

$\frac{9}{5}x27+32=x-32+32$

Sử dụng phép toán nghịch đảo để di chuyển 32

$\frac{9}{5}x27+32=x$

x, đại diện cho nhiệt độ ở độ F, bị cô lập ở một vế

$80.6=x$

Mức cao hôm nay tính bằng độ F

    // END Algebra FLOW

Đây là một quá trình quen thuộc để giải phương trình. Ta có thể sử dụng cùng một quá trình này để tìm các hàm nghịch đảo liên quan đến đại số. Chúng ta hãy xem xét hai bước chính trong việc giải các phương trình trên.


    // NOTES
    // Several columns to show alignment between text and steps. Does not need to remain as several columns.

::: column(width=240)

{.text-center} Hàm số ban đầu: $27=\frac{5}{9}(x-32) $

::: column(width=240)

{.text-center} Hàm ngược: $\frac{9}{5}x27+32=x$

:::

Nhớ lại rằng chúng ta đã thay thế 27 vào C(x) vì đó là nhiệt độ đã cho của ta. Hãy đặt y bằng 27 để đại diện cho giá trị đầu ra trong một cặp có thứ tự.

::: column.grow

{.text-center} Hàm số ban đầu: $y=\frac{5}{9}(x-32) $

::: column(width=240)

{.text-center} Hàm ngược: $\frac{9}{5}y+32=x$

::: column.grow

Bây giờ hãy nhớ rằng để vẽ đồ thị cho hàm nghịch đảo khi chúng ta mua đồ lưu niệm ở chợ trong `{destination} ', chúng ta đã hoán đổi các tọa độ x và y. Tức là, ta đã chuyển đổi giá trị đầu vào và đầu ra. Hãy làm điều tương tự trong hàm ngược.

::: column(width=240)

{.text-center} $\frac{9}{5}x+32=y$

::: column.grow

Nhắc lại ký hiệu cho các hàm ngược sử dụng tên chữ cái của hàm ban đầu với -1 ở vị trí lũy thừa. Điều này có nghĩa là y trong hàm nghịch đảo đại diện bởi `C^(-1)(x)`.

Hãy xem xét các hàm gốc và hàm ngược song song với nhau.

::: column(width=240)

{.text-center} $\frac{9}{5}x+32=C^{-1}(x)$

::: column.grow

{.text-center} $C(x)=\frac{5}{9}(x-32) $

::: column(width=240)

{.text-center} $\frac{9}{5}x+32=C^{-1}(x)$

:::

 Nhớ lại ví dụ áo thi đấu ở trên rằng việc chuyển một giá trị qua một máy hàm thì cuối cùng máy hàm ngược của nó sẽ cho ta cùng một giá trị. Ta gọi cái này là `f(f^(-1)(x))=x`. Hãy chứng tỏ điều này đúng cho C(x) và `C^(-1)(x)`.

    // NOTES
    // Use same function builder inspirations as above.
    // Let's use the function machine as the way to explore `f(f^(-1)(x))=x`. List lots of numbers to pass through the machines. List a few variables, including x, to pass through. We can dig into the algebraic composition  functions in another chapter.

Hãy xác định xem hai hàm này có hàm nghịch đảo hay không.

{.text-center} $f(x)=4-\frac{3}{2}x\\ g(x)=\frac{1}{2}x+\frac{3}{2}$

    // NOTES
    // Students use function machine. They see they are not inverses.

Máy hàm chỉ ra rằng f(x) và g(x) [[không phải là | là]] nghịch đảo.

---

Hãy tìm hàm ngược của f(x).

    // NOTES
    // Students put the steps cards in order, then match the equation cards to the steps cards.

{.text-center} $f(x)=4-\frac{3}{2}x $

    // NOTES
    // Several columns to show alignment between text and steps. Does not need to remain as several columns.
    // Left column indicates equation cards. Right column represents steps cards.
    // Students put the steps cards in order, then they fill in the blanks of the equations cards.

::: column(width=240)

{.text-center} $y=4-\frac{3}{2}x$

::: column(width=240)

thay thế y cho f(x)

::: column(width=240)

{.text-center} $x=4-\frac{3}{2}y$

::: column(width=240)

chuyển đổi x và y

::: column(width=240)

{.text-center} $x-4=-\frac{3}{2}y$

::: column(width=240)

giải tìm y như bình thường

::: column(width=240)

{.text-center} $-2(x-4)={3}y$
$\frac{-2x+8}{3}=y$

::: column(width=240)

{.text-center} $\frac{-2x+8}{3}=f^{-1}(x)$

::: column(width=240)

thếe `f^(-1)(x)` vào y

:::

Ta biết có một số cách để xác định và chứng minh các hàm ngược. Chọn phương pháp yêu thích của bạn và giải thích lý do.

    // NOTES
    // Multiple select. No correct answer (i.e. open ended)

[tùy chọn 1] (đảo ngược phương trình theo phép toán đại số)
[tùy chọn 2] (vẽ đồ thị bằng cách sử dụng các điểm tọa độ và nghịch đảo của chúng)
[tùy chọn 3] (vẽ đồ thị bằng cách sử dụng đường thẳng y=x làm trục đối xứng)
[tùy chọn 4] (sơ đồ ánh xạ)

    // NOTES
    // Open-ended answer field

Hàm số và hàm ngược là những ý tưởng cơ bản trong mã hóa và giải mã. Kiểm tra [Codes and Ciphers](https://mathigon.org/course/codes/introduction) để xem những ý tưởng này thực hiện như thế nào!


--------------------------------------------------------------------------------


## Tốc độ biến đổi

> section: rates-of-change
> sectionStatus: dev

    // NOTE
    // Local server trouble - not able to visualize design decisions. Followed the conventions I could find in terms of notes, fixme tags, image/ graph mock-ups, and targets. Targets do not have objects set, but the syntax should indicate where the target is intended to go. Worked last to first. Some of these conventions change as I learned more from other code.

Trong suốt lịch sử, vi khuẩn và vi rút đã gây cản trở các quần thể có quy mô khác nhau, từ các nông thôn đến thành thị. Chúng ta thấy chu kỳ của các bệnh truyền nhiễm như đậu mùa, dịch hạch, nhiễm khuẩn salmonella, sốt vàng da, cúm, bại liệt, AIDS, ebola, Zika và COVID-19 thay đổi tiến trình lịch sử.

Toán học có thể giúp chúng ta hiểu được quy mô và tác động của các đợt bùng phát dịch bệnh. Hôm nay chúng ta sẽ tập trung vào [hàm số](gloss:function) mô tả các ca nhiễm liên quan đến dịch COVID-19.

::: column(width=240)

![](/content/functions/images/6/Screenshot_2020-07-09_at_09.52.32.png)

::: column.grow

Bảng bên phải hiển thị các ca nhiễm lũy tích dưới dạng một hàm của thời gian. Nhớ lại rằng cách diễn đạt này có nghĩa là thời gian là giá trị [[đầu vào | đầu ra]]

###fixme: hide until blank filled
 and cumulative confirmed cases is the output.

Từ lũy tích này có nghĩa là tổng số hiện tại qua tất cả thời gian. Điều đó có nghĩa là con số này chỉ tăng lên, ngay cả khi các ca nhiễm hàng ngày bắt đầu giảm. Để có một bức tranh chính xác hơn về những gì đang xảy ra, chúng ta có thể tính toán số ca mắc mới mỗi ngày.

::: column(width=240)

![](/content/functions/images/6/Screenshot_2020-07-09_at_09.52.45.png)

::: column.grow

Ví dụ, chúng ta có thể đặt các điểm trên đồ thị bên phải vào ngày 26 tháng 1 và ngày 12 tháng 6. Hệ số góc của đường đi qua hai điểm này được gọi là [t](gloss:secant-line)he **tốc độ biến đổi trung bình** cho khung thời gian này.

::: column(width=240)

![](/content/functions/images/6/Screenshot_2020-07-09_at_09.53.21.png)

::: column.grow

Đường này ước tính các ca nhiễm đang tăng với tốc độ hơn [[14]] tỷ mỗi ngày.

::: column(width=240)

![](/content/functions/images/6/Screenshot_2020-07-09_at_10.00.25.png)

::: column.grow

Bây giờ, chúng ta có thể thấy rằng đường này không thể hiện được về số lượng các ca nhiễm hàng ngày thay đổi như thế nào theo thời gian. Diện tích phần màu xanh dương hiển thị khoảng cách giữa tốc độ biến đổi trung bình và đồ thị thực tế.

Hãy xem liệu có cách nào để làm cho tốc độ biến đổi trung bình được ước tính tốt hơn biến đổi thực tế hàng ngày không.

::: column(width=240)

![](/content/functions/images/6/Screenshot_2020-07-09_at_10.11.24.png)

::: column.grow

Khi chúng ta phóng to trên phạm vi ngày nhỏ hơn, ta thấy rằng số lượng ca nhiễm lũy tích tạo ra những bước nhảy vọt lớn vào một số ngày. Tốc độ biến đổi trung bình có thể làm trơn tru những bước nhảy này.

Điều này có thể đặc biệt hữu ích đối với các tập dữ liệu có giá trị ngoại lai lớn. Dữ liệu ngoại lai là dữ liệu khác biệt đáng kể so với các điểm dữ liệu khác. Trong thống kê, ta nhận ra rằng các giá trị ngoại lai có thể kéo giá trị trung bình và độ lệch chuẩn theo hướng của chúng.

:::

Điều tương tự có thể xảy ra ở đây với dữ liệu này. Những ngày có tỷ lệ tăng đặc biệt cao hoặc thấp có thể làm cho đồ thị bị lởm chởm. Tốc độ biến đổi trung bình có thể giúp làm mịn đồ thị và có lẽ giúp ta hiểu về những gì đang diễn ra trong một khoảng thời gian cụ thể. Bí quyết là điều chỉnh khoảng thời gian ở kích thước thích hợp. Ta sẽ xem xét điều này nhiều hơn trong [thống kê](/course/statistics).

---

Tốc độ biến đổi trung bình cũng có thể cung cấp một cách để so sánh sự biến đổi giữa các quốc gia khác nhau. Hãy so sánh các ca nhiễm lũy tích ở [USA](target:1_USAgraph) và [Italy](target:2_ITgraph) vào tháng 3 năm 2020.

{.fixme} Học sinh có thể sử dụng kí hiệu chữ thập để đọc dữ liệu từ biểu đồ. Họ cũng có thể vẽ các đường giữa điểm gây chú ý (như đã lưu ý trong bài) để hình dung tốc độ biến đổi.

![](/content/functions/images/6/Screenshot_2020-07-09_at_10.43.53.png)

::: column.grow

Chúng ta có thể thấy rằng Ý có số ca nhiễm lũy tích cao hơn cho đến tháng 3 [[27]]. Điều này có nghĩa là Ý có nhiều ca nhiễm COVID-19 hơn trong hầu hết tháng 3.

::: column(width=240)

![](/content/functions/images/6/Screenshot_2020-07-09_at_10.52.43.png)

:::

::: column.grow

Khi chúng ta xem xét tốc độ biến đổi trung bình của hai quốc gia trong khoảng thời gian từ ngày 9 tháng 3 đến ngày 18 tháng 3, ta thấy rằng số ca hàng ngày của Ý đang tăng hơn khoảng [[2]] nghìn ca mỗi ngày so với Hoa Kỳ.

Điều hợp lý là quốc gia có số ca mắc bệnh cao nhất sẽ có số ca mắc bệnh cao hơn mỗi ngày. Nhưng điều gì đó đặc biệt xảy ra trong khoảng thời gian từ ngày 19 đến ngày 26 tháng 3.

::: column(width=240)

![](/content/functions/images/6/Screenshot_2020-07-09_at_10.49.26.png)

:::

---

::: column.grow

Trong tuần này, tổng số ca nhiễm ở Hoa Kỳ vẫn thấp hơn Ý. Tuy nhiên, số ca nhiễm của Hoa Kỳ tăng nhanh hơn của Ý. Số ca nhiễm hàng ngày của Hoa Kỳ tăng nhanh hơn khoảng [[3]] nghìn ca mỗi ngày so với Ý!

Mặc dù nó có vẻ trái ngược với mong đợi của chúng ta, nhưng mối quan hệ kỳ lạ này giữa tốc độ biến đổi trung bình và tổng số ca là cách duy nhất mà số ca tổng cộng của Hoa Kỳ vượt qua Ý.

::: column(width=240)

![](/content/functions/images/6/Screenshot_2020-07-09_at_11.01.15.png)

:::

Như chúng ta đã thấy, tốc độ biến đổi trung bình có thể hữu ích giúp ta hiểu dữ liệu thống kê. Chúng cũng có thể giúp chúng ta hiểu các đối tượng đang chuyển động. Hãy cùng xem xét tốc độ biến đổi trong lặn SCUBA diving và sứ mệnh tàu con thoi.

---

### Lặn biển bằng bình dưỡng khí SCUBA Diving

::: column(width=240)

![](/content/functions/images/6/Screenshot_2020-07-02_at_13.03.48.png)

::: column.grow

Lặn biển Scuba diving (lặn biển sử dụng bình dưỡng khí) là một ngành công nghiệp trị giá XXX đô la trên toàn cầu. Mọi người đi du lịch đến các địa điểm để lặn ở những vùng nước mới và khác nhau. Với ngành công nghiệp XXX giải trí này đang phát triển, hướng dẫn cho người lặn an toàn là ưu tiên hàng đầu của các tổ chức như PADI và DAN. Áp suất của nước lên cơ thể con người cao hơn so với áp suất của nước trên mặt đất trong khí quyển. Và những áp lực đó càng tăng khi người lặn càng sâu.

::: column(width=240)

[Các video về Nhóm người lặn trong thời gian dừng an toàn tại Adobe Stock](https://stock.adobe.com/video/group-of-divers-during-safety-stop/122711283?prev_url=detail)

{.fixme} Video 14s tuyệt đẹp về điểm dừng an toàn

::: column.grow

Quy luật của khí và áp suất là không khí chúng ta hít thở, ngay cả với thiết bị lặn, có thể thay đổi XXX và XXX khi áp suất nước tăng lên. Sức nén này cần phải đảo ngược khi áp suất giảm khi một người lặn ngoi lên mặt nước. Nếu một người lặn nổi lên quá nhanh, các khí trong tế bào của họ sẽ không có thời gian để XXX - tạo ra bọt bóng trong các mô và khớp. Điều này có thể dẫn đến bệnh giảm áp. Để ngăn chặn điều này, những người lặn cần chú ý đến tốc độ đi lên của họ. Đúng vậy, tốc độ. Ý kiến là nên đi lên chậm hơn 10-15 mét mỗi phút.

::: column(width=240)

![](/content/functions/images/6/Screenshot_2020-07-09_at_13.28.42.png)

{.fixme} Có rất nhiều lựa chọn tuyệt vời trong Adobe Stock khi tìm kiếm: SS Thistlegorm.

::: column.grow

S.S. Thistlegorm là một trong 10 địa điểm lặn tìm xác tàu đắm hàng đầu trên thế giới. Con tàu Hải quân Thương gia Anh này bị chìm vào ngày 6 tháng 10 năm 1941 trong Chiến tranh thế giới thứ hai. Jacques Cousteau phát hiện ra xác tàu của cô vào đầu những năm 1950.

::: column.grow

Đây là thông tin chi tiết về độ sâu của lần lặn điển hình tới SS Thistlegorm. Ta gọi một đồ thị như thế này là một hàm **vị trí**. Các giá trị y cho chúng ta biết vị trí của người lặn so với mặt nước, trong khi trục x cho chúng ta biết *khi nào* họ đang ở bất kỳ vị trí nhất định nào.

Độ sâu tối đa của người lặn là khoảng [[30+-.25]] mét khoảng [[40+-2]] phút lặn. Ta hãy xem xét các đặc điểm chính khác trong đồ thị này. Chúng sẽ cung cấp cho ta phạm vi để tập trung khi nghĩ về việc liệu người lặn có nổi lên với tốc độ an toàn hay không. Gắn nhãn đồ thị với từng đặc điểm chính.

::: column(width=240)

![](/content/functions/images/6/Screenshot_2020-07-09_at_13.30.23.png)

{.fixme} Trên đây là mô phỏng của một mô tả sơ lược thực tế hơn. Nối nó với các yếu tố nhiễu của hình ảnh bên dưới.

![](https://upload.wikimedia.org/wikipedia/commons/d/db/Dive_computer_recorded_profile_example.png)

[image citation](https://en.wikipedia.org/wiki/File:Dive_computer_recorded_profile_example.png)

:::

{.fixme} Thiết kế thẻ cho các từ dưới đây. Học sinh kéo đến đồ thị trên.

::: column(width=100)

hoành độ giao điểm với trục Ox

giá trị lơn nhất

hoành độ giao điểm với trục Ox

::: column(width=100)

tăng

tăng

tăng

::: column(width=100)

giảm

giảm

giảm

:::

Lưu ý rằng đồ thị có một loạt các đỉnh và khoảng lõm. Các điểm cao và thấp dường như ngẫu nhiên này được gọi là "nhiễu". Nhiều yếu tố khác nhau có thể đóng góp vào dữ liệu như thế này. Kết quả đo GPS thường bị nhiễu do kết nối giữa máy tính của người lặn và vệ tinh bị mất hiệu lực.

Ta có thể sử dụng tốc độ biến đổi trung bình để làm mịn đồ thị này giống như ta đã làm trong đồ thị COVID-19 ở trên.

::: column(width=240)

![](/content/functions/images/6/Screenshot_2020-07-09_at_13.52.19.png)

{.fixme} Trên đây là mô phỏng của một mô tả sơ lược thực tế hơn. Nối nó với các yếu tố nhiễu của hình ảnh bên dưới.

![](/content/functions/images/6/Screenshot_2020-07-02_at_14.41.47.png)

::: column.grow

Ta thấy rằng hàm số vị trí của người lặn tăng lên ít nhiều từ (45, -30) đến ([[60+-5, [[0]]). Hai điểm này cung cấp cho ta đủ thông tin để tính toán **tốc độ biến đổi trung bình** của người lặn là [[2]] mét mỗi phút, thấp hơn rất nhiều so với ngưỡng 10-15 mét mỗi phút. Cho đến giờ, có vẻ như người lặn này ngăn ngừa được bệnh giảm áp.

::: column(width=240)

![](/content/functions/images/6/Screenshot_2020-07-09_at_13.56.16.png)

{.fixme} Trên đây là mô phỏng của một mô tả sơ lược thực tế hơn. Nối nó với các yếu tố nhiễu của hình ảnh bên dưới.

![](/content/functions/images/6/Screenshot_2020-07-02_at_14.46.02.png)

::: column.grow

Tuy nhiên, hãy lưu ý rằng tốc độ tăng không phải là hằng số. Người lặn dường như đã nghỉ giải lao trên đường đi.

Điều này đặt ra câu hỏi - liệu người lặn đã bao giờ vượt quá tốc độ nổi lên được khuyến nghị chưa?

:::

Để trả lời câu hỏi này, chúng ta có thể [đặt các điểm](target:1_point, target:2_point) trên đồ thị cho biết các đoạn chúng ta muốn tách biệt. Đường thẳng đi qua hai trong hai điểm này được gọi là cát tuyến](gloss:secant). Chúng ta có thể so sánh **cát tuyến** với đồ thị thực tế. [Khoảng cách](target:1_distance) giữa hai điểm cho chúng ta biết tốc độ biến đổi trung bình giữa hai điểm chính xác như thế nào so với những gì đồ thị cho ta thấy.

Sử dụng thanh trượt để xem việc thay đổi số lượng trung bình ảnh hưởng như thế nào đến tốc độ biến đổi trung bình tương đối.

{.fixme} Trạng thái gần đúng cho thanh trượt. Thiết kế tương tự cho dữ liệu "độ sâu so với thời gian". Các hình ảnh là mô phỏng dựa trên dữ liệu cũ.

![](/content/functions/images/6/Screenshot_2020-07-02_at_14.47.24.png)

![](/content/functions/images/6/Screenshot_2020-07-02_at_14.48.09.png)

![](/content/functions/images/6/Screenshot_2020-07-02_at_14.48.36.png)

Càng có nhiều đường biểu diễn tốc độ biến đổi trung bình, thì các đường cát tuyến biểu thị càng [[gần với | xa hơn]] đồ thị. Chọn các phát biểu đúng khác.

{.fixme} Nhiều lựa chọn

Hệ số góc của đường cát tuyến càng gần với tốc độ biến đổi trên đồ thị các ca lũy tích giữa các điểm giao nhau.

Hệ số góc của đường cát tuyến càng xa với tốc độ biến đổi trên đồ thị các ca lũy tích giữa các điểm giao nhau.

Khoảng cách giữa đường cát tuyến và đồ thị các ca lũy tích tăng lên.

Khoảng cách giữa đường cát tuyến và đồ thị các ca lũy tích giảm xuống

Hệ số góc của đường cát tuyến thay đổi.

---

{.fixme} Thiết kế tương tự cho dữ liệu "độ sâu so với thời gian". Hình ảnh bên dưới là mô phỏng với dữ liệu cũ.

::: column(width=240)

![](/content/functions/images/6/Screenshot_2020-07-02_at_15.06.21.png)

{.fisxme} Chỉ làm nổi bật một số yếu tố nhiễu. Ta có thể quyết định mức độ chi tiết mà ta muốn ở đây.

::: column.grow

Dữ liệu dựa trên việc đọc GPS như thế này thường có rất nhiều "nhiễu", hoặc các điểm có vẻ không phù hợp với xu hướng chung của các điểm còn lại. Một cách để giải quyết với những điểm như thế này là coi chúng là những điểm bất thường. Tốc độ biến đổi trung bình nên loại bỏ những điểm nhiễu này.

::: column(width=240)

![](/content/functions/images/6/Screenshot_2020-07-02_at_15.16.57.png)

{.fixme} Độ chính xác cấp độ giả lập.

::: column.grow

Những đường phù hợp nhất như thế này làm giảm hoặc loại bỏ nhiễu từ GPS. Từ đây, chúng ta có thể xác định xem liệu người lặn có vượt quá tốc độ nổi lên an toàn hay không.

Để làm điều này, ta sẽ xem xét *nhiều* tốc độ biến đổi trung bình.

::: column(width=240)

![](/content/functions/images/6/Screenshot_2020-07-02_at_15.22.50.png)

::: column.grow

{.fixme} Đưa thanh trượt về không. Mục tiêu là tiếp tuyến. Bạn dường như đã biết rõ ràng về những gì tính năng này sẽ có. Ta có thể mô phỏng điều gì đó nếu bạn muốn, nhưng nó có vẻ đó không phải là ưu tiên lớn nhất trong chương này.

:::

Khi ta thêm nhiều đường xấp xỉ tốc độ biến đổi, hai điểm trên đồ thị sẽ gần nhau hơn. Khi khoảng cách này trở nên rất nhỏ, tốc độ biến đổi trung bình xấp xỉ với **tốc độ biến đổi tức thời**.

---

Di chuyển đường dọc theo đồ thị vị trí để xem tốc độ biến đổi tức thời thay đổi như thế nào.

Đường này được gọi là **[tiếp tuyến] (gloss:tangent)**. Nó chỉ chạm vào đồ thị vị trí tại một điểm so với cát tuyến thì cắt đồ thị tại hai điểm. Hệ số góc của tiếp tuyến là **tốc độ biến đổi tức thời** của người lặn.

Ta có thể vẽ các hệ số góc của các đường tiếp tuyến trên một đồ thị mới. Lưu ý trục hoành là thời gian kể từ khi bắt đầu lặn. Trục tung là tốc độ đi lên và xuống của người lặn.

{.fixme} Có vẻ như nó sẽ hoạt động tốt nhất với các thanh trượt *hơn*, lần này di chuyển thời gian giống như thay đổi hoặc như một dạng hoạt ảnh thực tế. Hình ảnh là mô phỏng trạng thái.

![](/content/functions/images/6/Screenshot_2020-07-09_at_14.16.53.png)

![](/content/functions/images/6/Screenshot_2020-07-09_at_14.17.08.png)

Đồ thị vị trí và tốc độ trông rất khác nhau nhưng được tạo từ cùng một dữ liệu. Đồ thị vị trí hữu ích nhất để biết chính xác độ sâu của người lặn trong bất kỳ thời điểm nào trong quá trình lặn. Đồ thị tốc độ hữu ích nhất để biết người lặn đã điều chỉnh quá trình giảm áp suất của họ tốt như thế nào. Giá trị y lớn nhất trên đồ thị tốc độ là khoảng [[8+-.2]] mét trên phút, vì vậy người lặn đã chăm sóc tốt cho việc giảm áp suất của họ.

---

Nối công dụng/thông tin với đồ thị thích hợp

::: column(width=100)

vị trí trong hồ bơi

quãng đường đua

race time

thời gian của lượt

::: column(width=100)

khi anh ấy mệt mỏi

tốc độ trong quãng đường đầu tiên

tốc độ trong quãng đường thứ hai

phần chậm nhất của cuộc đua

mối quan hệ với những vận động viên bơi lội khác

::: column(width=100)

đồ thị vị trí

đồ thị vận tốc

:::

Mối quan hệ giữa hai đồ thị này, thực sự giữa hai hàm được biểu diễn bằng đồ thị, được gọi là **[đạo hàm](gloss:derivative)**. Cụ thể, đồ thị vận tốc là đạo hàm của đồ thị vị trí. Mối quan hệ này tồn tại với nhiều hàm số. Đạo hàm có thể cung cấp thông tin hữu ích được ẩn trong đồ thị vị trí. Trong trường hợp này, người lặn có thể nhanh chóng xác định xem liệu anh ấy/cô ấy/họ có nằm trong các khuyến nghị an toàn cho bệnh giảm áp hay không.

Hãy xem xét một ứng dụng khác của đạo hàm.

---

### Khám phá tàu con thoi

{.fixme} Dữ liệu từ: https://www.nasa.gov/pdf/522588main_AP_ED_Phys_ShuttleLaunch.pdf

Tàu con thoi *Discovery* là một trong những tàu con thoi trong chương trình tàu con thoi của NASA. Riêng Discovery đã phóng và hạ cánh 39 lần trong khoảng 27 năm từ 1984 đến 2011. Các sứ mệnh của nó bao gồm cả nhiệm vụ nghiên cứu và lắp ráp cho Trạm vũ trụ quốc tế.

Các chuyến bay của tàu con thoi như Discovery được chia thành bốn giai đoạn: đi lên, đi vào, quỹ đạo và điểm hẹn. Đây là [đồ thị độ cao](target:1_altgraph) cho giai đoạn đi lên của một trong những sứ mệnh của tàu Discovery. Tàu con thoi cần đạt tốc độ ít nhất 7.85 km/giây để đạt được quỹ đạo. Ta sẽ cần đồ thị tốc độ để xác định xem khi nào tàu Discovery đạt đến tốc độ này.

{.fixme} Học sinh sử dụng công cụ tiếp tuyến tương tự như trên để vẽ đồ thị tốc độ. Hình ảnh bên dưới là mô hình trạng thái.

![](/content/functions/images/6/Screenshot_2020-07-08_at_15.09.45.png)

Trục hoành sẽ dễ đọc hơn nếu đường lưới ở đơn vị phút (ví dụ: 60, 120, v.v.).

![](/content/functions/images/6/Screenshot_2020-07-08_at_14.53.25.png)

Tàu Discovery không đạt được tốc độ cần thiết vào khoảng [[470+-10]] giây. Nó chỉ mất khoảng [[25+-5]] giây để phá vỡ rào cản âm thanh với tốc độ 343 mét/giây. Đó là một sự thay đổi đáng kinh ngạc về tốc độ. Tàu con thoi bay từ 0 đến hơn 343 mét/giây trong khoảng nửa phút. Đó là [gia tốc](gloss:acceleration) sẽ kéo một phi hành gia về chỗ ngồi của họ.

Trên thực tế, sự an toàn của phi hành đoàn và thiết bị đòi hỏi gia tốc của tàu con thoi phải ở mức dưới 29 mét mỗi `giây^2`.

Chúng ta thường nghĩ về gia tốc đối với những chiếc xe hơi nhanh. Hãy nghĩ "Chiếc Ferrari này đi từ 0 đến 100 km một giờ trong 2.4 giây!" **Gia tốc** thực chất là đạo hàm của vận tốc. Điều đó có nghĩa là gia tốc đo sự biến đổi của tốc độ trong một thời gian nhất định. Hãy xem làm thế nào gần đến giới hạn an toàn là 29 mét mỗi `giây^2'.

{.fixme} Học sinh sử dụng công cụ tiếp tuyến tương tự như trên để vẽ đồ thị gia tốc. Các hình ảnh là mô phỏng trạng thái.

![](/content/functions/images/6/Screenshot_2020-07-08_at_15.09.45.png)

{.fixme} Trục hoành sẽ dễ đọc hơn nếu đường lưới chia ở phút (ví dụ: 60, 120, v.v.).

![](/content/functions/images/6/Screenshot_2020-07-08_at_14.53.25.png)

![](/content/functions/images/6/Screenshot_2020-07-08_at_15.16.08.png)

Gia tốc tối đa trong giai đoạn đi lên này là khoảng [[28+-1]] mét trên giây, chỉ ở giới hạn an toàn. Hãy nhớ rằng tàu Discovery chỉ mất khoảng 30 giây để phá vỡ tốc độ âm thanh. Gia tốc ở giây thứ 30 là [[17+-2]] mét trên `giây^2', thậm chí không gần với gia tốc tối đa mà phi hành đoàn và tàu con thoi trải nghiệm sau đó trong giai đoạn đi lên.

Giai đoạn đi lên của tàu bao gồm một số sự kiện giữa khi cất cánh và khi lên đến quỹ đạo. Các biến thiên nhỏ trong đồ thị vị trí và đồ thị vận tốc thể hiện dưới dạng bước nhảy lớn trong đồ thị gia tốc. Kéo các sự kiện đến vị trí tương ứng của chúng trên đồ thị gia tốc. Một số sự kiện là các điểm đơn lẻ trên đồ thị và những sự kiện khác là toàn bộ các phần của đồ thị.

{.fixme} Các thẻ thiết kế cho mỗi đường bên dưới

::: column(width=100)

Tàu con thoi cất cánh

Tách Rocket Booster vững chắc

Ngắt động cơ chính 

::: column(width=100)

Động cơ chính của tàu con thoi làm gia tốc thay đổi trơn tru

Tách bể bên ngoài

::: column(width=100)

Tốc độ biến đổi gia tốc âm (lực cản không khí lớn)

Gia tốc không đổi (3 g’s)

Vào quỹ đạo

:::

---

Từ sự lây lan của virus đến sự giảm áp suất lặn đến các chuyến bay vào vũ trụ, mối quan hệ giữa vận tốc và vị trí không đổi. Vận tốc là đạo hàm của vị trí. Đồ thị ở vị trí nào thể hiện độ dốc, đồ thị vận tốc thể hiện điểm tọa độ nào. Tiếp tục thực hành trực quan mối quan hệ này bằng cách nối các đồ thị vị trí ở bên trái với đồ thị vận tốc ở bên phải.

{.fixme} xáo trộn các thẻ bên dưới. Học sinh hãy nối lại.

![](/content/functions/images/6/chart.png)

![](/content/functions/images/6/chart_(3).png)

![](/content/functions/images/6/chart_(5).png)

![](/content/functions/images/6/chart_(7).png)

![](/content/functions/images/6/chart_(9).png)

![](/content/functions/images/6/chart_(11).png)

![](/content/functions/images/6/chart_(1).png)

![](/content/functions/images/6/chart_(2).png)

![](/content/functions/images/6/chart_(4).png)

![](/content/functions/images/6/chart_(6).png)

![](/content/functions/images/6/chart_(8).png)

![](/content/functions/images/6/chart_(10).png)
