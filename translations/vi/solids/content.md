# Các hình khối 3D

## Giới thiệu

> section: introduction
> sectionStatus: dev
> color: "#4E53D0"
> level: Foundations

     
   // Nhận xét chung: - Tôi thấy sự pha trộn giữa cốt truyện lịch sử và các tương tác rất hấp dẫn. - Cân nhắc thêm một vài loại câu hỏi 'kiểm tra sự hiểu biết' để chia nhỏ văn bản và chuyển từ mục / tiểu mục này sang cái khác. - Tư duy không gian có thể mất nhiều công sức đối với một số học sinh. Cân nhắc việc thêm các lời nhắc của người hướng dẫn dành riêng cho chủ đề mà bạn đang thảo luận. -Hãy nghĩ về việc chuẩn hóa cách bạn muốn viết 2D và 3D +philipp@mathigon.org sẽ giúp ích rất nhiều ở đây. - Các chuyển tiếp và tham chiếu cốt truyện giảm dần về cuối chương. Tôi rất vui khi thấy cái này hoạt động!

   // Mục thuật ngữ - Kích thước (chiều): Kích thước trong toán học là thước đo kích cỡ hoặc khoảng cách của một đối tượng.
Cho đến nay, chúng ta mới chỉ xem xét hình học phẳng, 2 chiều như hình tròn hoặc hình chữ nhật - nhưng chúng ta đang sống trong một thế giới ba chiều. Mỗi đối tượng mà chúng ta nhìn thấy hoặc chạm vào đều có ba __chiều__.
:: column.fit

    figure: x-img(src="images/ch1_2.gif" width="300" height="300")

::: column.grow

Một điểm có 0 kích thước. Một điểm chỉ xác định một vị trí nhưng nó không có kích thước.

Một đường thẳng có một kích thước, chúng ta có thể đo chiều dài của nó (l), nhưng nó không có chiều rộng hoặc chiều dày.

Một hình vuông có hai kích thước, chúng ta có thể đo chiều dài (l), và vuông góc với chiều dài, chiều rộng (w).

Một hình lập phương có ba kích thước, ta có thể đo chiều dài của nó (l); chiều rộng (w); và vuông góc với cả hai kích thước đó, ta có chiều cao của nó (h).

:::

---

Hình học phẳng nghiên cứu về các điểm, đường thẳng và các hình dạng hai chiều (2D) như đa giác và hình tròn không có độ dày. __Đa giác__ là hình phẳng chỉ có chiều dài và chiều rộng.

Hình học không gian là nghiên cứu về các hình dạng ba chiều (3D) có chiều sâu hoặc độ dày cũng như chiều dài và chiều rộng. Ngay cả một tờ giấy cũng có độ dày và là hình dạng 3D, nhưng vì độ dày của nó quá nhỏ nên chúng ta thường bỏ qua nó.
    // Trang 2

::: column.fit

    figure: x-img(src="images/ch1_42.jpg" width="200" height="133")

::: column.grow

Ngay sau khi loài người bắt đầu xây dựng các tòa nhà phức tạp, chúng ta cần hình học không gian. Trong một số văn bản của người Babylon và Ai Cập, bạn có thể thấy rằng họ quan tâm đến các vấn đề liên quan đến kích thước của các kim tự tháp và các cấu trúc khác mà họ đã thực hiện.

Kể từ đó, các kiến ​​trúc sư đã sử dụng hình học 3D để xác định hình dạng không gian của một tòa nhà. Ngày nay, thiết kế của các tòa nhà đang không ngừng phát triển bằng cách kết hợp các hình dạng 3D khác nhau và các đặc tính của chúng.
:::

::: column(width=300)

    // https://commons.wikimedia.org/wiki/File:Barcelona_Cube-Ball-Pyramid_roof.jpg
    figure: x-img(src="images/ch1_26.png" width="300" height="225")

{.caption} Barcelona Cube-Ball-Pyramid roof

::: column(width=300)

    // https://www.frazierdeeter.com/nationally-ranked-u-s-accounting-and-advisory-firm-expands-to-u-k/london-skyline/
    figure: x-img(src="images/ch1_18.png" width="300" height="188.5")

{.caption} London Skyline

:::

---
> id: examples

Giống như chúng tôi đã phân loại các hình phẳng thành một số loại như đa giác hoặc tứ giác, chúng tôi có thể phân loại hình khối 3D thành một số loại khác nhau:

__Một khối đa diện(polyhedron) là một khối hình học ba chiều có các mặt phẳng. Số nhiều của khối đa diện là "các khối đa diện" (polyhedra).__
Từ đa diện xuất phát từ tiếng Hy Lạp Cổ điển là poly (nhiều) + hedron (cơ sở, mặt)

::: column.fit

    x-polyhedron(size=200 shape="Cube")

::: column.fit

    x-polyhedron(size=200 shape="Octahedron")

::: column.fit

    x-polyhedron(size=200 shape="Dodecahedron")

::: column.fit

    x-polyhedron(size=200 shape="Tetrahedron")

::: column.fit

    x-polyhedron(size=200 shape="PentagonalPrism")

::: column.fit

    x-polyhedron(size=200 shape="StellatedDodecahedron")

:::

---

> id: poly-parts

Khối đa diện có nhiều hình dạng và kích thước khác nhau giống như hình đa giác.
Chúng có thể đơn giản như một khối lập phương hoặc một kim tự tháp, hoặc phức tạp như một đa diện hình sao với nhiều cạnh.

    // Trang 3

    // INTERACTIVE-1.01: Các phần của khối đa diện

    // Một công cụ phóng to tương tác để hiển thị các phần của khối đa diện với các định nghĩa

    figure: x-polyhedron(size=400 shape="Icosahedron" rotate=0)

   // Liên kết bảng chú giải thuật ngữ

 MẶT: Các đa giác tạo nên mặt của hình đa diện.
 CẠNH: Các đoạn thẳng mà hai mặt của nó được nối với nhau.
 ĐỈNH: "Giao điểm của các cạnh" của một hình đa diện được gọi là các đỉnh của nó.

---

> id: poly-ident

Những hình khối nào trong số các hình khối này là khối đa diện?

::: x-binary-swipe(a-title="Polyhedra" b-title="Not Polyhedra")

::: div.card.c-teal(solution="a")

    figure: x-polyhedron(size=150 shape="OpenBox")

:::

::: div.card.c-green(solution="a")

    figure: x-polyhedron(size=150 shape="AngularCylinder")

:::

::: div.card.c-orange(solution="b")

    figure: x-solid.cone(size=150)

:::

::: div.card.c-blue(solution="b")

    figure: x-solid.cylinder(size=150)

:::

::: div.card.c-yellow(solution="a")

    figure: x-polyhedron(size=150 shape="Stair")

:::

::: div.card.c-teal(solution="b")

    figure: x-solid.sphere(size=150)

:::

:::

---

Mặc dù chúng ta đang sống trong thế giới 3D, việc nắm bắt các hình dạng 3D và đặc tính của chúng có thể là một thách thức.

    // Trang 4

::: column(width=300)

    <div style="padding:56.25% 0 0 0;position:relative;"><iframe src="https://player.vimeo.com/video/8675372?title=0&byline=0&portrait=0" style="position:absolute;top:0;left:0;width:100%;height:100%;" frameborder="0" allow="autoplay; fullscreen" allowfullscreen></iframe></div><script src="https://player.vimeo.com/api/player.js"></script>

    // http://www.flatlandthemovie.com/index.html

::: column.grow

The Flatland là một bộ phim hoạt hình dựa trên cuốn sách Flatland: A Romance of Many Dimensions của Edwin Abbott. Bộ phim xoay quanh việc các hình dạng 2D không thể nắm bắt được chiều không gian thứ ba. Các nhân vật là hình tròn, hình tam giác và hình vuông sống trong thế giới 2D. Thực tế của họ tan vỡ khi một quả cầu từ Thế giới 3D đến thăm.
:::

---

Nếu không nhận ra, bạn sẽ thấy nhiều loại khối đa diện khác nhau trước đây:

::: column.grow

{.todo} IMAGE: Xúc sắc

::: column.grow

    figure: x-img(src="images/ch1_38.png" width="200" height="200")

Bóng đá bao gồm [[ngũ giác]] và [[lục giác]]. Các nhà toán học gọi hình dạng này là một khối đa diện 20 mặt bị cụt.

:::

---

Có một số điều không thể trong thế giới 2D lại có thể trở thành hiện thực trong 3D.

    // Trang 5

Hãy thử câu đố này ngay bây giờ.

Bạn có thể tạo ra 4 hình tam giác bằng nhau bằng cách sử dụng 6 cây tăm mà không cần uốn cong hoặc cắt chúng không?

    // TODO (LATER): INTERACTIVE-1.02: Câu đố tăm xỉa răng

    figure: x-img(src="images/ch1_toothpicks.png" width="434" height="262")

Bí quyết một lần nữa là suy nghĩ trong 3D thay vì 2D.

    // Trang 6

---

### Hình lập phương

Một trong những hình khối 3D phổ biến nhất là hình lập phương.

::: column.fit

    figure: x-img(src="images/ch1_47.png" width="106" height="80")

::: column.fit

    figure: x-img(src="images/ch1_27.png" width="80" height="80")

::: column.fit

    figure: x-img(src="images/ch1_5.png" width="80" height="80")

::: column.fit

    figure: x-img(src="images/ch1_7.png" width="142" height="80")

::: column.fit

    figure: x-img(src="images/ch1_9.png" width="142" height="80")

:::

Hình lập phương là một hình 3d có 6 mặt đều là [[hình vuông]].

::: column.fit

    figure: x-img(src="images/ch1_3.png" width="200" height="207")

::: column.grow

Ví dụ, Hình lập phương Rubik là một món đồ chơi cổ điển được phát minh vào năm 1974 bởi kiến ​​trúc sư và giáo sư thiết kế Erno Rubik người Hungary . Mỗi mặt của khối Rubik có 9 ô vuông màu.

Mặc dù một trong những khối nhỏ hơn (khối chính giữa) không được để lộ ra ngoài, nhưng nếu đếm cẩn thận, chúng ta thấy rằng khối Rubik được tạo thành từ [[27]] khối lập phương nhỏ hơn có thể xoay được sắp xếp trong một lưới 3x3x3.

:::

---

Một hình lập phương có tất cả các cạnh cùng độ dài. Nếu độ dài của tất cả các cạnh của nó là 1 đơn vị thì nó được gọi là hình lập phương đơn vị. Các hình lập phương đơn vị có thể được xếp chồng lên nhau để tạo ra các khối 3D khác nhau.

Các khối 3D bên dưới bao gồm các hình lập phương đơn vị. Chúng ta có thể tìm ra số lượng các hình lập phương được dùng trong mỗi hình này trong đó bao gồm cả các hình lập phương ẩn?

Xoay các khối dưới đây để tìm số lượng các hình lập phương được sử dụng để xây dựng chúng.
    // https://www.nctm.org/Classroom-Resources/Illuminations/Interactives/Isometric-Drawing-Tool/

::: column(width=300)

    figure
      x-voxel-painter(width=300 height=300 shape="0.0,1.0,-1.5,0.0,2.0,-1.5,0.0,3.0,-1.5,1.0,0.0,-1.5,2.0,0.0,-1.5,3.0,0.0,-1.5,0.0,0.0,-0.5,0.0,1.0,-0.5,0.0,2.0,-0.5,1.0,0.0,-0.5,2.0,0.0,-0.5,0.0,0.0,0.5,0.0,1.0,0.5,1.0,0.0,0.5,0.0,0.0,1.5,0.0,0.0,-1.5" playingFieldSize="7" color="rgb(237, 140, 200)" rotateOnly hideGrid explodeOnGrab)

[[16]] cubes

::: column(width=300)

    figure
      x-voxel-painter(width=300 height=300 shape="0.0,0.0,-1.0,0.0,0.0,1.0,0.0,1.0,-1.0,1.0,0.0,-1.0,1.0,1.0,-1.0,-1.0,0.0,-1.0,0.0,-1.0,-1.0,-1.0,-1.0,-1.0,1.0,-1.0,-1.0,-1.0,1.0,-1.0,0.0,1.0,0.0,1.0,0.0,0.0,1.0,1.0,0.0,-1.0,0.0,0.0,0.0,0.0,0.0,0.0,-1.0,0.0,-1.0,-1.0,0.0,1.0,-1.0,0.0,-1.0,1.0,0.0,0.0,2.0,-1.0,1.0,2.0,-1.0,-1.0,2.0,-1.0,0.0,-2.0,-1.0,1.0,-2.0,-1.0,-1.0,-2.0,-1.0,-2.0,0.0,-1.0,-2.0,-1.0,-1.0,-2.0,1.0,-1.0,-2.0,2.0,-1.0,-2.0,-2.0,-1.0,2.0,0.0,-1.0,2.0,-1.0,-1.0,2.0,1.0,-1.0,2.0,2.0,-1.0,2.0,-2.0,-1.0" playingFieldSize="8" color="blue" rotateOnly hideGrid explodeOnGrab)

[[35]] cubes

:::

    // Trang 7

---

### Hình hộp chữ nhật

::: column.grow

Giống như một hình vuông là hình chữ nhật, một hình lập phương cũng là một hình hộp chữ nhật
A__Cuboid__ là một hình hộp, trong đó tất cả sáu cạnh đều là hình chữ nhật. Ví dụ, hộp đựng bánh pizza, ngũ cốc hay giày đều là hình hộp chữ nhật.

Hình hộp chữ nhật là một số khối đa diện phổ biến nhất mà chúng ta sử dụng hàng ngày.

    // TODO: INTERACTIVE-1.03: Hình hộp chữ nhật với các bộ phận được dán nhãn

::: column.fit

    figure: x-img(src="images/ch1_10.jpg" width="200" height="156")

:::

---
> id: cuboid-parts

    figure: x-polyhedron(size=400 shape="Cube" rotate=0)

Về cơ bản, hình hộp chữ nhật là một hình đa diện có sáu mặt hình chữ nhật. Các mặt đối diện của hình hộp chữ nhật giống hệt nhau và song song với nhau. Hình hộp chữ nhật có [[12]] cạnh, [[8]] đỉnh.
::: column(width=200)

    figure: x-img(src="images/ch1_8.png" width="200" height="200")

::: column.grow

Một hộp bánh pizza trung bình có kích thước là 33 cm x 33 cm x 4 cm. Nghĩa là nó có chiều dài 33 cm, chiều rộng 33 cm và chiều cao hoặc chiều sâu 4 cm.
Đôi khi một hình hộp chữ nhật có hai mặt vuông và bốn mặt hình chữ nhật giống như hầu hết các hộp bánh pizza.

:::

---

    // Trang 8

Một hộp ngũ cốc trung bình có kích thước 30 cm x 20 cm x 8 cm.

::: column.fit

    figure: x-img(src="images/ch1_46.png" width="301" height="189")

::: column.grow

Một công ty quảng cáo đã làm một hộp ngũ cốc có nắp đậy cao 6 mét bên ngoài Phòng trưng bày Nghệ thuật Vancouver vào năm 2012.
Bạn có đoán được kích thước của hộp ngũ cốc này không?
Chiều dài: [[4 m]] Chiều rộng: [[1,6 m]] Chiều cao: 6 m
Hộp ngũ cốc là một hình hộp chữ nhật có sáu mặt [[hình chữ nhật]] .
:::

---

    figure: x-img(src="images/ch1_48.png" width="600" height="257")

Khi bạn cố gắng gửi những cái hộp từ nơi này đến nơi khác thông qua dịch vụ chuyển phát, công ty sẽ hỏi bạn kích thước của gói hàng ở dạng “d x r x c” để tính toán kích thước và trọng lượng của hộp để xác định mức phí vận chuyển.

Hãy thử xác định các kích thước của các hình hộp chữ nhật ở dạng “d x r x c”:

::: column(width=150)

    figure
      x-voxel-painter(width=150 height=200 shape="-0.5,0.0,-2.5,-0.5,1.0,-2.5,-0.5,-1.0,-2.5,0.5,-0.0,-2.5,0.5,-1.0,-2.5,0.5,1.0,-2.5,-0.5,0.0,-1.5,-0.5,1.0,-1.5,-0.5,-1.0,-1.5,0.5,-0.0,-1.5,0.5,-1.0,-1.5,-0.5,1.0,-3.5,0.5,1.0,-1.5,-0.5,-1.0,-3.5,-0.5,0.0,-3.5,0.5,-0.0,-3.5,0.5,-1.0,-3.5,0.5,1.0,-3.5,-0.5,0.0,-0.5,-0.5,1.0,-0.5,-0.5,-1.0,-0.5,0.5,-0.0,-0.5,0.5,-1.0,-0.5,0.5,1.0,-0.5,-0.5,0.0,0.5,-0.5,1.0,0.5,-0.5,-1.0,0.5,0.5,-0.0,0.5,0.5,-1.0,0.5,0.5,1.0,0.5,-0.5,0.0,1.5,-0.5,1.0,1.5,-0.5,-1.0,1.5,0.5,-0.0,1.5,0.5,-1.0,1.5,0.5,1.0,1.5,-0.5,0.0,2.5,-0.5,1.0,2.5,-0.5,-1.0,2.5,0.5,-0.0,2.5,0.5,-1.0,2.5,0.5,1.0,2.5,-0.5,0.0,3.5,-0.5,1.0,3.5,-0.5,-1.0,3.5,0.5,-0.0,3.5,0.5,-1.0,3.5,0.5,1.0,3.5" playingFieldSize="8" color="rgb(19,122,200)" rotateOnly hideGrid)

[[3]]x[[2]]x[[8]]

::: column(width=150)

    figure
      x-voxel-painter(width=150 height=200 shape="-0.0,-2.0,0.0,0.0,-1.0,0.0,0.0,1.0,0.0,-0.0,0.0,0.0,0.0,2.0,0.0" playingFieldSize="5" color="rgb(32,188,252)" rotateOnly hideGrid)

[[5]]x[[1]]x[[1]]

::: column(width=150)

    figure
      x-voxel-painter(width=150 height=200 shape="1.0,-1.0,-0.5,1.0,-2.0,-0.5,1.0,1.0,-0.5,1.0,0.0,-0.5,1.0,2.0,-0.5,2.0,-1.0,-0.5,2.0,-2.0,-0.5,2.0,1.0,-0.5,2.0,0.0,-0.5,2.0,2.0,-0.5,-2.0,-1.0,-0.5,-2.0,-2.0,-0.5,-2.0,1.0,-0.5,-0.0,-2.0,-0.5,0.0,-1.0,-0.5,0.0,1.0,-0.5,-0.0,0.0,-0.5,0.0,2.0,-0.5,-2.0,0.0,-0.5,-2.0,2.0,-0.5,-1.0,-1.0,-0.5,-1.0,-2.0,-0.5,-1.0,1.0,-0.5,-1.0,0.0,-0.5,-1.0,2.0,-0.5,-2.0,-1.0,0.5,-2.0,-2.0,0.5,-2.0,1.0,0.5,-2.0,0.0,0.5,-2.0,2.0,0.5,-1.0,-1.0,0.5,-1.0,-2.0,0.5,-1.0,1.0,0.5,-1.0,0.0,0.5,-1.0,2.0,0.5,0.0,-1.0,-2.5,-0.0,-2.0,-2.5,0.0,1.0,-2.5,-0.0,0.0,-2.5,0.0,2.0,-2.5,1.0,-1.0,-2.5,1.0,-2.0,-2.5,1.0,1.0,-2.5,1.0,0.0,-2.5,1.0,2.0,-2.5,2.0,-1.0,-2.5,2.0,-2.0,-2.5,2.0,1.0,-2.5,2.0,0.0,-2.5,2.0,2.0,-2.5,-2.0,-1.0,-2.5,-2.0,-2.0,-2.5,-2.0,1.0,-2.5,-2.0,0.0,-2.5,-2.0,2.0,-2.5,-1.0,-1.0,-2.5,-1.0,-2.0,-2.5,-1.0,1.0,-2.5,-1.0,0.0,-2.5,-1.0,2.0,-2.5,-2.0,-1.0,-1.5,-2.0,-2.0,-1.5,-2.0,1.0,-1.5,-2.0,0.0,-1.5,-2.0,2.0,-1.5,-1.0,-1.0,-1.5,-1.0,-2.0,-1.5,-1.0,1.0,-1.5,-1.0,0.0,-1.5,-1.0,2.0,-1.5,0.0,-1.0,1.5,-0.0,-2.0,1.5,0.0,1.0,1.5,-0.0,0.0,1.5,0.0,2.0,1.5,1.0,-1.0,1.5,1.0,-2.0,1.5,1.0,1.0,1.5,1.0,0.0,1.5,1.0,2.0,1.5,2.0,-1.0,1.5,2.0,-2.0,1.5,2.0,1.0,1.5,2.0,0.0,1.5,2.0,2.0,1.5,-2.0,-1.0,1.5,-2.0,-2.0,1.5,-2.0,1.0,1.5,-2.0,0.0,1.5,-2.0,2.0,1.5,-1.0,-1.0,1.5,-1.0,-2.0,1.5,-1.0,1.0,1.5,-1.0,0.0,1.5,-1.0,2.0,1.5,-2.0,-1.0,2.5,-2.0,-2.0,2.5,-2.0,1.0,2.5,-2.0,0.0,2.5,-2.0,2.0,2.5,-1.0,-1.0,2.5,-1.0,-2.0,2.5,-1.0,1.0,2.5,-1.0,0.0,2.5,-1.0,2.0,2.5,0.0,-1.0,0.5,-0.0,-2.0,0.5,0.0,1.0,0.5,-0.0,0.0,0.5,0.0,2.0,0.5,1.0,-1.0,0.5,1.0,-2.0,0.5,1.0,1.0,0.5,1.0,0.0,0.5,1.0,2.0,0.5,2.0,-1.0,0.5,2.0,-2.0,0.5,2.0,1.0,0.5,2.0,0.0,0.5,2.0,2.0,0.5,0.0,-1.0,-1.5,-0.0,-2.0,-1.5,0.0,1.0,-1.5,-0.0,0.0,-1.5,0.0,2.0,-1.5,1.0,-1.0,-1.5,1.0,-2.0,-1.5,1.0,1.0,-1.5,1.0,0.0,-1.5,1.0,2.0,-1.5,2.0,-1.0,-1.5,2.0,-2.0,-1.5,2.0,1.0,-1.5,2.0,0.0,-1.5,2.0,2.0,-1.5,0.0,-1.0,2.5,-0.0,-2.0,2.5,0.0,1.0,2.5,-0.0,0.0,2.5,0.0,2.0,2.5,1.0,-1.0,2.5,1.0,-2.0,2.5,1.0,1.0,2.5,1.0,0.0,2.5,1.0,2.0,2.5,2.0,-1.0,2.5,2.0,-2.0,2.5,2.0,1.0,2.5,2.0,0.0,2.5,2.0,2.0,2.5" playingFieldSize="7" color="rgb(205,110,252)" rotateOnly hideGrid)

