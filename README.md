\\# 🏦 Retail Banking – RFM \\\& Machine Learning Segmentation







This project analyses retail banking transaction data to identify actionable customer segments using both \\\*\\\*rule-based RFM analysis\\\*\\\* and \\\*\\\*unsupervised machine learning (K-Means)\\\*\\\*.  



The goal is to help marketing, CRM, and data teams \\\*\\\*understand customer behaviour\\\*\\\*, improve retention, and drive profitability.







---







\\## 📂 Repository Structure







data/



raw/ # Original transaction and customer data



processed/ # Cleaned and model-ready data (tracked via Git LFS)



notebooks/



01\\\_rfm\\\_refinement.ipynb # Data cleaning, date normalization, and RFM scoring



02\\\_rfm\\\_refinement.ipynb # Rule-based segmentation, business insights, and visual analysis



02b\\\_rfm\\\_refinement.ipynb # K-Means clustering, performance evaluation, and actionable insights



app/



streamlit\\\_dashboard.py # (Optional) Streamlit dashboard for interactive exploration











---







\\## ⚙️ Project Workflow







\\### \\\*\\\*1️⃣ Data Preparation\\\*\\\*



\\- Imported and cleaned transaction and customer datasets.



\\- Standardised and parsed all date fields (`TransactionDate`, `CustomerDOB`) using UK day-first format.



\\- Fixed century rollovers (e.g., 2057 → 1957) and removed implausible or missing dates.



\\- Computed \\\*\\\*Recency\\\*\\\*, \\\*\\\*Frequency\\\*\\\*, and \\\*\\\*Monetary\\\*\\\* metrics per customer.







\\### \\\*\\\*2️⃣ RFM Segmentation (Rule-Based)\\\*\\\*



\\- Scored each metric on a scale of 1–5 and assigned customers to rule-based segments:



\&nbsp; - \\\*Best Customers\\\*, \\\*Loyal (Lower Spend)\\\*, \\\*At Risk\\\*, \\\*High-Value Inactive\\\*, \\\*New/Promising\\\*, etc.



\\- Visualised customer share via bar and pie charts.



\\- Derived actionable business recommendations:



\&nbsp; - \\\*\\\*Retain\\\*\\\* Best Customers and High Spenders.



\&nbsp; - \\\*\\\*Re-engage\\\*\\\* At-Risk and Inactive customers.



\&nbsp; - \\\*\\\*Upsell\\\*\\\* Loyal Low-Spend customers.







\\### \\\*\\\*3️⃣ Machine Learning Segmentation (K-Means)\\\*\\\*



\\- Applied transformations:



\&nbsp; - Log-transform on Frequency and Monetary



\&nbsp; - Inverted Recency (so higher = more recent)



\&nbsp; - Standardised features with `StandardScaler`



\\- Evaluated \\\*\\\*k = 2–10\\\*\\\* using Elbow and Silhouette methods, selecting \\\*\\\*k = 4\\\*\\\*.



\\- Clustered customers into natural segments and profiled centroids.



\\- Compared to RFM logic to validate behavioural consistency and reduce At-Risk customers to <20%.







\\### \\\*\\\*4️⃣ Business Insights\\\*\\\*



| Segment | Description | Recommended Action |



|----------|--------------|--------------------|



| High-Value Loyalists | Frequent and recent spenders | Reward with VIP programs, loyalty points |



| New/Promising | Recent joiners with rising spend | Strengthen onboarding, targeted follow-up |



| At-Risk/Dormant | Previously high-value but inactive | Reactivation campaigns, “We miss you” offers |



| Regular Spenders | Moderate frequency \\\& spend | Cross-sell complementary products |







---







\\## 💻 Streamlit Dashboard (Next Phase)



The interactive dashboard will display:



\\- \\\*\\\*KPIs:\\\*\\\* total customers, revenue, and average CLV  



\\- \\\*\\\*Filters:\\\*\\\* by segment, recency range, frequency  



\\- \\\*\\\*Visuals:\\\*\\\* segment distributions, R/F/M trends, centroid heatmaps  



\\- \\\*\\\*Insights Tab:\\\*\\\* recommended CRM actions per segment  







Run locally with:



```bash



streamlit run app/streamlit\\\_dashboard.py







```







---







\\## 🧠 Key Learnings







\\- Proper \\\*\\\*date normalization\\\*\\\* and feature scaling are critical before clustering.



\\- Combining \\\*\\\*RFM logic + ML segmentation\\\*\\\* improves targeting precision.



\\- Git LFS integration ensures large datasets are tracked efficiently.



\\- Clear visual profiling supports stakeholder interpretation and strategic planning.







---







\\## ⚙️ Reproducibility







\\### \\\*\\\*Environment Setup\\\*\\\*







```bash



conda create -n retail-analytics python=3.11 -y



conda activate retail-analytics



pip install pandas numpy scikit-learn seaborn matplotlib streamlit







\&nbsp; 







jupyter notebook



\\# Then open and run in order:



\\# 01\\\_rfm\\\_refinement.ipynb



\\# 02\\\_rfm\\\_refinement.ipynb



\\# 02b\\\_rfm\\\_refinement.ipynb







\\## 🧾 Version Control Best Practices



\\- `.gitignore` excludes checkpoints and temp files.



\\- \\\*\\\*Git LFS\\\*\\\* tracks large CSVs:



\&nbsp; ```bash



\&nbsp; git lfs install



\&nbsp; git lfs track "data/\\\*\\\*/\\\*.csv"



\&nbsp; git add .gitattributes



\&nbsp; git commit -m "Enable Git LFS for all CSVs"



\&nbsp;       







\\### 🖥️ On the Anaconda Prompt



When you actually want to \\\*\\\*save or push your work\\\*\\\*, that’s when you \\\*\\\*run\\\*\\\* the real commands — like these:







```bash



git add .



git commit -m "Updated README and notebook structure"



git push origin main















👤 Author







Omolara Okiki



Data Analyst | Business Intelligence | CRM Segmentation



📧 omolara.okiki@example.com







📍 West Midlands, UK



🔗 \\\[LinkedIn / Portfolio / GitHub links]





