# ViT5: Tinh chỉnh mô hình sinh câu hỏi trắc nghiệm tự động (Question Generation)

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![PyTorch](https://img.shields.io/badge/PyTorch-1.12+-orange.svg)
![HuggingFace](https://img.shields.io/badge/%F0%9F%A4%97-Transformers-yellow.svg)
![License](https://img.shields.io/badge/License-MIT-green.svg)

## Giới thiệu dự án
Dự án này tập trung vào việc nghiên cứu và tinh chỉnh (Fine-tuning) mô hình ngôn ngữ ViT5 (kiến trúc Transformer dành cho tiếng Việt) để thực hiện nhiệm vụ sinh câu hỏi trắc nghiệm tự động từ văn bản nguồn. Hệ thống cho phép điều khiển mức độ tư duy của câu hỏi dựa trên thang đo nhận thức Bloom. 

Đây là sản phẩm trong học phần Thực tập nghề nghiệp 1 tại Khoa Công nghệ Thông tin - Trường ĐH Sư phạm TP.HCM.

## Các tính năng nổi bật
- Phân tầng nhận thức: Hỗ trợ sinh câu hỏi theo 3 mức độ: Nhận biết, Thông hiểu và Vận dụng.
- Đa lĩnh vực: Hoạt động tốt trên các ngữ liệu Địa lý, Tin học, Ngữ văn và Sinh học.
- Định dạng chuẩn: Đầu ra luôn đảm bảo cấu trúc JSON giúp dễ dàng tích hợp vào các hệ thống LMS.
- Giao diện trực quan: Tích hợp Web UI bằng Gradio để tương tác thời gian thực.

## Kết quả thực nghiệm (Metrics)
Sau giai đoạn Ultra Training (15 Epochs) với các kỹ thuật tối ưu hóa như Label Smoothing và Cosine Decay, mô hình đạt được:
- BLEU-4: 27.42
- ROUGE-L: 45.21
- Tốc độ phản hồi: ~1.52 giây/câu hỏi.

## Cấu trúc thư mục dự án
```text
├── data/               # Tập dữ liệu huấn luyện (13.000 mẫu)
├── src/                # Mã nguồn tiền xử lý và cấu hình mô hình
├── notebooks/          # Google Colab notebooks cho huấn luyện và đánh giá
├── app.py              # Script khởi chạy giao diện Gradio
├── requirements.txt    # Danh sách thư viện cần thiết
└── README.md           # Tài liệu hướng dẫn dự án
```
🚀 Hướng dẫn cài đặt và sử dụng
1. Cài đặt môi trường
```Bash

git clone https://github.com/duonglamkhang/ViT5-Question-Gen.git
cd ViT5-Question-Gen
pip install -r requirements.txt
```
2. Chạy Demo
```Bash

python app.py
```
💡 Phân tích lỗi và Hạn chế (Error Analysis)
Trong quá trình thực nghiệm, hệ thống đã được phân tích sâu về lỗi Ảo tưởng logic (Logical Hallucination) khi xử lý các ngữ cảnh phức tạp (ví dụ: nhầm lẫn các hệ quả kinh tế tại Đông Nam Bộ). Việc nhận diện lỗi này giúp định hướng tối ưu hóa cơ chế Attention trong tương lai.

👨‍💻 Tác giả
Sinh viên: Dương Lâm Khang

Khoa: Công nghệ Thông tin - ĐH Sư phạm TP.HCM

Giảng viên hướng dẫn: ThS. Lương Trần Ngọc Khiết & CH. Lê Thanh Thoại.

📄 Bản quyền
Dự án này được phát hành dưới giấy phép MIT.