[[5]]x[[5]]x[[6]]

::: column(width=150)

    figure
      x-voxel-painter(width=150 height=200 shape="0.0,-2.0,0.0,-1.0,-2.0,0.0,1.0,-2.0,0.0,0.0,-3.0,0.0,-1.0,-3.0,0.0,1.0,-3.0,0.0,-0.0,1.0,0.0,-1.0,1.0,0.0,1.0,1.0,0.0,0.0,0.0,0.0,-1.0,0.0,0.0,1.0,0.0,0.0,0.0,-1.0,0.0,-1.0,-1.0,0.0,1.0,-1.0,0.0,-0.0,3.0,0.0,-1.0,3.0,0.0,1.0,3.0,0.0,-0.0,2.0,0.0,-1.0,2.0,0.0,1.0,2.0,0.0" playingFieldSize="7" color="rgb(256,157,237)" rotateOnly hideGrid)

[[7]]x[[3]]x[[1]]

:::

---

    // Trang 9

### Thể tích

::: column.fit

    figure: x-img(src="images/ch1_36.png" width="200" height="138")

::: column.grow

Theo một truyền thuyết, đã có một trận dịch hạch tàn khốc ở Hy Lạp vào năm 430 TCN. Người Delian (công dân của một hòn đảo thuộc Hy Lạp, Delos) đã đến đền thờ thần Apollo, người đã nói với họ rằng bệnh dịch sẽ dừng lại khi họ ___ tăng gấp đôi thể tích của bàn thờ của ông ấy .___
:::

::: column.grow

{.todo} IMAGE

Đây là đoạn có__chiều dài 1__.

::: column.grow

{.todo} IMAGE

Một hình vuông mà tất cả các cạnh có độ dài là 1 có __diện tích 1__.

::: column.grow

{.todo} IMAGE

Một hình lập phương mà tất cả các cạnh có độ dài là 1 có __thể tích 1__.

:::


Chúng ta có thể tìm thể tích của các hình phức tạp hơn bằng cách xác định xem nó chứa bao nhiêu hình lập phương có thể tích 1.

Bàn thờ của thần Apollo là một ngôi đền hình lập phương với các kích thước chiều dài, chiều rộng và chiều cao là 5 mét.

Người Delian đã tăng gấp đôi các cạnh của bàn thờ, nhưng bệnh dịch vẫn chưa dừng lại. Có chuyện gì đã sai?

Một cách để tìm thể tích của hình hộp chữ nhật là lấp đầy vào hình hộp bằng các hình lập phương đơn vị.

Thể tích là số hình lập phương đơn vị lấp đầy một vùng 3D, không có bất kỳ khoảng trống hoặc chồng chéo nào.

---

> id: temple-display-1

Hãy nhìn vào bàn thờ của Apollo. Nếu chiều dài cạnh của bàn thờ ban đầu là 5 đơn vị, thì đáy của nó là một hình vuông 5x5 có [[25]] hình lập phương đơn vị.

::: column.fit

    figure
      x-voxel-painter(width=200 height=200 shape="" playingFieldSize="5" rotateOnly hideGrid)

::: column.grow

Chúng tôi tiếp tục lấp đầy bàn thờ bằng cách thêm nhiều hình lập phương hơn.
Lớp đầu tiên là một hình vuông 5 x 5 được xếp từ [[25]] hình lập phương
:::

---

> id: temple-filling

    // Trang 10

    figure
      x-voxel-painter(width=300 height=300 shape="" playingFieldSize="5" rotateOnly hideGrid)
    // TODO: Dùng thanh trượt

Sẽ có [[5]] lớp gồm 25 hình lập phương .
Phải có các hình lập phương `5 x 25 = input (125)` để lấp đầy toàn bộ bàn thờ.

---

_ Nghĩa là bàn thờ lúc đầu có thể tích 125 đơn vị thể tích .__

Người Delian đã không làm theo các hướng dẫn một cách cẩn thận. Họ [[gấp đôi mỗi cạnh]] của bàn thờ.
Hãy xem điều gì đã xảy ra khi họ nhân đôi cạnh.
::: column.fit

    figure
      x-voxel-painter(width=300 height=300 color="blue" shape="4.5,-2.5,4.6,4.5,-3.5,4.6,4.5,-4.5,4.6,4.5,2.5,4.6,4.5,1.5,4.6,4.5,0.5,4.6,4.5,-0.5,4.6,4.5,4.5,4.6,4.5,3.5,4.6,1.5,-4.5,4.6,2.5,-4.5,4.6,3.5,-4.5,4.6,-4.5,1.5,4.6,-2.5,-4.5,4.6,-1.5,-4.5,4.6,-0.5,-4.5,4.6,0.5,-4.5,4.6,-4.5,-4.5,4.6,-3.5,-4.5,4.6,-4.5,2.5,4.6,-4.5,3.5,4.6,-4.5,4.5,4.6,-4.5,-2.5,4.6,-4.5,-1.5,4.6,-4.5,-0.5,4.6,-4.5,0.5,4.6,4.5,-1.5,0.5,-4.5,-3.5,4.6,-1.5,4.5,4.6,-2.5,4.5,4.6,-3.5,4.5,4.6,2.5,4.5,4.6,1.5,4.5,4.6,0.5,4.5,4.6,-0.5,4.5,4.6,4.5,-2.5,0.5,3.5,4.5,4.6,4.5,-3.5,0.5,4.5,-4.5,0.5,4.5,2.5,0.5,4.5,1.5,0.5,4.5,0.5,0.5,4.5,-0.5,0.5,4.5,4.5,0.5,4.5,3.5,0.5,1.5,-4.5,0.5,2.5,-4.5,0.5,3.5,-4.5,0.5,-2.5,-4.5,0.5,-1.5,-4.5,0.5,-0.5,-4.5,0.5,0.5,-4.5,0.5,-4.5,-4.5,0.5,-3.5,-4.5,0.5,-4.5,1.5,0.5,-4.5,2.5,0.5,-4.5,3.5,0.5,-4.5,4.5,0.5,-4.5,-2.5,0.5,-4.5,-1.5,0.5,-4.5,-0.5,0.5,-4.5,0.5,0.5,-4.5,-3.5,0.5,-1.5,4.5,0.5,-2.5,4.5,0.5,-3.5,4.5,0.5,2.5,4.5,0.5,1.5,4.5,0.5,0.5,4.5,0.5,-0.5,4.5,0.5,3.5,4.5,0.5,3.5,-1.5,4.6,3.5,-2.5,4.6,3.5,-3.5,4.6,3.5,2.5,4.6,3.5,1.5,4.6,3.5,0.5,4.6,3.5,-0.5,4.6,3.5,3.5,4.6,2.5,-1.5,4.6,2.5,-2.5,4.6,2.5,-3.5,4.6,2.5,2.5,4.6,2.5,1.5,4.6,2.5,0.5,4.6,2.5,-0.5,4.6,2.5,3.5,4.6,1.5,-1.5,4.6,1.5,-2.5,4.6,1.5,-3.5,4.6,1.5,2.5,4.6,1.5,1.5,4.6,1.5,0.5,4.6,1.5,-0.5,4.6,1.5,3.5,4.6,0.5,-1.5,4.6,0.5,-2.5,4.6,0.5,-3.5,4.6,0.5,2.5,4.6,0.5,1.5,4.6,0.5,0.5,4.6,0.5,-0.5,4.6,0.5,3.5,4.6,-0.5,-1.5,4.6,-0.5,-2.5,4.6,-0.5,-3.5,4.6,-0.5,2.5,4.6,-0.5,1.5,4.6,-0.5,0.5,4.6,-0.5,-0.5,4.6,-0.5,3.5,4.6,-1.5,-1.5,4.6,-1.5,-2.5,4.6,-1.5,-3.5,4.6,-1.5,2.5,4.6,-1.5,1.5,4.6,-1.5,0.5,4.6,-1.5,-0.5,4.6,-1.5,3.5,4.6,-2.5,-1.5,4.6,-2.5,-2.5,4.6,-2.5,-3.5,4.6,-2.5,2.5,4.6,-2.5,1.5,4.6,-2.5,0.5,4.6,-2.5,-0.5,4.6,-2.5,3.5,4.6,-3.5,-1.5,4.6,-3.5,-2.5,4.6,-3.5,-3.5,4.6,-3.5,2.5,4.6,-3.5,1.5,4.6,-3.5,0.5,4.6,-3.5,-0.5,4.6,-3.5,3.5,4.6,4.5,-1.5,-4.5,4.5,-2.5,-4.5,4.5,-3.5,-4.5,4.5,-4.5,-4.5,4.5,2.5,-4.5,4.5,1.5,-4.5,4.5,0.5,-4.5,4.5,-0.5,-4.5,4.5,4.5,-4.5,4.5,3.5,-4.5,1.5,-4.5,-4.5,2.5,-4.5,-4.5,3.5,-4.5,-4.5,-2.5,-4.5,-4.5,-1.5,-4.5,-4.5,-0.5,-4.5,-4.5,0.5,-4.5,-4.5,-4.5,-4.5,-4.5,-3.5,-4.5,-4.5,-4.5,1.5,-4.5,-4.5,2.5,-4.5,-4.5,3.5,-4.5,-4.5,4.5,-4.5,-4.5,-2.5,-4.5,-4.5,-1.5,-4.5,-4.5,-0.5,-4.5,-4.5,0.5,-4.5,-4.5,-3.5,-4.5,-1.5,4.5,-4.5,-2.5,4.5,-4.5,-3.5,4.5,-4.5,2.5,4.5,-4.5,1.5,4.5,-4.5,0.5,4.5,-4.5,-0.5,4.5,-4.5,3.5,4.5,-4.5,3.5,-1.5,-4.5,3.5,-2.5,-4.5,3.5,-3.5,-4.5,3.5,2.5,-4.5,3.5,1.5,-4.5,3.5,0.5,-4.5,3.5,-0.5,-4.5,3.5,3.5,-4.5,2.5,-1.5,-4.5,2.5,-2.5,-4.5,2.5,-3.5,-4.5,2.5,2.5,-4.5,2.5,1.5,-4.5,2.5,0.5,-4.5,2.5,-0.5,-4.5,2.5,3.5,-4.5,1.5,-1.5,-4.5,1.5,-2.5,-4.5,1.5,-3.5,-4.5,1.5,2.5,-4.5,1.5,1.5,-4.5,1.5,0.5,-4.5,1.5,-0.5,-4.5,1.5,3.5,-4.5,0.5,-1.5,-4.5,0.5,-2.5,-4.5,0.5,-3.5,-4.5,0.5,2.5,-4.5,0.5,1.5,-4.5,0.5,0.5,-4.5,0.5,-0.5,-4.5,0.5,3.5,-4.5,-0.5,-1.5,-4.5,-0.5,-2.5,-4.5,-0.5,-3.5,-4.5,-0.5,2.5,-4.5,-0.5,1.5,-4.5,-0.5,0.5,-4.5,-0.5,-0.5,-4.5,-0.5,3.5,-4.5,-1.5,-1.5,-4.5,-1.5,-2.5,-4.5,-1.5,-3.5,-4.5,-1.5,2.5,-4.5,-1.5,1.5,-4.5,-1.5,0.5,-4.5,-1.5,-0.5,-4.5,-1.5,3.5,-4.5,-2.5,-1.5,-4.5,-2.5,-2.5,-4.5,-2.5,-3.5,-4.5,-2.5,2.5,-4.5,-2.5,1.5,-4.5,-2.5,0.5,-4.5,-2.5,-0.5,-4.5,-2.5,3.5,-4.5,-3.5,-1.5,-4.5,-3.5,-2.5,-4.5,-3.5,-3.5,-4.5,-3.5,2.5,-4.5,-3.5,1.5,-4.5,-3.5,0.5,-4.5,-3.5,-0.5,-4.5,-3.5,3.5,-4.5,4.5,-1.5,1.5,4.5,-2.5,1.5,4.5,-3.5,1.5,4.5,-4.5,1.5,4.5,2.5,1.5,4.5,1.5,1.5,4.5,0.5,1.5,4.5,-0.5,1.5,4.5,4.5,1.5,4.5,3.5,1.5,1.5,-4.5,1.5,2.5,-4.5,1.5,3.5,-4.5,1.5,-2.5,-4.5,1.5,-1.5,-4.5,1.5,-0.5,-4.5,1.5,0.5,-4.5,1.5,-4.5,-4.5,1.5,-3.5,-4.5,1.5,-4.5,1.5,1.5,-4.5,2.5,1.5,-4.5,3.5,1.5,-4.5,4.5,1.5,-4.5,-2.5,1.5,-4.5,-1.5,1.5,-4.5,-0.5,1.5,-4.5,0.5,1.5,-4.5,-3.5,1.5,-1.5,4.5,1.5,-2.5,4.5,1.5,-3.5,4.5,1.5,2.5,4.5,1.5,1.5,4.5,1.5,0.5,4.5,1.5,-0.5,4.5,1.5,3.5,4.5,1.5,4.5,-1.5,2.5,4.5,-2.5,2.5,4.5,-3.5,2.5,4.5,-4.5,2.5,4.5,2.5,2.5,4.5,1.5,2.5,4.5,0.5,2.5,4.5,-0.5,2.5,4.5,4.5,2.5,4.5,3.5,2.5,1.5,-4.5,2.5,2.5,-4.5,2.5,3.5,-4.5,2.5,-2.5,-4.5,2.5,-1.5,-4.5,2.5,-0.5,-4.5,2.5,0.5,-4.5,2.5,-4.5,-4.5,2.5,-3.5,-4.5,2.5,-4.5,1.5,2.5,-4.5,2.5,2.5,-4.5,3.5,2.5,-4.5,4.5,2.5,-4.5,-2.5,2.5,-4.5,-1.5,2.5,-4.5,-0.5,2.5,-4.5,0.5,2.5,-4.5,-3.5,2.5,-1.5,4.5,2.5,-2.5,4.5,2.5,-3.5,4.5,2.5,2.5,4.5,2.5,1.5,4.5,2.5,0.5,4.5,2.5,-0.5,4.5,2.5,3.5,4.5,2.5,4.5,-1.5,3.5,4.5,-2.5,3.5,4.5,-3.5,3.5,4.5,-4.5,3.5,4.5,2.5,3.5,4.5,1.5,3.5,4.5,0.5,3.5,4.5,-0.5,3.5,4.5,4.5,3.5,4.5,3.5,3.5,1.5,-4.5,3.5,2.5,-4.5,3.5,3.5,-4.5,3.5,-2.5,-4.5,3.5,-1.5,-4.5,3.5,-0.5,-4.5,3.5,0.5,-4.5,3.5,-4.5,-4.5,3.5,-3.5,-4.5,3.5,-4.5,1.5,3.5,-4.5,2.5,3.5,-4.5,3.5,3.5,-4.5,4.5,3.5,-4.5,-2.5,3.5,-4.5,-1.5,3.5,-4.5,-0.5,3.5,-4.5,0.5,3.5,-4.5,-3.5,3.5,-1.5,4.5,3.5,-2.5,4.5,3.5,-3.5,4.5,3.5,2.5,4.5,3.5,1.5,4.5,3.5,0.5,4.5,3.5,-0.5,4.5,3.5,3.5,4.5,3.5,4.5,-1.5,-3.5,4.5,-2.5,-3.5,4.5,-3.5,-3.5,4.5,-4.5,-3.5,4.5,2.5,-3.5,4.5,1.5,-3.5,4.5,0.5,-3.5,4.5,-0.5,-3.5,4.5,4.5,-3.5,4.5,3.5,-3.5,1.5,-4.5,-3.5,2.5,-4.5,-3.5,3.5,-4.5,-3.5,-2.5,-4.5,-3.5,-1.5,-4.5,-3.5,-0.5,-4.5,-3.5,0.5,-4.5,-3.5,-4.5,-4.5,-3.5,-3.5,-4.5,-3.5,-4.5,1.5,-3.5,-4.5,2.5,-3.5,-4.5,3.5,-3.5,-4.5,4.5,-3.5,-4.5,-2.5,-3.5,-4.5,-1.5,-3.5,-4.5,-0.5,-3.5,-4.5,0.5,-3.5,-4.5,-3.5,-3.5,-1.5,4.5,-3.5,-2.5,4.5,-3.5,-3.5,4.5,-3.5,2.5,4.5,-3.5,1.5,4.5,-3.5,0.5,4.5,-3.5,-0.5,4.5,-3.5,3.5,4.5,-3.5,4.5,-1.5,-2.5,4.5,-2.5,-2.5,4.5,-3.5,-2.5,4.5,-4.5,-2.5,4.5,2.5,-2.5,4.5,1.5,-2.5,4.5,0.5,-2.5,4.5,-0.5,-2.5,4.5,4.5,-2.5,4.5,3.5,-2.5,1.5,-4.5,-2.5,2.5,-4.5,-2.5,3.5,-4.5,-2.5,-2.5,-4.5,-2.5,-1.5,-4.5,-2.5,-0.5,-4.5,-2.5,0.5,-4.5,-2.5,-4.5,-4.5,-2.5,-3.5,-4.5,-2.5,-4.5,1.5,-2.5,-4.5,2.5,-2.5,-4.5,3.5,-2.5,-4.5,4.5,-2.5,-4.5,-2.5,-2.5,-4.5,-1.5,-2.5,-4.5,-0.5,-2.5,-4.5,0.5,-2.5,-4.5,-3.5,-2.5,-1.5,4.5,-2.5,-2.5,4.5,-2.5,-3.5,4.5,-2.5,2.5,4.5,-2.5,1.5,4.5,-2.5,0.5,4.5,-2.5,-0.5,4.5,-2.5,3.5,4.5,-2.5,4.5,-1.5,-1.5,4.5,-2.5,-1.5,4.5,-3.5,-1.5,4.5,-4.5,-1.5,4.5,2.5,-1.5,4.5,1.5,-1.5,4.5,0.5,-1.5,4.5,-0.5,-1.5,4.5,4.5,-1.5,4.5,3.5,-1.5,1.5,-4.5,-1.5,2.5,-4.5,-1.5,3.5,-4.5,-1.5,-2.5,-4.5,-1.5,-1.5,-4.5,-1.5,-0.5,-4.5,-1.5,0.5,-4.5,-1.5,-4.5,-4.5,-1.5,-3.5,-4.5,-1.5,-4.5,1.5,-1.5,-4.5,2.5,-1.5,-4.5,3.5,-1.5,-4.5,4.5,-1.5,-4.5,-2.5,-1.5,-4.5,-1.5,-1.5,-4.5,-0.5,-1.5,-4.5,0.5,-1.5,-4.5,-3.5,-1.5,-1.5,4.5,-1.5,-2.5,4.5,-1.5,-3.5,4.5,-1.5,2.5,4.5,-1.5,1.5,4.5,-1.5,0.5,4.5,-1.5,-0.5,4.5,-1.5,3.5,4.5,-1.5,4.5,-1.5,-0.5,4.5,-2.5,-0.5,4.5,-3.5,-0.5,4.5,-4.5,-0.5,4.5,2.5,-0.5,4.5,1.5,-0.5,4.5,0.5,-0.5,4.5,-0.5,-0.5,4.5,4.5,-0.5,4.5,3.5,-0.5,1.5,-4.5,-0.5,2.5,-4.5,-0.5,3.5,-4.5,-0.5,-2.5,-4.5,-0.5,-1.5,-4.5,-0.5,-0.5,-4.5,-0.5,0.5,-4.5,-0.5,-4.5,-4.5,-0.5,-3.5,-4.5,-0.5,-4.5,1.5,-0.5,-4.5,2.5,-0.5,-4.5,3.5,-0.5,-4.5,4.5,-0.5,-4.5,-2.5,-0.5,-4.5,-1.5,-0.5,-4.5,-0.5,-0.5,-4.5,0.5,-0.5,-4.5,-3.5,-0.5,-1.5,4.5,-0.5,-2.5,4.5,-0.5,-3.5,4.5,-0.5,2.5,4.5,-0.5,1.5,4.5,-0.5,0.5,4.5,-0.5,-0.5,4.5,-0.5,3.5,4.5,-0.5,4.5,-1.5,4.6" playingFieldSize="10" rotateOnly hideGrid)

::: column.grow

Khi chúng ta gấp đôi các cạnh của khối lập phương như người Delian đã làm với bàn thờ là không chính xác, sẽ có [[100]] khối lập phương và [[10]] lớp. Do đó, bàn thờ thứ hai mà họ xây dựng có thể tích là [[1000]] đơn vị thể tích.

Nhân đôi kích thước của một hình ba chiều sẽ làm thể tích của nó nhân [[8]].

Người Delian đã không tăng gấp đôi bàn thờ - họ đã làm nó lớn hơn 8 lần.

:::

Đáng lẽ họ phải tăng gấp đôi thể tích thay vì độ dài các cạnh.

::: column.fit

    figure: x-img(src="images/ch1_43.png" width="200" height="133")

::: column.grow

Để tìm thể tích của khối lập phương, người ta nhân số hình lập phương ở lớp thứ nhất với chiều cao. Lớp đầu tiên này được gọi là đáy và thường đề cập đến các mặt trên và dưới của khối lập phương.
:::

---

> id: temple-display-2

    // Trang 11

::: column.fit

    figure
      x-voxel-painter(width=200 height=200 shape="" playingFieldSize="5" rotateOnly hideGrid)

::: column.grow

Nhắc lại bàn thờ ban đầu. Chúng tôi đã đếm [[25]] hình lập phương trong mỗi lớp. Ngoài ra, chúng tôi có thể đã tính toán [[diện tích | chiều dài | đường chéo]] của đáy.
Số lớp chúng tôi thêm vào tạo thành [[chiều cao]] của bàn thờ.

Chúng tôi đã tính toán thể tích của bàn thờ hình lập phương bằng cách nhân [[Diện tích đáy]] và [[chiều cao]].

:::

---

Diện tích đáy => `Sđáy = input(5) x input(5) =25 m^2` và chiều cao là 5 mét

`Thể tích = Sđáy x h`

`Thể tích = 25 x 5 = input(125) m^3`

Nói cách khác, thể tích của một khối lập phương là tích của chiều dài, [[chiều rộng]] và [[chiều cao]].

`Thể tích = dài x rộng x cao`
::: column.grow

Một hình lập phương có cùng chiều dài, chiều rộng và chiều cao.
Thể tích của một hình lập phương có độ dài cạnh là "a" đơn vị là
`V = a • a • a = blank(x, "a3", "3a", "3 + a")`

Nhân độ dài ba cạnh cho phép chúng ta xác định thể tích của khối lập phương một cách hiệu quả.

::: column.fit

    figure: x-img(src="images/ch1_29.png" width="92" height="87")

:::

Một hình lập phương có độ dài cạnh là 3 cm có thể tích là [[27]] cm khối, ta có thể viết là 27 cm3.

Một hình lập phương có chiều dài cạnh là 4 inch có thể tích là [[64]] inch khối, chúng ta có thể viết là 64 [[in3]].

