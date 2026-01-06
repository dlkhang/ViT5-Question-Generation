# 🚀 ViT5: Tinh chỉnh mô hình sinh câu hỏi trắc nghiệm tự động (Question Generation)

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![PyTorch](https://img.shields.io/badge/PyTorch-1.12+-orange.svg)
![HuggingFace](https://img.shields.io/badge/%F0%9F%A4%97-Transformers-yellow.svg)

## 📌 Giới thiệu dự án
Dự án này tập trung vào việc tinh chỉnh (Fine-tuning) mô hình ngôn ngữ ViT5 (phiên bản kiến trúc Transformer dành riêng cho tiếng Việt) để thực hiện nhiệm vụ sinh câu hỏi trắc nghiệm tự động từ một đoạn văn bản nguồn. 

Đây là kết quả của quá trình thực tập nghiên cứu, nhằm hỗ trợ giáo viên và các đơn vị giáo dục số hóa ngân hàng đề thi một cách nhanh chóng và chính xác.

## ✨ Các tính năng chính
- Đa cấp độ nhận thức: Điều khiển mô hình sinh câu hỏi theo các mức độ Bloom (Nhận biết, Thông hiểu, Vận dụng).
- Định dạng chuẩn: Kết quả đầu ra được đóng gói dưới dạng JSON, dễ dàng tích hợp vào các hệ thống LMS.
- Giao diện trực quan: Hỗ trợ demo thông qua Gradio.
- Xử lý đa lĩnh vực: Vận hành tốt trên các môn học như Ngữ văn, Địa lý, Tin học, Sinh học.

## 📊 Kết quả thực nghiệm (Metrics)
Sau giai đoạn **Ultra Training** (15 Epochs), mô hình đạt được các chỉ số ấn tượng:
- BLEU-4: 27.42
- ROUGE-L: 45.21
- Thời gian phản hồi trung bình: 1.52 giây/câu hỏi.
## 🛠 Cấu trúc thư mục
├── data/               # Chứa tập dữ liệu huấn luyện (13.000 samples)
├── models/             # Chứa checkpoints và trọng số mô hình sau huấn luyện
├── notebooks/          # Google Colab notebooks (Train & Eval)
├── src/                # Mã nguồn chính (Tiền xử lý, Model class)
├── app.py              # File chạy giao diện Gradio
├── requirements.txt    # Các thư viện cần thiết
└── README.md           # Hướng dẫn sử dụng dự án

🚀 Hướng dẫn cài đặt và sử dụng
1. Cài đặt môi trường
Bash

git clone [https://github.com/your-username/ViT5-Question-Gen.git](https://github.com/your-username/ViT5-Question-Gen.git)
cd ViT5-Question-Gen
pip install -r requirements.txt
2. Sử dụng Giao diện (Gradio)
Bash

python app.py
📸 Hình ảnh Demo
(Bạn hãy chèn ảnh chụp màn hình giao diện web Gradio ở Chương 3 vào đây)

💡 Bài học rút ra (Error Analysis)
Trong quá trình phát triển, dự án đã giải quyết bài toán Ảo tưởng logic (Logical Hallucination) bằng cách tối ưu hóa cơ chế Beam Search và kỹ thuật Label Smoothing, giúp mô hình bám sát ngữ cảnh nguồn hơn.

👨‍💻 Tác giả
Dương Lâm Khang - Sinh viên Khoa Công nghệ Thông tin, Đại học Sư phạm TP.HCM.

Giảng viên hướng dẫn: ThS. Lương Trần Ngọc Khiết & CH. Lê Thanh Thoại.

