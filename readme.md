# LARAVEL ZERO TO HERO

### Mục lục
1. [Typography](#typo)
2. [PSR standard](#psr)


___
#### 1. Typography <a name="typo"/>
- **PascalCase/ CapitalCamelCase**: 
  + Viết hoa tất cả các chữ cái đầu
- **camelCase**: 
  + Từ đầu tiên viết thường, các từ tiếp theo viết hoa chữ cái đầu tiên
- **underscore/ snake_case/ c_case**: 
  + Tất cả chữ viết thường, phân tách các từ với nhau bằng dấu gạch dưới `_`
- **kebab-case/ caterpillar-case/ dash-case/ hyphen-case/ lisp-case/ spinal-case/ css-case**:
  + Tất cả chữ viết thường, phân tách các từ với nhau bằng dấu gạch nối `-`
- **flatcase**: 
  + Tất cả chữ viết thường, các từ viết liền
- **MACRO_CASE/ UPPER_CASE**: 
  + Tất cả chữ viết hoa, các từ phân tách bằng dấu gạch dưới `_`
- **COBOL-CASE/ TRAIN-CASE**: 
  + Tất cả chữ viết hoa, các từ phân tách bằng dấu gạch ngang `-`

___
#### 2. PSR standard <a name="psr"/>
 PSR là viết tắt của `PHP Standard Recommendation`. Hiện có 12 chuẩn code php từ PSR-1 đến PSR-12 và được chia thành 4 nhóm: autoloading, interface, http, coding styles.

- Autoloading: Quy ước về cách code để có thể sử dụng namespace dễ dàng
  + [PSR-4](./psr/psr-4.md)
- Inferface: Quy ước về cách code thư viện ví dụ như logging, cache,...
  + PSR-3, PSR-6, PSR-11, PSR-13, PSR-14, PSR-16
- HTTP: Quy ước cách code làm sao để tương tác với các request, response HTTP 1 cách tốt nhất
  + PSR-7, PSR-5, PSR-15, PSR-17, PSR-18
- Coding styles: Quy ước về phong cách code
  + [PSR-1](./psr/psr-1.md), [PSR-2](./psr/psr-2.md), [PSR-12](./psr/psr-12.md)

