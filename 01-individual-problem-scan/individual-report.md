# 01 — Individual Problem Scan

> Điền theo Phase 1 + Phase 2 trong `01-worksheet.md`. Tự scan trước, dùng AI sau để phản biện. Không copy ví dụ Weekly Report.

## Thông tin cá nhân

- Họ và tên: Trần Long Khánh
- Mã học viên: 2A202602538
- Vai trò / bối cảnh (VD: sinh viên năm X, intern PM, ...): Sinh viên năm cuối
- Công việc hằng tuần (3-5 gạch đầu dòng để soi problem): AI enginer Intern 

---

## Phase 1 — Scan 5+ problems (tối thiểu 5, khuyến khích 8-10)

**Cách điền:** mỗi dòng = việc gì + ai chịu + đo bằng gì. Cột `Dấu hiệu thật` bắt buộc có số: mất bao lâu (bấm giờ mấy lần), mấy lần/tuần, bao nhiêu người gặp, log/ticket/quote nào.

| # | Lăng kính (Lặp lại / Tốn thời gian / AI có thể tốt hơn / Pain từ người khác) | Problem quan sát được | Ai chịu ảnh hưởng? | Dấu hiệu thật (số + bằng chứng) |
|---|---|---|---|---|
| 1 | Lặp lại / Tốn thời gian | Setup môi trường. Mỗi lần chuyển project đều phải check version, library,.. | AI enginer | Khi chuyển một dự án thì sẽ tạo một env khác nhau nhằm tránh xung đột, nhưng khi không kiểm soát kỹ trong env thì sẽ phải setting lại library, thậm chí phải xóa môi trường và setup lại env |
| 2 |Lặp lại / Tốn thời gian | Fix bug. Khi build một project, việc dính bug là điều hết sức bình thường, nhưng khi fix thường mất rất nhiều thời gian, nguyên nhân có thể do code, do phần cứng, do thư viện, ... | AI Enginer, Đồng nghiệp, Tôi | Khi thực hiện trên Jetson, cần phải tìm nguyên nhân vì sao DLA chạy chậm hơn GPU ?. Với các project bình thường phải tìm hiểu vì sao bug ? Do torch, hay code ??? |
| 3 | Tốn thời gian | Di chuyển nhiều. Có nhiều lúc khiến tôi phải di chuyển quá nhiều | Tôi, Đồng nghiệp | Một ngày có thể di chuyển 40-60km, thời gian di chuyển đến 2h |
| 4 | Tốn thời gian | Tôi thường dành khá nhiều thời gian trong buổi tối để chs game | Tôi | Tầm 2-4h mỗi ngày |
| 5 | AI có thể tốt hơn/ Tốn thời gian/Lặp lại | Build từ đầu một sản phẩm, nhưng phải ngồi kiểm soát AI, thiết kế kiến trúc cho AI làm, kiểm chứng code | Tôi, Đồng nghiệp | Các dự án mới, các Project mới |


> Gợi ý tự soi: tuần trước mất nhiều thời gian nhất vào việc gì? Việc gì hay trì hoãn? Người khác hay hỏi lại câu gì? Workflow nào ai cũng biết là chậm?

**AI đã dùng ở Phase 1 (nếu có):**
- Prompt đã hỏi:
- Ý dùng được:
- Ý bỏ vì không phải pain thật:

**Self-check Phase 1:**
- [ ] Đủ 5+ dòng, mỗi dòng có actor + số đo cụ thể
- [ ] Dùng ít nhất 3/4 lăng kính
- [ ] Không có dòng chung chung kiểu "mất nhiều thời gian"

---

## Phase 2 — Top 3 Problem Cards

### 2.1. Chọn top 3

Giữ bài nào: actor cụ thể, workflow vẽ được 3-7 bước, bottleneck ở 1 bước, impact đo được. Loại bài quá rộng.

