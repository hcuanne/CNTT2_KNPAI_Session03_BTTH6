
# 1. Bối cảnh
Phòng đào tạo cần sử dụng AI để chuẩn hóa thông tin sinh viên và chuyển dữ liệu sang JSON.

# 2. Yêu cầu đầu ra
- Dữ liệu được chuẩn hóa thành JSON.
- Gồm các trường: fullName, email, status.
- Không thêm hoặc làm mất bản ghi.
- Dữ liệu không xác định sử dụng UNKNOWN.
- Kiểm tra tổng số bản ghi.
- Chỉ xuất JSON thô, không giải thích.

# 3. Bài làm

## Prompt theo CREATE

**C - Context:** Bạn là AI hỗ trợ phòng đào tạo chuẩn hóa dữ liệu sinh viên.

**R - Role:** Đóng vai chuyên viên xử lý dữ liệu.

**E - Examples:** 
Nguyễn Văn An - an.nguyen@gmail.com - đang học

**A - Action:**
- Đọc và tách thông tin sinh viên.
- Chuẩn hóa các trường fullName, email, status.
- Status chỉ nhận: đang học, bảo lưu, nghỉ học.
- Nếu không xác định được, dùng UNKNOWN.
- Đếm số bản ghi và kiểm tra trước khi xuất.

**T - Tone:** Chính xác, không thêm thông tin.

**E - Extras:** Chỉ xuất JSON thô, không Markdown hoặc giải thích.

## Kết quả JSON

    {
      "students": [
        {
          "fullName": "Nguyễn Văn An",
          "email": "an.nguyen@gmail.com",
          "status": "đang học"
        },
        {
          "fullName": "Trần Thị Bình",
          "email": "binhtt@gmail.com",
          "status": "bảo lưu"
        },
        {
          "fullName": "Lê Hoàng Nam",
          "email": "nam.le@gmail.com",
          "status": "đang học"
        },
        {
          "fullName": "Phạm Minh Đức",
          "email": "duc.pham@gmail.com",
          "status": "nghỉ học"
        }
      ],
      "totalRecords": 4
    }
