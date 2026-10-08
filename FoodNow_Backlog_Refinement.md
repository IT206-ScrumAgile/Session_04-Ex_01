
## Bước 1. Tìm lỗi (INVEST)

| Mã | Kết quả và lý do |
|----|------------------|
| US1 | **Đạt:** vai trò rõ, một việc, có lợi ích, thử được bằng cách chọn loại món rồi xem kết quả. |
| US2 | **Sai T (Testable):** "đẹp và dễ dùng" là cảm nhận chủ quan, không có tiêu chí đo được nên không biết khi nào là xong (kéo theo khó ước lượng E). |
| US3 | **Sai V (Valuable):** vai trò là lập trình viên và lợi ích "code dễ bảo trì" chỉ phục vụ nhóm kỹ thuật, không mang giá trị trực tiếp cho khách hàng/người dùng; ngoài ra còn vi phạm N (Negotiable) vì áp đặt sẵn giải pháp "React". Đây là việc kỹ thuật (technical task), nên ghi như task kỹ thuật hoặc gắn vào story có giá trị cho người dùng, không viết thành User Story. |
| US4 | **Sai S (Small):** gộp quá nhiều việc (3 mức thời gian, 2 chiều lọc, xuất Excel, gửi email tự động) nên không vừa 1 Sprint và không ước lượng được (kéo theo E). |

---

## Bước 2. Sửa lỗi

### a) Viết lại US2 với tiêu chí "dễ dùng" đo được

**US2 (viết lại):** Là một khách hàng, tôi muốn đặt xong một đơn món chỉ với tối đa 3 bước từ lúc chọn món đến lúc xác nhận, để đặt món nhanh mà không cần ai hướng dẫn.

**Tiêu chí chấp nhận (đo được):**
- Từ màn hình danh sách món đến màn hình xác nhận đơn có **không quá 3 bước/màn hình**.
- Thử nghiệm với 5 người dùng lần đầu: **ít nhất 4/5 người** đặt xong 1 đơn trong **≤ 2 phút** mà không cần trợ giúp.

### b) Tách US4 thành 2 story nhỏ và đặt vào cây Epic → Feature → Story

```
Epic: Báo cáo & theo dõi kinh doanh
└── Feature: Báo cáo doanh thu cho admin
    ├── US4a: Là một admin, tôi muốn xem báo cáo doanh thu theo ngày, tuần, tháng
    │         trên màn hình, để theo dõi kết quả kinh doanh.
    └── US4b: Là một admin, tôi muốn xuất báo cáo doanh thu đang xem ra file Excel,
              để lưu trữ và gửi cho ban giám đốc.
```

Phần còn lại của US4 (lọc theo khu vực, theo nhà hàng, tự động gửi email cho ban giám đốc) **không bỏ**, được ghi thành các story riêng cùng Feature này, xếp ở cuối backlog và chỉ làm rõ khi gần tới lượt.

---

## Bước 3. Xếp lại backlog

### a) Thứ tự ưu tiên

| Thứ tự | Story | Lý do |
|--------|-------|-------|
| 1 | US2 (đã sửa) – đặt món tối đa 3 bước | Luồng đặt món là cốt lõi của FoodNow, tạo ra đơn hàng và doanh thu, giá trị khách hàng cao nhất. |
| 2 | US1 – lọc nhà hàng theo loại món | Giúp khách tìm món nhanh, hỗ trợ trực tiếp việc đặt món; nhỏ, rõ, ít rủi ro. |
| 3 | US4a – xem doanh thu ngày/tuần/tháng | Phục vụ admin, cần có dữ liệu đơn hàng từ luồng đặt món trước; ít gấp hơn các story khách hàng. |
| 4 | US4b – xuất báo cáo ra Excel | Phụ thuộc US4a (phải có báo cáo mới xuất được) nên đứng sau. |

### b) Theo DEEP, story đứng đầu (US2)

**Mức chi tiết:** story đầu backlog phải **chi tiết nhất** (Detailed appropriately): đủ rõ để nhóm làm ngay, gồm mô tả rõ ràng, tiêu chí chấp nhận đo được, đạt INVEST, đã được **ước lượng**, và nhỏ vừa trong 1 Sprint. Các story càng xuống dưới càng thô (US4b chỉ cần mô tả ngắn).

**Buổi Refinement còn phải làm với nó trước khi đưa vào Sprint:**
1. Cùng PO và nhóm phát triển hỏi đáp để làm rõ phạm vi, mockup/luồng màn hình, trường hợp đặc biệt (giỏ trống, hết món, thanh toán lỗi).
2. Chốt/hoàn thiện tiêu chí chấp nhận và cách kiểm thử.
3. Cả nhóm **ước lượng** (ví dụ Planning Poker, story points); nếu quá lớn thì tách tiếp.
4. Xác định phụ thuộc, rủi ro và kiểm tra đạt **Definition of Ready**.
5. PO xếp lại thứ tự nếu cần; sau đó story mới sẵn sàng để chọn vào Sprint Planning.