| Rank | Problem (copy từ bảng scan) | Vì sao chọn (2-3 ý) | Điều còn chưa chắc |
|---|---|---|---|
| 1 |Setup môi trường. Mỗi lần chuyển project đều phải check version, library,.. | Workflow rất rõ: tạo env → cài dependency → kiểm tra CUDA/PyTorch/library → chạy project → phát hiện conflict → sửa/cài lại. Bottleneck nằm ở bước phát hiện dependency/version conflict. Có thể đo bằng thời gian setup, số lần lỗi, số lần phải recreate env. | Chưa có số liệu thật: trung bình setup một project mất bao lâu, bao nhiêu lần/tuần, bao nhiêu lần phải xóa env làm lại. |
| 2 | Fix bug. Khi build một project, việc dính bug là điều hết sức bình thường, nhưng khi fix thường mất rất nhiều thời gian, nguyên nhân có thể do code, phần cứng, thư viện,... | Pain xảy ra thường xuyên với AI Engineer. Workflow có thể vẽ: gặp lỗi → đọc log → xác định nhóm nguyên nhân → kiểm tra code/library/hardware → thử fix → rerun. Bottleneck rõ nhất là xác định root cause từ log và môi trường. Impact đo được bằng thời gian debug/lỗi và số lần thử trước khi fix được. | Hiện problem còn hơi rộng. Nên thu hẹp thành ví dụ: “Mất nhiều thời gian xác định root cause của lỗi khi deploy/train AI trên Jetson” thay vì toàn bộ mọi loại bug. |
| 3 | Build từ đầu một sản phẩm, nhưng phải ngồi kiểm soát AI, thiết kế kiến trúc cho AI làm, kiểm chứng code. | Đây là workflow thực tế khi dùng AI coding: mô tả yêu cầu → thiết kế kiến trúc → giao AI code → review → test → sửa prompt/code → tích hợp. Bottleneck có thể nằm ở review và kiểm chứng code AI sinh ra. Có khả năng đo bằng thời gian review, số vòng sửa, số bug của code do AI sinh ra. | Problem hiện quá rộng và chưa có bằng chứng số. Cần thu hẹp thành một bước cụ thể, ví dụ “Review và kiểm chứng code do AI sinh ra tốn nhiều thời gian”. |

### 2.2. Problem Cards chi tiết (lặp lại cho cả 3 cards)

---

#### Problem Card #1 — [Setup và quản lý môi trường cho project AI]

```text
Problem 1 câu:
Mỗi khi chuyển sang một project AI mới, tôi mất nhiều thời gian để tạo môi trường, kiểm tra version và xử lý xung đột giữa Python, CUDA, PyTorch và các thư viện.

Actor:
Tôi, AI Engineer, đồng nghiệp trong team AI.

Thời điểm / bối cảnh:
Khi bắt đầu project mới, clone project cũ sang máy khác, chuyển từ PC sang Jetson/server hoặc quay lại một project sau thời gian dài.

Current workflow 3-7 bước:
1. Clone project và đọc README/requirements.
2. Tạo Conda/venv mới.
3. Cài Python và các thư viện cần thiết.
4. Kiểm tra CUDA, PyTorch, driver và dependency.
5. Chạy thử project.
6. Nếu lỗi, tìm package/version xung đột.
7. Gỡ/cài lại package hoặc xóa env và tạo lại từ đầu.

Bottleneck:
Xác định chính xác package/version nào đang gây conflict và tìm được tổ hợp version tương thích.

Impact:
- Có thể mất từ vài chục phút đến vài giờ cho một lần setup lỗi.
- Khi phải tạo lại environment, toàn bộ thời gian cài đặt trước đó bị mất.
- Làm chậm việc bắt đầu coding/training/inference.
- Có thể ảnh hưởng cả đồng nghiệp nếu project không có environment reproducible.

Success metric:
- Giảm thời gian setup environment ít nhất 50%.
- Giảm số lần phải recreate environment.
- ≥ 80% dependency conflict được xác định đúng ngay trong lần phân tích đầu.
- Project có thể chạy được sau tối đa 1-2 vòng chỉnh dependency.

Non-AI alternative:
- Dùng Docker.
- Lock dependency bằng requirements.txt / environment.yml / poetry.lock.
- Viết script setup tự động.
- Chuẩn hóa base environment theo từng loại project.

AI hypothesis:
AI có thể đọc requirements, environment hiện tại, CUDA/Python/PyTorch version và error log để phát hiện conflict, đề xuất phiên bản tương thích và sinh command sửa environment.

Quick gut:

[ ] No AI / process fix
[ ] Rule
[x] Workflow
[ ] Agent
[ ] Chưa biết

Draft workflow Card #1

CURRENT STATE — khoảng 45-120 phút
(ước tính ban đầu, cần bấm giờ ít nhất 3 lần để xác nhận)

[1 Clone + đọc dependency: 10']
        ↓
[2 Tạo env + install: 15-30']
        ↓
[3 Chạy thử: 5']
        ↓
[4 Debug dependency/version: 20-60']  <-- BOTTLENECK
        ↓
[5 Reinstall / recreate env: 15-30']

FUTURE STATE — mục tiêu 20-40 phút

[1 Clone project + scan dependency: 5']
        ↓
[2 Tool tự collect Python/CUDA/GPU/package: 2']
        ↓
[3 AI phân tích compatibility + sinh fix plan: 3-5']
        ↓
[4 Human review command: 3']  <-- HUMAN BOUNDARY
        ↓
[5 Auto install + validation: 10-25']

Fallback:
Nếu AI đề xuất version sai thì không tự động thay đổi environment.
Hệ thống chỉ đưa command đề xuất + lý do + khả năng rollback.
Engineer review trước khi execute.

```
---

