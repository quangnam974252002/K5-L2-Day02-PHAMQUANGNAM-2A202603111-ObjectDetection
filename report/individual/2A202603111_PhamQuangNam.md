# Báo cáo cá nhân — Ngày 2 Object Detection

Đổi tên file theo `MSSV_HoTen.md`, ví dụ `20241234_NguyenVanAn.md`. Điền kết quả thật, xóa dòng hướng dẫn khi nộp. Xem [quy định nộp](../../SUBMISSION.md).

## 1. Thông tin học viên

- Họ tên: Phạm Quang Nam
- MSSV: 2A202603111
- Email: quangnam97425@gmail.com
- Lớp: C401
- Link repo bài làm: https://github.com/quangnam974252002/K5-L2-Day02-ObjectDetection
- Link Colab đã chạy: https://colab.research.google.com/github/quangnam974252002/K5-L2-Day02-ObjectDetection/blob/main/notebooks/day2_annotation_to_yolo.ipynb#scrollTo=cTfQnJepqIos

## 2. Schema và mini guideline

Dẫn tới [GUIDELINE_MINI.md](../../GUIDELINE_MINI.md). Tóm tắt ba ca mơ hồ đã quyết định, cách áp dụng schema và phần cần giảng viên làm rõ.

## 3. Annotation và self-QC

- Số file nhãn train: 
- Kết quả checker và lỗi đã xử lý:
- Danh sách ít nhất 10 ảnh đã rà bằng mắt:
- Lỗi bỏ sót/box/class phát hiện khi rà và cách sửa: 
- Commit khóa nhãn ban đầu:

## 4. Gold QC và rework

| Chỉ số | Trước sửa | Sau sửa nếu có |
|---|---:|---:|
| TP | 452 | |
| FP | 375 | |
| FN | 201 | |
| Precision | 0.5466 | |
| Recall | 0.6922 | |
| F1 | 0.6108 | |
| mean_iou_of_matches | 0.8602 | |
| passed | false | |

Dẫn tới `outputs/annotation_evaluation.json` trong repo. Nếu rework, ghi ảnh, lỗi đã kiểm, quyết định sửa/giữ và lý do. Không suy nguyên nhân chỉ từ FP/FN. Không có rework thì ghi rõ.

## 5. Kết quả YOLO

- Runtime, GPU/CPU, phiên bản Ultralytics và Torch:
Runtime : 1.8ms
GPU/CPU : CPU intel xeon CPU @ 2.20Ghz
Ultralytics ver : 8.4.208
Torch ver : 2.14.1

- Các tham số thay đổi so với notebook nếu có và lý do:
- Đường dẫn best checkpoint trong phiên chạy:

| Chỉ số trên 10 ảnh eval | Giá trị |
|---|---:|
| Precision | 0.4594385742507652 |
| Recall | 0.23838652482269504 |
| mAP50 | 0.27734324435382446 |
| mAP50–95 | 0.20790403164191681 |

Đặt cả 2 folder `assets/eval_predictions/` và `assets/yolo26_runs/` (giải nén từ `day2_colab_outputs.zip`) cạnh báo cáo và dẫn link tương đối. Không chỉ ghi số; chỉ ra ít nhất một ảnh và vật thể cụ thể.

Trả lời bốn câu hỏi cuối notebook:

1. Lớp nào recall thấp nhất? Ảnh nào minh họa? 
lớp "bus" recall thấp nhất, ảnh minh họa tên BoxR_curve.

2. Nếu mAP50 cao nhưng mAP50–95 thấp, cần kiểm điều gì trên box?
Kiểm tra annotations trên cvat xem box có quá ruộng hoặc quá hẹp, đồng thời kiểm tra box có bị lệch hoặc đang không theo guideline

3. Lỗi class nào có thể liên quan guideline? Dữ kiện nào hỗ trợ nhận xét?
Lỗi class mà có thể do hoặc liên quan đến guideline là gán nhãn không rõ ràng hoặc không nhất quán. Dữ kiện như Prediction và Ground Truth có thể dùng để nhận xét

4. Vì sao không dùng 10 ảnh eval để train? Vai trò validation của chúng trong notebook là gì?
Vì dùng 10 ảnh eval để train sẽ gây rò rỉ dữ liệu, làm mất tính khách quan khi đánh giá mô hình.

## 6. Khó khăn và cách xử lý

| Bước/thời điểm | Lỗi quan sát | Cách đã thử | Kết quả/còn thiếu |
|---|---|---|---|
| | | | |

## 7. Tự đánh giá theo rubric

Đối chiếu [RUBRIC.md](../../RUBRIC.md): phần nào đã có kết quả, phần nào còn thiếu hoặc chưa kiểm được. Không tự nhận hoàn thành bước chưa chạy.

## 8. Công cụ AI và tài liệu tham khảo

Ghi công cụ đã dùng, dùng ở bước nào và phần đã tự kiểm tra; không dùng thì ghi rõ. Liệt kê nguồn ngoài repo được sử dụng. Không ghi mật khẩu/token hoặc đính kèm gold train.