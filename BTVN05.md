**Bài 5 : Thiết kế quy trình tự động quản lý tệp bằng Terminal**   
 1\. Sơ đồ luồng IPO: Input (dữ liệu file thô trong Downloads) → Process (phân loại theo đuôi file) → Output (hành động di chuyển/xóa tương ứng).
   INPUT
            Các file trong Downloads
                      ↓  
                    PROCESS
              Kiểm tra đuôi file
                      ↓
┌──────────────┬──────────────┬─────────────┐  
│ .png, .jpg   │.py           │.tmp         │  
     ↓           ↓              ↓  
   OUTPUT      OUTPUT         OUTPUT  
 Chuyển vào   Chuyển vào      Xóa file  
   media/      scripts/        tạm

2\. Danh sách câu lệnh kịch bản cho Robot (dựa trên `mv` và `rm` đã học ở Lesson 03).  
mkdir \-p media scripts  
mv Downloads/\*.png media/  
mv Downloads/\*.jpg media/  
mv Downloads/\*.py scripts/  
rm \-i Downloads/\*.tmp

## **Ràng buộc & Trường hợp kiểm thử (Edge Case)** **\-**Nếu Robot gặp một thư mục trùng tên với file đang di chuyển, hệ thống báo lỗi *"Is a directory"* (kiến thức đã học ở Lesson 04). Robot cần xử lý thế nào để không gây crash?

\=\>Nếu tên file trùng với tên một thư mục ở đích, Robot cần kiểm tra trước khi di chuyển để tránh lỗi. 
