## ***01 - Individual Problem Scan***

|#	|Lăng kính	|Problem quan sát được	|Ai đang đau?	|Dấu hiệu thật|
|---|---|---|---|---|
|1   |Pain từ người khác   |PM tự commit deadline với stakeholder trước khi align với engineering  |Team member    |Deadline trượt liên tục, dev overtime cuối sprint, scope bị cắt phút chót, estimate bị inflate|
|2   |Pain từ người khác   |BA khai thác requirement không đủ rõ khiến dev implement sai chức năng  |Dev    |Dev phải rework nhiều, ticket reopen liên tục, QA fail do “không đúng ý khách”, acceptance criteria mơ hồ|
|3   |Pain từ người khác   |Dev lead tổ chức OT nhưng không có kế hoạch và tracking thời gian rõ ràng  |Team member    |OT kéo dài nhiều sprint, dev không biết OT bao lâu, burnout tăng, productivity giảm sau OT|
|4   |Tốn thời gian   |Phải cài đặt môi trường, các tool trước đây ít hoặc chưa sử dụng mà không có hướng dẫn cụ thể  |Học viên    |Mất nhiều giờ setup, lỗi môi trường khác nhau giữa máy|
|5   |Tốn thời gian   |Học viên di chuyển đến địa điểm học ở xa  |Học viên    |3 tiếng/ngày để đi và về |
|6   |Lặp lại   |Tổng hợp lại nhiều kiến thức mới phải tiếp thu mỗi ngày |Học viên    | 30 phút/ngày|
|7   |Sức khỏe   |Khó duy trì ổn định nhịp sinh hoạt khi chương trình học khá nặng  |Học viên    |Ngủ thất thường, ăn uống không đúng bữa|
|8   |Quản lý thông tin   |Phải theo dõi nhiều kênh thông tin khác nhau để không bỏ sót chương trình học  |Học viên    |Bỏ lỡ deadline, quên lịch học, phải tham gia nhiều nhóm theo nội dung chương trình|

## ***Top 3***

| Rank | Problem | Vì sao chọn | Điều còn chưa chắc |
|---|---|---|---|
| 1 | PM commit deadline | Ảnh hưởng lớn đến văn hóa/hiệu suất team, có workflow rõ | Có thay đổi được tư duy của PM không? |
| 2 | BA lấy req không rõ | Có thể dùng AI để check checklist/test case | Khó đo lường độ rõ |
| 3 | Quản lý thông tin | Nhiều người đau, AI có thể giúp tổng hợp | Scope có quá rộng không? |

## ***Problem Card #1 — PM commit deadline (Process alignment)***
### ***Problem 1 câu:***
PM thường xuyên tự commit deadline với stakeholder mà không qua bước align với Engineering, dẫn đến trễ tiến độ và team phải OT.

### ***Actor:***
Engineering team và Junior PM.

### ***Thời điểm / bối cảnh:***
Giai đoạn Planning đầu sprint hoặc khi nhận yêu cầu mới từ stakeholder.

### ***Current workflow:***
```
┌─────────────────┐      ┌──────────────┐        ┌────────────┐
│ 1 Stakeholder   │      │ 2 PM tính    │        │ 3 PM thông │
│   đưa yêu cầu   │  →   │ toán/commit  │  →     │ báo team   │
└─────────────────┘      └──────────────┘        └────────────┘
                                                        ↓
┌─────────────────┐      ┌──────────────┐       ┌───────────────┐
│ 6 Kết quả trễ   │ ←    │ 5 Team OT    │   ←   │ 4 Dev nhận    │
│ hoặc cắt scope  │      │ chạy đua     │       │ task/nhận ra  │
└─────────────────┘      └──────────────┘       └───────────────┘

```

### ***Bottleneck:***
Bước 2 — PM commit thiếu dữ liệu từ Engineering.

### ***Impact:***
Burnout cho team, giảm uy tín của team, sản phẩm kém chất lượng.

### ***Success metric:***
Tỉ lệ đạt deadline (On-time delivery) tăng từ 60% lên 90%; thời gian OT giảm.

### ***Non-AI alternative:***
Thiết lập quy trình "Engineering Sign-off" bắt buộc trước khi commit deadline.

### ***AI hypothesis:***
AI phân tích độ khó của task dựa trên lịch sử sprint và gợi ý thời gian thực tế cho PM trước khi commit.

### ***Quick gut:***
Workflow.

### ***Future workflow***
```
┌─────────────────┐      ┌──────────────────┐      ┌───────────────┐
│ 1 PM tiếp nhận  │      │ 2 AI phân tích   │      │ 3 AI gợi ý    │
│    yêu cầu      │  →   │ lịch sử (Jira)   │  →   │  estimate     │
└─────────────────┘      └──────────────────┘      └───────────────┘
                                                            
                                                            ↓
┌─────────────────┐      ┌──────────────────┐      ┌───────────────┐
│ 5 Commit chính  │ ←    │ 4 PM align với   │  ←   │ (Human Bound) │
│ xác/minh bạch   │      │  Eng dựa trên số │      │ PM review/đối │
└─────────────────┘      │  liệu của AI     │      │ soát kết quả  │
                         └──────────────────┘      └───────────────┘

```

## ***Problem Card #2 — BA lấy req không rõ***
### ***Problem 1 câu:***
Yêu cầu từ BA không đủ chi tiết khiến dev implement sai, gây lãng phí nguồn lực để rework.

### ***Actor:***
BA, Dev, QA.

### ***Bottleneck:***
Bước review tài liệu/ticket trước khi dev bắt đầu.

### ***Impact:***
Tốn 15-20% thời gian cho rework, tinh thần team đi xuống.

### ***AI hypothesis:***
AI đóng vai trò Devil's Advocate hoặc Checklist Reviewer, tự động quét ticket/tài liệu để tìm các lỗ hổng (missing edge cases, ambiguous language).

## ***Problem Card #3 — Quản lý thông tin ***
### ***Problem 1 câu:***
Học viên mất quá nhiều thời gian theo dõi nhiều kênh thông tin rời rạc (Slack, Email, LMS) dẫn đến bỏ lỡ thông báo quan trọng.

### ***Actor:***
Học viên.

### ***Bottleneck:***
Việc phải liên tục kiểm tra (manual check) các kênh để tìm thông báo mới.

### ***Impact:***
Mất 30 phút/ngày, rủi ro cao về trễ deadline học tập.

### ***AI hypothesis:***
Một AI Agent tổng hợp từ các nguồn (Slack, Email, LMS) vào cuối ngày hoặc khi có thông tin quan trọng, tóm tắt thành "To-do list" cho học viên.