Thể tích luôn được đo bằng đơn vị khối, chẳng hạn như inch khối (in3), feet khối [[ft3]], centimet khối (cm3) hoặc mét khối [[m3]].

Các ngôi đền Hy Lạp có một bố cục rất dễ đoán. Ở trung tâm, có một phần gọi là Cella lưu giữ một bức tượng của Thần mà ngôi đền thờ. Cella được bao quanh bởi một chuỗi dài các cột. Không phải lúc nào chúng cũng ở dạng lập phương mà chủ yếu ở dạng hình hộp chữ nhật.

    // Trang 12

Để tránh mọi tranh cãi trong tương lai, chúng ta có thể tìm ra một phương pháp chung để tìm thể tích của tất cả các hình hộp chữ nhật?

    figure: x-img(src="images/ch1_45.png" width="600" height="400")

{.caption} Mô hình của đền Aphrodite ở Hy Lạp

::: column.fit

    figure: x-img(src="images/ch1_blueprint.png" width="200" height="132")

::: column.grow

Lớp đầu tiên của hình hộp chữ nhật có [[24]] hình lập phương. Nó có nghĩa là diện tích đáy là 24 đơn vị diện tích.

[[Chiều cao]] cho chúng ta biết số lớp cần có để xếp chồng lên hình khối.

Tổng số khối lập phương cần dùng để tạo ra hình hộp chữ nhật này là [[24 x 5 = 120]].
:::

Thể tích là 120 đơn vị thể tích.

Chúng tôi lại tính toán thể tích bằng cách nhân [[Diện tích đáy]] và [[Chiều cao]].

`Thể tích = Diện tích đáy x chiều cao`
`V = Sđáy x h`

Nói cách khác, công thức tính thể tích của tất cả các hình hộp chữ nhật là [[tích]] ba kích thước của nó.

`Thể tích = dài x rộng x cao`
`V = d x r x c`

Bây giờ đến lượt bạn - tìm thể tích của các hình hộp sau.
  // Trang 13

::: column(width=200)

    figure
      x-voxel-painter(width=200 height=200 shape="0.5,-0.5,0.5,-0.5,-0.5,0.5,1.5,-0.5,0.5,0.5,-1.5,0.5,-0.5,-1.5,0.5,1.5,-1.5,0.5,-1.5,1.5,0.5,-1.5,0.5,0.5,-1.5,-0.5,0.5,-1.5,-1.5,0.5,0.5,1.5,-0.5,-0.5,1.5,-0.5,1.5,1.5,-0.5,0.5,0.5,-0.5,-0.5,0.5,-0.5,1.5,0.5,-0.5,0.5,-0.5,-0.5,-0.5,-0.5,-0.5,1.5,-0.5,-0.5,0.5,-1.5,-0.5,-0.5,-1.5,-0.5,1.5,-1.5,-0.5,-1.5,1.5,-0.5,-1.5,0.5,-0.5,-1.5,-0.5,-0.5,-1.5,-1.5,-0.5,0.5,1.5,-1.5,-0.5,1.5,-1.5,1.5,1.5,-1.5,0.5,0.5,-1.5,-0.5,0.5,-1.5,1.5,0.5,-1.5,0.5,-0.5,-1.5,-0.5,-0.5,-1.5,1.5,-0.5,-1.5,0.5,-1.5,-1.5,-0.5,-1.5,-1.5,1.5,-1.5,-1.5,-1.5,1.5,-1.5,-1.5,0.5,-1.5,0.5,1.5,0.5,-0.5,1.5,0.5,-1.5,-0.5,-1.5,1.5,1.5,0.5,-1.5,-1.5,-1.5,0.5,0.5,0.5,-0.5,0.5,0.5,0.5,1.5,1.5,1.5,0.5,0.5,-0.5,1.5,1.5,1.5,1.5,1.5,0.5,0.5,1.5,-0.5,0.5,1.5,1.5,0.5,1.5,0.5,-0.5,1.5,-0.5,-0.5,1.5,1.5,-0.5,1.5,0.5,-1.5,1.5,-0.5,-1.5,1.5,1.5,-1.5,1.5,-1.5,1.5,1.5,-1.5,0.5,1.5,-1.5,-0.5,1.5,-1.5,-1.5,1.5" playingFieldSize="4" color="rgb(250,225,90)" rotateOnly hideGrid)

Volume= [[4]] x [[4]] x [[4]] = [[64]]

::: column(width=200)

    figure
      x-voxel-painter(width=200 height=200 shape="1.0,0.5,2.0,0.0,0.5,2.0,1.0,-0.5,2.0,0.0,-0.5,2.0,-1.0,0.5,2.0,-1.0,-0.5,2.0,-1.0,0.5,0.0,-1.0,-0.5,0.0,1.0,0.5,-1.0,0.0,0.5,-1.0,1.0,-0.5,-1.0,0.0,-0.5,-1.0,-1.0,0.5,-1.0,-1.0,-0.5,-1.0,1.0,0.5,-2.0,0.0,0.5,-2.0,1.0,-0.5,-2.0,0.0,-0.5,-2.0,-1.0,0.5,-2.0,-1.0,-0.5,-2.0,1.0,0.5,0.0,0.0,0.5,0.0,1.0,-0.5,0.0,0.0,-0.5,0.0,1.0,0.5,1.0,0.0,0.5,1.0,1.0,-0.5,1.0,0.0,-0.5,1.0,-1.0,0.5,1.0,-1.0,-0.5,1.0" playingFieldSize="5" color="rgb(120,237,230)" rotateOnly hideGrid)

Volume= [[2]] x [[3]] x [[5]] = [[30]]

::: column(width=200)

    figure
      x-voxel-painter(width=200 height=200 shape="1.0,2.5,0.0,0.0,2.5,0.0,1.0,1.5,0.0,0.0,1.5,0.0,-1.0,2.5,0.0,-1.0,1.5,0.0,1.0,-1.5,0.0,0.0,-1.5,0.0,1.0,-2.5,0.0,0.0,-2.5,0.0,-1.0,-1.5,0.0,-1.0,-2.5,0.0,1.0,4.5,0.0,0.0,4.5,0.0,1.0,3.5,0.0,0.0,3.5,0.0,-1.0,4.5,0.0,-1.0,3.5,0.0,1.0,-3.5,0.0,0.0,-3.5,0.0,1.0,-4.5,0.0,0.0,-4.5,0.0,-1.0,-3.5,0.0,-1.0,-4.5,0.0,1.0,0.5,0.0,0.0,0.5,0.0,1.0,-0.5,0.0,0.0,-0.5,0.0,-1.0,0.5,0.0,-1.0,-0.5,0.0" playingFieldSize="10" color="rgb(139,160,58)" rotateOnly hideGrid)

Volume= [[1]] x [[3]] x [[10]] = [[30]]

:::

---

> id: painting-1
> goals: vol

Một số hình hộp chữ nhật có thể có cùng thể tích mặc dù chúng có hình dạng khác nhau.

    // TODO: INTERACTIVE-1.04: Voxel-painting
    figure
      x-voxel-painter(width=600 height=400 targetVolume=24 playingFieldSize="15" color-sides)
        button.icon-btn: x-icon(name="eraser")

Sử dụng các hình lập phương đơn vị để tạo ra một hình hộp chữ nhật sao cho thể tích là 24 đơn vị thể tích.

---

[[Không thể | Có thể]] tạo một khối lập phương bằng cách sử dụng 24 khối đơn vị vì 24 không phải là một số lập phương hoàn hảo.

Bạn có thể tạo ra bao nhiêu hình hộp khác nhau bằng cách sử dụng 24 hình khối?

[[Text Box]]

---
Bằng cách tìm các kích thước chưa biết của các hình lập phương khác nhau có thể tích là 24 đơn vị thể tích, chúng ta có thể quan sát diện tích đáy và chiều cao thay đổi như thế nào khi chúng ta có một lượng hình khối nhất định để tạo ra thể tích.
    table
      thead
        tr
          th Cuboids
          th(colspan="4") Dimensions
      tbody
        tr
          td
          td Length
          td Width
          td Height
          td Volume
        tr
          td A
          td 6
          td: x-blank(goal="blank-0" solution=2 placeholder="???")
          td 2
          td 24
        tr
          td B
          td: x-blank(goal="blank-1" solution=3 placeholder="???")
          td 1
          td 8
          td 24
        tr
          td C
          td 4
          td 3
          td: x-blank(goal="blank-2" solution=2 placeholder="???")
          td 24
        tr
          td D
          td: x-blank(goal="blank-3" solution=1 placeholder="???")
          td 2
          td 12
          td 24

    // Trang 14

::: column.fit

    figure: x-img(src="images/ch1_12.png" width="200" height="140")

::: column.grow

Nếu diện tích đáy của một hình hộp chữ nhật nhỏ hơn hình kia, thì chiều cao của nó phải là [[lớn hơn | nhỏ hơn | bằng]] để có cùng thể tích.

Nếu hai hình hộp chữ nhật có cùng chiều cao thì hình có diện tích đáy lớn hơn sẽ có thể tích [[lớn hơn | nhỏ hơn]].
:::

Bây giờ chúng ta đã biết về cách tìm thể tích của hình hộp chữ nhật, chúng ta có thể tìm một cách đo khác về chúng không?
---


----------------------------------------------------------------------------------------------------

## Các lưới và diện tích bề mặt
> section: surface-area
> sectionStatus: dev

### Nghĩa

::: column.fit

    // https://imgur.com/iJVU7
    x-img(width=300 height=179 src="images/ch2_sticky_notes_car.svg")

::: column.grow

_Là một trò đùa, bạn có thể muốn phủ nhiều tờ giấy ghi chú lên xe của bạn mình. Nhưng bạn sẽ cần bao nhiêu? _

:::

---

Hãy tạo một mô hình ô tô để ước tính số lượng giấy ghi chú mà chúng ta sẽ cần.

Chúng ta có thể sử dụng các hình lập phương đơn vị để tạo ra mô hình của chiếc xe:
::: column.fit

    figure
      x-voxel-painter(width=300 height=300 shape="0.5,-0.5,0.5,0.5,-0.5,-0.5,-0.5,-0.5,0.5,0.5,-1.5,-0.5,-0.5,-0.5,-0.5,-0.5,-1.5,-0.5,0.5,0.5,0.5,-0.5,0.5,0.5,0.5,1.5,-0.5,0.5,0.5,-0.5,-0.5,1.5,-0.5,-0.5,0.5,-0.5" playingFieldSize="2" orthographic color-sides rotateOnly hideGrid)

::: column.grow

Bạn có thể xoay mô hình để tìm xem cần bao nhiêu đơn vị diện tích để bao phủ tất cả các mặt của mô hình ba chiều (3D) này không bao gồm phần đáy.

Tổng các mặt của mặt trước và mặt sau = [[8]] hình vuông.

Trên cùng của mô hình: [[8]] hình vuông.

Tổng số bên trái và bên phải: [[12]] hình vuông.

Tổng diện tích là [[28]] __đơn vị diện tích__, không bao gồm phần đáy.
:::

---

{.todo} THẢO LUẬN: Chúng ta có cần chỗ trống này không? Có lẽ chúng ta nên làm điều gì đó khác với nó.

Điều này có nghĩa là diện tích bề mặt của chiếc xe thực tế là khoảng 28 [[mét | cm | inch | feet]]__vuông__ .
---

{.todo} THẢO LUẬN: sử dụng trình soạn thảo phương trình thay thế?

Nếu mỗi tờ giấy ghi chú là `0,006 m ^ 2`, thì
chúng ta sẽ cần có `input (28) / input (0,006) = 4467` tờ ghi chú để phủ kín xe!

---

Ở đây, chúng tôi đã tính toán __ diện tích bề mặt__ của mô hình ô tô để tìm ra tổng số tờ ghi chú cần thiết.

    // trang 2

__ Diện tích bề mặt của hình khối 3D là số đơn vị vuông bao phủ tất cả các mặt của hình đa diện, không có bất kỳ khoảng trống hoặc chồng chéo nào .__
---
> id: sides-rotation
> goals: red purple blue orange green yellow

::: column.grow

Đây là một lăng trụ hình chữ nhật được tạo thành từ [[12]] hình lập phương.

Nó có [[6]] mặt, nhưng chúng ta chỉ thấy ba mặt trong bản vẽ.

Xoay hình để xem tất cả các mặt của nó.

::: column.fit

    // TODO: INTERACTIVE-2.01

    figure
      x-voxel-painter(width=300 height=300 shape="0.5,-0.5,-0.0,0.5,-0.5,-1.0,-0.5,-0.5,-0.0,0.5,-0.5,1.0,-0.5,-0.5,-1.0,-0.5,-0.5,1.0,0.5,0.5,-0.0,-0.5,0.5,-0.0,0.5,0.5,1.0,-0.5,0.5,1.0,0.5,0.5,-1.0,-0.5,0.5,-1.0" playingFieldSize="3" color-sides rotateOnly hideGrid)
      .eraser()

:::

    figure: x-polypad(rotate="no")

---

Diện tích bề mặt = [[32]] __đơn vị diện tích__.
Các đơn vị được sử dụng để đo diện tích bề mặt là mét vuông (`" m "^ 2`), centimet vuông (` "cm" ^ 2`), inch vuông (`" in "^ 2`), feet vuông (` " ft "^ 2`), v.v.
---

### Diện tích bề mặt và thể tích

Diện tích bề mặt và [thể tích] (gloss: thể tích) là các thuộc tính khác nhau của các hình 3D. Sự khác biệt chính giữa chúng là [[diện tích bề mặt | thể tích]] là phép đo 2D và [[thể tích | diện tích bề mặt]] là phép đo 3D của hình khối.
---
> id: voxel-surface
> goals: area

Bạn có thể tạo ra các hình khối khác nhau bằng cách sử dụng cùng một số lượng hình khối.

    // TODO: INTERACTIVE-2.02: voxel painting
    figure
      x-voxel-painter(width=600 height=400 targetSurface=26 targetVolume=6 playingFieldSize="10" color-sides)
        button.icon-btn: x-icon(name="eraser")

Sử dụng 6 hình lập phương để tạo ra hình khối có diện tích bề mặt lớn nhất có thể.

Một hình hộp chữ nhật có diện tích bề mặt là [[26]] đơn vị diện tích là diện tích bề mặt lớn nhất mà chúng ta có thể tạo ra bằng cách sử dụng sáu hình lập phương.

Bây giờ, hãy tạo một hình khối với diện tích bề mặt nhỏ nhất có thể.
:::

---

Diện tích bề mặt tối thiểu là [[22]]  đơn vị diện tích.

---

    // trang 3

Cả hai hình khối bạn đã tạo ra đều có thể tích là [[6]] đơn vị thể tích nhưng có diện tích bề mặt khác nhau. Lưu ý rằng các hình lập phương tạo thành hình khối có diện tích bề mặt càng nhiều [[trải ra | gọn nhẹ]]. Nhiều mặt của chúng hiện ra.
---

Trong tự nhiên, diện tích bề mặt lớn hay nhỏ đối với thể tích quyết định đặc tính sống của sinh vật.

Mối quan hệ giữa diện tích bề mặt và thể tích của một vật thể quan trọng đến mức nó ảnh hưởng đến nơi một động vật có thể sống khi một tế bào phải phân chia, hoặc kích thước của cánh của một chiếc máy bay airbus.

Ví dụ, bạn có biết tại sao voi có đôi tai khổng lồ không?

    // https://depositphotos.com/11745121/stock-photo-elephant-isolated-on-white.html
    figure: x-img(width=600 height=400 src="https://static9.depositphotos.com/1007373/1174/i/950/depositphotos_11745121-stock-photo-elephant-isolated-on-white.jpg")

Voi châu Phi là loài động vật trên cạn lớn nhất trên Trái đất. Chúng có thể được nhận ra bằng đôi tai lớn hơn so với các loài voi khác. Chúng cao tới 4 mét và nặng trung bình 6 tấn.

Voi và tất cả các loài động vật tạo ra nhiệt bên trong tỷ lệ với thể tích của chúng. Động vật lớn hơn tạo ra nhiều nhiệt hơn đối với những động vật nhỏ như chuột.

Hầu hết các phản ứng như truyền nhiệt xảy ra ở bề mặt của các vật thể và sinh vật. Có nghĩa là nếu một động vật lớn sống trong một môi trường nóng, thì nó cần phải tỏa nhiệt bằng cách [[tối đa hóa | tối thiểu hóa]] diện tích bề mặt của nó.
---

::: column(width=200)

    figure
      x-voxel-painter(width=200 height=200 shape="0.5,-1.5,-0.5,0.5,-1.5,-1.5,-0.5,-1.5,-0.5,0.5,-1.5,0.5,-0.5,-1.5,-1.5,-0.5,-1.5,0.5,0.5,-0.5,-0.5,-0.5,-0.5,-0.5,0.5,-0.5,0.5,-0.5,-0.5,0.5,0.5,0.5,-1.5,-0.5,0.5,-1.5,0.5,1.5,-1.5,-0.5,1.5,-1.5,0.5,0.5,-0.5,0.5,-0.5,-1.5,-0.5,0.5,-0.5,-0.5,-0.5,-1.5,0.5,1.5,-0.5,-0.5,1.5,-0.5,0.5,0.5,0.5,-0.5,0.5,0.5,0.5,1.5,0.5,-0.5,1.5,0.5,0.5,-1.5,1.5,-0.5,-1.5,1.5,0.5,-0.5,1.5,-0.5,-0.5,1.5,0.5,0.5,1.5,-0.5,0.5,1.5,0.5,1.5,1.5,-0.5,1.5,1.5" playingFieldSize="4" color="rgb(129,129,129)" rotateOnly hideGrid)

::: column.fit

    figure: x-img(src="images/ch2_42.png" width="204" height="200")

::: column.grow

Bạn có thể coi voi là một hình hộp chữ nhật 4 x 4 x 2 có diện tích bề mặt là [[64]] đơn vị diện tích và thể tích là [[32]] đơn vị thể tích. Chúng cần tăng diện tích bề mặt của chúng để làm giảm nhiệt được tạo ra do thể tích lớn của chúng nhanh hơn.
:::

---

    // trang 4

::: column.grow

Tai của voi châu Phi trung bình là 180 cm x 110 cm. Cả hai tai thêm vào [[8]] `" m "^ 2` diện tích bề mặt cho con voi. Tai làm tăng diện tích bề mặt của voi giúp cho sự tỏa nhiệt nhanh hơn.
::: column.fit

    // https://www.robertharding.com/preview/832-379041/african-elephant-loxodonta-africana-portrait-extended-ears-aggressive/
    x-img(width=200 height=134 src="https://www.robertharding.com/watermark.php?type=preview&im=RF/RH_RF/HORIZONTAL/832-379041")

:::

---

Ngoài ra, nếu bạn đang sống ở Nam Cực, bạn sẽ muốn một tỷ số giữa diện tích bề mặt và thể tích nhỏ. Điều này sẽ làm giảm sự mất nhiệt và bảo tồn nhiệt trong cơ thể. Đó là lý do tại sao các phiên bản cực của động vật thường [[lớn hơn | nhỏ hơn]] đối với các loài khác trong cùng họ.
---
> id: cube-table

    // https://www.deviantart.com/bigfancat/art/The-bears-size-fancat-766492662
    figure: x-img(width=760 height=358 src="https://images-wixmp-ed30a86b8c4ca887773594c2.wixmp.com/f/2344a679-4e4d-4a4c-86e1-d5c45b2f06cf/dcocliu-eb3044fa-3a87-43e4-8c3a-de95a11fdb0f.jpg/v1/fill/w_1024,h_482,q_75,strp/the_bears_size__fancat__by_bigfancat_dcocliu-fullview.jpg?token=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJ1cm46YXBwOiIsImlzcyI6InVybjphcHA6Iiwib2JqIjpbW3siaGVpZ2h0IjoiPD00ODIiLCJwYXRoIjoiXC9mXC8yMzQ0YTY3OS00ZTRkLTRhNGMtODZlMS1kNWM0NWIyZjA2Y2ZcL2Rjb2NsaXUtZWIzMDQ0ZmEtM2E4Ny00M2U0LThjM2EtZGU5NWExMWZkYjBmLmpwZyIsIndpZHRoIjoiPD0xMDI0In1dXSwiYXVkIjpbInVybjpzZXJ2aWNlOmltYWdlLm9wZXJhdGlvbnMiXX0.V_Q04x86SQC81P2wJ0lKXKN3EP_NXKhmeYV71ayTVgU")

Mối quan hệ giữa thể tích và diện tích bề mặt khi kích thước của một hình thay đổi là một nguyên tắc toán học được gọi là [luật square-cube ] (gloss:square-cube-law). __ (SA: V) .__

Động vật có thể được coi là những hình khối đơn giản:

    table
      thead
        tr
          th Side Length of a Cube
          th The Surface Area of the Cube
          th The Volume of the Cube
          th Surface Area to Volume Ratio (SA:V)
      tbody
        tr
          td
            p 1x1x1
            x-voxel-painter.c1(width=100 height=100 playingFieldSize="2" rotateOnly hideGrid)
          td: x-blank(goal="blank-0" solution=6 placeholder="???")
          td 1
          td 6:1
        tr
          td
            p 2x2x2
            x-voxel-painter.c2(width=100 height=100 playingFieldSize="3" rotateOnly hideGrid)
          td: x-blank(goal="blank-1" solution=24 placeholder="???")
          td: x-blank(goal="blank-2" solution=8 placeholder="???")
          td 3:1
        tr
          td
            p 3x3x3
            x-voxel-painter.c3(width=100 height=100 playingFieldSize="4" rotateOnly hideGrid)
          td: x-blank(goal="blank-3" solution=54 placeholder="???")
          td 27
          td 2:1
        tr
          td
            p 6x6x6
            x-voxel-painter.c6(width=100 height=100 playingFieldSize="7" rotateOnly hideGrid)
          td 216
          td: x-blank(goal="blank-4" solution=216 placeholder="???")
          td 1:1
        tr
          td
            p 10x10x10
            x-voxel-painter.c10(width=100 height=100 playingFieldSize="11" rotateOnly hideGrid)
          td 600
          td 1000
          td: x-blank(goal="blank-5" solution="3:5" placeholder="???")
        tr
          td
            p 20x20x20
            x-voxel-painter.c20(width=100 height=100 playingFieldSize="21" rotateOnly hideGrid)
          td 2400
          td 8000
          td: x-blank(goal="blank-6" solution="3:10" placeholder="???")

    // trang 5

Khi bạn tiếp tục tăng kích thước cạnh của khối lập phương, [[Thể tích | Diện tích bề mặt]] sẽ lớn lên nhanh hơn.
---

    figure: x-img(width=600 height=475 src="images/volume-area.png")

[Galileo] (bio: galileo) có thể là người đầu tiên chính thức nhận ra điều này khi ông trình bày trong cuốn sách năm 1638 của mình, Hai khoa học mới. Ngoài sinh học, nó có nhiều ứng dụng trong các lĩnh vực khoa học khác nhau như cơ khí, sinh thái, kỹ thuật.

