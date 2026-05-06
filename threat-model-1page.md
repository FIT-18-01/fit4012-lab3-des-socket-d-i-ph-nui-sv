# Threat Model - Lab 3

## Thông tin nhóm
- Thành viên 1: Student 1 - MSSV: 12345678
- Thành viên 2: Student 2 - MSSV: 87654321

## Assets
- Bản tin gốc (plaintext) cần truyền đi.
- DES key và IV được gửi cùng packet.
- Ciphertext và header độ dài trong packet TCP.

## Attacker model
- Attacker có thể nghe lén kênh TCP trong cùng mạng nội bộ.
- Attacker có thể sửa đổi hoặc tái phát packet trước khi đến receiver.
- Attacker không có quyền truy cập trực tiếp vào máy sender hoặc receiver.

## Threats
- Eavesdropping: attacker đọc được key, IV và ciphertext vì tất cả đi qua cùng luồng không mã hoá.
- Tampering: attacker thay đổi ciphertext gây lỗi giải mã hoặc dữ liệu sai.
- Replay attack: attacker gửi lại packet cũ để receiver xử lý lại bản tin.

## Mitigations
- Không gửi key và IV plaintext trên cùng luồng; dùng trao đổi khóa an toàn hoặc kênh mã hoá.
- Thêm xác thực message/MAC để phát hiện packet bị thay đổi.
- Dùng TLS hoặc VPN để bảo vệ cả tính toàn vẹn và tính bảo mật của kênh truyền.

## Residual risks
- DES vốn yếu và có thể bị brute-force nếu dùng trong hệ thống thực tế.
- Nếu attacker có quyền can thiệp vào máy chủ sender/receiver, kênh an toàn vẫn bị phá vỡ.
