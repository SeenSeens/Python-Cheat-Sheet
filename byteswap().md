# byteswap()

## 1. byteswap() là gì?

- `byteswap()` là một phương thức dùng cho đối tượng `array` trong Python (`from array import array`).

- Nó sẽ **đảo ngược thứ tự các byte** trong **mỗi phần tử** của array.

Nói đơn giản:

- Nếu dữ liệu của bạn lưu trữ theo kiểu byte order khác (ví dụ: đọc từ một file của máy tính khác với endian khác), thì `byteswap()` giúp bạn chuyển đổi đúng lại.

## 2. Cú pháp:

`array.byteswap()`

- Không có tham số.

- Thao tác trực tiếp trên array (không trả về array mới).

## 3. Ví dụ dễ hiểu:

`from array import array`

- Tạo array kiểu 'h' (signed short, 2 bytes)

`arr = array('h', [1, 256, 512])`

`print("Trước khi byteswap:", arr)`

`arr.byteswap()`

`print("Sau khi byteswap:", arr)`

- **Kết quả** (giá trị sẽ thay đổi tùy thuộc hệ thống):

`Trước khi byteswap: array('h', [1, 256, 512])
Sau khi byteswap: array('h', [256, 1, 2])`

➔ Mỗi phần tử đã bị đổi byte trong bộ nhớ!

## 4. Khi nào cần dùng byteswap()?

- Khi **đọc file nhị phân** từ máy khác hệ điều hành (ví dụ từ máy Big-endian sang Little-endian hoặc ngược lại).

- Khi **giao tiếp với thiết bị** cần đúng thứ tự byte.

- Khi cần **xử lý dữ liệu nhị phân thấp cấp**.

## 5. Các lưu ý quan trọng:

- `byteswap()` chỉ hoạt động với array có phần tử **cỡ 1, 2, 4, hoặc 8 bytes**.

- Nếu bạn dùng kiểu dữ liệu khác (không đúng size), Python sẽ báo lỗi `RuntimeError`.

- **byteswap()** sẽ **thay đổi dữ liệu ngay tại chỗ** (in-place), **không tạo ra bản sao**.

## 6. Ví dụ thêm với kiểu int 4 bytes:

`from array import array`

`arr = array('i', [1, 2, 3])`

`print([hex(x) for x in arr])` **# In dạng hex cho dễ thấy bytes**

`arr.byteswap()`

`print([hex(x) for x in arr])`

➔ Bạn sẽ thấy cách `hex` của từng phần tử thay đổi hoàn toàn sau `byteswap()`!

## 7. Tóm lại:

|             | Nội dung                                               |
| ----------- | ------------------------------------------------------ |
| Mục đích    | Đảo byte trong từng phần tử của array                  |
| Hoạt động   | Thay đổi trực tiếp trên array                          |
| Áp dụng cho | Các phần tử có kích cỡ 1, 2, 4, hoặc 8 bytes           |
| Lỗi         | Gây lỗi RuntimeError nếu sai kích cỡ                   |
| Ứng dụng    | Đọc file từ hệ thống khác, giao tiếp thiết bị nhị phân |