### Diện tích bề mặt so với thể tích

    // trang 6

Hãy kéo các ví dụ về đại lượng liên quan đến thể tích và diện tích bề mặt để hoàn thành sơ đồ:

    // INTERACTIVE-2.04

::: x-binary-swipe(a-title="Volume" b-title="Surface Area")

{div.card.c-red (solution = "a")} Một thùng chứa được bao nhiêu nước?

{div.card.c-teal (solution = "b")} Cần bao nhiêu vải để phủ bề mặt của hình khối?

{div.card.c-green (solution = "a")} Được đo bằng đơn vị thể tích, như `" in "^ 3` hoặc` "m" ^ 3`.

{div.card.c-orange (solution = "a")} Dung tích của hộp là bao nhiêu?

{div.card.c-blue (solution = "a")} Cần bao nhiêu vật liệu để chế tạo một hình khối?

{div.card.c-yellow (solution = "b")} Cần bao nhiêu sơn để vẽ các mặt của một hình?

{div.card.c-Purple (solution = "b")} Được đo bằng các đơn vị diện tích, như `" in "^ 2` hoặc` "m" ^ 2`.

:::

---
> id: cube-draw

### Lưới

Các nghệ sĩ và nhà toán học như [Leonardo Da Vinci] (bio: leonardo) đã dành nhiều nỗ lực để thể hiện các vật thể 3D trên giấy 2D. Thành tựu lớn nhất của Da Vinci trong lĩnh vực này là các bức tranh minh họa cho cuốn sách năm 1509 của [Luca Pacioli] (bio: pacioli) _ Tỷ lệ thần thánh_. Da Vinci đã vẽ khoảng 60 hình minh họa khác nhau về các khối đa diện trong cuốn sách.

    // trang 7

    // https://www.georgehart.com/virtual-polyhedra/leonardo.html

::: column.fit

    x-img(width=150 height=207 src="https://www.georgehart.com/virtual-polyhedra/figs/leonardo-72-solid.jpg")

::: column.fit

    x-img(width=150 height=219 src="https://www.georgehart.com/virtual-polyhedra/figs/leonardo-72-vacuum.jpg")

::: column.fit

    x-img(width=150 height=184 src="https://www.georgehart.com/virtual-polyhedra/figs/leonardo-dodec-solid.jpg")

::: column.fit

    x-img(width=150 height=199 src="https://www.georgehart.com/virtual-polyhedra/figs/leonardo-dodec.jpg")

:::

Vì không phải tất cả chúng ta đều có năng khiếu nghệ thuật như Da Vinci, chúng ta có thể sử dụng giấy kẻ ô vuông để vẽ các khối đa diện. Hãy bắt đầu bằng cách vẽ một __hình lập phương__ trên lưới có chấm.

    // INTERACTIVE-2.05
    figure: x-polypad(grid="square-dots")

---

> id: net-1

   
Khi hình khối trở nên phức tạp, việc vẽ chúng trên giấy 2D cũng khó hơn. Nhưng có một cách khác để biểu diễn hình khối 3D trên mặt phẳng 2D.
 // trang 8

Chúng ta có thể sử dụng [lưới] (gross: lưới) của hình khối bao gồm các đa giác tạo thành các mặt của một hình đa diện.

    // INTERACTIVE-2.06: Hình khối 3D với một thanh trượt để mở và đóng lưới. (Có thể bao gồm cả lưới các ví dụ của Da Vinci)

::: column.fit.s1

    x-net(size=100 :p="progress")

::: column.fit.s2

    x-net(size=100 :p="progress")

::: column.fit.s3

    x-net(size=100 :p="progress")

:::

    x-slider(:bind="progress" steps=1000 speed=1)

---

__Chúng là những áo khoác 2D bao phủ toàn bộ bề mặt của hình khối 3D .__

Ví dụ, lưới của một khối lập phương bao gồm [[6]] hình vuông. Với sự sắp xếp chính xác của các hình vuông, họ có thể gấp lại một hình lập phương.
---
> id: cube-net-draw

Hãy thử vẽ __lưới__ của một khối lập phương:

    // INTERACTIVE-2.07
    figure: x-polypad(grid="square-dots")

Có nhiều cách khác nhau để sắp xếp sáu hình vuông để gấp lại thành một hình lập phương.

Hãy xem cái nào dưới đây có thể được gấp lại thành hình lập phương.

::: column.fit

    x-img(width=100 height=87 src="images/cubenet.png")

:::

---

{.todo} INTERACTIVE-2.08: Ảnh động của lưới

    // BÌNH LUẬN: Sau mỗi ảnh động

    // trang 9

    // BÌNH LUẬN: Sau A:

Hàng của các hình vuông trong Hình A có thể được gấp lại thành một vòng và sau đó hình vuông gần nhất với chiếc nhẫn sẽ đóng lại một mặt, nhưng hình vuông còn lại sẽ phải chồng lên một mặt hiện có.

    // BÌNH LUẬN: Sau B:

Hàng của các hình vuông trong dạng B có thể được gấp lại thành một vòng và hai hình vuông còn lại có thể đóng hai mặt còn lại. Bạn có thể hình dung hai mặt đó là đáy của hình lập phương.

    // BÌNH LUẬN: Sau C:

Khi bạn gấp hàng của các hình vuông trong Hình C thành một vòng, hình vuông thứ năm sẽ chồng lên hình vuông đầu tiên.

    // BÌNH LUẬN: Sau D:

Hàng của các hình vuông trong Hình D có thể được gấp lại thành một vòng và hai hình vuông còn lại có thể đóng hai mặt còn lại. Bạn có thể hình dung hai mặt đó là đáy của hình lập phương.

    // NHẬN XÉT: Sau khi phóng to B và D:

Một trong những hình lập phương phổ biến nhất mà chúng ta bắt gặp hàng ngày là xúc xắc.
---
> id: die-faces-1
> goals: faces-placed

Hãy cố gắng tạo một xúc xắc thích hợp của riêng chúng ta bằng cách chèn các mặt một cách chính xác.

Các mặt đối diện của một xúc sắc này luôn có tổng số 7.

    // INTERACTIVE-2.09: Nối các lưới mặt xúc xắc với nhau
    figure: div.die-faces
      svg(viewBox="0 0 400 300")
      div.faces
        div.face
        div.face
        div.face
        div.face
        div.face
        div.face

{.reveal(when="faces-placed")} Great!

---
> id: die-faces-2
> goals: faces-placed

Hãy thử một lần nữa:

    // INTERACTIVE-2.09: Nối các lưới mặt xúc xắc với nhau
    figure: div.die-faces
      svg(viewBox="0 0 400 300")
      div.faces
        div.face
        div.face
        div.face
        div.face
        div.face
        div.face

---

Bây giờ chúng ta có thể xác định các mặt đối diện của một con xúc sắc bằng cách sử dụng lưới, hãy thử một câu đố khác:
::: column.fit

{.todo} THẢO LUẬN: CÓ TƯƠNG TÁC?: Màu sắc của các mặt

::: column.grow

Mỗi mặt của một khối lập phương được sơn một màu khác nhau.

Dưới đây là những góc nhìn khác nhau về cái xúc xắc được sơn này.

:::

---

Mặt đối diện của màu vàng được sơn [[xanh lam | tím | hồng | lục | đỏ]].

---

Mặt đối diện của màu xanh lục được sơn [[hồng |xanh lam | tím | lục | đỏ]].

---

Mặt đối diện của màu đỏ được sơn [[tím | xanh lam | hồng | lục | đỏ]].

    // trang 10

_{button.btn.continue}Continue_

---

    // BÌNH LUẬN: Tôi có một trò chơi ghép hình ở phần lăng trụ và hình chóp mà tôi có thể kéo vào đây? Ở đó, tôi cũng đã từng chơi trò chơi để ôn tập các loại hình lăng trụ và hình chóp

   // BÌNH LUẬN: Thay vào đó, chúng ta có thể có một applet ở đây để tam giác đều, ngũ giác, lục giác, hình vuông để cho phép chúng tạo lưới với sự trợ giúp của thanh trượt - hơn là chúng ta có thể mở / đóng chúng để xem hình khối của chúng - theo cách này, chúng ta có thể có một số câu hỏi như số mặt tối thiểu của một khối đa diện

{.todo} INTERACTIVE-2.10: Xây dựng lưới
---

### Sử dụng lưới để tính diện tích bề mặt

Một__lưới__ cho phép chúng tôi xem tất cả các mặt của hình khối 3D cùng một lúc. Chúng ta có thể sử dụng lưới để tìm diện tích bề mặt của các hình hộp chữ nhật thay vì đếm số lượng các hình vuông trong mỗi mặt một.

    // trang 11

Hãy tìm diện tích bề mặt của hình hộp chữ nhật này bằng cách sử dụng lưới của nó

::: column.fit

{.todo} INTERACTIVE-2.11: hình khối với thanh trượt (solid <-> net)

::: column.grow

Lưới của cái hộp hình hộp chữ nhật thể hiện ba cặp hình chữ nhật:

4 cm x 2 cm,

[[3]] cm x [[2]] cm, và

[[4]] cm x [[3]] cm.

:::

::: column.fit

    figure: x-img(src="images/ch2_16.png" width="300" height="154")

::: column.grow

Với thông tin này, bây giờ chúng ta có thể tính toán số lượng các tông cần thiết để làm hộp; `(4 * 2) + (4 * 2) + (3 * 2) + (3 * 2)+ (4 * 3) + (4 * 3) = input (52)" cm vuông "`

Diện tích bề mặt của hình hộp là 52 [[`" cm "^ 2` | cm]].

:::

---

Sử dụng thanh trượt để mở hình hộp chữ nhật vào lưới của nó. Sau đó kéo các thước đo chiều dài cạnh sang các cạnh tương ứng để tìm diện tích bề mặt.

    // BÌNH LUẬN: Bây giờ chỉ bao gồm các nhãn

{.todo} INTERACTIVE-2.12: solid <-> net

---

Các hình chữ nhật màu hồng có tổng diện tích là [[64]] `" m "^ 2`

---

Các hình chữ nhật màu vàng có tổng diện tích là [[48]] `" m "^ 2`

---

Các hình chữ nhật màu cam có tổng diện tích là [[24]] `" m "^ 2`

---

Vậy hình hộp chữ nhật có tổng diện tích là [[136]] `" m "^ 2`.

---

Chúng ta có thể nghĩ ra các phím tắt để tìm diện tích bề mặt của hình hộp chữ nhật không?

Hãy xem các hình hộp chữ nhật ở đây:

    // trang 12

Sử dụng các thanh trượt để mở lưới của các hình hộp chữ nhật.

{.todo} INTERACTIVE-2.13: solid <-> net

Kéo các phép tính diện tích trên các vùng tương ứng.

---

::: column.grow

`"Diện tích bề mặt của hình hộp" = ` _{x-equation(solution="2ab" keys="" short-var)}_ ` + ` _{x-equation(solution="2bc" keys="" short-var)}_ ` + ` _{x-equation(solution="2ac" keys="" short-var)}_

::: column(width=250)

`"Diện tích bề mặt của hình lập phương" = ` _{x-equation(solution="6 a^2" keys="sup" short-var)}_

:::

---
> id: soccer-net

Vì lưới bao gồm các hình phẳng tạo thành các mặt của hình khối 3D, chúng ta luôn có thể sử dụng chúng để tính diện tích bề mặt của các hình khối phức tạp hơn.
::: column.fit

    // INTERACTIVE-2.14
    figure
      x-net(size=300 :p="progress")
      x-slider(:bind="progress" steps=1000 speed=1)

::: column.grow
Hãy xem quả bóng đá ở đây, sử dụng thanh trượt để mở lưới của nó. Có [[12]] ngũ giác và [[20]] lục giác. Nếu diện tích của mỗi ngũ giác là 30 `" cm "^ 2` và diện tích của mỗi lục giác là 45` "cm" ^ 2`, thì diện tích bề mặt của quả bóng là [[1260]] `" cm "^ 2 `.
:::

---

   // trang 13

Trong chương tiếp theo, chúng ta sẽ xem xét các lưới, diện tích bề mặt và thể tích của các loại khối đa diện khác nhau.
---

## Hình lăng trụ và hình chóp
> section: prism-pyramid
> sectionStatus: dev
> id: honeycomb-intro

::: column.fit

    figure: x-img(src="images/ch3_35.png" width="300" height="176")

::: column.grow

Cấu trúc tuyệt vời của tổ ong mật đã thu hút sự chú ý của con người trong nhiều thế kỷ.

Ong thu thập mật hoa và phấn hoa từ hoa để làm mật ong cho đàn của chúng. Mật ong cung cấp cho ong năng lượng cần thiết để chúng tồn tại và sinh sản, cũng như để xây dựng tổ ấm của chúng.
:::

::: column.fit

    // INTERACTIVE-3.01
    figure: x-polyhedron(shape="HexagonalPrism" size=250 rotate=0)

::: column.grow

Những ngôi nhà này được gọi là ** honeycomb. ** Tất cả các loài ong trên trái đất đang sử dụng cùng một hình dạng để tạo ra tổ ong của chúng.

_Nhưng tại sao những con ong_ lại tạo ra những tổ ong theo hình dạng như họ làm vậy?
:::

---

Mỗi ô tổ ong thực chất là một loại khối đa diện đặc biệt được gọi là [lăng trụ] (gloss: lăng trụ).

_{span.comments(text="Tôi tự hỏi liệu có tương tác nào có thể xuất hiện ở đây trước khi tìm hiểu thuật ngữ và các ví dụ khác nhau về lăng trụ không? Có lẽ học sinh có thể thử nhiều bản sao của các lăng trụ khác nhau - một số có thể được căn chỉnh mà không có bất kỳ khoảng trống nào và một số tạo ra khoảng trống? Sau đó, đối với những cái không tạo ra khoảng trống, họ có thể nghĩ xem cái nào sẽ xây dựng cấu trúc tốt nhất cho ong? Điều này có thể cung cấp một điểm vào tốt hơn trước khi nhảy vào thuật ngữ. | Điều này có thể thiết lập lên mục 'kho chứa tối đa' trên trang tiếp theo một cách độc đáo. | Thực tế, hình lăng trụ lục giác đó có thể ghép các từ 'đồng đẳng', 'song song' và 'đáy' để giới thiệu khái niệm lăng trụ. Mặt khác, tôi muốn nói về khái niệm "lăng trụ nào có thể xếp" sau này * | Bạn đã biết hướng hoặc cuộc trò chuyện mà bạn cần đưa ra quyết định ở đây chưa? | Tương tác với ** tôi đoán có thể làm được điều này - Tôi cũng cố gắng tạo một applet có thể được sử dụng trong các chương về hình trụ ")} Hình lăng trụ_ là một loại hình đa diện có _ ** hai * * _ [đồng dư] (pill: cam) _ ** các mặt đa giác ** _ [song song] (pill: cam) với nhau.

Những mặt giống hệt nhau đó được gọi là _ {span.comments (text = "(gloss: đáy) Tôi bạn đã cung cấp định nghĩa sơ bộ của thuật ngữ trong chương trước. Vì thế, không cần phải viết lại.")} ** [đáy] ( pill: màu cam) ** _. Chúng thường được sử dụng để chỉ ra _mặt trên_ và mặt dưới__ của lăng trụ. Trên thực tế, lăng trụ được đặt tên theo hình dạng của đáy của chúng. Đó là lý do tại sao hình dạng tổ ong được gọi là lăng trụ [[lục giác | hình chữ nhật | hình tam giác]] .

    // BÌNH LUẬN: Chúng ta nên thêm một đoạn văn (và sơ đồ tương tác) cho thấy rằng tất cả các mặt cắt song song với các đáy là đồng đẳng
---

::: column.fit

    figure: x-img(src="images/ch3_32.png" width="200" height="147")

::: column.grow

Hãy tưởng tượng cắt một hình lăng trụ thành nhiều lớp mỏng song song với đáy của nó.

Tất cả các mặt cắt ngang sẽ có cùng hình dạng và kích thước. Các mặt cắt ngang sẽ là ** đồng đẳng. **

Hãy nghĩ về một ổ bánh mì cắt lát, mỗi lát bánh mì có hình dạng và kích thước giống nhau. Hình dạng của bánh mì là một hình lăng trụ.
:::

Có tất cả các loại lăng trụ như lăng trụ tam giác, lăng trụ chữ nhật, lăng trụ ngũ giác, vân vân. ** Hình hộp chữ nhật ** mà chúng ta đã thấy trong chương trước cũng là hình lăng trụ:** lăng trụ. ** [[hình chữ nhật | hình tam giác | hình ngũ giác | hình lục giác]] 
---

    // INTERACTIVE-3.02

::: column.fit

    figure: x-polyhedron(size=200 shape="TriangularPrism")

::: column.fit

    figure: x-polyhedron(size=200 shape="PentagonalPrism")

::: column.fit

    figure: x-polyhedron(size=200 shape="Cube")

:::

Các ô tổ ong luôn được căn chỉnh theo chiều ngang. Chúng chia sẻ bức tường với ô bên cạnh để giảm lượng sáp được sử dụng để xây dựng mỗi ô.

::: column.grow

Những bức tường chung đó là _{span.comments(text="(gloss:mặt bên) cần định nghĩa | Bumping . | Các mặt bên của hình ba chiều là các mặt tứ giác (chủ yếu là hình chữ nhật) ngoại trừ các mặt đáy của hình khối. ")} ** [mặt bên] (pill: màu xanh lục) ** _ của hình lăng trụ lục giác. Các mặt bên là [[hình chữ nhật | hình tam giác | hình vuông | ngũ giác | lục giác]].
::: column.fit

    figure: x-img(src="images/ch3_58.png" width="100" height="59")

:::

---

::: column.grow

Trong tất cả các loại lăng trụ, các đáy được nối với nhau bằng một tập hợp các hình chữ nhật _ (hoặc đôi khi là các hình bình hành) _ không phụ thuộc vào loại đáy.

[Lưới] (gloss: lưới) của lăng trụ lục giác có thể cung cấp cái nhìn tốt hơn về tất cả các mặt. Hoàn toàn có [[8]] _ {span.comments (text = " Hình khối tương tác với một thanh trượt - các mặt, đỉnh, cạnh được mã hóa màu")} ** [các mặt] (pill: xanh lam) ** _, [[ 2]] trong số chúng là các đáy lục giác và [[6]] còn lại là các mặt bên hình chữ nhật.
::: column.fit

    // TODO: INTERACTIVE-3.03
    figure: x-img(src="images/ch3_21.png" width="200" height="165")

:::

---

Một lăng trụ lục giác có [[12]] _ {span.comments (text = "(gloss: đỉnh) Tôi đã cung cấp cho bạn định nghĩa sơ bộ thuật ngữ trong chương trước. Vì vậy, không cần phải viết lại.")} ** [các đỉnh] (pill: xanh lam) ** _ và [[18]] _ {span.comments (text = "(gloss: cạnh đa diện)")} ** [các cạnh] (pill: xanh lá) ** _
---

** Tại sao ong chọn lăng trụ lục giác chứ không phải các lăng trụ khác? **

    // BÌNH LUẬN: Một tương tác nơi học sinh có thể xếp các lăng trụ khác nhau để xem cái nào có thể lát.

    // INTERACTIVE-3.04
    figure: x-img(src="images/ch3_50.png" width="600" height="482")

_{span.comments(text="Học sinh có thể chọn một lăng trụ và thử lát - lăng trụ tam giác cho dấu kiểm, hình ngũ giác cho dấu thập, v.v....")}_

Các lăng trụ lục giác có thể được xếp cạnh nhau mà không có khoảng trống hoặc chồng lên nhau nhưng [hình hộp chữ nhật] (pill: màu xanh lam) và [lăng trụ tam giác] (pill: màu xanh lam)cũng có thể như vậy.

    figure: x-img(src="images/ch3_67.svg" width="444" height="159")

_{span.comments(text="Đây có thể là bước tiếp theo của hoạt ảnh trước đó")}_

Ong cần ** kho chứa lớn nhất ** đựng mật ong mà không dùng nhiều sáp hơn mức cần thiết. Điều này có nghĩa là họ cần sử dụng ít sáp nhất có thể để tạo ra cái tổ có thể lưu trữ nhiều mật ong nhất có thể.

Nhớ lại phương pháp chúng ta sử dụng để tính thể tích của hình hộp chữ nhật.

    // TODO?: Use math rendering

** Thể tích ** = [[Diện tích đáy| Chu vi đáy]] x [[chiều cao | chiều rộng]]
---

Chúng ta có thể sử dụng cùng một công thức cho tất cả các lăng trụ không?

    figure: x-img(src="images/ch3_9.png" width="600" height="318")

::: column.grow

Lý do mà thể tích của hình hộp chữ nhật được tính là _ {span.comments (text = "chia thành cát lát hình hộp")} ** `diện tích đáy xx chiều cao` ** _ là vậy; các hình hộp chữ nhật được tạo thành bởi các lớp lặp lại có cùng kích thước với đáy.

Hãy xem xét các lăng trụ này để xem liệu chúng có được tạo thành từ nhiều lớp của cùng một đa giác làm đáy.

::: column.fit

    figure: x-img(src="images/ch3_11.png" width="200" height="217")

:::

     // BÌNH LUẬN: Cảnh đầu tiên: các lăng trụ khác nhau được đưa ra (nhìn không cắt lát) và không phải lúc nào cũng ở vị trí thẳng đứng. Học sinh có thể xoay các lăng trụ để tìm và chọn diện tích đáy.

    // BÌNH LUẬN: Cảnh thứ hai: Sau mỗi lần chọn, các lăng trụ có thể được cắt song song với đáy của chúng để cho thấy chúng được tạo thành từ các đa giác đồng đẳng

Xoay các lăng trụ để chọn các đáy của chúng.

    // BÌNH LUẬN: Cho lăng trụ tam giác:

Chúng ta hãy xem xét các lát cắt khác nhau của lăng trụ.

Tất cả các lớp hình tam giác có kích thước [[giống nhau | khác]] kích thước của đáy.
---

   // BÌNH LUẬN: Đối với hình lăng trụ lục giác: Hãy xem các mặt cắt khác nhau của hình lăng trụ.

Tất cả các lớp lục giác đều có kích thước [[giống | khác]] kích thước của đáy.
---

Vì tất cả các lăng trụ đều được tạo thành từ nhiều lớp đáy của chúng, chúng ta [có thể | không thể]] sử dụng cùng một công thức

---

    // TODO?: Make purple

`" Thể tích "_" Lăng trụ "` = [[Diện tích đáy | Chu vi đáy]] x [[chiều cao | chiều rộng]]

---

Bây giờ, sử dụng thanh trượt để thử các đa giác khác nhau làm đáy của lăng trụ dùng làm một tổ ong. Trung bình Chiều rộng và chiều dài ô cho một tổ ong là khoảng 4mm và chiều sâu là 10 mm.
::: tab

#### Lăng trụ tam giác

::: column.fit

    figure: x-img(src="images/ch3_16.png" width="200" height="162")

::: column.grow

