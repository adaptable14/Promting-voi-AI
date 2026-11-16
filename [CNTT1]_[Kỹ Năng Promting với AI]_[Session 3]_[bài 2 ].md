# **Prompt theo khung CREATE**
**C – Context (Bối cảnh):**

Một nền tảng Thương mại điện tử muốn phân tích tự động hàng nghìn phản hồi của khách hàng mỗi ngày để chuyển đến đúng phòng ban xử lý (Kỹ thuật, Chăm sóc khách hàng, Giao hàng, Kho vận).

Frontend Dashboard yêu cầu nhận dữ liệu dưới dạng JSON có phân loại rõ ràng để vẽ biểu đồ thống kê mức độ hài lòng theo từng chủ đề.

**R – Request (Yêu cầu):**

Phân tích phản hồi khách hàng theo 3 thuộc tính:

-   Sentiment: Positive, Negative hoặc Neutral.
    
-   Topics: Product, Delivery, Service hoặc System.
    
-   Score: Điểm hài lòng từ 1 đến 5.
    

**E – Explanation (Giải thích):**

Kết quả phân tích được sử dụng trên Dashboard để thống kê cảm xúc khách hàng theo từng chủ đề và chuyển phản hồi đến đúng phòng ban.

**A – Action (Hành động):**

1.  Đọc và xác định cảm xúc chính của khách hàng.
    
2.  Xác định tất cả chủ đề xuất hiện trong phản hồi.
    
3.  Chấm điểm hài lòng từ 1 đến 5.
    
4.  Viết tóm tắt nội dung dưới 15 từ.
    
5.  Loại bỏ các từ cảm thán không cần thiết.
    

**T – Tone (Giọng điệu):**

 khách quan, chính xác, ngắn gọn và dễ hiểu.

**E – Extras (Bổ sung):**

Sử dụng Few-shot Prompting với 3 ví dụ mẫu như sau :

**Ví dụ 1 – Tích cực ( Positive )**

Input: "Sản phẩm đẹp, giao hàng nhanh, nhân viên tư vấn rất nhiệt tình."

Output:  

{"sentiment": "Positive",  
"topics": ["Product", "Delivery", "Service"],  
"score": 5,  
"summary": "Sản phẩm đẹp, giao nhanh, nhân viên tư vấn nhiệt tình"  }


**Ví dụ 2 – Tiêu cực (Negative)**

Input: "Điện thoại bị lỗi, ứng dụng cũng thường xuyên bị treo."

Output:  

{"sentiment": "Negative",  
"topics": ["Product", "System"],  
"score": 1,  
"summary": "Điện thoại bị lỗi và ứng dụng thường xuyên bị treo"  }


**Ví dụ 3 – Trung lập (Neutral)**

Input: "Tôi nhận được hàng vào**Positive** ."

Output:  

{"sentiment": "Neutral",  
"topics": ["Delivery"],  
"score": 3,  
"summary": "Khách hàng nhận hàng vào đúng ngày hạn giao hàng " }

**QUY TẮC PHÂN LOẠI:**

-   Positive: Khách hàng hài lòng, khen ngợi.
    
-   Negative: Khách hàng không hài lòng, phàn nàn.
    
-   Neutral: phản ứng trung lập, không thể hiện rõ cảm xúc của khách hàng 
    
-   Product: Liên quan đến sản phẩm.
    
-   Delivery: Liên quan đến giao hàng.
    
-   Service: Liên quan đến nhân viên, chăm sóc khách hàng.
    
-   System: Liên quan đến website, ứng dụng và lỗi hệ thống.
    
-   Một phản hồi có thể có nhiều chủ đề. Ví dụ như : khen giao hàng nhanh nhưng chê sản phẩm thì phải gắn cả Product và Delivery.
    
-   Score từ 1 đến 5, tương ứng với mức độ hài lòng tăng dần.
    
-   Summary phải dưới 15 từ, không chứa từ cảm thán thừa thãi .
    

**DỮ LIỆU ĐẦU VÀO:**

{{customer_feedback}}

**ĐỊNH DẠNG JSON :**


{"sentiment": "Invalid",  
"topics": ["Invalid"],  
"score": null,  
"summary": "Invalid feedbac  }



**RÀNG BUỘC:**

-   Chỉ xuất JSON object thuần túy.
    
-   Không thêm lời giải thích, tiêu đề hoặc Markdown vào kết quả.
    
-   Không sử dụng thư viện ngoài.
    
-   Không tự ý thêm thông tin không có trong phản hồi.
