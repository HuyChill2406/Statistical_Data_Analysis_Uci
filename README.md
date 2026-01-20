# Statistical_Data_Analysis_Uci

# Phân tích Thống kê & Khám phá Dữ liệu (EDA) trên các bộ dữ liệu UCI

Repository này bao gồm **3 notebook Jupyter** thực hiện phân tích dữ liệu dạng bảng (tabular data) theo quy trình đầy đủ:
**làm sạch dữ liệu → EDA → phân tích phân phối & ngoại lệ → kiểm định giả thuyết → phân tích tương quan**,  
áp dụng trên các bộ dữ liệu thực tế từ **UCI Machine Learning Repository**.

---

## Tổng quan các Notebook

### 1) `AdultIncome_522H0131.ipynb`
- **Bộ dữ liệu:** Adult / Census Income (UCI)
- **Kích thước:** **32.560 dòng × 15 cột**
- **Mục tiêu:**  
  Phân tích các yếu tố nhân khẩu học và nghề nghiệp, đồng thời đánh giá mối liên hệ thống kê với mức thu nhập.

**Kiểm định thống kê chính:**
- **Kiểm định Chi-square:** `sex` vs `income`  
  → χ² = **1516.7020**, p-value ≈ **0**  
  ⇒ Có mối liên hệ có ý nghĩa thống kê giữa giới tính và mức thu nhập.

---

### 2) `HeartDisease_522H0131.ipynb`
- **Bộ dữ liệu:** UCI Heart Disease (gộp từ 4 nguồn: Cleveland, Hungarian, Switzerland, VA)
- **Kích thước:** **920 dòng × 14 cột**
- **Mục tiêu:**  
  Khám phá các yếu tố y học liên quan đến bệnh tim, xử lý dữ liệu thiếu và phân tích mối quan hệ giữa các biến.

**Kiểm định thống kê chính:**
- **Kiểm định Chi-square:** `sex` vs `num` (tình trạng bệnh tim)  
  → χ² = **84.1451**, p-value = **4.60e-20**  
  ⇒ Có mối liên hệ có ý nghĩa thống kê giữa giới tính và nguy cơ mắc bệnh tim.

---

### 3) `WineQuality_522H0131.ipynb`
- **Bộ dữ liệu:** UCI Wine Quality (Red & White)
- **Xử lý:** Gộp hai bộ dữ liệu, bổ sung biến phân loại **`type`**
- **Kích thước:** **6.497 dòng × 13 cột**
- **Mục tiêu:**  
  So sánh đặc trưng hóa học giữa rượu vang đỏ và trắng, phân tích phân phối chất lượng rượu và mối quan hệ giữa các biến.

**Kiểm định thống kê chính:**
- **Kiểm định Chi-square:** `type` vs `quality` (đã phân nhóm)  
  → χ² = **35.0171**, p-value = **2.4896e-08**  
  ⇒ Loại rượu có ảnh hưởng đáng kể đến phân bố chất lượng.

---

## Quy trình phân tích chung

### 1) Chuẩn bị dữ liệu
- Đọc và gộp dữ liệu từ nhiều nguồn
- Xử lý giá trị thiếu và trùng lặp
- Chuẩn hóa định dạng và biến phân loại

### 2) Khám phá dữ liệu (EDA)
- Thống kê mô tả (mean, std, min/max, quartiles)
- Kiểm tra dữ liệu thiếu
- Trực quan hóa:
  - Histogram (phân phối)
  - Boxplot (phát hiện ngoại lệ)
  - Countplot (biến phân loại)
  - Scatter plot và pairplot

### 3) Phân tích phân phối & chuẩn hóa
- Đánh giá hình dạng phân phối dữ liệu
- Kiểm định chuẩn hóa (Shapiro-Wilk, KS-test, Anderson-Darling)
- Nhận xét khả năng áp dụng các kiểm định tham số

### 4) Kiểm định giả thuyết
- Trình bày giả thuyết H0 và H1
- Áp dụng kiểm định Chi-square trên từng bộ dữ liệu
- Diễn giải p-value và kết luận ở mức ý nghĩa α = 0.05

