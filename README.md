# Customer Segmentation Using K-Means (Machine Learning)

This project performs **Customer Segmentation** using **K-Means clustering** to group customers into meaningful segments based on their **Age, Annual Income, and Spending Score**.
It is a beginner-friendly, end-to-end clustering workflow focused on preprocessing, clustering, and visualization.

---

## Problem Statement

Customers behave differently in terms of spending and income. Treating all customers the same reduces marketing results.  
The goal of this project is to:
- Group customers into **clusters (segments)**
- Use these segments to understand customer types (example: high income–high spending, low income–low spending, etc.)

**Output:** Each customer gets a **Cluster label** (0, 1, 2, ...)

---

## Selection of Data

**Dataset Type Used:** Tabular customer dataset (structured data)

**Features used for clustering:**
- `Age`
- `Annual_Income(k$)`
- `Spending_Score(1-100)`

(Your dataset also contains `CustomerID`, which is used only as an identifier.)

---

## Collection of Data

Data is created/loaded into a pandas DataFrame in the notebook using Python (`pandas`).  
In your current code, the dataset is provided as a sample dictionary and converted into a DataFrame.

---

## EDA (Exploratory Data Analysis)

Basic checks are done to understand the dataset before clustering:
- Preview the dataset using `df.head()`
- Confirm columns and values are loaded correctly

This helps ensure the data is ready for clustering.

---

## Data Preprocessing

Before clustering, the feature columns are standardized using **StandardScaler** because K-Means is distance-based.

**Why scaling is important:**
- Income values are much larger than age/spending score
- Without scaling, K-Means will get biased toward large-number features

Used in code:
- `StandardScaler().fit_transform(X)`

---

## Dividing Training and Testing

This is an **unsupervised learning** project, so a train/test split is not required here.  
The model clusters the available customer records directly.

---

## Model Selection

**Model used:** K-Means Clustering

K-Means is chosen because:
- It is simple and beginner-friendly
- Works well for grouping similar customers into clear segments

Used in code:
- `KMeans(n_clusters=3, random_state=42, n_init=10)`

---

## Evaluation Matrix (Used in this Project)

This project evaluates results mainly by **cluster assignment + visualization**:
- Customers are assigned into clusters using `fit_predict()`
- Clusters are visualized using a scatter plot (Income vs Spending Score) colored by cluster

---

## Main Libraries Used (and why)

1. `pandas`  
   - Creates the dataset as a DataFrame and helps in viewing/handling tabular data (`pd.DataFrame`, `df.head()`).

2. `matplotlib.pyplot`  
   - Used to visualize the clusters using a scatter plot (`plt.scatter`, `plt.xlabel`, `plt.title`, `plt.show`).

3. `sklearn.preprocessing.StandardScaler`  
   - Standardizes the feature values so K-Means is not biased toward larger numbers (`scaler.fit_transform(X)`).

4. `sklearn.cluster.KMeans`  
   - Builds the clustering model and assigns each customer to a segment (`KMeans(...)`, `fit_predict`).

---

## How to Run Locally

### Option 1: Run in Jupyter / VS Code
1. Open your notebook file
2. Run cells from top to bottom

### Option 2: Run in Google Colab
1. Upload the notebook to Colab
2. Run cells from top to bottom

---

## Output

- A new column `Cluster` is added to the dataset
- A cluster plot is displayed:
  - X-axis: Annual Income (k$)
  - Y-axis: Spending Score (1-100)
  - Color: Cluster label (segment)

---

## Developer

Grishma C.D
