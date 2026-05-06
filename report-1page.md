# Report 1 page - Lab 3

## Thông tin nhóm
- Thành viên 1: Student 1 - MSSV: 12345678
- Thành viên 2: Student 2 - MSSV: 87654321

## Mục tiêu
- Xây dựng hệ thống Sender/Receiver truyền bản tin qua TCP socket với mã hoá DES-CBC.
- Hiểu cách tạo key, IV, padding PKCS#7 và header độ dài.
- Kiểm thử giao thức, bảo mật kênh và xử lý lỗi khi nhận packet.

## Phân công thực hiện
- Student 1: cài đặt `sender.py`, mã hoá DES-CBC, kiểm thử sender và ghi log gửi.
- Student 2: cài đặt `receiver.py`, giải mã DES-CBC, kiểm thử receiver và viết threat model.
- Làm chung: thiết kế packet, viết docs, chạy demo và hoàn thiện báo cáo.

## Cách làm
- `sender.py` tạo key và IV ngẫu nhiên 8 byte, mã hoá bản tin bằng DES-CBC và PKCS#7.
- `des_socket_utils.py` thực hiện padding/unpad, đóng gói packet `key+iv+length+ciphertext` và giải mã.
- `receiver.py` nhận header, parse packet, giải mã và in bản tin gốc.
- `tests/` bao gồm kiểm thử unit và tích hợp cho protocol, padding, tamper và wrong key.

## Kết quả
- Hệ thống chạy được với Receiver lắng nghe và Sender gửi packet qua TCP.
- `pytest -q` đã kiểm tra thành công các case bình thường và negative.
- Đã bổ sung log demo trong `logs/` để minh chứng chạy thật.

## Kết luận
- Đã củng cố hiểu biết về DES-CBC, vai trò key/IV và padding PKCS#7.
- Nhận thấy việc gửi key và IV plaintext qua socket là điểm yếu bảo mật lớn.
- Cần dùng kết nối an toàn hơn (TLS/MAC hoặc trao đổi khóa an toàn) cho hệ thống thực tế.