#### Problem Card #2 — [Xác định root cause khi project AI gặp lỗi]

```text
Khi project AI gặp lỗi, tôi mất nhiều thời gian để xác định lỗi đến từ code, library, CUDA/driver, phần cứng hay cấu hình hệ thống.

Actor:
Tôi, AI Engineer, đồng nghiệp phát triển/deploy AI.

Thời điểm / bối cảnh:
Trong lúc training, inference, convert model, TensorRT deployment hoặc chạy model trên Jetson/server.

Current workflow 3-7 bước:
1. Chạy chương trình và gặp lỗi.
2. Đọc traceback/log.
3. Search error trên Google/GitHub/Stack Overflow/documentation.
4. Đặt giả thuyết: code, library, driver, CUDA, hardware...
5. Chạy các command kiểm tra từng giả thuyết.
6. Thay config/package/code rồi chạy lại.
7. Lặp lại đến khi tìm được root cause.

Bottleneck:
Phân loại đúng root cause ngay từ đầu và biết cần kiểm tra thông tin nào tiếp theo.

Impact:
- Một lỗi khó có thể mất từ hàng chục phút đến nhiều giờ.
- Có nhiều vòng thử-sai không tạo ra thông tin mới.
- Engineer phải đọc log dài và tìm kiếm ở nhiều nguồn khác nhau.
- Ví dụ thực tế: cần tìm nguyên nhân vì sao workload trên Jetson/DLA chậm hơn GPU hoặc không thực sự chạy trên DLA.

Success metric:
- Giảm thời gian xác định root cause ≥ 40%.
- Giảm số vòng thử-sai trước khi xác định đúng nguyên nhân.
- Top-3 nguyên nhân AI đề xuất chứa root cause thật ≥ 80% trường hợp.
- Mỗi recommendation phải đi kèm command kiểm chứng.

Non-AI alternative:
- Tạo troubleshooting checklist.
- Chuẩn hóa logging.
- Viết script collect system information.
- Xây internal wiki chứa các lỗi đã gặp.

AI hypothesis:
AI có thể kết hợp traceback, log, hardware info, version library và lịch sử lỗi để phân loại nguyên nhân, xếp hạng hypothesis và đề xuất command kiểm chứng theo thứ tự.

Quick gut:

[ ] No AI / process fix
[ ] Rule
[ ] Workflow
[x] Agent
[ ] Chưa biết

Draft workflow Card #2

CURRENT STATE — khoảng 30-180+ phút
(cần log thời gian của ít nhất 3-5 bug để xác nhận)

[1 Gặp error: 1']
        ↓
[2 Đọc log: 10-20']
        ↓
[3 Search web/docs: 15-40']
        ↓
[4 Đặt hypothesis + thử fix: 20-90+']  <-- BOTTLENECK
        ↓
[5 Rerun]
        ↺ nếu lỗi tiếp tục thì quay lại bước 2-4

FUTURE STATE — mục tiêu 15-60 phút

[1 Error + log]
        ↓
[2 Auto collect system/package/hardware info: 1-2']
        ↓
[3 AI tạo ranked root-cause hypotheses: 2-5']
        ↓
[4 AI đưa diagnostic commands]
        ↓
[5 Human review + chạy command: 5-15']  <-- HUMAN BOUNDARY
        ↓
[6 AI cập nhật hypothesis → đề xuất fix]

Fallback:
Nếu confidence thấp hoặc nguyên nhân liên quan hardware/driver nguy hiểm,
AI chỉ đưa checklist kiểm tra và không tự động thay đổi hệ thống.
Engineer quyết định thao tác cuối cùng.
```

---

#### Problem Card #3 — [Review và kiểm chứng code do AI sinh ra]

