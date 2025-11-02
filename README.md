# 🏦 Retail Banking – RFM & Machine Learning Segmentation

This project analyses retail banking transaction data to identify actionable customer segments using both **rule-based RFM analysis** and **unsupervised machine learning (K-Means)**.  
The goal is to help marketing, CRM, and data teams **understand customer behaviour**, improve retention, and drive profitability.

---

## 📂 Repository Structure

```bash
data/
├── raw/                     # Original transaction and customer data  
├── processed/               # Cleaned and model-ready data (tracked via Git LFS)

notebooks/
├── 01_rfm_refinement.ipynb  # Data cleaning, normalization, and RFM scoring  
├── 02_rfm_refinement.ipynb  # Rule-based segmentation, business insights, and visuals  
├── 02b_rfm_refinement.ipynb # K-Means clustering, evaluation, and insights  

app/
└── streamlit_dashboard.py   # (Optional) Streamlit dashboard for interactive exploration

---

## ⚙️ Project Workflow

### **1️⃣ Data Preparation**
- Imported and cleaned transaction and customer datasets.
- Standardised and parsed date fields (`TransactionDate`, `CustomerDOB`) using day-first format.
- Fixed century rollovers (e.g., 2057 → 1957) and removed implausible/missing dates.
- Computed **Recency**, **Frequency**, **Monetary** per customer.

### **2️⃣ RFM Segmentation (Rule-Based)**
- Scored each metric (1–5) and assigned rule-based segments (*Best Customers*, *Loyal (Lower Spend)*, *At Risk*, *High-Value Inactive*, *New/Promising*, …).
- Visualised distributions (bar/pie).
- Actions:
  - **Retain** Best Customers / High Spenders with VIP & early-access.
  - **Re-engage** At-Risk/Inactives with “win-back” offers.
  - **Upsell** Loyal Low-Spend with cross-sell bundles.

### **3️⃣ Machine Learning Segmentation (K-Means)**
- Transforms: log(F), log(M); invert Recency (higher = more recent); standardise with `StandardScaler`.
- Evaluated **k=2–10** via Elbow, Silhouette; selected **k=4**.
- Profiled centroids and mapped to business labels; reduced over-broad “At-Risk” to <20%.

### **4️⃣ Business Insights**
| Segment            | Description                         | Recommended Action                           |
|--------------------|-------------------------------------|----------------------------------------------|
| High-Value Loyal   | Frequent & recent spend             | VIP perks, loyalty points, referrals         |
| New/Promising      | Recent joiners, rising activity     | Onboarding, nudges, targeted follow-ups      |
| At-Risk/Dormant    | Previously active, now inactive     | Reactivation journeys, limited-time offers   |
| Regular Spenders   | Moderate frequency & spend          | Cross-sell complementary products            |

---

## 💻 Streamlit Dashboard (Next Phase)

Will show:
- **KPIs:** customers, revenue, avg CLV  
- **Filters:** by segment, recency range, frequency  
- **Visuals:** segment distribution, R/F/M trends, centroid heatmaps  
- **Insights:** recommended actions per segment  

---

### Run locally:
```bash
streamlit run app/streamlit_dashboard.py

```


## 🧠 Key Learnings

- Proper **date normalization** and feature scaling are critical before clustering.
- Combining **RFM logic + ML segmentation** improves targeting precision.
- Git LFS integration ensures large datasets are tracked efficiently.
- Clear visual profiling supports stakeholder interpretation and strategic planning.


## ⚙️ Reproducibility

 
### **Environment Setup**
```bash
conda create -n retail-analytics python=3.11 -y
conda activate retail-analytics
pip install pandas numpy scikit-learn seaborn matplotlib streamlit

jupyter notebook
# Then open and run, in order:
# notebooks/01_rfm_refinement.ipynb
# notebooks/02_rfm_refinement.ipynb
# notebooks/02b_rfm_refinement.ipynb

```


## 🧾 Version Control Best Practices

- `.gitignore` excludes checkpoints and temporary files to keep the repository clean.  
- **Git LFS (Large File Storage)** is used to track and manage large CSV files efficiently.  

Set up Git LFS

```bash
git lfs install
git lfs track "data/**/*.csv"
git add .gitattributes
git commit -m "Enable Git LFS for all CSVs"
---

## 👤 Author

**Omolara Okiki** 📚  
📊 *Data Analyst | Business Intelligence | CRM Segmentation*  
📍 *West Midlands, UK*  

🔗 **Connect:**  
- [GitHub](https://github.com/omoleek77)  
- [LinkedIn](https://www.linkedin.com/in/omolara-okiki)  
- [Portfolio / Projects](https://github.com/omoleek77?tab=repositories)
