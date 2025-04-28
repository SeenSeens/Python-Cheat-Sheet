# buffer_info()

## 1. buffer_info() là gì?

Phương thức `buffer_info()` của một đối tượng **array** trong Python **trả về một tuple** gồm:

- `address`: địa chỉ bộ nhớ hiện tại nơi mảng được lưu.

- `length`: số lượng phần tử trong mảng.

**Cú pháp**:

`address, length = array.buffer_info()`

## 2. Ứng dụng của buffer_info()

- Chủ yếu dùng trong lập trình hệ thống (khi bạn làm việc với C/C++, hoặc các thao tác thấp cấp như IOCTL).

- Bạn có thể cần địa chỉ bộ nhớ để chuyển dữ liệu tới một hàm trong C yêu cầu void* kiểu con trỏ.

- Hoặc để xử lý nhanh dữ liệu nhị phân mà không cần copy bộ nhớ.

**Chú ý**:

Kết quả `buffer_info()` chỉ hợp lệ miễn là:

- Mảng đó **vẫn còn tồn tại**.

- Không có **thay đổi độ dài** (như `append()`, `pop()`, `remove()`, v.v.) sau khi gọi `buffer_info()`.

## 3. Công thức tính kích thước vùng nhớ:

Bạn có thể tính ra số **byte** mảng chiếm bộ nhớ bằng công thức:

`size_in_bytes = array.buffer_info()[1] * array.itemsize`

- `itemsize` là số byte mà mỗi phần tử của mảng chiếm (ví dụ: 4 bytes với `int`, 8 bytes với `double`...).

## 4. Lưu ý về Buffer Protocol

- Trong các phiên bản Python mới hơn, người ta **khuyến cáo dùng Buffer Protocol** thay vì `buffer_info()` để quản lý vùng nhớ tốt hơn, linh hoạt hơn.

- `buffer_info()` **giữ lại chỉ vì lý do tương thích ngược** với các chương trình Python cũ.


