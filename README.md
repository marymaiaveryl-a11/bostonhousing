# ABOUT THIS REPO: bostonhousing
**Boston Housing Price Regression Analysis (Nov 2025 Solo project — Econometrics coursework)**

Engineered features, compared 5 regression models via stepwise selection (R2 = 0.80), and validated reliability with full diagnostic
testing (VIF, Breusch–Pagan, White, Durbin–Watson, Ramsey RESET) — delivering structured, actionable findings using Stata MP.

# Link access to database:
https://gist.github.com/nnbphuong/def91b5553736764e8e08f6255390f37

**Nguồn:** Bộ dữ liệu Boston Housing (phiên bản đã loại biến về sắc tộc Black) từ tác giả Harrison & Rubinfeld (1978).
Kích thước: 506 quan sát, 14 biến ban đầu, không có giá trị khuyết.

# Mục tiêu và câu hỏi nghiên cứu
Xây dựng và so sánh nhiều mô hình hồi quy (tuyến tính, bán log, log–log, mô hình tương tác) để chọn ra mô hình phù hợp nhất.

Đo lường mức độ và chiều tác động của các nhóm yếu tố: xã hội (tội phạm, LSTAT), kinh tế (thuế, PTRATIO), môi
trường – vị trí (NOX, CHAS, RAD, DIS, RM) lên giá nhà MEDV.

Đánh giá độ phù hợp của mô hình qua R², AIC, BIC, các kiểm định chẩn đoán và đề xuất hàm ý thực tiễn.

# Giới thiệu
Dự án này phân tích các yếu tố ảnh hưởng đến giá trị bất động sản tại khu vực Boston dựa trên bộ dữ liệu kinh điển Boston Housing. Mục tiêu là xây dựng mô hình kinh tế lượng dự báo giá nhà và rút ra hàm ý chính sách cho quy hoạch đô thị và quản lý thị trường bất động sản.

# Dữ liệu
Kích thước: 506 quan sát, 14 biến ban đầu, không có giá trị khuyết.

Biến phụ thuộc: MEDV – giá trị trung vị của nhà ở do chủ sở hữu (nghìn USD).

Các biến độc lập chính: CRIM, ZN, INDUS, CHAS, NOX, RM, AGE, DIS, RAD, TAX, PTRATIO, LSTAT, cùng các biến xử lý như CHAS_DUMMY, RAD_HIGH, AGE_CAT, L_* và RM_LSTAT.

# Phương pháp
**Tiền xử lý:**
Tạo biến giả cho CHAS, RAD, AGE_CAT (3 nhóm tuổi khu dân cư).

Biến đổi logarit cho các biến định lượng, tạo biến tương tác RM × LSTAT.

**Mô hình:**
Ước lượng 5 dạng mô hình: OLS cơ bản, OLS robust, bán log, log–log, mô hình có biến tương tác.

So sánh R², AIC, BIC để chọn mô hình tương tác làm nền, sau đó tinh chỉnh bằng Stepwise (Backward) ở mức ý nghĩa 5%.

**Kiểm định:**
Đa cộng tuyến (VIF), phương sai thay đổi (Breusch–Pagan, White), tự tương quan (Durbin–Watson), phân phối chuẩn phần dư (Shapiro–Wilk, Histogram, Q–Q) và chỉ định mô hình (Ramsey RESET).

**Mô hình cuối cùng (Final Model)**
Mô hình tối ưu gồm 11 biến độc lập: CRIM, ZN, CHAS_DUMMY, NOX, RM, DIS, RAD, TAX, PTRATIO, LSTAT, RM_LSTAT.
