## **Bước 1: Phân tích lỗi**

**Prompt bị lỗi:**

Hãy viết một bài chia sẻ về Kỹ thuật Prompting Nâng cao (Logic & Chuỗi) bằng ngôn ngữ [language]. Dành cho đối tượng .

**Phân tích lỗi:**

-   Prompt sử dụng hai kiểu dấu khác nhau là `[ ]` và `{ }`.
    
-   Tên biến chưa được viết thống nhất, gây khó khăn khi nhận diện.
    
-   Khi thay thế thông tin tự động, hệ thống có thể không nhận diện đúng các biến.
    
-   Khó quản lý và tái sử dụng prompt khi có nhiều dữ liệu khác nhau.
    

**Nguyên nhân:** Cách khai báo biến không thống nhất khiến AI hoặc hệ thống tự động hóa khó xác định chính xác vị trí cần thay thế thông tin.

## **Bước 2: Đồng bộ biến số**

Thống nhất tất cả biến về dạng `[TÊN_BIẾN]`, sử dụng chữ in hoa và dấu gạch dưới để dễ nhận biết.

**Prompt sau khi sửa lỗi:**

Hãy viết một bài chia sẻ về Kỹ thuật Prompting Nâng cao (Logic & Chuỗi) bằng ngôn ngữ [NGÔN_NGỮ]. Dành cho đối tượng [ĐỐI_TƯỢNG].

**Bảng khai báo biến số:**

| STT | Biến số | Ý nghĩa |
|---|---|---|
| 1 | [NGÔN_NGỮ] | Ngôn ngữ dùng để viết nội dung |
| 2 | [ĐỐI_TƯỢNG] | Đối tượng hướng đến của bài viết |