Vì đáy của lăng trụ là tam giác đều _ {span.comments (text = "tablet to yellow area")} [Diện tích đáy] (pill: màu xanh lam) _ có thể được tính bởi `1/2 (" đáy" xx "chiều cao") `

`" S "_" đáy "= (4 * 3.5) / 2 = 7" mm "^ 2`

`" V "_" Lăng trụ "=" S "_" đáy "xx" Chiều cao của lăng trụ "`

`" V "_" Lăng trụ "=` _ {span.comments (text = "Chúng ta có thể tạo các phương trình cho tất cả các phép tính")} _ `7 xx 10 = 70" mm "^ 3`

:::
::: tab

#### Lăng trụ hình vuông

::: column.fit

    figure: x-img(src="images/ch3_42.png" width="200" height="157")

::: column.grow

Vì đáy của lăng trụ là hình vuông _ {span.comments (text = "pill to yellow area")} [Diện tích đáy] (pill: xanh lam) _ có thể tính bằng cách bình phương độ dài cạnh

`" S "_" Đáy "= 4 xx 4 = 16" mm "^ 2`

`" V "_" Lăng trụ "=" S "_"Đáy"xx" Chiều cao của lăng trụ "`

`" V "_" Lăng trụ "=` _ {span.comments (text = "Phương trình")} `16 xx 10 = 160" mm "^ 3`_

:::
::: tab

#### Lăng kính lục giác

::: column.fit

    figure: x-img(src="images/ch3_53.png" width="200" height="169")

::: column.grow

Vì đáy của lăng trụ là lục giác,

_{span.comments(text="pill to yellow area")}Diện tích đáy_ là diện tích sáu tam giác đều mà hình lục giác được tạo thành

    // BÌNH LUẬN: Vì đáy của lăng trụ là tam giác đều,Diện tích đáy được tính là ½ (đáy x chiều cao) S đáy = (4 x 3.5)/2= 7 `"mm"^2`

`"S"_"Đáy" = 6 xx 7 = 42 "mm"^2`

`"V"_"Lăng trụ" = "S"_"Đáy" xx "Chiều cao của lăng trụ"`

    // BÌNH LUẬN: Phương trình
`"V"_"Lăng trụ" = 42 xx 10 = 420 "mm"^3`

:::
:::


So với các hình lăng trụ khác không có khe hở hoặc chồng lên nhau (chẳng hạn như hình tam giác và hình vuông), hình lăng trụ lục giác tạo ra một hình có thể tích lớn nhất.

Hãy nhớ rằng, ong cũng cần sử dụng ít sáp nhất có thể để tạo ra cái tổ này. Vì chúng chỉ có thể tạo ra 1 oz sáp bằng cách sử dụng 8 oz mật ong, nên loại sáp này cũng rất quý đối với chúng. Chúng không thể tiêu nhiều sáp hơn mức cần thiết.

Để tìm lượng sáp cần thiết để xây bức tường ngăn cách các ô, chúng ta cần tìm [[diện tích bề mặt | thể tích]] của lăng trụ.

---

Sử dụng [[lưới | phép chiếu]] có thể giúp chúng ta tính diện tích bề mặt của lăng trụ.

---

Chúng ta đã biết cách tính diện tích đáy của các lăng trụ.

    // BÌNH LUẬN: (Hình khối 3D có thanh trượt để mở lưới của chúng và đóng lại)

::: tab

#### Lăng trụ tam giác

::: column.fit

    figure: x-img(src="images/ch3_16.png" width="200" height="162")

::: column.grow

    // COMMENT: Pill:

`"S"_"Đáy"(4 * 3.5) / 2 = 7 "mm"^2`

  Có [[3]] _ {span.comments (text = "Pill: các mặt bên trên lưới")} mặt bên hình chữ nhật_ với diện tích [[3]] x [[10]] = [[30]] `"mm" ^ 2`.

Vì vậy, tổng diện tích của các mặt sẽ là

    // BÌNH LUẬN: lời nhắc của người hướng dẫn: Vì chỉ có một mặt cuối của tổ ong được đóng lại, chúng ta chỉ có diện tích một đáy được đưa vào tính toán diện tích bề mặt.

`"S"_"Lăng trụ đứng " = "S"_"Đáy" + pill("S"_"Mặt bên", "blue") = [[37]]  "mm"^2`

:::
::: tab

#### Lăng trụ hình vuông

::: column.fit

    figure: x-img(src="images/ch3_42.png" width="200" height="157")

::: column.grow

`"S"_"Đáy" = 4 xx 4 = 16 "mm"^2`

Có [[4]] _{span.comments (text = "Pill: mặt bên trên lưới")} mặt bên hình chữ nhật_ với diện tích [[4]] x [[10]] = [[40]] `"mm" ^ 2`.
Vì vậy, tổng diện tích của các mặt sẽ là
`"S"_"Hình lăng trụ" = pill("S"_"Đáy", "green") + pill("S"_"Mặt bên", "blue") = [[56]]  "mm"^2`

:::
::: tab

#### Lăng trụ lục giác

::: column.fit

    figure: x-img(src="images/ch3_53.png" width="200" height="169")

::: column.grow

    // BÌNH LUẬN: Vì đáy của lăng trụ tam giác đều nên Diện tích đáy có thể được tìm thấy bằng ½ (đáy x chiều cao) S đáy = (4 x 3,5) / 2 = 7 'mm ^ 2

`"S"_"Đáy" = 6 xx 7 = 42 "mm"^2`

Có [[6]] _ {span.comments (text = "Pill: các mặt bên trên lưới")} mặt bên hình chữ nhật_ với diện tích [[6]] x [[10]] = [[60]] `"mm" ^ 2`.

Vì vậy, tổng diện tích của tất cả các  mặt sẽ là
`"S"_"Hình lăng trụ" = pill("S"_"Đáy", "blue") + pill("S"_"mặt bên", "green") = [[102]] "mm"^2`

:::
:::

---

_{span.comments (text = "Ở đây, chúng tôi cũng có thể căn chỉnh chúng bên cạnh nhau, hiển thị các bức tường được chia sẻ - và tính toán lại diện tích bề mặt cho phù hợp. Nhưng điều này có thể phức tạp không? | Tôi tự hỏi liệu một hoạt ảnh có hiển thị diện tích bề mặt như thế nào khi nhiều lăng trụ được xếp chồng lên nhau sẽ là một mẹo nhỏ? Học sinh không cần phải tính toán lại. | Vâng, điều đó chắc chắn sẽ tốt hơn | Điều này có thể được thực hiện với applet mà tôi đã đề cập trước đây ")} Mặc dù có vẻ như diện tích bề mặt của hình lăng trụ lục giác cao hơn, lượng sáp này phải được tạo ra để tạo ra thể tích 420 `" mm "^ 3`_

    figure: x-img(src="images/ch3_63.png" width="600" height="403")

Hãy xem các tổ ong có hình dạng khác nhau để xem cần bao nhiêu ô để tạo ra thể tích 420 `" mm "^ 3`
::: column.fit

    figure: x-img(src="images/ch3_56.png" width="271" height="200")

::: column.fit

    figure: x-img(src="images/ch3_65.png" width="225" height="200")

:::

   // BÌNH LUẬN: Một hoạt ảnh có thể được thực hiện như trong đơn vị vòng tròn;

_{span.comments (text = "Có thể hiển thị hoạt ảnh nhanh dưới dạng 6 cái tổ hình tam giác xếp lớp theo chiều ngang để so sánh với tổ hình lục giác. | Có thể ba hoạt ảnh này có thể xảy ra đồng thời? Hoặc có thể trong một bộ sưu tập / thanh cuộn trình chiếu. Nó có thể rất mạnh cho học sinh xem và so sánh cạnh nhau. ")} Để có thể tích_ 420` "mm" ^ 3` của lăng trụ tam giác, bạn cần sử dụng [[6]] chúng. Vì vậy, diện tích bề mặt của 6 lăng trụ tam giác sẽ bằng 6 lần [[37]], do đó 222 `" mm "^ 2`
---

_{span.comments(text=" Một ảnh động nhanh có thể cho thấy tổ ong đáy vuông xếp lớp 2-3 theo chiều ngang để so sánh với tổ lục giác.")}Để tạo thể tích_ 420 `" mm "^ 3` với lăng trụ vuông, bạn cần sử dụng nhiều hơn 2 lăng trụ có bề mặt lớn hơn 102` "mm" ^ 2`
::: column.grow                                                                                                       

Để tạo ra cùng một thể tích để chứa, ong cần sử dụng nhiều sáp hơn làm diện tích bề mặt của các lăng trụ tam giác hoặc lăng trụ hình vuông. Đó là lý do tại sao (Neglecting the _ {span.comments (text = "Các đầu khép kín của ô tổ ong cũng là một ví dụ về hiệu quả hình học, đáy này bao gồm ba mặt phẳng giao nhau để cung cấp sự liên kết hoàn hảo. Hình dạng của các ô sao cho hai lớp tổ ong đối diện lồng vào nhau, với mỗi mặt của các đầu khép kín được chia sẻ bởi các ô đối lập. | en.wikipedia.org/wiki/Honeycomb | @philipp Tôi đã tự hỏi liệu có đáng xây dựng một kho lưu trữ các sự thật thú vị khác không . Cái này có thể tồn tại ở đó và xuất hiện giống như các mục từ điển thuật ngữ và tiểu sử. Tôi cũng có một vài ý tưởng từ các chương của mình. ")} closed ends_ tổ ong), tổ ong có hình dạng lăng trụ lục giác.

Các đầu khép kín của các ô tổ ong phức tạp hơn một chút.

Chúng được cấu tạo bởi ba mặt phẳng phẳng để đảm bảo các đầu ô vuông dựa vào nhau mà vẫn có hình dạng tổng thể của ô tổ ong, giảm thiểu diện tích bề mặt cho một thể tích nhất định.
::: column.fit

    figure: x-img(src="images/ch3_17.png" width="150" height="94")

:::

Ngày nay, người ta cũng tranh luận rằng ong xây dựng các ô hình trụ sau đó biến đổi thành lăng trụ lục giác thông qua một quá trình vẫn còn đang tranh cãi như lực vật lý và tạo hình cơ học.

[Charles Darwin] (bio: darwin) mô tả tổ ong như một kiệt tác của kỹ thuật _ “hoàn toàn hoàn hảo trong việc tiết kiệm sức lao động và sáp.” _

---

Thiết kế kiến ​​trúc bắt chước tự nhiên khi tìm kiếm giải pháp của _ {span.comments (text = "Tôi không nghĩ đó là trường hợp ở đây - hầu hết các hình dạng trong các ví dụ dưới đây được chọn đơn giản vì lưới đường phố và không gian có sẵn.")} bền vững và hiệu quả_. Tất cả các loại lăng trụ được sử dụng thường xuyên trong kiến ​​trúc.
::: column(width=300)

    figure: x-img(src="images/ch3_10.png" width="600" height="337")

{.caption} Những Cabin hình lục giác

::: column(width=300)

    figure: x-img(src="images/ch3_1.png" width="183" height="275")

{.caption} Tòa nhà FLat Iron ở Thành phố New York, một lăng trụ [[tam giác | lục giác | ngũ giác]] 22 tầng
::: column(width=300)

    figure: x-img(src="images/ch3_4.png" width="225" height="225")

{.caption} The Baltimore Trung tâm Thương mại Thế giới, một lăng trụ [[ngũ giác | tam giác | lục giác]] 30 tầng

::: column(width=300)

    figure: x-img(src="images/ch3_22.png" width="600" height="865")

{.caption} The Seagram Building ở XXX,một lăng trụ [[hình chữ nhật | hình vuông | hình tam giác]] 38 tầng
:::

---

Hãy cùng xem những tòa nhà cao nhất trên thế giới.

    figure: x-img(src="images/ch3_66.png" width="600" height="250")

Khi các tòa nhà ngày càng cao hơn, chúng bắt đầu mất đi hình dạng giống như lăng trụ và trở nên giống hình tam giác hơn.
---

###  Kim tự tháp

Kim tự tháp là một loại hình kiến ​​trúc đặc biệt được phát triển từ thời cổ đại và vẫn được sử dụng cho đến ngày nay cho các tòa nhà hiện đại. Các kim tự tháp đầu tiên được xây dựng ở Lưỡng Hà, nhưng các kim tự tháp nổi tiếng nhất là kim tự tháp Ai Cập và Maya.
    figure: x-img(src="images/ch3_41.png" width="425" height="282")

Người Ai Cập biết những bức tường thẳng đứng sẽ kém ổn định hơn khi chúng cao lên, đó là lý do tại sao lần đầu tiên họ thử những viên gạch xếp chồng lên nhau theo chiều nghiêng. Họ nhận ra rằng một kim tự tháp giúp bạn có được sự ổn định nhất với ít vật liệu nhất.

Nhờ sự ổn định của cấu trúc hình tam giác, Đại kim tự tháp Giza vẫn là công trình cao nhất thế giới trong 4000 năm cho đến khi tháp Eiffel được xây dựng vào năm 1889. Đại kim tự tháp là di tích lâu đời nhất trong danh sách Bảy kỳ quan thế giới cổ đại , được xây dựng cách đây gần 4600 năm.

Bạn có thể tưởng tượng số lượng đá cần thiết để xây dựng những kỳ quan cổ đại khổng lồ này không?

    // BÌNH LUẬN: https://depositphotos.com/15412875/stock-photo-view-of-the-pyramids-near.html

    figure: x-img(src="images/ch3_47.png" width="600" height="243")


Đại kim tự tháp Giza cùng với Kim tự tháp Menkaure và Kim tự tháp Khafre

Giống như hình lăng trụ, những hình chóp cũng là hình đa diện. Nhưng không giống như lăng trụ, ** hình chóp ** chỉ có [[một | hai | ba]] đa giác ** đáy **. Tất cả các mặt khác của hình chóp đều gặp nhau tại một [[đỉnh | mặt | cạnh]] được gọi là _ {span.comments (text = "(gloss: Đỉnh của hình chóp) mục mới - cần định nghĩa | Đỉnh của hình chóp là điểm mà các mặt bên gặp nhau. ")} ** Đỉnh hình chóp ** _.
---

Có rất nhiều loại hình chóp khác nhau, tùy thuộc vào hình dạng của đáy của chúng.

** Cũng giống như hình lăng trụ, Hình chóp được đặt tên theo hình dạng của  ** _ {span.comments (text = "Có thể tạo một phần tương tác ở đây trong đó học sinh nhấp chuột vào phần đáy như tôi đã mô tả trong phần hình lăng trụ? Không phải là chủ yếu ở đây, nhưng ít nhất cũng phải có một kết nối tốt. ")} ** đáy ** _.
   
 figure: x-img(src="images/ch3_79.png" width="600" height="237")

    figure: x-img(src="images/ch3_71.png" width="327" height="393")

    figure: x-img(src="images/ch3_57.png" width="600" height="417")

