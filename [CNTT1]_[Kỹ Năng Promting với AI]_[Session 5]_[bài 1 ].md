
# **1. Prompt**
Bạn là một chuyên  gia  trong việc quản lý tài chính . Hãy giúp tôi lập kế hoạch chi tiêu hàng tháng dựa trên những thông tin sau:

-   Thu nhập hàng tháng: [Nhập số tiền]
    
-   Thuế và các khoản khấu trừ: [Nhập số tiền]
    
-   Chi phí cố định: [Nhập số tiền]
    
-   Các khoản nợ cần trả: [Nhập số tiền và thời hạn]
    
-   Mục tiêu tiết kiệm: [Nhập số tiền hoặc tỷ lệ phần trăm]
    

### **Yêu cầu:**

Hãy suy nghĩ từng bước một và tính toán chi tiết trước khi đưa ra kết quả. Thực hiện theo các bước:

1.  Tính số tiền còn lại sau khi trừ thuế và chi phí cố định.
    
2.  Xác định số tiền cần dùng để trả nợ đúng hạn.
    
3.  Dành ít nhất 20% thu nhập sau thuế cho việc tiết kiệm.
    
4.  Chia số tiền còn lại cho các khoản chi tiêu hàng ngày theo quy tắc 50/30/20 cải tiến.
    
5.  Kiểm tra lại các phép tính để đảm bảo không chi tiêu vượt quá số tiền đang có và tổng tỷ lệ phân bổ bằng 100%.
    

### **Yêu cầu đầu ra gồm 2 phần:**

#### **Phần 1: Các bước tính toán**

-   Ghi rõ công thức tính.
    
-   Trình bày các phép tính cộng, trừ, nhân, chia.
    
-   Nêu kết quả sau mỗi bước.
    

#### **Phần 2: Bảng phân bổ ngân sách**

Trình bày bằng bảng Markdown gồm các cột:  
| Hạng mục | Số tiền | Tỷ lệ % | Ghi chú |

**Lưu ý:**

-   Phải trả nợ đúng hạn.
    
-   Tiết kiệm tối thiểu 20% thu nhập sau thuế.
    
-   Không được chi tiêu vượt quá thu nhập.
    
-   Tổng tỷ lệ phân bổ phải bằng chính xác 100%.
    
-   Nếu số tiền không đủ để đáp ứng các khoản chi, hãy nêu rõ và đề xuất cách điều chỉnh.
    
-   Không sử dụng Python hoặc Pydantic.
# 2. ví dụ kết quả chạy thử của 
## **ví dụ kết giá trị ở bảng  sau** :
| Biến số | Giá trị |
|---|---|
| Thu nhập hàng tháng | 12.000.000 VNĐ |
| Thuế | 500.000 VNĐ |
| Chi phí cố định | 3.000.000 VNĐ |
| Các khoản nợ | 2.000.000 VNĐ |
| Mục tiêu tiết kiệm | 20% thu nhập sau thuế |
## kết quả Ai chả về với ví dụ ở bảng trên:
### **Phần 1: Các bước tính toán**
 **Bước 1: Tính thu nhập sau thuế và trừ chi phí cố định**

-   Thu nhập hàng tháng: 12.000.000 VNĐ.
    
-   Thuế: 500.000 VNĐ.
    
-   Chi phí cố định: 3.000.000 VNĐ.
    

Phép tính:

12.000.000 - 500.000 = 11.500.000 VNĐ.

11.500.000 - 3.000.000 = 8.500.000 VNĐ.

**Bước 2: Tính tiền trả nợ**

Số tiền còn lại sau khi trả nợ:

8.500.000 - 2.000.000 = 6.500.000 VNĐ.

**Bước 3: Tính tiền tiết kiệm**

Mục tiêu tiết kiệm là 20% thu nhập sau thuế:

11.500.000 × 20% = 2.300.000 VNĐ.

**Bước 4: Tính tiền còn lại để chi tiêu**

6.500.000 - 2.300.000 = 4.200.000 VNĐ.

Khoản tiền này dùng cho ăn uống, đi lại và các nhu cầu cá nhân.

**Bước 5: Kiểm tra ngân sách**

500.000 + 3.000.000 + 2.000.000 + 2.300.000 + 4.200.000 = 12.000.000 VNĐ.

Tổng ngân sách đã được phân bổ đầy đủ, không vượt quá thu nhập.

### **Phần 2: Bảng phân bổ ngân sách**

| Hạng mục | Số tiền (VNĐ) | Tỷ lệ % | Ghi chú |
|---|---:|---:|---|
| Thuế | 500.000 | 4,17% | Khoản khấu trừ |
| Chi phí cố định | 3.000.000 | 25% | Tiền sinh hoạt |
| Trả nợ | 2.000.000 | 16,67% | Thanh toán nợ |
| Tiết kiệm | 2.300.000 | 19,16% | Tiết kiệm hàng tháng |
| Chi tiêu linh hoạt | 4.200.000 | 35% | Ăn uống, đi lại |
| **Tổng cộng** | **12.000.000** | **100%** | |
