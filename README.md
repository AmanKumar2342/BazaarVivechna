# Bazar Vivechna - RFM Analysis

## 📊 Project Overview

This project applies **RFM segmentation** to a retail sales dataset to identify and categorize customers based on their purchasing behavior.  
RFM stands for:

- **Recency** – How recently a customer made a purchase  
- **Frequency** – How often a customer makes purchases  
- **Monetary** – How much a customer spends

By calculating and scoring these metrics, the analysis uncovers high-value customer segments. The results inform data-driven marketing strategies such as retention efforts, loyalty programs, and targeted campaigns.

---

## 🗂 Dataset Description

The analysis uses a sample CSV file: `sales_data_sample.csv`, containing approximately 2,800 sales records and 25 fields including:

- `ORDERNUMBER`
- `ORDERDATE`
- `SALES`
- `CUSTOMERNAME`

After cleaning and preprocessing, 92 unique customers remain for the RFM segmentation.

---

## 🔍 Methodology

### 1. Data Cleaning & Preparation
- Unnecessary columns (addresses, contact info, etc.) are dropped.
- `PRODUCTINITIAL` is extracted from `PRODUCTCODE`.
- Dates are parsed for calculating recency.

### 2. RFM Calculation
For each customer:
- **Recency** = Days since last purchase (relative to a fixed reference date)
- **Frequency** = Total number of orders
- **Monetary** = Total spend

### 3. Scoring
Each RFM metric is divided into **quartiles (1–4)**:
- Higher scores indicate **more favorable** behavior (e.g., more recent, frequent, or higher spend).
- Quartile-based scoring provides relative ranking across customers.

### 4. Segmentation using Clustering
- RFM scores are used as a 3D feature space.
- **K-Means Clustering** groups customers with similar profiles.
- The **Elbow Method** helps determine the optimal number of clusters.
- Segments represent customer types (e.g., loyal, at-risk, new, lapsed).

---

## 🧰 Technologies Used

- **Python 3**
- `pandas`, `numpy` – Data manipulation and numerical operations  
- `matplotlib`, `seaborn` – Data visualization  
- `scikit-learn` – KMeans clustering  
- `datetime`, `scipy`, `statsmodels` – Date operations and basic statistics  
- **Google Colab** or **Jupyter Notebook** for development

---

## ⚙️ Usage Instructions

1. Install required packages:
   ```bash
   pip install pandas numpy matplotlib seaborn scipy statsmodels scikit-learn

2. Ensure `sales_data_sample.csv` is in your working directory.

3. Open the notebook:

   `BazarVivechna_RFM.ipynb` in **Jupyter Notebook** or **Google Colab**.

4. Run the cells sequentially. The notebook is self-contained and fully annotated for clarity.

---

## 📈 Results Summary

### Output Includes:
- **RFM Tables**: Raw values and quartile scores per customer.
- **Cluster Assignments**: Each customer belongs to a cluster based on their RFM profile.
- **Visualizations**:
  - Elbow curve for optimal `k` selection.
  - 3D scatter plots of RFM clusters.

### Example Insights:
- **Cluster 1**: Low recency, high frequency, high spend → **Loyal, high-value customers**
- **Cluster 2**: High recency, low frequency, low spend → **Lapsed or low-value customers**

### These insights support:
- Personalized marketing strategies  
- Customer retention and win-back campaigns  
- Lifecycle marketing planning and budget allocation  

---

## 🧱 Project Structure

- **Data Loading & Cleaning**: Import libraries, load CSV, and remove irrelevant columns  
- **Exploratory Analysis**: Visualize sales patterns and order status  
- **RFM Computation**: Calculate Recency, Frequency, and Monetary metrics per customer  
- **RFM Scoring**: Apply quartile-based scoring (higher score = better customer behavior)  
- **Clustering**: Use KMeans with elbow method to segment customers  
- **Interpretation**: Compare average RFM values per cluster to understand customer behavior  

---

## 💡 Business Value

By identifying and segmenting customers using RFM analysis, businesses can:

- **Focus on high-value customers** with tailored loyalty programs and rewards  
- **Re-engage at-risk or inactive customers** with personalized offers  
- **Maximize ROI** through well-targeted and cost-effective marketing campaigns  
