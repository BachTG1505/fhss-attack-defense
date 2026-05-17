# Phòng thí nghiệm: FHSS-Attack-Defense

Bài thực hành Labtainers – Đánh giá độ bền vững và tối ưu hóa hệ thống giấu tin âm thanh sử dụng kỹ thuật FHSS chống lại các kịch bản tấn công phá hủy tín hiệu.

---

## Mô tả

Bài lab mô phỏng hệ thống:

- Audio steganography
- Frequency Hopping Spread Spectrum (FHSS)
- Tấn công phá hủy tín hiệu
- Phân tích độ bền vững dữ liệu ẩn
- Tối ưu hóa tham số chống nhiễu

Người học sẽ trực tiếp:

- Nhúng dữ liệu bí mật
- Tấn công tín hiệu
- Phân tích phổ tín hiệu
- Đo BER
- Đánh đổi giữa robustness và audio quality

---

## Tải về và chạy

```bash
imodule https://github.com/BachTG1505/fhss-attack-defense/raw/main/fhss-attack-defense.tar

cd ~/labtainer/trunk/scripts/labtainer-student

labtainer fhss-attack-defense
Các nhiệm vụ
Task 1 – Baseline Embedding

Nhúng thông điệp bí mật với cấu hình mặc định:

K_REPEAT=1
ALPHA=10.0
Task 2 – Baseline Extraction

Trích xuất dữ liệu và kiểm tra tính toàn vẹn.

Kết quả mong đợi:

BER = 0.00%
Task 3 – Visual Spectrum Analysis

Quan sát phổ tín hiệu bằng Sonic Visualiser.

Mở file:

before_attack.sv

Kết quả:

Tín hiệu FHSS ổn định
Không xuất hiện nhiễu phá hủy
Task 4 – Gaussian Noise Attack

Kích hoạt chuỗi tấn công nhiễu Gaussian.

Bao gồm:

4 mức độ phá hủy tăng dần

Quan sát:

FHSS hopping bị che phủ bởi noise burst
Tăng lỗi khôi phục dữ liệu
Task 5 – Post-Attack Analysis

Dùng Sonic Visualiser để phân tích tín hiệu sau tấn công.

Mở:

after_attack.sv

Phân tích:

Nhiễu đè lên hopping frequency
Sai lệch phổ tín hiệu

Kết quả:

BER tăng mạnh theo mức nhiễu
Task 6 – MP3 Compression Attack

Thực hiện nén MP3 suy hao.

So sánh các bitrate:

320 kbps
128 kbps
64 kbps

Kết quả:

Bitrate thấp làm mất thành phần nhúng
Dữ liệu ẩn suy giảm mạnh
Task 7 – Defense Optimization

Khảo sát mã nguồn và tìm cấu hình tối ưu:

K_REPEAT=3
ALPHA=60.0

Mục tiêu:

Tăng khả năng sửa lỗi
Giảm BER sau tấn công
Task 8 – Constraint Validation

Kiểm tra:

PSNR
BER

Kết quả mong đợi:

PSNR = 43.12 dB
BER <= 5%
Task 9 – Final Summary

Tổng hợp kết quả toàn bài lab.

Đánh giá trade-off giữa:

robustness
audio quality
attack resistance
Công cụ sử dụng
Python 3
NumPy
SciPy
pydub
ffmpeg
Sonic Visualiser
Kiến thức đạt được
FHSS communication
Audio steganography
Gaussian noise attack
Compression attack
Error correction strategy
Signal robustness analysis
Tác giả
Họ và tên: Trương Gia Bách
Mã sinh viên: B22DCAT024
Lớp: D22CQAT04-B
Học phần: INT14102 – Kỹ thuật giấu tin
Giảng viên hướng dẫn: PGS.TS. Đỗ Xuân Chợ

