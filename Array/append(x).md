# append(x)

## 1. append(x) là gì?

- `append(x)` là **một phương thức** dùng để `thêm một phần tử` **x** **vào cuối** một **array** (hoặc list trong Python nói chung).

Nếu bạn đang dùng **module** `array` (từ `from array import array`) thì:

- `append(x)` **chỉ thêm được phần tử** có đúng kiểu dữ liệu phù hợp với `typecode` của array đó.

Nếu bạn đang dùng **list thông thường** thì:

- `append(x)` thêm bất kỳ đối tượng nào vào cuối list.

## 2. Cú pháp:

`array.append(x)`

- `x` là **giá trị** bạn muốn thêm vào.

- Với **array**, `x` phải đúng kiểu dữ liệu quy định bởi `typecode` của array.

## 3. Ví dụ thực tế:

### 3.1 Với list bình thường:

- Danh sách (list) trong Python

`lst = [1, 2, 3]`
`lst.append(4)`
`print(lst)`

- Kết quả:

`[1, 2, 3, 4]`

### 3.2 Với array từ module array:

`from array import array`

- Tạo một array kiểu số nguyên 4 byte ('i')

`arr = array('i', [10, 20, 30])`

`arr.append(40)`
`print(arr)`

- Kết quả:

`array('i', [10, 20, 30, 40])`

➔ Phần tử `40` được thêm vào cuối mảng.

## 4. Lưu ý:

- Nếu bạn cố `append` một giá trị **sai kiểu** vào một array, `Python` sẽ báo lỗi `TypeError`.

- Ví dụ lỗi:

`from array import array`

`arr = array('i', [1, 2, 3])`

`arr.append(3.5)`  **# Sai kiểu! array kiểu 'i' chỉ nhận int**

- Chạy sẽ lỗi:

`TypeError: 'float' object cannot be interpreted as an integer`

## 5. Tóm lại:

| Loại              | Ý nghĩa                                             |
| ----------------- | --------------------------------------------------- |
| `list.append(x)`  | Thêm x vào cuối danh sách, không cần quan tâm kiểu. |
| `array.append(x)` | Thêm x vào cuối mảng, phải đúng kiểu `typecode`.    |
