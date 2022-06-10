# Chuẩn viết code cơ bản - PSR-1
- PSR-1 trình bày những tiêu chuẩn nguyên tắc chung, cơ bản nên theo khi viết code PHP.

1. Nguyên tắc chung
- Các file phải sử dụng `<?php`(thẻ mở bắt đầu code php) hoặc `<?=`(echo)
- File code PHP phải sử dụng encode: `UTF-8 without BOOM`
- Các file nên chứa các khai báo (lớp, hàm, hằng ...) hoặc các tác dụng phụ (thiết lập, xuất dữ liệu chung ...) nhưng KHÔNG NÊN chứa cả hai
- Các Namespace và lớp (class) phải theo chuẩn "autoloading" [PSR-4](./psr-4.md)
- Tên class và namespace viết theo kiểu `PascalCase`
- Hằng số viết theo kiểu `MACRO_CASE`
- Tên method và function viết theo kiểu `camelCase`

2. Chi tiết
I. Các thẻ php
   Mã PHP PHẢI sử dụng kiểu mở thẻ đầy đủ để nhúng mã <?php ?>, hoặc short-echo <?= ?> xuất dữ liệu trong HTML. Không được sử dụng các loại thẻ khác như thẻ ngắn
II. Hiệu ứng phụ
- Một file CÓ THỂ khai báo ra các thành phần mới (các lớp, hàm, hằng ...) và không dẫn đến các hiệu ứng phụ hoặc file đó CÓ THỂ thi hành các tác vụ logic dẫn đến hiệu ứng phụ, nhưng trong một file không nên chứa cả hai điều trên.
- Hiệu ứng phụ có nghĩa là thực hiện một logic (tác vụ) mà nó chẳng liên quan đến các lớp, hàm, hằng ... hay chỉ thực hiện việc gộp file
- Hiệu ứng phụ gồm xuất dữ liệu chung, sử dụng tường minh lệnh require và include, kết nối đến dịch vụ ngoài, sửa đổi thiết lập ini, thiết lập cách hiện thị lỗi và ngoại lệ, thay đổi các biến toàn cục, biến tĩnh, đọc và ghi file ..

Ví dụ sau trong một file vừa tạo ra hàm mới vừa chứa các hiệu ứng phụ, nên tránh điều này
```php
<?php
// Thay đổi php.ini - hiệu ứng phụ
ini_set('error_reporting', E_ALL);

// Nạp file.php - hiệu ứng phụ
include "file.php";

// Xuất dữ liệu chung - hiệu ứng phụ
echo "<html>\n";

// Khai báo hàm
function foo()
{

}
```
Còn file sau chứa khai báo mà không có hiệu ứng phụ nào
```php
<?php
// Khai báo hàm
function foo()
{
    // function body
}

// Lệnh kiểm tra điều kiện để khai báo không coi là hiệu ứng phụ của file
if (! function_exists('bar')) {
    function bar()
    {
        // function body
    }
}
```

III. Các namespace và tên class
- CácNamespace và Lớp PHẢI theo chuẩn "autoloading" PSR-4
- Có nghĩa là mỗi lớp được khai báo trên mỗi file PHP riêng và namespace tối thiểu có một cấp, cấp đầu là tên vendor.
- Tên lớp lại PHẢI đúng dạng PascalCase.

Ví dụ đúng chuẩn của 1 file:
```php
<?php
namespace Vendor\Model;

class Foo
{
}
```
IV. Hằng, Thuộc tính và Phương thức của lớp
- Hằng theo chuẩn ở trên, tất cả PHẢI viết hoa, phân cách từ bởi _

Ví dụ hằng đúng chuẩn:
```php
<?php
namespace Vendor\Model;

class Foo
{
    const VERSION = '1.0';
    const DATE_APPROVED = '2022-06-11';
}
```

- Thuộc tính tùy cách sử dụng viết dạng $PascalCase dạng $camelCase hay $snake_case, chỉ yêu cầu thống nhất về cách sử dụng trong phạm vi package, lớp, phương thức
- Phương thức thì đặt tên theo dạng camelCase().
