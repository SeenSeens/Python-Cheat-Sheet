# count(*x*)

## 1. count(x) là gì?

- `count(x)` là **một phương thức** của `array` (và cả `list` trong Python) dùng để:

➔ **Đếm số lần** xuất hiện của giá trị `x` trong array.

## 2. Cú pháp:

`array.count(x)`

- `x` là giá trị bạn muốn đếm trong array.

## 3. Ví dụ đơn giản:

`from array import array`

`arr = array('i', [1, 2, 3, 2, 2, 4])` # Tạo một array kiểu 'i' (int 4 bytes)

`print(arr.count(2))` # Đếm số lần số 2 xuất hiện

**Kết quả**:

`3`

➔ Vì số `2` xuất hiện **3 lần** trong array.

## 4. Một vài ví dụ khác:

`arr = array('i', [5, 5, 5, 5])`

`print(arr.count(5))`  # 4
`print(arr.count(1))`  # 0 (vì không có số 1)

## 5. Lưu ý:

- `count(x)` **so sánh đúng kiểu**.
  Ví dụ, trong array kiểu `'i'` (số nguyên), nếu bạn tìm `3.0` (float) sẽ tự động được **ép thành int** trước khi đếm.

- Nếu `x` không có trong array **➔** Trả về 0.

## 6. Tóm tắt:

|                | Nội dung                                                   |
| -------------- | ---------------------------------------------------------- |
| Công dụng      | Đếm số lần giá trị `x` xuất hiện trong array               |
| Giá trị trả về | Một số nguyên (0 nếu không tìm thấy)                       |
| Ghi nhớ        | So sánh theo giá trị, và cần đúng kiểu (hoặc ép kiểu ngầm) |

## 7. So sánh nhanh `list.count(x)` và `array.count(x)`:

|                 | list                    | array                                   |
| --------------- | ----------------------- | --------------------------------------- |
| Cấu trúc        | Bất kỳ loại dữ liệu nào | Cùng một kiểu dữ liệu (theo `typecode`) |
| Dùng `count(x)` | Có                      | Có                                      |


