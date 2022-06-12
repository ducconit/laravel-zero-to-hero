# PSR-2 - Hướng dẫn trình bày code PHP
- Trình bày theo quy tắc ở đây áp dụng cho tất cả các dự án PHP, giúp cho code sáng sủa, dễ hiểu, dễ bảo trì hơn
- Hướng dẫn này kế thừa và mở rộng thêm cho [Psr-1](./psr-1.md) : Tiêu chuẩn cơ bản khi viết code.


**1. Tổng quan về trình bày code PHP**
- Code PHẢI tuân thủ [PSR-1](./psr-1.md)
- Code PHẢI sử dụng 4 ký tự space để lùi khối (không dùng tab)
- KHÔNG PHẢI cố định chiều dài của dòng code; dòng code PHẢI dưới 120 ký tự; NÊN dưới hoặc bằng 80 ký tự.
- PHẢI có một dòng trắng sau khai báo namespace, và PHẢI có một dòng trắng sau mỗi khối code.
- Ký tự mở `{` khai báo lớp PHẢI ở dòng tiếp theo, và đóng `}` PHẢI ở dòng tiếp theo sau thân class.
- Ký tự `{` cho hàm PHẢI ở dòng tiếp theo, và ký tự `}` kết thúc hàm PHẢI ở dòng tiếp theo của thân hàm.
- Các visibility (public, private, protected)  PHẢI được khai báo cho tất cả các hàm và các thuộc tính của lớp; abstract và final PHẢI được khai báo trước visibility. static PHẢI khai báo sau visibility
- Các từ khóa điều khiển khối (if, elseif, else) PHẢI có một khoảng trống sau chúng; gọi hàm, phương thức thì KHÔNG ĐƯỢC làm như vậy.
- Mở khối `{` cho cấu trúc điều khiển PHẢI trên cùng một dòng; và đóng khối này `}` với ở dòng tiếp theo của thân khối.
- Hằng số true, false, null PHẢI viết với chữ thường.
- Từ khóa extends và implements PHẢI cùng dòng với class.
- implements nhiều lớp, thì mỗi lớp trên một dòng
- keyword var KHÔNG ĐƯỢC dùng sử dụng khai báo property.
- Tên property KHÔNG NÊN có tiền tố `_` nhằm thể hiện thuộc protect hay private.
- Tham số cho hàm, phương thức: KHÔNG được thêm space vào trước dấu , và PHẢI có một space sau ,. Các tham số CÓ THỂ trên nhiều dòng, nếu làm như vậy thì PHẢI mỗi dòng 1 tham số.
- abstract, final PHẢI đứng trước visibility, còn static PHẢI đi sau.

**2. Gọi phương thức và hàm**

- Khi gọi một hàm hay phương thức của lớp, KHÔNG ĐƯỢC có khoảng trắng giữa phương thức, hàm và toán tử và dấu ( đồng thời không được có khoảng trắng sau (. không có khoảng trắng trước ), như phần trên không được có khoảng trắng trước , nhưng PHẢI có khoảng trắng sau ,**
