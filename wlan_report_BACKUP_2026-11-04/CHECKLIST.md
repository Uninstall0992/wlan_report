# Checklist báo cáo WLAN – Nhóm 9

Đánh giá theo mã nguồn hiện tại ngày 30/10/2026, cập nhật ngày **31/10/2026** sau
khi đối chiếu với `Networking/Mô hình infrastructure.docx` và bộ ảnh
`Networking/picture source`. “Đạt” nghĩa là nội dung đã có; “Chờ” nghĩa là cần
dữ liệu, cấu hình hoặc xác nhận thực tế, không được tính là hoàn tất.

## Cấu trúc báo cáo (13 mục)

| # | Yêu cầu | Trạng thái |
|---|---|---|
| 1 | Trang bìa và thông tin nhóm | Đạt khung; sáu trường MSSV/tên còn trống |
| 2 | Mục lục | Đạt |
| 3 | Giới thiệu và mục tiêu bài tập | Có phần tổng quan; cần rà soát mục tiêu cụ thể theo đề |
| 4 | Khái niệm WLAN | Đạt |
| 5 | Thành phần và kiến trúc WLAN | Đạt |
| 6 | Mô hình Infrastructure và Ad-hoc | **Đạt (31/10)**: bổ sung mục 3.3 và bảng đối chiếu chi tiết 12 tiêu chí (`tab:infra-adhoc-detail`) |
| 7 | Giải pháp kết nối Laptop, Desktop, Smartphone | Đạt phần hướng dẫn lý thuyết |
| 8 | Hướng dẫn cấu hình router và thiết bị | Có quy trình khái quát + quy trình IBSS 6 bước có lệnh cụ thể; **vẫn phải đối chiếu model/router thực tế** |
| 9 | Hình ảnh minh chứng bắt buộc | **Đạt phần Ad-hoc (6 ảnh)**: `fig:win-hosted`, `fig:hwsim-radios`, `fig:netns`, `fig:adhoc-config`, `fig:adhoc-check`, `fig:adhoc-ping`; còn chờ ảnh Router/AP và ảnh kết nối thiết bị vật lý |
| 10 | Kết quả thử nghiệm và thảo luận | **Đạt phần Ad-hoc**: bảng `tab:adhoc-env`, `tab:adhoc-results`, mục hạn chế; phần Router/AP và thiết bị vật lý còn trống |
| 11 | Kết luận | Có kết luận lý thuyết; cập nhật sau khi xong phần hạ tầng |
| 12 | Tài liệu tham khảo | Đạt khung BibTeX; cần kiểm tra PDF build để xác nhận trích dẫn |
| 13 | Bảng tỷ lệ đóng góp và minh chứng chữ ký | Có bảng; chờ tỷ lệ và chữ ký thật |

**Tiến độ cấu trúc:** 13/13 mục đã có mặt (100%). Sau cập nhật 31/10, các mục 6,
9 và một phần 10 đã có nội dung thực chất; các hạng mục còn thiếu dữ liệu thực tế
là 1, 8, 10 (phần Router/AP – thiết bị vật lý), 11, 12 (xác nhận build) và 13.

## Checklist nghiệm thu trong `KeHoach/phancong.pdf` (14 mục)

| # | Tiêu chí | Trạng thái |
|---|---|---|
| 1 | Có phần khái niệm | Đạt |
| 2 | Có phần thành phần | Đạt |
| 3 | Trình bày Infrastructure và Ad-hoc | **Đạt**: lý thuyết + đối chiếu chi tiết + minh chứng IBSS thực nghiệm |
| 4 | Hướng dẫn kết nối Laptop, Desktop, Smartphone | Đạt hướng dẫn; kết quả thực tế chờ |
| 5 | Ghi thông tin cần thiết trước cấu hình router/thiết bị | Có bảng mẫu; chờ điền |
| 6 | Cấu hình SSID theo tên nhóm | Chờ cấu hình và xác nhận SSID |
| 7 | Cấu hình tất cả chức năng router hỗ trợ | Chờ model và thực nghiệm |
| 8 | Có ảnh minh chứng cấu hình trong báo cáo | Chờ ảnh Router/AP thật (phần Ad-hoc đã có) |
| 9 | Có kết quả kiểm tra kết nối các thiết bị | Chờ kết quả thật |
| 10 | Ad-hoc có ít nhất 2 node ping được nhau | **Đạt (31/10)**: ping 4/4 gói, mất gói 0%, RTT 0,048–0,271 ms trên IBSS `demoAdhoc`, kênh 6 |
| 11 | Video có thuyết minh và thể hiện người cấu hình | Chờ video |
| 12 | Kiểm tra ngày cập nhật video trước hạn nộp | Chờ video; hạn nộp theo PDF là 09/11/2026 |
| 13 | Có tỷ lệ đóng góp và minh chứng chữ ký | Có biểu mẫu; chờ tỷ lệ/chữ ký |
| 14 | Kiểm tra tên và định dạng file bàn giao | Chờ xuất bản bản nộp cuối |

**Nghiệm thu đã đạt:** 4/14 = 29% (khái niệm, thành phần, mô hình Infrastructure
– Ad-hoc, demo Ad-hoc hai node ping). So với 14% ngày 30/10, tiêu chí 3 và 10 đã
chuyển từ “chờ” sang “đạt”. 10 tiêu chí còn lại cần dữ liệu/đầu ra nhóm.

## Ghi chú

- `phancong.pdf` nêu 5 thành viên; yêu cầu báo cáo hiện tại là để trống 6 thành
  viên. Mẫu bìa theo yêu cầu mới có 6 dòng; cần xác nhận số thành viên chính thức
  trước khi chốt.
- Đã thêm `figures/` (bản sao 6 ảnh từ `Networking/picture source`) và
  `\usepackage{graphicx}` trong `preamble.tex`; khi làm việc cục bộ phải chép cả
  thư mục `figures/` vào cùng cấp `main.tex`.
- Không sinh lại `main.pdf`. Đã kiểm tra tĩnh: cân bằng ngoặc, khớp
  `\begin`/`\end`, và mọi `\ref` có `\label` tương ứng; chưa kiểm tra trực quan
  khổ giấy hay ngắt trang bằng bản PDF mới.
- Không sử dụng số liệu giả định: mọi con số trong phần thực nghiệm đều lấy từ
  ảnh chụp của nhóm (ping, `station dump`, `iw dev info`).
