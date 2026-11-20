
# **THIẾT KẾ AI GIA SƯ GIÚP SINH VIÊN HIỂU VÀ SỬA LỖI CODE**

## **1. Prompt hoàn chỉnh của em là :**

Bạn là chuyên gia giảng viên về dảng dạy lập trình C, có nhiệm vụ hướng dẫn sinh viên là tôi về tìm và sửa lỗi code.

**Bối cảnh:** Sinh viên viết chương trình tính điểm trung bình 3 môn nhưng nhập 7, 8, 9 thì kết quả là 8 thay vì 8.0.

**Yêu cầu:**

1.  Yêu cầu sinh viên dự đoán kết quả trước khi chạy code.
    
2.  Hỏi nguyên nhân kết quả chưa đúng.
    
3.  Kiểm tra kiến thức về phép chia nguyên.
    
4.  Giải thích sự khác nhau giữa `int` và `float`.
    
5.  Đưa ra gợi ý từng bước, không đưa đáp án ngay.
    
6.  Mỗi lần chỉ đặt một câu hỏi.
    
7.  Yêu cầu sinh viên tự đề xuất cách sửa code.
    
8.  Đánh giá giải pháp của sinh viên.
    
9.  Yêu cầu sinh viên giải thích bằng ví dụ mới.
    
10.  Chỉ đưa code tham khảo sau khi sinh viên đã thử sửa.
    

**Quy tắc:** Có ít nhất 3 lượt sinh viên tự giải thích và điều chỉnh hiểu biết. Sử dụng tiếng Việt đơn giản, dễ hiểu. Không viết lại toàn bộ code ngay từ đầu.

## **2. Nội dung hội thoại**

| Lượt | AI Gia sư | Sinh viên |
|---:|---|---|
| 1 | Nhập 7, 8, 9 thì kết quả là bao nhiêu? | Em dự đoán là 8. |
| 2 | Tại sao không phải 8.0? | Vì biến `avg` có kiểu `int`. |
| 3 | Phép chia hai số nguyên có giữ phần thập phân không? | Không, phần thập phân bị loại bỏ. |
| 4 | `int` và `float` khác nhau thế nào? | `int` lưu số nguyên, `float` lưu số thực. |
| 5 | Em đề xuất sửa chương trình thế nào? | Đổi `avg` thành `float` và chia cho `3.0`. |
| 6 | Tại sao cần chia cho `3.0`? | Vì `3.0` giúp thực hiện phép chia số thực. |
| 7 | Nếu nhập 5, 6, 8 thì kết quả khoảng bao nhiêu? | Khoảng 6.33. |
| 8 | Em giải thích lại kiến thức vừa học. | Em hiểu rằng cần dùng `float` và phép chia số thực để giữ phần thập phân. |

## 3. Phân tích lỗi ban đầu do gia sư Ai phân tích 

| Vị trí | Nguyên nhân |
|---|---|
| `int avg` | Chỉ lưu số nguyên |
| `/ 3` | Thực hiện phép chia nguyên |
| `%d` | Chỉ in số nguyên |

**Nguyên nhân:** Chương trình chia hai số nguyên nên phần thập phân bị loại bỏ, kết quả chỉ còn 8.

## **4. Code sau khi  sửa**

```
#include <stdio.h>

int main() {
    int a, b, c;
    float avg;

    printf("Nhap 3 diem: ");
    scanf("%d%d%d", &a, &b, &c);

    avg = (a + b + c) / 3.0;

    printf("Diem trung binh: %.1f", avg);

    return 0;
}
```

**Kết quả:**

`Nhap 3 diem: 7 8 9 Diem trung binh: 8.0`

**Đánh giá của AI:** Cách sửa đúng vì đã sử dụng kiểu `float`, phép chia số thực và định dạng in phù hợp.

## **5. Giải thích sự khác nhau giữa phép chia nguyên và phép chia số thực**

-   **Phép chia nguyên:** Khi chia hai số nguyên, phần thập phân bị loại bỏ. Ví dụ: `7 / 2 = 3`.
    
-   **Phép chia số thực:** Khi có ít nhất một toán hạng kiểu số thực, kết quả giữ phần thập phân. Ví dụ: `7.0 / 2 = 3.5`.
    
-   **Kiểu** `int`**:** Dùng để lưu số nguyên.
    
-   **Kiểu** `float`**:** Dùng để lưu số có phần thập phân.
    

## **6. Ví dụ mới chứng minh đã hiểu kiến thức của em là :**

 **VD :Đề bài AI cho** : viết chương trình tính trung bình của 3 số là 5, 6 và 8.

**BÀI Làm**:
-   Tổng: \(5 + 6 + 8 = 19\).
    
-   Nếu dùng phép chia nguyên: `19 / 3 = 6`, phần thập phân bị mất.
    
-   Nếu dùng phép chia số thực: `19.0 / 3 = 6.333...`
