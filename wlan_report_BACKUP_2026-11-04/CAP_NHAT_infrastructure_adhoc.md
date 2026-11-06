# Cập nhật nội dung mô hình Infrastructure / Ad-hoc – 31/10/2026

Đợt cập nhật này đối chiếu báo cáo `wlan_report` với hai nguồn trong
`My Drive > Networking`:

- `Mô hình infrastructure.docx` (bản giải thích mô hình Infrastructure và Ad-hoc
  kèm quy trình demo IBSS trên Linux của nhóm).
- `picture source` (6 ảnh chụp: `Picture1.png` … `Picture6.png`).

## 1. Kết quả đối chiếu tài liệu với báo cáo (trước khi sửa)

| Nội dung trong tài liệu nguồn | Trạng thái trong báo cáo cũ | Xử lý |
|---|---|---|
| Phân cấp Infrastructure, 3 nhóm thành phần (AP/router, client, hạ tầng dây) | Chỉ có ở mức khái niệm | Viết lại đầy đủ trong mục mới 3.3.1 |
| BSS/BSSID, ESS, roaming, SSID dùng chung | Đã có nhưng rời rạc | Bổ sung nguồn BSSID, roaming, giới hạn của ESS truyền thống |
| IBSS: không AP, BSSID ảo ngẫu nhiên, beacon luân phiên, tính cô lập | Chưa có | Bổ sung toàn bộ (3.3.2) |
| Ad-hoc chỉ ổn định trên 802.11b/g/n 2.4 GHz; chỉ WEP hoặc mạng mở | Chưa nêu | Bổ sung + nối với phần bảo mật |
| MANET/VANET/FANET là tiến hóa của Ad-hoc; Wi-Fi Direct thay thế IBSS | Đã có MANET/Wi-Fi Direct, thiếu VANET/FANET | Bổ sung |
| Windows 10/11, Android, macOS không hỗ trợ Ad-hoc; chỉ Linux hỗ trợ | Báo cáo cũ chỉ nói chung "nếu nền tảng không hỗ trợ" | Khẳng định lại + gắn minh chứng ảnh 1 |
| Quy trình demo IBSS (mac80211_hwsim, network namespace, `iw ... ibss join`) | Mục 6.3 chỉ là hướng dẫn chung, không có lệnh | Thay bằng quy trình 6 bước cụ thể |
| Kết quả đo (ping 4/4, RTT, station dump) | Phần 7 để trống | Điền bảng kết quả + 6 hình minh chứng |

## 2. Các tệp đã thay đổi

- `sections/03b_infrastructure_adhoc.tex` (**mới**): mục 3.3 gồm mô hình hạ tầng,
  mô hình Ad-hoc/IBSS và **bảng đối chiếu chi tiết 12 tiêu chí**
  (`tab:infra-adhoc-detail`), bổ trợ cho bảng tổng quát `tab:infra-vs-adhoc` đã có.
- `sections/06_configuration_guide.tex`: mục "Thiết lập và kiểm chứng mạng Ad-hoc
  (IBSS) trên nền Linux" được viết lại thành 6 bước có lệnh cụ thể; bảng ghi cấu
  hình thực tế đã điền dòng Ad-hoc.
- `sections/07_evidence_results.tex`: chèn 6 ảnh minh chứng (Hình `fig:win-hosted`,
  `fig:hwsim-radios`, `fig:netns`, `fig:adhoc-config`, `fig:adhoc-check`,
  `fig:adhoc-ping`), thêm bảng môi trường `tab:adhoc-env` và bảng kết quả
  `tab:adhoc-results`, viết phần thảo luận/hạn chế. Hai ô ảnh Router/AP và kết nối
  thiết bị **vẫn để trống** vì nhóm chưa cung cấp ảnh.
- `preamble.tex`: thêm `\usepackage{graphicx}` và `\graphicspath{{figures/}}`
  (trước đây gói này chưa được nạp nên không thể chèn ảnh); bỏ dòng `longtable`
  bị lặp.
- `main.tex`: thêm `\input{sections/03b_infrastructure_adhoc}` ngay sau
  `sections/03_architecture`.
- `figures/` (**mới**): bản sao 6 ảnh từ `Networking > picture source` để
  `\includegraphics{figures/PictureN.png}` biên dịch được.

Lưu ý thứ tự ảnh: tài liệu .docx đánh số "Hình 1" cho ảnh `iw dev`, nhưng bộ
`picture source` có thêm `Picture1.png` là ảnh kiểm tra `netsh` trên Windows.
Vì vậy trong báo cáo: Picture1 = kiểm tra Windows, Picture2 = `iw dev`,
Picture3 = namespace, Picture4 = lệnh cấu hình, Picture5 = `iw info` +
`station dump`, Picture6 = ping.

## 3. Việc còn lại (chưa làm, cần nhóm quyết định)

- **Chưa biên dịch PDF** theo yêu cầu trước đó của nhóm; các kiểm tra tĩnh đã chạy:
  cân bằng ngoặc, khớp `\begin`/`\end`, và mọi `\ref` đều có `\label` tương ứng.
  `main.pdf` trong thư mục vẫn là bản cũ, không phản ánh nội dung mới.
- Cần chép thư mục `figures/` vào bản làm việc git cục bộ (Drive chỉ giữ bản sao).
- Còn thiếu ảnh minh chứng cấu hình Router/AP và ảnh kết nối Laptop/Desktop/
  Smartphone; kết quả đo thông lượng thật và video demo vẫn chờ nhóm.
- Các khẳng định "Android và macOS không hỗ trợ Ad-hoc" lấy theo tài liệu nhóm;
  báo cáo mới chỉ kiểm chứng trực tiếp trên Windows 11 (Picture1) và Linux.