Ví dụ: nếu _ {span.comments (text = ""Hình khối tương tác với một thanh trượt để mở lưới của nó với các bộ phận được mã hóa màu")} đáy_ là một ** hình vuông **, thì nó được gọi là “ ** hình chóp ** [[vuông | tam giác]]”

---

Bất kể hình dạng của đáy của nó là gì, một hình chóp luôn có ** các mặt bên **[[tam giác | hình vuông]]. 

---

Trước khi bắt tay vào làm kim tự tháp, các nhà xây dựng Ai Cập phải tính toán thể tích của nó để có được lượng đá đúng để xây kim tự tháp.
    figure: x-img(src="images/ch3_68.png" width="600" height="600")


Hãy tưởng tượng cắt một hình chóp thành nhiều lớp mỏng song song với đáy của nó.

Tất cả các mặt cắt ngang sẽ có hình dạng hoàn toàn giống nhau nhưng kích thước khác nhau. Khi bạn đi lên, kích thước của các lát cắt giảm tỷ lệ thuận với đáy của kim tự tháp. Các thiết diện của hình chóp song song với đáy của nó đồng dạng nhưng không [[đồng đẳng | bằng]].

---

Vì hình chóp được tạo thành bằng cách giảm kích thước của các lớp có cùng đáy, chúng ta [[không thể | có thể]] sử dụng ‘** _ diện tích của đáy nhân với chiều cao _ **’ để tính ** thể tích **.

---

Đây chắc chắn là một lợi thế lớn trong quá trình xây dựng, nhưng nó đòi hỏi một phương pháp khác để tính thể tích của các hình chóp
{.fixme} Chúng ta nên thêm một đoạn văn (và sơ đồ tương tác) cho thấy rằng tất cả các mặt cắt song song với các đáy là đồng dạng (nhưng không đồng đẳng).

Khi tôi dạy điều này ở trường, chúng tôi có một tập hợp nhiều hình lăng trụ và hình chóp khác nhau có cùng đáy và cùng chiều cao. Học sinh dự đoán xem sẽ có bao nhiêu hình chóp để lấp đầy hình lăng trụ liên quan. Sau đó, học sinh dùng gạo hoặc mì ống hoặc nước để kiểm tra giả thuyết của mình. Họ đổ đầy hình chóp và đổ nó vào lăng trụ và đếm xem cần bao nhiêu để lấp đầy nó. Tôi thấy đây là một bài học thực sự mạnh mẽ và hiệu quả. Tôi tự hỏi làm thế nào một số trong số đó có thể được kết hợp ở đây? Tôi vẽ hình ảnh GIF trên trang chiếu đầu tiên có một số hoạt ảnh về điều đó, nhưng tôi tự hỏi liệu có cách nào để khiến học sinh làm điều đó không? Có thể có một hình chóp hình vuông rỗng và một hình hộp chữ nhật rỗng và đổ đầy nước vào hình chóp bằng cách đặt nó dưới một cái bồn rửa và sau đó họ phải kéo nó qua hình hộp và lấp đầy khối đó. Sau đó, họ thực sự sẽ phải làm điều đó 3 lần. Không hoàn toàn mạnh mẽ như tôi nghĩ, nhưng nếu họ làm điều đó 2-3 lần, họ sẽ giúp xây dựng sự hiểu biết về công thức. | Tôi hoàn toàn đồng ý - Tôi đã thực hiện cùng một thí nghiệm với các học sinh của mình với bộ các hình khối hình học .. Tôi đã định nói chuyện với Philipp về các hình ảnh động, pills, mục tiêu di chuột trong phần này. Phần này phải thực sự tương tác để trẻ nắm bắt được công thức | Đồng ý với cả hai bạn ở đây. Yếu tố tương tác thực sự cho phép học sinh khám phá ở đây sẽ giảm bớt áp lực về ngôn ngữ / văn bản. Vì đây là một khái niệm quan trọng và đôi khi là thách thức. Nó có thể đáng giá nếu bạn cần ít nỗ lực đọc nhất có thể. Và tôi nghĩ rằng tất cả các trang trình chiếu đều giúp tạo nền tảng cho sự tương tác!
---

::: tab

#### Thí nghiệm

    figure: x-img(src="images/ch3_38.jpg" width="600" height="338")

::: tab

#### Sự phân tách

    figure
        x-img(src="images/ch3_77.jpg" width="600" height="338")
        x-img(src="images/ch3_39.jpg" width="600" height="338")

::: tab

#### Hình lập phương

    figure: x-img(src="images/ch3_26.jpg" width="600" height="338")

:::

---

`"Thể tích"_"Hình chóp" = ("Diện tích đáy" * "Chiều cao") / 3`

Bây giờ chúng ta có thể tính toán số lượng đá cần thiết để xây dựng Đại kim tự tháp Giza.

::: column.fit

    figure: x-img(src="images/ch3_pyramid_3.png" width="326" height="202")

::: column.grow

Chiều cao của Đại kim tự tháp Giza là 146,7 m.

Hãy chắc chắn rằng bạn không nhầm lẫn ** chiều cao nghiêng ** của hình chóp với ** chiều cao hình chóp. **

_{span.comments(text="(gloss:chiều cao mặt bên)thuật ngữ mới - cần định nghĩa. Định nghĩa ở đây là khởi đầu tốt. | Chiều cao nghiêng là số đo dọc theo mặt hình tam giác. Đó là chiều cao của mặt bên. ")} ** Chiều cao nghiêng ** _ là số đo dọc theo một mặt hình tam giác. Nó là chiều cao của mặt bên.
:::

_{span.comments(text="(gloss:solid-height)thuật ngữ mới - cần định nghĩa. Định nghĩa ở đây là khởi đầu tốt.  | Chiều cao hình chóp là số đo bên trong từ đỉnh đến tâm của đáy. ")} ** Chiều cao hình chóp ** _ là số đo bên trong từ đỉnh đến ** tâm ** của đáy.

Để có thể tính thể tích của một hình chóp, bạn cần biết [[chiều cao hình chóp| chiều cao nghiêng]].
---

::: column.fit

    figure: x-img(src="images/ch3_70.png" width="300" height="268")

::: column.grow

Đáy của Đại kim tự tháp là một hình vuông với mỗi cạnh có kích thước 230 m và có diện tích là [[52900]] `" m "^ 2`.

Cái đó bao nhiêu? Hãy tưởng tượng một sân bóng đá. Gần 10 sân bóng có thể nằm gọn trong nền của Đại Kim Tự Tháp.

Nhớ lại rằng thể tích của hình chóp là [[một phần ba | một nửa]] tích của diện tích đáy và chiều cao.

Vậy thể tích là: `" Thể tích "= (" Diện tích đáy"*" Chiều cao ") / 3 = 2,6" triệu "" m "^ 3`

:::

---

Có nhiều chỗ cho Pharaoh và đồ đạc của ông ấy. Người ta ước tính khoảng 2,3 triệu khối đá, mỗi khối nặng trung bình từ 2,5 đến 15 tấn đã được sử dụng để xây dựng một kim tự tháp có kích thước như vậy. Truyền thuyết kể rằng công trình này được xây dựng chỉ trong 20 năm, nghĩa là cứ 5 phút mỗi ngày đêm lại phải di chuyển một khối nhà vào vị trí.
    figure: x-img(src="images/ch3_45.png" width="600" height="489")

    figure: x-img(src="images/ch3_25.jpg" width="600" height="681")

_{span.comments (text = "Có thể bằng cách sử dụng hai hình ảnh này, một hoạt ảnh trước-sau có thể được tạo ra.")} _Một sự thật ít được biết đến về Đại kim tự tháp Giza là nó được bao phủ bởi màu trắng mịn _{span.comments (text = "Lớp đá bên ngoài của kim tự tháp Khufu được xây bằng đá Tura. Đây là một loại đá vôi trắng đẹp đặc biệt và được khai thác ở Tura, nằm về phía đông nam của Giza ở phía bên kia sông Nile. ")}Tura_ vỏ đá vôi, hiện chỉ tồn tại ở nắp trên ._ {span.comments (text = "Một quá trình chuyển đổi rất hay.")}Đá này bao phủ lớp ngoài của các mặt bên của kim tự tháp để làm cho chúng hoàn toàn nhẵn_.

Nó được đánh bóng cho đến khi tỏa sáng để kim tự tháp lấp lánh dưới ánh mặt trời.

Hãy nghĩ xem cần bao nhiêu khối đá vôi để bao phủ Đại kim tự tháp. Để xác định có bao nhiêu khối, chúng ta cần biết [[diện tích bề mặt | thể tích]] của 4 mặt bên hình tam giác của hình chóp.
---

::: column.fit

    figure: x-img(src="images/ch3_72.png" width="300" height="268")

::: column.grow

Nhớ lại rằng tất cả các hình chóp có chiều cao nghiêng, là chiều cao của [[mặt bên | mặt đáy]] của nó. Nó thường được ký hiệu là `s` hoặc` l`.

Chiều cao nghiêng được sử dụng để tính [[diện tích | chu vi]] của các mặt bên.
:::

---

Chiều cao nghiêng của Đại kim tự tháp là 186,6m. Diện tích mỗi mặt tam giác là [[½ (chiều cao xx đáy) | diện tích đáy xx height]] là 21.500 `" m "^ 2`.
---

::: column.fit

    x-img(src="images/ch3_pyramid_side.svg" width="200" height="164")

::: column.grow

Vì chúng ta có [[4]] mặt bên nên tổng ** diện tích mặt bên ** là _ {span.comments (text = "Thay vì kết quả trực tiếp, đây cũng có thể là trình bày bằng một phương trình ")} [[86000]] _

Mỗi khối đá vôi bao phủ khoảng 1,25 mét vuông. Vì vậy, người Ai Cập cần thêm gần 70 000 đá vôi trắng để che các mặt bên của kim tự tháp.

Mặc dù vẫn còn là một bí ẩn về cách người Ai Cập xây dựng các kim tự tháp, _ {span.comments (text = "gph.is/1yqexne")}, nó không còn là điều bí ẩn đối với chúng ta về số lượng đá được sử dụng để xây hoặc đắp chúng_.
:::

---

Các phép tính Diện tích bề mặt trong lăng trụ và hình chóp có nhiều bước hơn so với việc tìm thể tích của chúng.

Trong tính toán diện tích bề mặt, ** lưới ** cho phép chúng ta nhìn thấy tất cả các mặt của hình khối cùng một lúc. Trong khi tính toán diện tích bề mặt, diện tích đáy hoặc diện tích mặt bên, thay vì làm việc trên hình ảnh của hình khối, việc vẽ lưới giúp chúng ta hình dung các mặt ẩn.
_{span.comments(text="Có thể là một sự thật thú vị, thông tin này cũng có thể được thêm vào (không cần giải thích thêm)?.")} Bạn có biết điều đó không? _

Cách hiệu quả nhất để xếp trái cây là gì?

::: column.fit

    figure: x-img(src="images/ch3_12.png" width="200" height="146")

::: column.grow

Trên các quầy hàng ở chợ hoặc xe bán hàng rong, hầu hết các loại trái cây như táo và cam được sắp xếp thành [[hình chóp| lăng trụ]].

Năm 1611, Johannes Kepler tuyên bố rằng đặt mỗi quả lên trên một khoảng trống của lớp quả bên dưới là cách sắp xếp các vật hình cầu hiệu quả nhất.

Sau gần 400 năm, vào năm 1998, Thomas Hales đã trình bày một chứng minh về Giả thuyết Kepler. Chứng minh dài 300 trang và phải cần đến máy tính để xác minh tính đúng đắn của nó.
:::

Rõ ràng, khi nói đến việc xếp đá và trái cây hoặc chất đống đạn của súng thần công trên tàu, hình chóp luôn là hình dạng thuận tiện nhất!

---

### Các lưới của lăng trụ và hình chóp

** Hãy nhớ **, các lưới bao gồm [[đa giác | hình hộp chữ nhật | hình vuông]] tạo thành các mặt của một hình đa diện.


---

      // BÌNH LUẬN: Gấp lưới của hoạt ảnh đa diện khác nhau: Solids w / Slide

    figure: x-img(src="images/ch3_14.jpg" width="600" height="349")

    figure: x-img(src="images/ch3_59.png" width="316" height="159")

    figure: x-img(src="images/ch3_3.png" width="500" height="302")

---

// BÌNH LUẬN: Trò chơi kết hợp

Ở đây bạn có lưới các lăng trụ hoặc hình chóp khác nhau.

Ghép mỗi lưới với hình khối mà nó thuộc về.

    figure: x-img(src="images/ch3_51.png" width="600" height="134")

    figure: x-img(src="images/ch3_5.png" width="298" height="282")

    figure: x-img(src="images/ch3_44.png" width="309" height="223")

    figure: x-img(src="images/ch3_2.png" width="460" height="220")

    figure: x-img(src="images/ch3_15.png" width="600" height="389")

    figure: x-img(src="images/ch3_55.png" width="600" height="99")

    figure: x-img(src="images/ch3_78.png" width="600" height="568")

    figure: x-img(src="images/ch3_74.png" width="259" height="292")

    figure: x-img(src="images/ch3_55.png" width="600" height="99")

   
   // BÌNH LUẬN: Sau mỗi kết hợp đúng, lưới sẽ gấp lại để bao bọc hình khối.

_{span.comments (text = "Đây cũng giống như một cái nhìn tổng quan về các lăng trụ và hình chóp khác nhau - tôi đã nghĩ đến việc đưa ra các ví dụ thực tế về từng hình trong số chúng bên cạnh phần giải thích - nhưng nó có thể mâu thuẫn với trò chơi- như bản chất của hoạt động? | Tôi nghĩ nó có thể hoạt động, đặc biệt là vì câu hỏi được 'mở khóa'. Văn bản có thể ở trong một cột và ảnh có thể ở trong một cột. Ảnh có thể có chú thích ngắn gọn giải thích mối liên hệ. Đối với tôi , điều này phù hợp với ý tưởng chơi game là mở khóa thông tin ẩn. | HOẶC có thể sinh viên ghép lưới với ví dụ ngoài đời? | có thể sau khi khớp với lăng trụ thực, lăng trụ có thể chuyển sang ví dụ ngoài đời thực? Tôi không chắc | Chắc chắn cái này đã được làm bởi Philipp. Tôi nghĩ bạn đang có một cái gì đó thú vị. ")} _
   
  // BÌNH LUẬN: Sau mỗi kết hợp đúng:
  // BÌNH LUẬN: Cho hình lăng trụ chữ nhật

Một lăng trụ hình chữ nhật có [[ba | bốn | năm | hai]] cặp hình chữ nhật, tức là. sáu mặt hình chữ nhật. Hãy nhớ rằng, lăng trụ hình chữ nhật còn được gọi là [[hình hộp chữ nhật | hình chữ nhật]].

---

   // BÌNH LUẬN: Cho hình chóp tam giác

Một hình chóp tam giác có [[4]] mặt là tam giác. Nếu tất cả các tam giác như nhau thì nó là một ** đa diện đều ** và được gọi là ** tứ diện đều. Khối tứ diện đều có 4 tam giác bằng nhau. **

---

   // BÌNH LUẬN: Cho lăng trụ bát giác

Một lăng trụ bát giác có [[2]] đáy là bát giác và [[8]] mặt bên là hình chữ nhật.
---
    // BÌNH LUẬN: Cho hình chóp lục giác

Một hình chóp lục giác có [[1]] đáy là lục giác và [[6]] mặt bên là tam giác.
---

   // BÌNH LUẬN: Đối với hình lập phương

Một hình lập phương có [[6]] mặt là hình vuông  _đồng đẳng_ với nhau. Một **Hình lập phương** cũng là một [[đa diện đều | đa giác đều]].

---

  // BÌNH LUẬN: Cho lăng trụ tam giác

Một lăng trụ tam giác có [[2]] đáy là tam giác và [[3]] mặt bên là hình chữ nhật.

---
> id: nets-properties
> goals: all-swiped

Lưới của khối đa diện có thể cung cấp cho bạn rất nhiều thông tin về các mặt và các đặc điểm khác của hình khối. Các thuộc tính của lưới có thể giúp chúng ta so sánh và đối chiếu giữa các lăng trụ và kim tự tháp.

Vuốt từng thuộc tính sang loại thích hợp
    // INTERACTIVE-3.12

::: x-binary-swipe(a-title="Nets of prisms" b-title="Nets of pyramids")

{div.card(solution="a")} Chúng có thể có hình chữ nhật làm mặt bên


{div.card(solution="b")} Chúng có tất cả các hình tam giác là các mặt bên

{div.card(solution="b")} Chúng có một đa giác mà không phải là tam giác

{div.card(solution="a")} Chúng có một cặp đa giác mà không phải là hình chữ nhật

{div.card(solution="b")} Số mặt bên của chúng bằng số cạnh của đáy của chúng

:::

---

Trong chương trước, chúng ta cũng đã thấy rằng có nhiều lưới cho một khối lập phương. Còn hình lăng trụ và hình chóp thì sao?

Có phải chỉ có một lưới duy nhất có thể cho họ?

    figure: x-img(src="images/ch3_48.png" width="600" height="359")

_Các đa giác có thể được sắp xếp theo [[các cách khác nhau | chỉ có một cách]] để được ghép vào cùng một lăng trụ hoặc hình chóp._

---

Bạn có thể sắp xếp các hình tam giác và hình chữ nhật này theo nhiều cách khác nhau để gấp thành một hình lăng trụ tam giác.

Sử dụng lưới để vẽ một trong các lưới có thể có của lăng trụ tam giác.

    // BÌNH LUẬN: Sau đó, các lưới có thể khác sẽ xuất hiện.

    figure: x-img(src="images/ch3_23.png" width="507" height="87")

   // BÌNH LUẬN: giống như biến hình ‘một lưới đóng lại tạo thành lăng trụ, sau đó mở ra như một lưới khác và tiếp tục như vậy‘ 

    figure: x-img(src="images/ch3_60.png" width="564" height="846")

---

Chúng ta có thể chưa xây kim tự tháp hay tòa nhà cao nhất thế giới, nhưng chúng ta có thể bắt đầu lập kế hoạch cho một ngôi nhà trên cây (nhà trò chơi/ lều…).

Giống như người Ai Cập, trước khi bắt đầu xây dựng, chúng ta cần tính toán lượng vật liệu mà chúng ta sẽ sử dụng cho bề mặt bên ngoài của mô hình.

Một hình lăng trụ có hình dạng ngôi nhà được tạo ra bằng cách gắn một [[lăng trụ tam giác hình chóp tam giác | hình chóp hình vuông]] trên đỉnh của một [[hình lăng trụ chữ nhật | hình lăng trụ ngũ giác]].
---

Những loại hình khối này được gọi là ** Hình khối hỗn hợp **.

Một _{span.comments(text="(gloss:Hình khối hỗn hợp)thuật ngữ mới - Cần định nghĩa. Định nghĩa ở đây là khởi đầu tốt. | Hình khối tổng hợp là một hình được tạo thành từ nhiều hơn một hình khối. ")} ** composite solid ** _ là một hình được tạo thành từ nhiều hơn một hình khối.
::: column.fit

    figure: x-img(src="images/ch3_76.svg" width="300" height="264")

::: column.grow

    // TODO: Quyết định làm gì với cái này(can blanks be pills?)

Đáy của lăng trụ hình ngôi nhà bao gồm [[[hình chữ nhật]]] (pill: xanh mòng két) và [[[hình tam giác]]] (pill: màu cam).

Chúng ta có thể tìm diện tích của hình chữ nhật và hình tam giác riêng biệt rồi cộng chúng lại để tìm ra [[diện tích đáy | chu vi đáy]].

[Diện tích hình chữ nhật](pill:teal)is _{span.comments(text="Equation field")}`3 xx 2 = 6 "m"^2`_ and the [triangle’s area](pill:orange) is _{span.comments(text="Equation Field")}`(1/2) (3 xx 2) = 3 "m"2`_

Vì thế diện tích là  [[9]] `"m"^2`

:::

---

Bây giờ chúng ta có thể tìm thấy ** diện tích mặt bên ** của mô hình;

Có cách nào để đơn giản hóa các phép tính?

Hãy tưởng tượng bạn mở lăng trụ thành một tấm lưới. Sử dụng thanh trượt để xem ** lưới ** của lăng trụ hình ngôi nhà.
    figure: x-img(src="images/ch3_40.png" width="600" height="315")

    // BÌNH LUẬN: Màu được mã hóa - có thể xoay - Mô hình tương tác với thanh trượt để mở lưới của nó

    // BÌNH LUẬN: Khi mặt bên mở ra:

Đôi khi chúng ta có thể đơn giản hóa quá trình bằng cách kết hợp các mặt bên và tìm diện tích của vùng kết hợp.

    figure: x-img(src="images/ch3_52.png" width="600" height="551")

   
// BÌNH LUẬN: Cảnh 1

Chúng ta có thể sử dụng một hình chữ nhật lớn thay vì những hình nhỏ hơn riêng biệt.

Chúng ta có thể coi ngôi nhà giống như hình lăng trụ có ba phần: hai đáy giống hệt nhau và một hình chữ nhật dài được dán dọc theo các cạnh của đáy.

Hình chữ nhật có chiều cao [[giống | khác]] với hình lăng trụ và chiều rộng của nó là [[chu vi của đáy | chiều rộng của đáy]].
---

   // BÌNH LUẬN: Cảnh 2

    figure: x-img(src="images/ch3_8.png" width="600" height="569")

** Trên thực tế, đối với tất cả các hình lăng trụ, bạn có thể kết hợp từng mặt bên là hình chữ nhật và tìm tổng diện tích mặt bên bằng cách nhân chiều cao của hình lăng trụ với chu vi của mặt đáy. **

Vậy diện tích của hình chữ nhật lớn mà bao phủ tất cả các mặt bên của lăng trụ là [[12]] xx 4 = [[48]] `" m "^ 2`.

---

    // BÌNH LUẬN: Cảnh 3

Bây giờ, tất cả những gì chúng ta sẽ làm là thêm hai [[diện tích đáy | chu vi đáy]] vào [[diện tích mặt bên | chu vi mặt bên]].

---

Vì vậy diện tích toàn phần là  [[66]] `"m"^2`.

---

Còn về thể tích thì sao?

Diện tích đáy là 9 `" m "^ 2` và chiều cao là [[4]]` "m" `.
---

Do đó, sau khi hoàn thành việc xây dựng, ngôi nhà trên cây của bạn sẽ có thể tích là [[36]] `" m "^ 3`

---

Bạn có thể có các thiết kế khác nhau cho ngôi nhà trên cây của mình, nhưng, miễn là chúng có hình dạng giống như lăng trụ, thể tích của chúng sẽ luôn được tính là `` "Diện tích đáy" xx "Chiều cao" `.
_{span.comments(text="Tôi không chắc sẽ đưa phần này vào vì chương ngày càng dài hơn.  Ví dụ: chúng ta có thể tạo một ngôi nhà với hình chóp và hình lăng trụ để tìm thể tích. Tôi cũng sẽ đưa các ví dụ đó vào nhé? Hay giống như một nội dung trung gian? | Bạn nói đúng, tôi nghĩ điều này sẽ tăng thêm độ dài. Nếu bạn kết thúc việc xây dựng thể tích tương tác ở trên, tôi nghĩ rằng ý tưởng này đủ tương tự với điều này để bạn không cần phải xây nhà. | Tôi tự hỏi liệu điều này có có đáng để trò chuyện nhanh chóng hoặc trong một cuộc gọi không? Tôi tiếp tục xem xét lại các ý tưởng. ")} _ 
                                                                                                     
    // BÌNH LUẬN : Bộ sưu tập hoạt ảnh

    figure: x-img(src="images/ch3_73.png" width="600" height="572")

    figure: x-img(src="images/ch3_18.png" width="563" height="372")

    figure: x-img(src="images/ch3_61.png" width="450" height="450")

    // BÌNH LUẬN : Trên các hình đã cho, học sinh có thể được yêu cầu  xác định diện tích đáy.

    // BÌNH LUẬN : Trên các hình đã cho, học sinh có thể được yêu cầu xác định diện tích đáy. Sau khi tạo diện tích đáy chính xác; Giá trị của diện tích đáy xuất hiện.

    // BÌNH LUẬN : Trên các hình đã cho, học sinh có thể được yêu cầu xác định diện tích đáy. Sau đó chúng ta yêu cầu học sinh xác định chiều cao.
    
    // BÌNH LUẬN: Trên các hình đã cho, học sinh có thể được yêu cầu  xác định diện tích đáy. Và giá trị của chiều cao xuất hiện.

    // BÌNH LUẬN: Trên các hình đã cho, học sinh có thể được yêu cầu  xác định diện tích đáy. Sau đó họ nhập các giá trị cần thiết để tính Thể tích.

    // BÌNH LUẬN: Trên các hình đã cho, học sinh có thể được yêu cầu xác định diện tích đáy. Và giá trị của thể tích xuất hiện.] (pill: xanh lam)
---

## Hình trụ và hình nón

> section: cylinder-cone
> sectionStatus: dev

** Bạn đã bao giờ tự hỏi tại sao tất cả các tên lửa đều có hình dạng giống nhau? **

::: column.fit

    figure: x-img(src="images/ch4_19.png" width="300" height="281")

::: column.grow

Trong 60 năm qua, công nghệ tên lửa đã phát triển vượt bậc, và hơn 35 000 tên lửa đã được đưa lên vũ trụ.

Trong khi phóng tên lửa lên vũ trụ, bạn cần lưu ý ba lực lượng chính:

_ {span.comments (text = "Trọng lực là lực hút một vật hướng vào tâm trái đất hoặc bất kỳ hành tinh nào khác.")} * Trọng lực * _, _ {span.comments (text = "Lực cản không khí là  lực ngược hướng với chuyển động của một vật khi nó đi qua không khí. Còn được gọi là 'lực cản'. ")} * lực cản của không khí * _ and _ {span.comments (text =" Lực đẩy của một động cơ phản lực hoặc tên lửa. Lực đẩy do động cơ tên lửa tạo ra bằng cách sử dụng nhiên liệu để đẩy tên lửa lên. ")} * lực đẩy * _
:::

Hình dạng của tên lửa được thiết kế để giảm thiểu lực cản của không khí được gọi là lực cản. Các bề mặt trơn, ** bề mặt tròn ** tạo ra ít ma sát hơn nên gây ra lực cản [[ít | nhiều]] hơn.
---

Do đó, rõ ràng là chúng ta cần [[không đa diện | đa diện]] trong thiết kế tên lửa.
---

** Tên lửa là**_{span.comments (text ="Pills: hình nón biến mất ở mô hình tên lửa - và chỉ hình trụ được hiển thị.")} ** hình trụ ** _ ** trong thân và ** _ { span.comments (text = "Pills: hình trụ biến mất ở mô hình tên lửa - và chỉ hình nón được hiển thị.")} ** hình nón ** _ ** ở trên cùng. **
Chúng ta có thể coi ** hình trụ ** là phiên bản có dạng tròn của lăng trụ. Tương tự, chúng ta nói rằng phiên bản tròn của một hình chóp là một ** hình nón **.
::: column(width=300)

    // Lăng trụ-> Hoạt ảnh hình trụ

Sử dụng _{span.comments(text="Variable slider")}thanh trượt_ để tăng số lượng các cạnh của hình lăng trụ

Khi số lượng các cạnh tăng lên, lăng trụ bắt đầu giống một hình trụ hơn.

    figure: x-img(src="images/ch4_30.png" width="300" height="107")

::: column(width=300)

    // Hình chóp->Hoạt ảnh hình nón

Dùng thanh trược để tăng số lượng các cạnh của hình lăng trụ.
Khi số lượng các cạnh tăng lên, hình chóp bắt đầu giống một hình nón hơn.

    figure: x-img(src="images/ch4_27.png" width="150" height="154")

:::
    // Một hình trụ tương tác
::: column.fit

    figure: x-img(src="images/ch4_33.png" width="150" height="150")

::: column.grow

Hình trụ bao gồm hai hình tròn đồng đẳng, song song được nối với nhau bởi một mặt cong. Các vòng tròn này là các_ {span.comments (text = "pills")}đáy _ ** của hình trụ.
Phần hình trụ của tên lửa chứa các thành phần thiết yếu của tên lửa như oxy lỏng, bình chứa hydro và động cơ.
:::

---

Trên thực tế, tất cả các bình chịu áp lực như tàu chở nhiên liệu đều có hình tròn, vì hình tròn cung cấp sức mạnh tối đa từ áp suất bên trong. Hình dạng hình trụ làm trọng lượng nhẹ hơn cho các bức tường tên lửa. Hình trụ cũng không có bất kỳ "điểm yếu" nào như các cạnh của [[lăng trụ | đa giác]].
---

::: column.fit

    figure: x-img(src="images/ch4_1.png" width="170" height="156")

::: column.grow

Vấn đề duy nhất với các cấu trúc hình trụ là tỷ lệ kéo. Giá trị này có thể được giảm một chút bằng cách thêm một hình nón lên trên cùng.

Hình dạng hình nón có thể ở các dạng khác nhau tùy theo mục đích của tên lửa.

:::

    // Một hình nón tương tác

::: column.fit

    figure: x-img(src="images/ch4_24.png" width="150" height="150")

::: column.grow

Một hình nón có [[chỉ một | hai]] **đáy** hình tròn được nối với một điểm duy nhất được gọi là ** đỉnh ** hoặc ** đỉnh hình nón **.

Mũi hình nón của tên lửa thường chở các vật như vệ tinh, hàng hóa hoặc hành khách. Nếu là bình xăng bên ngoài, nó mang bình ôxy lỏng.
:::

---

Nón mũi cũng được thiết kế cho tất cả các tàu bay như máy bay và tàu bay zeppelins cũng như các phương tiện dưới nước và trên đất liền với tốc độ cao.

Trong khi hình dạng của các tên lửa hầu hết giống nhau, chúng có thể có kích thước khác nhau tùy theo loại nhiệm vụ.

** Chiều cao của tên lửa có nhiệm vụ quay quanh quỹ đạo mang trọng tải 23 tấn là bao nhiêu? **
::: column.fit

    figure: x-img(src="images/ch4_8.png" width="188" height="142")
    // https://www.youtube.com/watch?time_continue=5&v=su9EVeHqizY&feature=emb_logo
    // https://en.wikipedia.org/wiki/Space_Shuttle_external_tank#/media/File:STS-116_PreLaunch_(NASA_KSC-06PD-2670).jpg

::: column.grow

Loại nhiệm vụ ảnh hưởng đến lượng nhiên liệu mà tên lửa phải mang theo. Phần đáng kể của thể tích của tên lửa được chứa bởi các thùng nhiên liệu, do đó kích thước của tên lửa chủ yếu phụ thuộc vào các thùng nhiên liệu.

Đối với một nhiệm vụ trên quỹ đạo, các thùng nhiên liệu phải có khả năng chứa khoảng 550 nghìn lít oxy lỏng và 1,5 triệu lít hydro.
:::

Trong một tàu con thoi, thùng nhiên liệu bên ngoài mang một bình hydro lỏng hình trụ.

** Thể tích ** của hình trụ là số đo mô tả hình trụ sẽ chứa bao nhiêu (tính theo đơn vị thể tích). Nó là một số đo của không gian bên trong hình trụ.

Hãy nghĩ về một xấp tiền xu như một mô hình của một hình trụ. Số đồng xu bạn đặt chồng lên nhau thực sự là _ {span.comments (text = "Chiều cao của hình trụ là khoảng cách vuông góc giữa các đáy.")} [[Chiều cao | bán kính| đường kính | chu vi] ] _ của hình trụ.
::: column.fit

    figure: x-img(src="images/ch4_15.png" width="239" height="118")

::: column.grow

Vì vậy, không gian bạn đã tạo với chồng xu về cơ bản là [[chiều cao | chiều rộng]] nhân với [[diện tích | chu vi]] của mỗi đồng xu.

Giống như các lăng trụ, một hình trụ có thể tích bằng ** tích của ** [[diện tích đáy | chu vi đáy]] ** và ** [[chiều cao | chiều rộng]] của nó.
:::

---

Nhớ lại rằng tỉ số giữa diện tích hình tròn và bình phương bán kính của nó là một số không đổi được gọi là_{x-equation.small(solution="π" keys="π")}_. Vậy diện tích hình tròn là _{x-equation.small(solution="π r^2" keys="π sup" short-var)}_.
---

Pi là một số [[vô tỉ | hữu tỉ]].
---

Điều này chỉ ra rằng phần thập phân của π vô hạn không tuần hoàn.
π = 3.1415926…

Thể tích của một hình trụ là,

{.text-center} `"V"_"Hình trụ" = "Diện tích đáy" xx "chiều cao"`

{.text-center} `"V"_"Hình trụ" = ` _{x-equation.small(solution="π r^2 × h" keys="π sup ×" short-var)}_

---

::: column.fit

    figure: x-img(src="images/ch4_25.png" width="300" height="176")
    //  https://www.nasa.gov/centers/johnson/pdf/584722main_Wings-ch3a-pgs53-73.pdf

::: column.grow

Bình chứa hydro hình trụ có đường kính khoảng 8 mét. Nó cần chứa 1,5 triệu lít hydro.

Hãy nhớ `1" \ dm "^ 3 = 1" \ lít "`

Vì vậy, thể tích của bình hydro phải vào khoảng [[1500]] `m ^ 3`.

:::

---

`1500 = input(pi) * input(4)^2 * "Chiểu cao"_"Bính chứa hydro lỏng"` khoảng 30 mét.

---

Mặt khác, bình oxy lỏng nằm ở trên cùng của bình bên ngoài và có ** dạng hình nón **.

Hãy nhớ rằng hình nón là [[hình chóp | lăng trụ]] - giống như hình khối có đáy là hình tròn
---

Mặc dù về mặt kỹ thuật, một hình nón không phải là một hình chóp, nhưng chúng có chung nhiều tính chất.

Để tính thể tích của một hình nón, chúng ta có thể sử dụng cùng một công thức với hình chóp được không?

Tỉ số thể tích của hình chóp và lăng trụ với đáy có cùng kích thước, hình dạng và cùng  _ {span.comments (text = "Chiều cao của hình nón là khoảng cách vuông góc giữa tâm của đáy và đỉnh hình nón.") } chiều cao_ is [[1]]: [[3]].
---

::: column.fit

    figure: x-img(src="images/ch4_3.gif" width="150" height="125")

::: column.grow


Hãy lặp lại thí nghiệm tương tự để xem cần bao nhiêu hình nón chứa nước để đổ đầy hình trụ có cùng bán kính và chiều cao.

Lấy nội dung của [[3]] hình nón để lấp đầy hình trụ có cùng đáy và chiều cao. Điều này có nghĩa là,
:::

---

{.text-center} `"V"_"Hình nón" =` _{x-equation.small(solution="1 / 3" keys="frac" numeric)}_ `xx blank("Base Area", "Base Perimeter") xx blank("height", "width")`

---

{.text-center} `"V"_"Hình nón" =` _{x-equation.small(solution="(1 / 3) × π r^2 × h" keys="frac sup π ×" short-var)}_

---

Mũi hình nón có cùng bán kính với hình trụ và phải chứa 550 nghìn lít khí oxi. Do đó bể hình nón phải có thể tích là 550 mét khối.
{.text-center} `550 =` _{x-equation.small(solution="1 / 3" keys="frac" numeric)}_ `*` _{x-equation.small(solution="π" keys="π")}_ `* input(4)^2 * blank("Height"_"OxygenTank","Radius"_"OxygenTank")`

---

{.text-center} khoảng 30 mét


Hình dạng thực của hình nón lớn hơn hình mà chúng ta đã tính toán ở đây và có chiều cao gần 17 mét. Vì vậy, tổng chiều cao của thùng phía ngoài là khoảng 50 mét.

Khi đầy nhiên liệu, chỉ riêng thùng ngoài đã nặng tới 760 nghìn kg. Các công ty tên lửa cố gắng tăng hiệu quả của tên lửa bằng cách giảm trọng lượng tổng thể và tăng khả năng chịu tải.

Theo thời gian, nhiều nỗ lực đã được thực hiện để giảm khối lượng khổng lồ của thùng. Thùng trọng lượng tiêu chuẩn được phát triển thành thùng siêu nhẹ bằng cách kiểm tra từng chi tiết nhỏ của tên lửa một cách cẩn thận.
    figure: x-img(src="images/ch4_4.png" width="400" height="308")

    // https://forum.nasaspaceflight.com/index.php?topic=39443.0


1981 Tàu con thoi Columbia so với Tàu con thoi Columbia 1982

Ban đầu, bình nhiên liệu được sơn màu trắng để bảo vệ chúng khỏi tác hại của tia cực tím. Các kỹ sư sau đó nhận ra rằng điều đó không gây ra vấn đề gì và tự hỏi ** nếu không sử dụng sơn, có thể giảm được bao nhiêu kilogram cân nặng? **

Để có thể tìm được lượng sơn đã sử dụng, chúng ta tính [[diện tích bề mặt | thể tích | chu vi]] của bể.
---

Một lần nữa, chúng ta có thể nghĩ về hình trụ và hình nón một cách riêng biệt.

** Diện tích bề mặt của hình trụ: **

 Chúng ta có thể sử dụng [[lưới | chiều cao | chiều rộng]] của hình trụ để tính diện tích bề mặt của nó.
---

::: column.fit

    figure: x-img(src="images/ch4_2.png" width="100" height="104")

    // Một hình trụ tương tác

::: column.grow

Lưới của hình trụ có hai [[hình tròn | hình chữ nhật]] với diện tích là  _{x-equation.small(solution="π r^2" keys="π sup" short-var)}_ mỗi cái. Mặt cong thực sự là một [[hình chữ nhật | hình vuông | hình tam giác | hình ngũ giác]] lớn.

Chiều cao của hình chữ nhật là [[h | w | b]] và chiều rộng của hình chữ nhật bằng [[chu vi của đáy | diện tích đáy | đường kính của đáy]] của các hình tròn.
:::

---

::: column.fit

    figure: x-img(src="images/ch4_34.svg" width="300" height="208")

::: column.grow


Vì mặt bên của hình trụ là hình chữ nhật, chúng ta có thể tìm diện tích bằng [[nhân | chia | cộng | trừ]] chiều dài và chiều rộng của hình chữ nhật;

Về cơ bản, nó là [[chu vi | bán kính | đường kính]] của đáy nhân với [[chiều cao | chiều rộng]] của hình trụ.

Do đó, diện tích bên là _{x-equation.small(solution="2 π r" keys="π" short-var)}_ `* blank("h","w")`.
:::

---

Vì vậy, ** Diện tích bề mặt ** của một hình trụ là tổng của tất cả các diện tích mặt.


{.text-center} `"S"_"Hình trụ" = ` _{x-equation.small(solution="2 π r^2" keys="π sup" short-var)}_ `+` _{x-equation.small(solution="2 π r × h" keys="π ×" short-var)}_

---

Diện tích bề mặt của phần bể hình trụ có chiều cao 30 mét, đường kính 8 mét. Đối với mô hình tên lửa, chúng ta cần tính [[chỉ một | hai]] diện tích đáy cho tổng diện tích bề mặt.
---

`"A" = (pi "r"^2) + (2 pi "r""h")`

`A = pi input(4)^2 + 2 pi input(4) * input(30)` gần đúng

---

`A = 800 blank("mét vuông","mét","mét khối")`.

---

**Diện tích bề mặt của hình nón:**

::: column.grow


Di chuyển thanh trượt để xem lưới của hình nón. Chúng ta có một [[hình tròn | hình cầu | hình vuông]] làm đáy và một [[ hình quạt tròn | tam giác | hình chữ nhật]] ở mặt bên

“s” được gọi là _ {span.comments (text = "Glossary Link")} ** chiều cao nghiêng ** _ của hình nón, giống như hình chóp. Chiều cao nghiêng là [[khác với | giống với]] chiều cao của hình nón.

Bây giờ chúng ta chỉ cần cộng diện tích của cả hai mặt;

Đáy của hình nón là hình tròn bán kính r nên diện tích của nó là

`"S"_"Đáy" =` _{x-equation.small(solution="π r^2" keys="π sup" short-var)}_

::: column.fit

    figure: x-img(src="images/ch4_11.png" width="150" height="156")

:::

---

::: column.fit

    figure: x-img(src="images/ch4_16.png" width="300" height="92")

::: column.grow

Chúng ta có thể nghĩ rằng mặt bên là một tam giác lớn bao gồm vô số tam giác. Tổng chiều dài của đáy tam giác là [[chu vi | diện tích | đường kính]] của hình tròn và chiều cao của nó là s, chiều cao nghiêng của hình nón.
:::

---

Nhớ lại rằng diện tích hình tam giác bằng một [[nửa | phần ba | phần tư]] tích của chiều dài đáy và chiều cao ứng với nó.
---

`"S"_"mặt bên" = 1/2 ` _{x-equation.small(solution="2 π r" keys="π" short-var)}_ `* blank("s","h","l")`

---

`"S"_"mặt bên" =` _{x-equation.small(solution="π r s" keys="π" short-var)}_

---


Khi đó, diện tích toàn phần của hình nón là

{.text-center} `"S"_"Hình nón" =` _{x-equation.small(solution="π r^2 + π r s" keys="π sup +" short-var)}_

---

Để tìm lượng sơn đã sử dụng, chúng ta cần tính [[diện tích mặt bên| diện tích đáy | diện tích bề mặt]] của hình nón.
---

Phần hình nón của bể có chiều cao nghiêng 20 mét và đường kính 8 mét.

`"S"_"Mặt bên" = pi * input(4) * input(20)` gần đúng

---

`"S"_"Mặt bên " = 250 blank("square meters", "meters", "cubic meters")`.

---

Tổng diện tích bề mặt của tên lửa là tổng diện tích của phần thân hình trụ [[800]] mét vuông và hình nón ở mũi [[250]] mét vuông là [[1050]] mét vuông.
---

Nếu một gallon sơn được sử dụng để phủ một ** 12 mét vuông, ** để phủ toàn bộ bể, thì gần như [[90]] gallon sơn phải được sử dụng.
---

Trọng lượng ước tính của một gallon sơn bên ngoài là gần 3 kg. Do đó, bằng cách không sơn xe tăng, các kỹ sư đã tiết kiệm [[270]] kg mà họ có thể sử dụng để tăng sức chở hàng hóa hoặc tăng hiệu quả của tàu con thoi
---

Cho đến nay, chúng ta đã học được diện tích bề mặt và các phép tính thể tích của hình trụ và hình nón cũng như các tính chất độc đáo của những hình khối này khiến chúng trở thành lựa chọn đúng đắn cho thiết kế tên lửa cũng như các phương tiện giảm lực cản trên cạn và dưới nước ..

Nếu chúng ta xem xét lại câu hỏi ban đầu của mình, chúng ta có thể xem xét một tính chất khác của hình trụ.

Hãy so sánh thể tích của các lăng trụ khác nhau có cùng chu vi đáy và chiều cao ;

    figure: x-img(src="images/ch4_28.png" width="600" height="532")


// Phiên bản 3D của applet này?

Nó cũng chỉ ra rằng các hình [[hình trụ | hình cầu | hình nón]] có thể tích lớn nhất so với các hình lăng trụ khác nhau có cùng chu vi đáy và chiều cao. Đây là một lý do khác khiến hình trụ có các đặc tính tốt nhất khi làm thùng chứa thực phẩm và đồ uống mà chúng ta sử dụng hàng ngày và các bồn chứa khổng lồ như silo chứa ngũ cốc.
---

::: column.fit

    figure: x-img(src="images/ch4_12.png" width="150" height="87")
    // 1: Fuel Storage tanks : https://depositphotos.com/65819151/stock-photo-fuel-storage-tank.html

::: column.fit

    figure: x-img(src="images/ch4_13.png" width="150" height="100")
    // 2: Tanker Truck: https://depositphotos.com/66305481/stock-photo-tanker-trucks.html

::: column.fit

    figure: x-img(src="images/ch4_10.png" width="300" height="111")
    // 3: Canned foods and beverages: https://depositphotos.com/51100149/stock-illustration-set-of-cans.html

::: column.fit

    figure: x-img(src="images/ch4_14.png" width="150" height="109")
    // 4: Scuba Tank: https://depositphotos.com/stock-photos/scuba-tank.html?filter=all\&qview=10890755

::: column.fit

    figure: x-img(src="images/ch4_17.png" width="150" height="100")
    // 5: Grain Silos: https://depositphotos.com/stock-photos/grain-silos.html?filter=all\&qview=17129999

:::

    // TIẾP TỤC

---


Trước đó, chúng ta đã thấy rằng hình trụ có các đặc tính tốt nhất như một vật chứa trong khi hình nón thường được sử dụng làm mái nhà, nơi trú ẩn, giỏ, v.v.

Trong suốt lịch sử, các túp lều và mái nhà hình nón được xây dựng và sử dụng bởi các nền văn minh khác nhau trên khắp thế giới ở những địa điểm và thời điểm khác nhau. Thậm chí có cả một thị trấn ở Ý, nổi tiếng với những mái nhà hình nón_trulli_độc đáo.
::: column(width=285)

    figure: x-img(src="images/ch4_18.png" width="285" height="190")

Cái nón hình nón, Châu Á

::: column(width=166)

    figure: x-img(src="images/ch4_22.png" width="166" height="190")

Người Mỹ bản địa ** Thanh thiếu niên **

::: column(width=189)

    figure: x-img(src="images/ch4_20.png" width="189" height="190")

Alberobello, Italy

:::

Ngoài ra, có rất nhiều ví dụ về sự hình thành đá hình nón trên khắp thế giới. Nhưng có lẽ điều đầu tiên xuất hiện trong đầu chúng ta khi chúng ta nghĩ về những hình nón là những mái nhà của Trái đất; Núi và núi lửa

::: column(width=150)

    figure: x-img(src="images/ch4_29.png" width="150" height="100")

Kasha-Katuwe

Sự hình thành đá, New Mexico

::: column(width=150)

    figure: x-img(src="images/ch4_26.png" width="150" height="100")

Những khối đá hình ống khói

Cappadocia, Thổ Nhĩ Kỳ

::: column(width=144)

    figure: x-img(src="images/ch4_6.png" width="144" height="100")
    // https://depositphotos.com/stock-photos/everest.html?filter=all\&qview=8593244

Đỉnh núi Everest 8850 m

Trái đất

::: column(width=130)

    figure: x-img(src="images/ch4_7.png" width="130" height="100")
    // span.comments(text="https://2016.spaceappschallenge.org/challenges/mars/space-route-66/projects/olympus-mons"

Núi lửa Olympus  Mons 21 000 m

Sao Hỏa

:::

Núi và núi lửa duy trì hình dạng hình nón thú vị của những sự tạo thành đá này nhưng chúng lớn hơn nhiều.

Ngọn núi cao nhất thế giới của chúng ta, Everest, đang phát triển cao hơn 5 cm mỗi năm. **Liệu nó có thể phát triển vô hạn và cao bằng ** _{span.comments(text ="Olympus Mons là một ngọn núi lửa hình khiên rất lớn trên hành tinh Sao Hỏa. Nó gần gấp 3 lần chiều cao của Đỉnh Everest so với mực nước biển. Nó là ngọn núi lửa cao nhất trong hệ mặt trời.")} ** Olympus Mons ** _**của sao Hỏa? Có giới hạn cho chiều cao tối đa có thể có của một ngọn núi trên Trái đất không? **

Có một sự thật thú vị về độ cao của những ngọn núi.

Bằng cách tính gần đúng hình dạng của các ngọn núi với [[hình nón | hình cầu | hình trụ]], chúng ta có thể tìm ra gần đúng chiều cao tối đa của một ngọn núi.
---
    
   // Một applet tương tác, nơi sinh viên có thể kéo độ cao của ngọn núi lên thêm 500 mét - tính toán trọng lượng của ngọn núi - khi đạt đến giới hạn tối đa, ngọn núi sẽ lún xuống.
   
 figure: x-img(src="images/ch4_21.gif" width="480" height="270")

    // 1A, 2A, 3A ... là câu trả lời của các câu hỏi mà chúng tôi sẽ không hiển thị - nhưng nếu applet được chấp thuận, chúng tôi có thể tổ chức lại chúng dưới dạng lời nhắc của trợ giảng. | khi sao Hỏa được chọn, tỷ lệ cạnh bên trái chuyển sang khoảng 0 - 30 000 bằng cách tăng 1000 mét tại một thời điểm | trang trình bày ở đây: https://drive.google.com/drive/folders/1MFMORovFBlcMZFQjUiLFuETQk\_6HAFeB?usp=sharing "

    // 1. ** Tỷ số giữa Trọng lượng và Diện tích đáy ** của một ngọn núi không được vượt quá cường độ nén của đá bên dưới ngọn núi. Nếu không, đá bên dưới núi bắt đầu nén. Ngọn núi sẽ vỡ vụn dưới sức nặng của chính chúng.
    // 2. Khối lượng là lượng vật chất trong một vật. Trọng lượng là lực hút của một khối lượng. Khối lượng có thể được tìm bằng tích của khối lượng riêng và thể tích của vật thể. Khi kết hợp; Tổng ** trọng lượng ** của một ngọn núi trên Trái đất là
    // 3. Thể tích của khối núi hình nón là _{x-equation.small(solution="(1 / 3) π r^2 h" keys="frac sup")}_. Nhưng vì núi thường là sự kết hợp của ba hoặc nhiều ngọn đồi, chúng ta sẽ bỏ qua hệ số `1 / 3` trong tính toán thể tích.
    // 4. Khi chúng ta hủy bỏ diện tích đáy và tổ chức lại phương trình;
    // 5.Nếu bạn chọn Sao Hỏa, chúng ta sẽ sử dụng cùng một phương trình với [[lực hấp dẫn]] của Sao Hỏa. Chúng ta có thể thấy rằng trên sao Hỏa, chiều cao tối đa của một ngọn núi có thể vào khoảng [[27]] km
    
// Sau 4)

Khi chúng ta giải bất đẳng thức ở đây, chúng ta sẽ thấy rằng một ngọn núi trên Trái đất có thể cao tối đa khoảng [[10]] km trước khi sụp đổ dưới trọng lượng của nó!
---

Đây chỉ cao hơn một chút so với đỉnh Everest!

Nếu Everest cao 8800 mét tiếp tục phát triển khoảng 5 cm mỗi năm, gần [[24000]] năm sau, chúng ta có thể hy vọng nó sẽ lún xuống !?
---

Nhưng đừng lo lắng! Chúng ta vẫn còn một ngọn núi khác trên thực tế cao hơn nhiều so với Đỉnh Everest.

Chỉ là nó ở trên sao Hỏa.

Ngọn núi lửa cao nhất trong hệ mặt trời là Olympus Mons trên sao Hỏa với độ cao hơn 21 km và bán kính 312 km.
    
  // Với 5)

Bạn có thể thay đổi các hằng số từ Trái đất sang sao Hỏa để tính chiều cao tối đa của một ngọn núi trên sao Hỏa.

Với một ước tính gần đúng vì lực hấp dẫn của sao Hỏa gần như bằng 1/3 trọng lực trên Trái đất. Chúng ta có thể kết luận rằng một ngọn núi trên sao Hỏa có thể cao gấp [[3]] lần một ngọn núi trên trái đất.
---

_{span.comments(text=""Tôi đã thấy hộp vấn đề màu xanh lam trong các chương mới. Sı Tôi đã nói đến ví dụ này từ phiên bản đầu tiên. Các câu trả lời không được hiển thị trong các chương đó. Nhưng tôi không biết chiến lược cho câu trả lời , đó là lý do tại sao tôi giữ chúng bây giờ. ")} GIẢI QUYẾT VẤN ĐỀ
::: column.fit

_ {span.comments (text =  Sı 

    figure: x-img(src="images/ch4_35.png" width="200" height="275")

::: column.grow

Một silo chứa hạt là một ví dụ khác về việc sử dụng hình trụ và hình nón. Nó thường được xây dựng từ hai hình nón và một hình trụ ở giữa. Silo được sử dụng trong nông nghiệp để lưu trữ ngũ cốc. Tìm sức chứa của silo hạt khổng lồ 12x20m?

Để tìm lượng hạt mà silo chứa, chúng ta cần tính [[thể tích | diện tích | chiều cao]] của từng hình khối riêng biệt và sau đó cộng chúng lại.

Hình nón bên trên và bên dưới có ​​bán kính [[6]] m và chiều cao là [[5]] m;
Thể tích của mỗi hình nón là:  _{x-equation.small(solution="1 / 3" keys="frac" numeric)}_ `xx` _{x-equation.small(solution="36 π" keys="π" numeric)}_ `xx input(5) =` _{x-equation.small(solution="60 π" keys="π" numeric)}_ mét khối


:::

---

Hình trụ có [[cùng| khác]] đáy hình tròn và chiều cao [[10]] m. Vậy thể tích của khối trụ là:  _{x-equation.small(solution="36 π" keys="π" numeric)}_ `xx input(10) =` _{x-equation.small(solution="360 π" keys="π" numeric)}_ mét khối.
---

Tổng thể tích của silo chứa hạt là _{x-equation.small(solution="480 π" keys="π" numeric)}_  mét khối tương đương 1500 mét khối.
---

    figure: x-img(src="images/ch4_9.png" width="600" height="600")

** Có thể làm giảm lực cản và những chiều cao mới sẽ đến với bạn! **
---

## Những hình cầu

> section: spheres
> sectionStatus: dev

::: column.grow


Trái đất là một hành tinh xanh lớn được bao phủ hầu hết bởi các đại dương. Nó là hành tinh lớn thứ năm trong hệ mặt trời của chúng ta và hiện tại, là hành tinh duy nhất được biết là có nước lỏng trên bề mặt của nó.

Với nguồn cung cấp nước quan trọng này, hành tinh quê hương của chúng ta là nơi duy nhất có khoảng ** 8,7 triệu loài ** trong vũ trụ đã biết.

** Có đủ nguồn cung cấp nước trên trái đất cho tất cả các loài bao gồm cả chúng ta không? **

::: column.fit

    figure: x-img(src="images/ch5_13.png" width="200" height="200")
    // image: http://pngimg.com/download/25351

:::

Mặc dù Trái đất của chúng ta không tròn hoàn hảo nhưng nó vẫn duy trì hình dạng chung của một **hình cầu.**

::: column.fit

    figure: x-img(src="images/ch5_45.svg" width="400" height="169")

::: column.grow

Hãy nhớ rằng, tập hợp tất cả các điểm cách đều một điểm nào đó trên mặt phẳng hai chiều được gọi là [[hình tròn | tam giác]].

Nếu chúng ta nghĩ về cùng một định nghĩa trong 3D, thì nó sẽ trở thành một _{span.comments(text="Link to glossary")}**hình cầu.**_

_{span.comments(text="depositphotos.com/vector-images/thermosphere.html?qview=226395398")}Từ "hình cầu" trong tiếng Hy Lạp có nghĩa là "quả địa cầu".

::: column.fit

    figure: x-img(src="images/ch5_1.png" width="150" height="135")

::: column.grow


Có rất nhiều thuật ngữ được nhắc đến trong thế giới của chúng ta liên quan đến từ "hình cầu".

Ví dụ, một lớp khí bao quanh Trái đất được gọi là **hình cầu ** atmo . Bầu khí quyển được chia thành các vùng khác nhau như tầng đối lưu ** hình cầu **, tầng bình lưu ** hình cầu **, tầng trung gian ** hình cầu ** và tầng điện ly **hình cầu  **.
:::

Trái đất có các bán *hình cầu* phía bắc và phía nam. Bán cầu có nghĩa là [[một nửa | một phần ba | một phần tư]] của hình cầu. Trái đất được chia thành hai bán cầu bởi _{span.comments(text="Xích đạo là đường tưởng tượng được vẽ xung quanh trái đất cách đều cả hai cực, chia trái đất thành hai bán cầu bắc và nam")} xích đạo_.
---

::: column.fit

    figure: x-img(src="images/ch5_24.png" width="150" height="161")

::: column.grow


Nếu bạn chia Trái đất thành các bán cầu thì được hình được gọi là ** Vòng tròn lớn. **

Có [[có vô hạn | chỉ một | chỉ hai]] vòng tròn lớn trong một hình cầu. Tất cả các đường kinh tuyến và đường xích đạo đều là những vòng tròn lớn của Trái đất.

Các vòng tròn lớn được sử dụng trong việc lập kế hoạch đường bay cho máy bay cũng như các luồng không khí và điều kiện thời tiết.
:::

---

** Đường truyền khí ngắn nhất có thể giữa hai điểm trên một mặt cong luôn nằm trên đường tròn lớn đi qua cả hai điểm đó. **

::: column.fit

    figure: x-img(src="images/ch5_28.png" width="133" height="100")
    // https://gisgeography.com/great-circle-geodesic-line-shortest-flight-path/

::: column.fit

    figure: x-img(src="images/ch5_23.png" width="123" height="100")
    
   // Chúng tôi có thể có một tương tác có thể hiển thị các vòng tròn lớn khác nhau của Trái đất đi qua các thành phố khác nhau "
:::

::: column.grow


Chúng ta biết rằng hai phần ba bề mặt trái đất được bao phủ bởi nước. Nhưng đó là bao nhiêu?

Từ trước đến nay, để có thể tìm diện tích bề mặt của hình khối, chúng tôi luôn sử dụng [[lưới | phép chiếu]] của hình khối.

Hãy nhớ rằng lưới là lớp phủ hai chiều của hình khối 3D.

::: column.fit

    figure: x-img(src="images/ch5_43.svg" width="200" height="200")

:::

---

Hãy _{span.comments(text="Công cụ vẽ tương tác")}cố gắng vẽ [lưới] (gloss: lưới) của một hình cầu._

Nếu không thể vẽ lưới các hình cầu thì làm sao chúng ta có bản đồ 2D của thế giới?

    // https://www.youtube.com/watch?time_continue=74\&v=b1xXTi1nFCo\&feature=emb_logo
    // A gif / video or slideshow?

Nếu _ {span.comments (text = "Quả địa cầu là mô hình hình cầu của Trái đất. Quả địa cầu phục vụ các mục đích tương tự như bản đồ, nhưng không giống như bản đồ, không làm biến dạng bề mặt.")} Quả địa cầu_ được làm phẳng thành bản đồ, kết quả sẽ bị nhăn và rách. Kích thước, hình dạng và vị trí tương đối của các lục địa sẽ thay đổi. Vì không thể vẽ được chính xác lưới của một hình cầu, chúng tôi phản chiếu bề mặt hình cầu của Trái đất lên một tờ giấy phẳng bằng cách sử dụng ** các phép chiếu khác nhau. **
    
    // Hình ảnh / video / Trình chiếu:

    figure: x-img(src="images/ch5_19.png" width="600" height="306")

    // Phép chiếu Robinson 

    figure: x-img(src="images/ch5_5.png" width="600" height="262")

    // Phép chiếu Goode’s Homolosine 

    figure: x-img(src="images/ch5_2.png" width="600" height="508")

    //Phép chiếu Mercator 

Thật không may, không có cách thực sự chính xác để biểu thị trái đất dưới dạng hình ảnh phẳng. Tất cả các bản đồ 2D đều bị bóp méo theo một cách nào đó!

Không có hình phẳng nào có thể gấp lại thành hình cầu.

Nếu chúng ta không thể vẽ lưới của nó, làm thế nào chúng ta có thể tìm thấy diện tích bề mặt của một hình cầu?

Có nhiều cách khác nhau để đưa ra công thức tính ** diện tích bề mặt ** và ** thể tích ** của một hình cầu. Chúng tôi có thể bắt đầu sử dụng hình khối 3D mà chúng tôi đã biết.
::: column.fit

    figure: x-img(src="images/ch5_3.png" width="200" height="125")

::: column.grow

Hãy nghĩ về một ** bán cầu ** có bán kính ** r ** đặt vừa vặn bên trong lăng trụ hình chữ nhật nhỏ nhất có thể.

Trong trường hợp này, các kích thước của lăng trụ hình chữ nhật theo “r” phải là

    // THẢO LUẬN: Để trống những thứ này? sử dụng trình soạn thảo phương trình? Nhiều lựa chọn?

_{span.comments(text="pills")}[[2r]] x [[2r]] x [[r]]_

:::

---

Vậy thể tích của hình lăng trụ là _{x-equation.small(solution="4 r^3" keys="sup" short-var)}_.
 
---

Thể tích của bán cầu chắc chắn là nhiều ** _ ít _ ** hơn thế.

::: column.fit

    figure: x-img(src="images/ch5_7.png" width="200" height="124")

::: column.grow

Lần này chúng ta hãy đặt bán cầu trong một hình trụ.

Hình trụ nhỏ nhất có thể mà chúng ta có thể đặt khít được bán cầu có cùng [[bán kính | thể tích]] với bán cầu và bán kính của nó bằng [[chiều cao | chiều rộng]] của nó.


Thể tích của hình trụ này là _{x-equation.small(solution="π r^2" keys="sup π" short-var)}_ `*` _{x-equation.small(solution="r" short-var)}_ `=` _{x-equation.small(solution="π r^3" keys="sup π" short-var)}_ và một lần nữa thể tích của bán cầu là [[nhỏ hơn | lớn hơn ]] hơn thế.

:::

---

Lần này, hãy chèn một hình nón có thể tích lớn nhất có thể vào bên trong bán cầu.

::: column.fit

    figure: x-img(src="images/ch5_27.png" width="200" height="137")

::: column.grow

Hình nón có chung [[đáy | thể tích | diện tích bề mặt]] với bán cầu và chiều cao của nó cũng bằng [[bán kính | hai lần bán kính]].

Thể tích của khối nón này là _{x-equation.small(solution="(1/3) π r^3" keys="sup frac π" short-var)}_.Lúc này, thể tích của bán cầu là [[lớn hơn | nhỏ hơn]] so với hình nón.
:::

---

Nếu chúng ta ** nhân đôi ** các đường biên này để đạt đến thể tích của cả một hình cầu;

`"V"_"CONE" < "V"_"SPHERE" < "V"_"CYLINDER"`

_{x-equation.small(solution="(2/3) π r^3" keys="sup frac π" short-var)}_ `< "V"_"SPHERE" <` _{x-equation.small(solution="2 π r^3" keys="sup π" short-var)}_

---

_{span.comments(text="Tôi không định đưa ra chứng minh thực sự vì nó có thể được nâng cao. - ở cấp độ trung cấp cũng đã có một số giải thích. Thay vào đó, tôi sẽ sử dụng câu chuyện và bảng demo nước nếu thấy ổn. ? ")} Trên thực tế, _ ở đây chúng ta đang theo bước chân của nhà Toán học vĩ đại của thời cổ đại,_{span.comments(text="Bio: liên kết đến mục nhập")}**Archimedes.**_  Mặc dù ông ấy rất nổi tiếng với câu chuyện "Eureka", ông có vô số phát minh và đóng góp khác cho toán học, khoa học và kỹ thuật.

Ông đã nghiên cứu các hình tròn, hình trụ và hình cầu cho đến khi ông qua đời và đưa ra các phép tính gần đúng cho số pi và ông đã phát hiện ra thể tích và diện tích của hình cầu bằng cách sử dụng các hình dạng mà ông đã biết như hình trụ và hình nón.

Theo một truyền thuyết, ngay cả những lời cuối cùng của anh ấy cũng là "Đừng làm hỏng những vòng tròn của tôi".
::: column.fit

    figure: x-img(src="images/ch5_15.png" width="200" height="212")

::: column.grow

Hãy nghĩ về một hình trụ có đường kính **_và chiều cao bằng nhau._**

và một hình cầu có ** _ cùng đường kính _ **

Archimedes đã chứng minh rằng có chính xác ** _ cùng một tỷ lệ _ ** giữa thể tích và diện tích bề mặt của chúng.

{.text-center} `"V"_"cylinder" / "V"_"sphere" = "A"_"cylinder" / "A"_"sphere"`

:::

Để tìm tỷ lệ này, hãy sử dụng thí nghiệm về nước mà chúng ta đã sử dụng trước đây khi so sánh hình chóp và hình lăng trụ.

Chúng ta cần có một hình trụ và hình nón có cùng chiều cao với đường kính của các đáy ** (h = 2r)** và một hình cầu có cùng đường kính.

    figure: x-img(src="images/ch5_35.svg" width="600" height="196")

    
   // Nước tương tác hay demo cát: (giống như đồng hồ cát)

   // Chúng tôi có thể tạo một tương tác trong đó học sinh có thể chọn giữa hình trụ, hình nón và hình cầu (với kích thước cụ thể đó) kéo và thả để tạo đồng hồ cát

   // Cảnh đầu tiên:

::: column.fit

    figure: x-img(src="images/ch5_34.png" width="100" height="215")

::: column.grow

Chúng ta đã biết rằng thể tích của hình nón là `input(1) / input(3)` của thể tích hình trụ có cùng kích thước. Nghĩa là, khi chúng ta đổ đầy nước vào hình trụ và đổ vào hình nón `input(2) / input(3)` nước sẽ vẫn còn trong hình trụ.

:::

---

    // Cảnh 2

::: column.fit

    figure: x-img(src="images/ch5_47.png" width="100" height="281")

::: column.grow

Bây giờ chúng ta hãy (thêm một quả cầu vào đồng hồ cát và) đổ lượng nước còn lại vào quả cầu:
:::

    // Cảnh 3

::: column.fit

    figure: x-img(src="images/ch5_44.png" width="100" height="250")

::: column.grow

Hình cầu đã đầy và hình trụ hiện đã hoàn toàn trống rỗng!

Bạn có thể xoay đồng hồ cát để lặp lại thử nghiệm.

Chúng ta vừa chứng minh rằng thể tích của hình cầu là `input(2) / input(3)`của hình trụ có cùng kích thước.

`"V"_"HÌNH CÂU" = (2/3) "V"_"HÌNH TRỤ"`

`"V"_"HÌNH CẦU" = 2 / 3` _{x-equation.small(solution="π r^2 h" keys="π sup" short-var)}_ since `"h" = 2"r"`, we can replace `"h"`

`"V"_"HÌNH CẦU" = (2/3) pi r^2 *` _{x-equation.small(solution="2 r" short-var)}_

`"V"_"HÌNH CẦU" = (2/3) * 2 pi *` _{x-equation.small(solution="r^3" keys="sup" short-var)}_

`"V"_"HÌNH CẦU" =` _{x-equation.small(solution="π r^3" keys="π sup" short-var)}_

:::

---


Archimedes cũng tìm ra ** tỷ số giống nhau ** tồn tại giữa ** diện tích bề mặt ** của hình trụ và hình cầu.

Diện tích bề mặt của hình trụ =  _{x-equation.small(solution="(2 π r^2) + (2 π r h)" keys="π sup +" short-var)}_

---

Diện tích bề mặt của hình trụ với `"h" = "2"` is: `2 pi r^2 + 2 pi r *` _{x-equation.small(solution="2 r" short-var)}_ `=` [[`6 pi "r"^2` | `4 pi "r"^2` | `8 pi "r"^2`]]

---

Nếu chúng ta sử dụng cùng một tỷ lệ `input(2) / input(3)` để tìm diện tích bề mặt của hình cầu;
---

`"S"_"HÌNH CẦU" =` _{x-equation.small(solution="4 π r^2" keys="π sup" short-var)}_

---

::: column.fit

    figure: x-img(src="images/ch5_4.png" width="181" height="217")

::: column.grow

Tỷ lệ `2/3` này khiến Archimedes thích thú đến mức ông muốn được ghi nhớ với khám phá này bằng cách yêu cầu một quả cầu nằm trong một hình trụ trên bia mộ của mình.
:::

Cảm ơn Archimedes, bây giờ chúng ta có thể quay lại câu hỏi ban đầu của mình. Chúng ta có thể tính toán diện tích bề mặt và thể tích của thế giới để tìm ra lượng nước thực sự trong đó.

::: column.grow


Bán kính của Trái đất ở xích đạo là 6378 km. Mặc dù nó không phải là một hình cầu hoàn hảo, nhưng chúng ta vẫn có thể sử dụng công thức thể tích của hình cầu để tính gần đúng.

`V_Trái đất =` _{x-equation.small(solution="π r^3" keys="π sup" short-var)}_ `= * pi * input(6378)^3 = 108.3 xx 10^10 "km"^3` **(khoảng 1 nghìn tỷ km khối) **


** Diện tích bề mặt ** của Trái đất cũng có thể được tìm thấy bằng cách sử dụng công thức Archimedes _{x-equation.small(solution="4 π r^2" keys="π sup" short-var)}_.

`"S"_"Trái đất" = 4 pi r^2 = 4 * pi * input(6378)^2 =` ** 510 triệu km vuông.**
::: column.fit

    figure: x-img(src="images/ch5_13.png" width="200" height="200")

:::

---

Khoảng 70% bề mặt Trái đất được bao phủ bởi nước. Nghĩa là **diện tích bề mặt của nước xấp xỉ `510 "triệu" xx %input(70) = input(357) "triệu km vuông"`.**
::: column.fit

    figure: x-img(src="images/ch5_41.svg" width="200" height="106")

::: column.grow


Độ sâu trung bình của các đại dương là khoảng 4 km, vì vậy chúng ta có thể tính thể tích của nước trên Trái đất dưới dạng là `input(357) "triệu" xx input(4)`: gần 1.4 tỷ `"km"^3` (14 x 1020 lít).

Điều này có nghĩa là trong khi nước bao phủ 70% bề mặt Trái đất, nó có thể tích nhỏ hơn nhiều so với 1% toàn bộ thể tích của Trái đất.

:::

    //TIẾP TỤC

---


Không chỉ thế giới của chúng ta mà các hành tinh và quỹ đạo khác cũng có hình cầu.

Hãy so sánh kích thước của mặt trăng và các hành tinh khác với bán kính, diện tích bề mặt và thể tích của Trái đất.

** Hãy nhớ rằng, thể tích của một hình cầu tỷ lệ thuận với [[lập phương | bình phương| ba phần tư]] của bán kính trong khi diện tích bề mặt tỷ lệ thuận với [[bình phương| lập phương | bốn lần]] bán kính. **
---

|                                                            |Radius| Volume | Surface Area |
| ---------------------------------------------------------- | --- | ---- | ---- |
| _{img(src="images/ch5_14.png" width=30 height=30)}_ Earth  | __r__ | __V__ | __A__ |
| _{img(src="images/ch5_6.png" width=30 height=30)}_ Moon    | `"r"/4` | `"V"/input(64)` | `"A"/16` |
| _{img(src="images/ch5_17.png" width=30 height=30)}_ Mars   | `"r"/2` | `"V"/8` | `"A"/input(4)` |
| _{img(src="images/ch5_20.png" width=30 height=30)}_ Saturn | `input(10) * "r"` | `1000"V"` | `input(100) * "A"` |

---

Hình cầu có những đặc tính độc đáo khiến chúng trở thành hình dạng yêu thích của nhiều môn thể thao, người máy, trái cây, thậm chí cả bong bóng xà phòng.

    div.row.padded
      div(style="width: 264px")
        div.row.padded
          div.fit
            figure: x-img(src="images/ch5_25.png" width="150" height="100")
            // https://depositphotos.com/stock-photos/soap-bubbles.html?filter=all\&qview=2076648
          div.fit
            figure: x-img(src="images/ch5_26.png" width="66" height="100")
            // https://depositphotos.com/stock-photos/bb8.html?filter=all\&qview=231776588
        p
          // I am not sure the include these details under each image or not?
          span.sentence For instance, the spherical shape of a soap bubble minimizes surface tension whereas the round figure of BB-8 gives it the ability to move in any direction
      div(style="width: 173px")
        figure: x-img(src="images/ch5_22.png" width="173" height="100")
        // https://depositphotos.com/stock-photos/balls-of-di%CC%87fferent-games.html?filter=all\&qview=37293593
        p
          span.sentence The round shape of the soccer ball makes it bounce evenly and gives uniform responses from each direction.
      div(style="width: 137px")
        figure: x-img(src="images/ch5_11.png" width="137" height="100")
        // https://depositphotos.com/208835438/stock-photo-top-view-circle-fruits-blue.html
        p
          span.sentence Round shapes of fruits can be a result of the equally-distributed outward expansion as well as the surface area to volume ratio of the spheres.

Hãy so sánh diện tích bề mặt và thể tích của một số hình khối 3D để xem cái nào có thể tích lớn nhất đối với một diện tích bề mặt nhất định;

    // Chúng ta có thể sử dụng applet 3D - học sinh có thể kéo và thả hình khối 3d từ menu bên phải. Sau đó, với các thanh trượt, họ có thể cố định diện tích bề mặt để xem cái nào có thể tích lớn nhất.

    // applet sẽ cho phép học sinh quan sát khi nào xảy ra với các diện tích bề mặt khi họ cân bằng thể tích hoặc ngược lại bằng cách sử dụng các thanh trượt

    figure: x-img(src="images/ch5_42.svg" width="600" height="337")


Bây giờ chúng ta cũng đã thấy rằng [[hình cầu | hình lập phương]] ** _ bao quanh thể tích tối đa cho diện tích bề mặt đã cho ._ ** Ví dụ: trái cây sử dụng lượng nguồn tối thiểu để lưu trữ tối đa chất dinh dưỡng.
---


Nếu hình cầu có nhiều thuộc tính như vậy thì tại sao không sử dụng chúng trong kiến ​​trúc?

Trong suốt đơn vị này, chúng tôi đã chứng kiến ​​cách kiến ​​trúc lấy cảm hứng từ vẻ đẹp của hình học dạng khối. Chỉ cần nghĩ về sự đối xứng và vẻ đẹp của các không gian được tạo ra bởi các khối cầu.

Vấn đề duy nhất đối với việc tạo ra các bề mặt hình cầu là sản xuất các tấm kính cong hoặc các vật liệu khác. Vào những năm 1940, nhà toán học _ {span.comments (text = "Liên kết đến tiểu sử")} Buckminster Fuller_ đã cải tiến khái niệm về tính gần đúng các bề mặt cong bằng cách sử dụng các tấm hình tam giác phẳng được gọi là ** vòm trắc địa ** và ** bề mặt **.
   
 figure: x-img(src="images/ch5_18.png" width="600" height="389")

Walt Disney Epcot “Spaceship Earth”

 (Orlando, US)

    figure: x-img(src="images/ch5_10.png" width="600" height="450")


Mất hơn hai năm để xây dựng điểm thu hút hình cầu nổi tiếng thế giới của Disney. Tên của nó là "Spaceship Earth" cũng được phổ biến bởi Buckminster Fuller.

Spaceship Earth là một hình cầu hoàn chỉnh, được hỗ trợ bởi ba cặp chân với đường kính 50 mét. Thể tích của hình cầu là `input (4) / input (3) *` _ {x-method.small (solution = "π" phím = "π")} _ `* input (253)`: gần 62.000 mét khối.
---

11.520 tam giác cân được lên kế hoạch sử dụng để tạo ra một hình cầu trắc địa hoàn hảo với kích thước này.

Giống như Epcot’s Spaceship Earth, có rất nhiều ví dụ hiện đại khác về các tòa nhà hình cầu trên thế giới.
{.todo} Slideshow:

    figure: x-img(src="images/ch5_21.png" width="600" height="399")

Thư viện Tianjin Binhai  (Tianjin, China)

Bên cạnh vẻ đẹp tròn trịa hoàn hảo, các đặc tính của quả cầu khiến nó trở thành sự lựa chọn hoàn hảo cho các công trình kiến ​​trúc hiện đại.
    figure: x-img(src="images/ch5_16.png" width="600" height="338")

Amazon Spheres (Seattle, Washington)

Hãy nhớ rằng, hình cầu bao quanh thể tích nhiều nhất cho một diện tích bề mặt nhất định của bất kỳ khối hình học nào.

Vì vậy, nó đòi hỏi ít vật liệu xây dựng hơn so với các tòa nhà thông thường dựa trên các hình dạng như lăng trụ hình chữ nhật.

    figure: x-img(src="images/ch5_9.png" width="600" height="400")

La Géode (Paris, Pháp)

Điều đó cũng có nghĩa là ít nhiệt bị mất hoặc thu được qua bên ngoài và cấu trúc nhận được ít lực hơn từ những cơn gió mạnh có khả năng làm hỏng nó.

    figure: x-img(src="images/ch5_8.png" width="600" height="338")

Sinh quyển (Montreal, Canada)

Ngoài ra, vì lý do tương tự của bong bóng xà phòng là hình cầu, các hình cầu phân phối tải trọng của tòa nhà trong toàn bộ cấu trúc, điều này mang lại cho tòa nhà sức mạnh lớn.
    figure: x-img(src="images/ch5_12.png" width="600" height="599")
