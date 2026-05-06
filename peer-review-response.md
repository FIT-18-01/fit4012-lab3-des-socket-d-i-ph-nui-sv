# Peer Review Response

## Thông tin nhóm
- Thành viên 1: Student 1 - MSSV: 12345678
- Thành viên 2: Student 2 - MSSV: 87654321

## Thành viên 1 góp ý cho thành viên 2
- Student 1 đề nghị Student 2 kiểm tra kỹ luồng nhận dữ liệu và xử lý buffer khi parse header và nhận ciphertext.

## Thành viên 2 góp ý cho thành viên 1
- Student 2 đề nghị Student 1 bổ sung test cho trường hợp ciphertext bị thay đổi và kiểm tra lỗi khi dùng sai key.

## Nhóm đã sửa gì sau góp ý
- Đã thêm test negative cho tamper và wrong key.
- Đã hoàn thiện tài liệu và log minh chứng.
- Đã kiểm tra lại giao thức sender/receiver để đảm bảo dữ liệu truyền đúng thứ tự `key+iv+length+ciphertext`.
