# Customer_Segmentation_ML

This project performs **Customer Segmentation** using Machine Learning to group customers into meaningful clusters based on their behavior and attributes. It follows a complete ML workflow:

**Problem Statement → Selection of Data → Collection of Data → EDA → Train/Test Split (if needed) → Model Selection → Evaluation Metrics**

Note: Customer Segmentation is usually an **Unsupervised Learning** problem, so the main focus is clustering instead of prediction.

---

## Problem Statement
Businesses have many customers with different spending patterns and preferences. Treating all customers the same reduces marketing performance.

Goal:
- Group customers into **clusters/segments**
- Use these segments for targeted marketing, offers, and better customer understanding

**Output:** Cluster label for each customer (Segment 0, 1, 2, ...)

---

## Selection of Data
**Dataset chosen:** Customer dataset (tabular data)

**Why this dataset?**
- Contains customer attributes that help identify patterns
- Suitable for clustering and segmentation
- Helps practice unsupervised ML workflow (EDA + preprocessing + clustering)

---

## Collection of Data
The dataset is loaded inside the notebook (`customersegmentaion.ipynb`) using Python libraries (commonly via `pandas.read_csv()`).

Typical sources:
- Kaggle dataset
- CSV file stored locally or in Google Drive
- Company/customer data sample dataset

---

## Main Libraries Used (and why)

1. `pandas`  
   - Load CSV data, clean it, handle DataFrame operations.

2. `numpy`  
   - Numerical operations and transformations.

3. `matplotlib.pyplot`  
   - Basic visualizations for EDA and cluster plotting.

4. `seaborn`  
   - Better statistical plots (distribution plots, correlation heatmap).

5. `sklearn.preprocessing`  
   Commonly used tools:
   - `StandardScaler` (scaling features for clustering)
   - `LabelEncoder` / `OneHotEncoder` (if categorical features exist)

6. `sklearn.cluster`  
   Common clustering algorithms:
   - `KMeans` (most common for customer segmentation)
   - `DBSCAN` (density-based clustering)
   - `AgglomerativeClustering` (hierarchical clustering)

7. `sklearn.metrics`  
   Clustering evaluation methods:
   - `silhouette_score`
   - Inertia / Elbow method (for KMeans)

---

## Overall Project Flow (Step-by-step)

### 1) Import Libraries
Import required libraries for:
- Data loading + analysis
- Visualization
- Preprocessing (scaling/encoding)
- Clustering model training
- Evaluation

### 2) Load the Dataset
- Load customer dataset into a DataFrame
- Inspect:
  - shape
  - column names
  - data types
  - missing values

### 3) EDA (Exploratory Data Analysis)
Goal: Understand customer behavior patterns.
- Check missing values and duplicates
- Explore distributions (income, spending, age, etc.)
- Correlation check (optional)
- Identify important features for clustering

### 4) Data Preprocessing
Before clustering, preprocessing is critical:
- Handle missing values
- Drop irrelevant columns (like CustomerID if it doesn't add value)
- Encode categorical features (if present)
- Scale numerical features using `StandardScaler`

Why scaling?
- Clustering uses distance calculations
- Features must be in the same scale to avoid bias

### 5) Feature Selection for Clustering
Select meaningful columns such as:
- Annual Income
- Spending Score
- Age
- Purchase frequency (if available)

### 6) Model Selection (Clustering)
**Most common model:** KMeans Clustering

Typical selection process:
- Use **Elbow Method** to choose optimal number of clusters (K)
- Train KMeans with selected K

### 7) Training the Model
- Fit the clustering model on processed features
- Assign cluster labels to each customer

### 8) Cluster Visualization
- Visualize clusters using scatter plots
- Color-code each cluster/segment to interpret patterns

### 9) Evaluation Metrics (Evaluation Matrix)
Since it is unsupervised learning, evaluation is different:

1. **Elbow Method (Inertia)**
- Helps decide the best number of clusters

2. **Silhouette Score**
- Measures how well points fit within their cluster
- Higher silhouette score means better cluster separation

3. **Cluster Profiling (Business View)**
- Compare averages per cluster (income, spending, etc.)
- Helps label clusters like:
  - High income / high spending
  - Low income / low spending
  - Budget customers, premium customers, etc.

---

## Model Used (Important)
Update this line with your exact model from the notebook:
- **Model:** KMeans Clustering (or DBSCAN / Hierarchical)

---

## How to Run Locally

### Option 1: Run in Jupyter Notebook
1. Download this repository
2. Open `customersegmentaion.ipynb` in Jupyter Notebook / VS Code / Google Colab
3. Run all cells from top to bottom

### Option 2: Run in Google Colab
1. Upload `customersegmentaion.ipynb`
2. Upload dataset file (if required)
3. Run all cells

---
## Developer
Grishma C.D