```text
Problem 1 câu:
Khi dùng AI để build project mới, tôi vẫn mất nhiều thời gian thiết kế kiến trúc, kiểm tra code AI sinh ra, chạy test và sửa các lỗi hoặc assumption sai.

Actor:
Tôi, AI Engineer, developer dùng AI coding assistant.

Thời điểm / bối cảnh:
Khi bắt đầu project mới hoặc giao một feature tương đối lớn cho AI coding assistant.

Current workflow 3-7 bước:
1. Xác định yêu cầu của feature/project.
2. Thiết kế kiến trúc và chia task.
3. Prompt AI tạo code.
4. Đọc và review code AI sinh ra.
5. Chạy test/build/inference.
6. Phát hiện bug hoặc thiết kế sai.
7. Sửa prompt/code và lặp lại.

Bottleneck:
Review và xác minh code AI sinh ra có thực sự đúng với requirement, architecture và environment thực tế hay không.

Impact:
- Phải dành nhiều thời gian giám sát thay vì chỉ giao task cho AI.
- Code có thể chạy được nhưng logic sai hoặc không phù hợp architecture.
- Với AI/ML project, lỗi còn có thể liên quan tensor shape, device, library version, dataset hoặc GPU.
- Một feature lớn có thể cần nhiều vòng prompt → code → test → fix.

Success metric:
- Giảm ≥ 40% thời gian review code AI.
- Giảm số vòng prompt-sửa trước khi feature pass test.
- ≥ 90% code thay đổi phải có test hoặc validation tương ứng.
- Không merge code khi critical test chưa pass.

Non-AI alternative:
- Coding guideline rõ ràng.
- CI/CD.
- Unit test/integration test.
- Static analysis/linter/type checking.
- Chia task nhỏ trước khi giao AI.

AI hypothesis:
Một AI reviewer độc lập có thể đọc requirement + architecture + git diff, sinh test, kiểm tra assumption và đánh dấu đoạn code có rủi ro trước khi con người review.

Quick gut:

[ ] No AI / process fix
[ ] Rule
[x] Workflow
[ ] Agent
[ ] Chưa biết

Draft workflow Card #3

CURRENT STATE — khoảng 60-180+ phút / feature
(cần đo thực tế trên 3 feature)

[1 Viết requirement: 10-20']
        ↓
[2 Thiết kế architecture/task: 15-30']
        ↓
[3 AI generate code: 5-15']
        ↓
[4 Review + test + tìm assumption sai: 30-90+']  <-- BOTTLENECK
        ↓
[5 Prompt/fix lại]
        ↺ có thể lặp nhiều vòng

FUTURE STATE — mục tiêu 30-90 phút

[1 Requirement + acceptance criteria: 10']
        ↓
[2 AI coding]
        ↓
[3 AI reviewer sinh test + inspect diff: 5-15']
        ↓
[4 CI chạy validation]
        ↓
[5 Human review phần flagged/high-risk: 15-30']  <-- HUMAN BOUNDARY

Fallback:
Nếu AI reviewer và coding agent cùng cho kết quả sai,
CI/test vẫn là gate bắt buộc.
Không tự động merge khi test fail hoặc confidence thấp.

---
```

### 2.3. Card muốn pitch nhất (chuẩn bị 2 phút)

**Card tôi muốn pitch nhất:**

```
Problem Card #3: Review và kiểm chứng code do AI sinh ra

```

**Vì sao (2-3 câu: workflow gì, số đo gì, impact gì):**

```
Workflow rất rõ. Khi mà build một model từ đầu, điều cần thiết nhất là phải tạo một prompt để có một baseline tốt nhất. Vậy trong prompt sẽ có gì ? Nó sẽ chứa thông tin kiến trúc model của mình, những thứ mà mình đã nghiên cứu,...

```

**Câu hỏi tôi muốn nhóm challenge (1-2 câu hỏi đúng chỗ yếu):**

``` -Kiến trúc tôi thiết kế đã thực sự đúng chưa? Hiệu quả không ?
    -Model được build có chạy ổn không ? Có vấn đề gì tiềm ẩn không ?
```

**AI phản biện Card (nếu có):**
- Điểm yếu AI chỉ ra: Việc build từ đầu quá nhiều rủi ro, nếu mình không kiểm soát kỹ thì khả năng fail là khá cao.
- Tôi sửa gì: Khi AI chạy xong từng lệnh thì tôi sẽ có nhiệm vụ check code, check thuật toán trước khi để AI chạy lệnh tiếp theo

### Self-check nộp phần 01
- [ ] Có 5+ problems + top 3 Cards đủ field
- [ ] Mỗi Card có workflow trước/sau + bottleneck + metric + fallback
- [ ] Đã chọn 1 card pitch + câu hỏi challenge
