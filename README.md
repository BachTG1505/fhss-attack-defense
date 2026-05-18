# Phòng thí nghiệm: FHSS-Attack-Defense

Bài thực hành Labtainers – Đánh giá độ bền vững và tối ưu hóa hệ thống giấu tin âm thanh DWT-FHSS-QIM chống lại các kịch bản tấn công phá hủy tín hiệu.

---

## Mô tả

Bài lab mô phỏng hệ thống:

- Audio steganography dùng DWT Haar 5 level
- Frequency Hopping Spread Spectrum (FHSS) + QIM (Quantization Index Modulation)
- Tấn công Gaussian Noise và MP3 Compression
- Phân tích Bit Error Rate (BER) thực tế
- Phòng thủ bằng Repetition Code + DELTA tối ưu
- Trade-off Imperceptibility (PSNR) vs Robustness (BER)

---

## Tải về và chạy

```bash
imodule https://github.com/BachTG1505/fhss-attack-defense/raw/main/fhss-attack-defense-v3.tar

cd ~/labtainer/trunk/scripts/labtainer-student

labtainer fhss-attack-defense
```

---

# Các nhiệm vụ

## Task 1 – Baseline Embedding

Nhúng thông điệp `HELLO PTIT!` (88 bit) với cấu hình mặc định:

```text
DELTA = 20.0
K_REPEAT = 1
```

Kết quả: PSNR ~108 dB (audio gần như không thay đổi)

---

## Task 2 – Baseline Extraction

Trích xuất tin từ stego sạch để kiểm tra tính toàn vẹn.

Kết quả mong đợi:

```text
BER = 0.00%
```

---

## Task 3 – Visual Spectrum (Before Attack)

Quan sát phổ tín hiệu bằng Sonic Visualiser, lưu session:

```text
before_attack.sv
```

---

## Task 4 – Gaussian Noise Attack

Tấn công bằng nhiễu Gaussian 4 mức σ:

- σ = 10, 50, 100, 200

Quan sát BER tăng theo σ với cấu hình DELTA thấp.

---

## Task 5 – Post-Attack Visual

Sonic Visualiser phân tích `attacked_audio.wav` (sigma=100), lưu session:

```text
after_attack.sv
```

---

## Task 6 – MP3 Compression Attack

Nén MP3 suy hao bằng ffmpeg với 3 bitrate:

- 128 kbps
- 64 kbps
- 32 kbps

Quan sát BER tăng khi bitrate giảm.

---

## Task 7 – Defense Optimization (TODO của sinh viên)

Mở `embed_message.py` và chỉnh 2 tham số:

```text
DELTA = 1000.0
K_REPEAT = 3
```

Ràng buộc:
- DELTA trong khoảng [500, 2000]
- K_REPEAT >= 3

---

## Task 8 – Constraint Validation

Verify đồng thời:

- PSNR >= 40 dB
- BER sau attack sigma=100 <= 5%
- Tham số trong khoảng cho phép

Kết quả mong đợi:

```text
PSNR = 70.51 dB
BER  = 0.00%
```

---

## Task 9 – Final Summary

Tổng hợp kết quả và trade-off:

- Imperceptibility (PSNR)
- Robustness (BER)
- Capacity (số bit/sample)

---

# Công cụ sử dụng

- Python 3
- NumPy, SciPy
- ffmpeg (nén MP3)
- Sonic Visualiser (phổ tín hiệu)
- DWT Haar 5-level (tự cài, không dùng pywt)
- QIM với hopping sequence (FHSS)
- Repetition Code (mã sửa lỗi)

---

# Kiến thức đạt được

- DWT-FHSS-QIM audio steganography
- Gaussian noise attack & Bit Error Rate analysis
- MP3 lossy compression attack
- Error correction via Repetition Code
- Multi-objective optimization (PSNR + BER + Capacity)
- Tam giác Stego trade-off

---

# Tác giả

- Họ và tên: Trương Gia Bách
- Mã sinh viên: B22DCAT024
- Lớp: D22CQAT04-B
- Học phần: INT14102 – Kỹ thuật giấu tin
- Giảng viên hướng dẫn: PGS.TS. Đỗ Xuân Chợ
