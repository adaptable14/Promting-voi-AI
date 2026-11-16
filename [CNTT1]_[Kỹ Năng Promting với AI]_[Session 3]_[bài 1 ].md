# **Prompt theo khung CREATE**
**C – Context: ( bối cảnh)**
Bộ phận Tuyển dụng (HR) của công ty công nghệ nhận được rất nhiều email ứng tuyển của sinh viên. Mỗi email viết theo một phong cách tự do khác nhau, khiến việc nhập liệu và tổng hợp thông tin ứng viên thủ công mất rất nhiều thời gian.

Bạn cần thiết kế một Prompt hệ thống giúp AI tự động trích xuất thông tin quan trọng từ các email thô này thành các cấu trúc dữ liệu chuẩn hóa để nạp vào hệ thống quản lý tuyển dụng.

**R – Request: ( yêu cầu )**  
Trích xuất 6 thông tin từ email ứng tuyển: Họ tên, Số điện thoại, Email, Vị trí ứng tuyển, Số năm kinh nghiệm, Kỹ năng chính 1.

**E – Explanation: ( giải thích )**  
Dữ liệu dùng để nhập trực tiếp vào database tuyển dụng, yêu cầu độ chính xác cao, không tự ý thêm thông tin.

**A – Action: ( hành động )**

-   Đọc và phân tích email ứng tuyển.
    
-   Xác định đúng các trường thông tin.
    
-   Chuẩn hóa họ tên thành viết hoa chữ cái đầu.

-   Gom kỹ năng trùng lặp thành một  danh sách riêng .
    
-   Thông tin thiếu ghi null.
    
-   Xuất đồng thời bảng Markdown và mảng JSON.
    

**T – Tone: ( dọng điệu )**
Chuyên nghiệp , chính xác, khách quan, ngắn gọn.

**E – Extras: ( bổ sung )**  
Sử dụng ít nhất 2 ví dụ mẫu để hướng dẫn AI nhận diện và định dạng dữ liệu.
**Ví dụ 1 :**
Input email:  
"Tôi tên là nguyễn văn a, ứng tuyển  Developer. SĐT: 0123456789 Email: [a@gmail.com]. Tôi có 2 năm kinh nghiệm với Python

Output:
| Họ tên | Số điện thoại | Email | Vị trí | Kinh nghiệm | Kỹ năng |
|---|---|---|---|---|---|
| Nguyễn Văn A | 0123456789 |a@gmail.com  |   Developer | 2  | Python |

**JSON**
[ {   "name": "Nguyễn Văn A",
    "phone": "0123456789",
    "email": "a@gmail.com",
    "position": " Developer",
    "experience_years": 2,
    "skills": ["Python"] }]
                       

**Ví dụ 2:**

Input email:  
"Tôi là Nguyễn Văn B, ứng tuyển Tester. Email: [b@gmail.com]. Tôi có 1 năm kinh nghiệm với c++,html  ."

Output:
| Họ tên | Số điện thoại | Email | Vị trí | Kinh nghiệm | Kỹ năng |
|---|---|---|---|---|---|
| Nguyễn Văn B | null | b@gmail.com | Tester | 1 |c++,html  |

**JSON:** 
 
[{"name": " Nguyễn Văn B ",  
"phone": null,  
"email": "[b@gmail.com]
"position": "Tester",  
"experience_years": 1,  
"skills": ["c++", "html"]  }]


**EMAIL ỨNG TUYỂN CẦN XỬ LÝ:**

{{email_raw}}
**EMAIL ỨNG TUYỂN:**

{{email_raw}}

**YÊU CẦU ĐẦU RA:**

1.  Bảng Markdown gồm: Họ tên, Số điện thoại, Email, Vị trí ứng tuyển, Kinh nghiệm, Kỹ năng.
    
2.  JSON thuần túy theo cấu trúc:
    


[{"name": null,  
"phone": null,  
"email": null,  
"position": null,  
"experience_years": null,  
"skills": []  }]

**QUY ĐỊNH:**

-   Chỉ trả về bảng Markdown và mảng JSON.
    
-   JSON đúng cú pháp.
    
-   Không tự bịa thông tin thêm sai lệch 
    
-   Thiếu dữ liệu hoặc thông tin chưa xác thực  ghi null.
    
-   skills là một mảng không được trùng lặp nhau .
    
-   Không viết giải thích ở đầu hoặc cuối kết quả. 
- Kiểm tra tính đúng đắn của cấu trúc JSON bằng  công cụ Validate JSON.
