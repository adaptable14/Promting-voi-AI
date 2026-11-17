## **Bước 1: Thiết kế giải pháp (I/O)**

### **1.1. Xác định bài toán**

-   **Tên giải pháp:** Tự động kiểm tra và xử lý đơn hàng tại cửa hàng.
    
-   **Mục đích:** Giúp cửa hàng kiểm tra thông tin đơn hàng, tính tổng tiền và phát hiện lỗi dữ liệu.
    
-   **Công nghệ sử dụng:** AI Prompting nâng cao, Prompt Chaining và Logic điều kiện.
    

### **1.2. Input (Dữ liệu đầu vào)**



| STT | Trường dữ liệu | Giá trị mẫu |
|---|---|---|
| 1 | Mã đơn hàng | DH001 |
| 2 | Tên khách hàng | Nguyễn Văn A |
| 3 | Tên sản phẩm | Áo thun |
| 4 | Số lượng | 2 |
| 5 | Đơn giá | 150.000 |
| 6 | Số điện thoại | 0987654321 |
| 7 | Địa chỉ | Hà Nội |


    

### **1.. Output (Kết quả đầu ra)**

| STT | Trường kết quả | Nội dung |
|---|---|---|
| 1 | Mã đơn hàng | DH001 |
| 2 | Khách hàng | Nguyễn Văn A |
| 3 | Sản phẩm | Áo thun |
| 4 | Số lượng | 2 |
| 5 | Đơn giá | 150.000đ |
| 6 | Tổng tiền | 300.000đ |
| 7 | Trạng thái | Hợp lệ |
| 8 | Ghi chú | Không có lỗi |

## **Bước 2: Viết Prompt và chạy thử**

### **2.1. Prompt hoàn chỉnh**

# VAI TRÒ

Bạn là nhân viên quản lý đơn hàng của một cửa hàng bán hàng online.

# BỐI CẢNH

Cửa hàng nhận được nhiều đơn hàng mỗi ngày. Việc kiểm tra và tính tiền thủ công mất thời gian và dễ xảy ra sai sót. Cần sử dụng AI để tự động hóa quy trình xử lý đơn hàng.

# YÊU CẦU

Hãy xử lý đơn hàng theo kỹ thuật Prompt Chaining gồm 3 giai đoạn:

**Giai đoạn 1: Kiểm tra dữ liệu**

-   Kiểm tra mã đơn hàng, tên khách hàng, sản phẩm, số lượng, đơn giá, số điện thoại và địa chỉ.
    
-   Nếu thiếu thông tin, ghi rõ trường dữ liệu bị thiếu.
    
-   Nếu số lượng hoặc đơn giá nhỏ hơn hoặc bằng 0, thông báo dữ liệu không hợp lệ.
    

**Giai đoạn 2: Tính toán**

-   Chỉ thực hiện khi dữ liệu hợp lệ.
    
-   Tính tổng tiền theo công thức: Tổng tiền = Số lượng × Đơn giá.
    
-   Kiểm tra lại kết quả tính toán.
    
-   Nếu dữ liệu không hợp lệ, dừng bước tính toán.
    

**Giai đoạn 3: Phân loại đơn hàng**

-   Nếu dữ liệu đầy đủ và chính xác: Hợp lệ.
    
-   Nếu thiếu thông tin: Cần bổ sung.
    
-   Nếu dữ liệu sai hoặc mâu thuẫn: Cần kiểm tra lại.
    

# RÀNG BUỘC VÀ XỬ LÝ LỖI

-   Không tự ý tạo thông tin còn thiếu.
    
-   Không tự sửa dữ liệu sai.
    
-   Nếu phát hiện dữ liệu bị trống, phải thông báo cụ thể.
    
-   Nếu một giai đoạn thất bại, không tiếp tục các giai đoạn phụ thuộc.
    
-   Luôn nêu nguyên nhân và hướng xử lý lỗi.
    

# ĐỊNH DẠNG ĐẦU RA

Trình bày kết quả bằng bảng gồm:  
Mã đơn hàng | Khách hàng | Sản phẩm | Số lượng | Đơn giá | Tổng tiền | Trạng thái | Ghi chú.

Sau bảng, đưa ra kết luận xử lý đơn hàng.

# DỮ LIỆU ĐẦU VÀO

Mã đơn hàng: DH001  
Tên khách hàng: Nguyễn Văn A  
Sản phẩm: Áo thun  
Số lượng: 2  
Đơn giá: 150000  
Số điện thoại: 0987654321  
Địa chỉ: Hà Nội

### **2.2. Kết quả chạy thử**

**Kết quả AI phản hồi:**

| Mã đơn hàng | Khách hàng | Sản phẩm | Số lượng | Đơn giá | Tổng tiền | Trạng thái |
|---|---|---|---|---|---|---|
| DH001 | Nguyễn Văn A | Áo thun | 2 | 150.000đ | 300.000đ | Hợp lệ |

**Ghi chú:** Thông tin đơn hàng đầy đủ, số lượng và đơn giá hợp lệ, không phát hiện lỗi.

**Kết luận:** Đơn hàng DH001 có tổng tiền là 300.000đ và đủ điều kiện chuyển sang bước chờ xác nhận.

### **2.3. Kiểm tra khả năng xử lý lỗi**

| STT | Dữ liệu thử nghiệm | Kết quả AI phản hồi |
|---|---|---|
| 1 | Bỏ trống tên khách hàng | Cần bổ sung tên khách hàng |
| 2 | Số lượng = -2 | Số lượng không hợp lệ |
| 3 | Đơn giá = 0 | Đơn giá không hợp lệ |
| 4 | Bỏ trống địa chỉ | Cần bổ sung địa chỉ |
| 5 | Đầy đủ thông tin | Đơn hàng hợp lệ |

