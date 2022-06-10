# PSR-4 - Autoloading
- Tiêu chuẩn kỹ thuật viết các lớp tự động nạp vào khi cần sử dụng đến, kỹ thuật tự Autoload trong PHP

1. diễn giải
 - Trước đây trong PHP việc nạp các file thư viện, mã dùng lại vào một file PHP khác thường dùng các lệnh include và require. Điều này thực sự mất thời gian và rắc rối. Tiếp theo từ PHP5 đã có các hàm trợ giúp tự động hóa việc gọi thư viện bằng các hàm như: spl_autoload_register, spl_autoload_functions, spl_autoload_extensions,...
 - Từ các hàm này cùng với khái niệm namespace trong PHP, các lập trình viên xây dựng cho mình một bộ code tự động nạp. Tuy nhiên để dễ dàng chia sẻ dùng lại code giữa các framework, giữa các dự án ..., cộng đồng PHP thống nhất một cách thức tự động nạp thư viện theo một chuẩn bố trí thư viện. Việc thống nhất đó hình thành một tiêu chuẩn nên tuân theo đó là PSR - 4 Autoload.
2. Cách dùng
 - Ứng dụng của tiêu chuẩn này như sau: Phải có một có chế và cách bố trí code trong các thư mục sao cho mọi lớp (class) đều có thể được tham chiếu đến

```
\<NamespaceName>(\<SubNamespaceNames>)\<ClassName>
```

Có nghĩa là mỗi lớp bạn phải xây dựng sao cho có thể được tham chiếu đến bởi dòng code ba thành phần: Namespace, Các SubNamespaceNames con, và tên lớp ClassName.

- NameSpace : Tiền đố đầu tiên bắt buộc phải có - được hiểu là tên vendor.  Tên này do bạn tự đặt, sao cho không xung đột tên các thư viện khác.
- SubNameSpaces: Các namespace con (theo sau NameSpace đầu tiên - vendor).  Có một hoặc nhiều tùy bạn. Nhưng bắt đầu từ SubNameSpace thì nó tương ứng với cấu trúc thư mục lưu trữ code.  Ví dụ bạn lưu trữ code thư viện tại thư mục gốc là src, và gọi đến một lớp của bạn tên là cls1 với cú pháp như sau \myvendor\namespace1\namespace2\cls1 điều này có nghĩa là trong thư mục src có thư mục tên là namespace1, trong namespace1 có thư mục namespace2.
- ClassName: Bắt buộc phải có và phải có tên file PHP trùng tên ClassName ở thư mục tương ứng với namespace cuối cùng (ClassName.php), trong file đó sẽ định nghĩa nội dung của code của lớp.