### 5) Phân tích tương quan
- Tính hệ số tương quan Pearson
- Trực quan hóa bằng heatmap
- Nhận xét các mối quan hệ nổi bật giữa các biến

---

## Hướng dẫn chạy Notebook

### Cách 1: Google Colab
1. Mở notebook trên Colab
2. Upload dữ liệu vào thư mục `/content/`
3. Chạy các cell theo thứ tự từ trên xuống

### Cách 2: Chạy Local
Cài đặt thư viện:
```bash
pip install pandas numpy matplotlib seaborn scipy chardet
```

# Statistical Data Analysis (EDA + Hypothesis Testing) on UCI Datasets
This repository contains 3 Jupyter notebooks that perform **end-to-end EDA**, **distribution/outlier analysis**, **statistical hypothesis testing**, and **correlation visualization** on real-world tabular datasets from UCI.

---

## Notebooks Overview

### 1) `AdultIncome_522H0131.ipynb`
- **Dataset:** Adult / Census Income (UCI)
- **Size:** **32,560 rows × 15 columns**
- **Goal:** Explore demographic & work-related factors and analyze statistical relationships with the income label.

**Key statistical test applied (on dataset):**
- **Chi-square test:** `sex` vs `income`  
  → χ² = **1516.7020**, p-value = **0.0000e+00** (significant association)

---

### 2) `HeartDisease_522H0131.ipynb`
- **Dataset:** UCI Heart Disease (merged from 4 sources: Cleveland, Hungarian, Switzerland, VA)
- **Size:** **920 rows × 14 columns**
- **Goal:** Explore medical risk factors, handle missing/outliers, analyze distributions and relationships with heart disease status.

**Key statistical test applied (on dataset):**
- **Chi-square test:** `sex` vs `num` (heart disease status)  
  → χ² = **84.1451**, p-value = **4.5976e-20** (significant association)

---

### 3) `WineQuality_522H0131.ipynb`
- **Dataset:** UCI Wine Quality (red + white)
- **Merge:** Combine `winequality-red.csv` and `winequality-white.csv`, add categorical column **`type`**
- **Size:** **6,497 rows × 13 columns**
- **Goal:** Compare chemical properties across wine types, analyze distribution patterns, test statistical dependence, and study correlations.

**Key statistical test applied (on dataset):**
- **Chi-square test:** `type` vs `quality` (quality grouped into categories)  
  → χ² = **35.0171**, p-value = **2.4896e-08** (significant association)

---

## What’s Included (Common Workflow Across Notebooks)

### 1) Data Preparation
- Load and integrate datasets (multi-source merge where applicable)
- Handle missing values and duplicates
- Feature formatting / categorical handling (e.g., `type` for wine)

### 2) Exploratory Data Analysis (EDA)
- Descriptive statistics (mean, std, quartiles, min/max)
- Missing-value inspection (including visual checks)
- Visual exploration:
  - Histograms / distribution plots
  - Boxplots (outlier detection)
  - Countplots for categorical variables
  - Pairplots / scatter plots (where suitable)

### 3) Distribution & Normality Analysis
- Distribution shape analysis (skewness, outliers)
- Normality checks using common tests (e.g., Shapiro-Wilk, KS-test, Anderson-Darling)
- Notes on implications for choosing parametric vs non-parametric tests

### 4) Hypothesis Testing
- Theory recap (t-test / Chi-square / ANOVA) and conditions for applying tests
- Practical application on each dataset with clear interpretation:
  - Contingency table
  - χ² statistic, degrees of freedom, p-value
  - Conclusion at α = 0.05

### 5) Correlation Analysis
- Pearson correlation
- Correlation heatmaps + interpretation of notable relationships

---

## How to Run

### Option A — Google Colab
1. Open the notebook in Colab
2. Upload dataset files into `/content/` (match the paths used in notebooks)
3. Run cells top-to-bottom

### Option B — Local (Jupyter)
Install dependencies:
```bash
pip install pandas numpy matplotlib seaborn scipy chardet
