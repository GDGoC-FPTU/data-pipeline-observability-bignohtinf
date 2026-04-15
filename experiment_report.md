# Experiment Report: Data Quality Impact on AI Agent

**Student ID:** AI20K-XXXX
**Name:** (Dien ten cua ban)
**Date:** (Dien ngay thuc hien)

---

## 1. Ket qua thi nghiem

Chay `agent_simulation.py` voi 2 bo du lieu va ghi lai ket qua:

| Scenario | Agent Response | Accuracy (1-10) | Notes |
|----------|----------------|-----------------|-------|
| Clean Data (`processed_data.csv`) | Based on my data, the best choice is Laptop at $1200 | | |
| Garbage Data (`garbage_data.csv`) | Based on my data, the best choice is Nuclear Reactor at $999999 | | |

---

## 2. Phan tich & nhan xet

### Tai sao Agent tra loi sai khi dung Garbage Data?

Dữ liệu "garbage" chứa nhiều lỗi làm méo kết quả đầu ra của agent. Các vấn đề thường gặp gồm: duplicate IDs (bản ghi trùng) làm các phép tổng hợp và xếp hạng bị lệch; wrong data types (ví dụ giá trị lưu dưới dạng chuỗi hoặc chứa ký tự) khiến phép so sánh và tính toán không chính xác; outliers (giá trị ngoại lai rất lớn như 999999) kéo trung bình/median và làm agent ưu tiên mục không hợp lý; null values hoặc trường trống nếu được gán bằng 0 hoặc được impute sai sẽ tạo bias; mislabeled columns hoặc unit inconsistency (USD vs VND) dẫn tới mapping thuộc tính sai. Những lỗi này ảnh hưởng trực tiếp tới bước tiền xử lý, thống kê mô tả và các thuật toán lựa chọn sản phẩm, vì vậy agent kết luận sai (garbage in → garbage out). Một prompt tốt không thể khắc phục các sai lệch cơ bản trong dữ liệu nếu pipeline không kiểm soát và làm sạch dữ liệu trước khi dùng.

---

## 3. Ket luan

**Quality Data > Quality Prompt?** (Dong y hay khong? Giai thich ngan gon.)

Đồng ý. Dữ liệu chất lượng hơn prompt: prompt rõ ràng quan trọng nhưng không thể bù đắp cho dữ liệu sai lệch, thiếu hoặc nhiễu. Trước khi tối ưu prompt cần đảm bảo validation, cleansing, xử lý missing/outlier và chuẩn hoá unit.
