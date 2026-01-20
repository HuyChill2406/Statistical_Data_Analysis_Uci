# Statistical_Data_Analysis_Uci

# Statistical Data Analysis (EDA + Hypothesis Testing) – Heart Disease & Wine Quality (UCI)

Repo này chứa **2 notebook** thực hiện phân tích thống kê mô tả, trực quan hóa, phân tích phân phối xác suất, **kiểm định giả thuyết** và **phân tích tương quan** trên 2 bộ dữ liệu nổi tiếng từ UCI.

---

## Notebooks

### 1) `HeartDisease_522H0131.ipynb`
- **Dataset:** UCI Heart Disease (gộp 4 tập: Cleveland, Hungarian, Switzerland, VA)
- **Kích thước sau khi gộp:** **920 dòng × 14 cột**
- **Mục tiêu phân tích:** khám phá dữ liệu bệnh tim, xử lý thiếu/outlier, phân phối biến, kiểm định thống kê và tương quan giữa các biến y học.

### 2) `WineQuality_522H0131.ipynb`
- **Dataset:** UCI Wine Quality (2 file: `winequality-red.csv`, `winequality-white.csv`)
- **Xử lý gộp:** thêm cột **`type`** để phân biệt **red/white**
- **Kích thước sau khi gộp:** **6497 dòng × 13 cột**
- **Mục tiêu phân tích:** so sánh đặc trưng hoá học giữa 2 loại rượu, phân tích phân phối, kiểm định giả thuyết và tương quan.

---

## Datasets (UCI)

- Heart Disease: UCI ML Repository – Heart Disease  
- Wine Quality: UCI Dataset – Wine Quality

> Gợi ý: Có thể chạy trên Google Colab bằng cách upload các file CSV/DATA vào `/content/` (đúng theo đường dẫn trong notebook).

---

## Nội dung chính (cả 2 notebook đều theo flow thống nhất)

### 1) Chuẩn bị dữ liệu
- Import thư viện (Pandas/Numpy/Matplotlib/Seaborn/SciPy…)
- Đọc dữ liệu, gộp dataset (Heart: 4 file; Wine: red + white + `type`)
- Chuẩn hóa kiểu dữ liệu và kiểm tra dữ liệu thiếu/trùng lặp

### 2) EDA – Exploratory Data Analysis
- Thống kê mô tả (mean, std, min/max, quartiles…)
- Kiểm tra missing values (heatmap)
- Trực quan hóa:
  - Histogram/Distribution
  - Boxplot (phát hiện outliers)
  - Countplot (biến phân loại)
  - Pairplot / Scatter plot / Heatmap (tùy notebook)

### 3) Phân tích phân phối xác suất
- Đánh giá hình dạng phân phối (skewness, z-score/outlier…)
- Kiểm định chuẩn hoá/độ phù hợp phân phối (ví dụ: Shapiro, KS, Anderson…)
- Nhận xét phân phối theo từng biến quan trọng

### 4) Kiểm định giả thuyết (Hypothesis Testing)
Notebook trình bày phần lý thuyết + ví dụ, sau đó **áp dụng vào dataset hiện tại**.

**Wine Quality – câu hỏi nghiên cứu (dataset hiện tại):**  
> “Liệu có mối liên hệ có ý nghĩa thống kê giữa **loại rượu** (`type`: red/white) và **nhóm chất lượng** (`quality` đã phân loại) hay không?”  
→ Dùng **Chi-square Test of Independence**.  
Kết quả notebook cho thấy p-value rất nhỏ (**~ 2.4896e-08**), hàm ý có bằng chứng mạnh để bác bỏ H0 (không độc lập).

**Heart Disease – câu hỏi nghiên cứu (dataset ngoài / áp dụng mẫu):**  
> “Liệu có mối liên hệ có ý nghĩa thống kê giữa **giới tính** (`sex`) và sự hiện diện bệnh động mạch vành đáng kể (`num = 1`) hay không?”  
→ Dùng **Chi-square Test of Independence**.  
Notebook minh họa p-value rất nhỏ (**~ 1.90e-06**), hàm ý có bằng chứng thống kê để bác bỏ H0 trong ví dụ.

> Lưu ý: Ngoài Chi-square, notebook còn trình bày/nhắc đến các kiểm định thường gặp như t-test và ANOVA (kèm điều kiện áp dụng và cách diễn giải).

### 5) Phân tích tương quan giữa các biến
- Trình bày hệ số tương quan (Pearson/Spearman)
- Tính tương quan giữa các biến số
- Trực quan hóa bằng scatter plot + heatmap
- Nhận xét ý nghĩa thực tiễn của các tương quan nổi bật

---

## Cách chạy (Recommended)

### Option A — Google Colab
1. Upload notebook lên Colab
2. Upload dữ liệu vào đúng đường dẫn `/content/` (theo notebook)
3. Run all cells từ trên xuống

### Option B — Local (Jupyter Notebook)
Cài thư viện:
```bash
pip install pandas numpy matplotlib seaborn scipy chardet
