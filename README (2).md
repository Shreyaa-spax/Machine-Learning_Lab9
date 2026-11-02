# Customer Segmentation using K-Means and Hierarchical Clustering

## Project Overview
This project applies unsupervised machine learning techniques to the **Wholesale Customers** dataset to group customers according to their annual spending patterns across different product categories.

The notebook performs data inspection and preprocessing, selects a cluster count, applies K-Means and hierarchical clustering, and visualizes and compares the resulting customer groups.

## Dataset
The notebook reads the file:

`Wholesale customers data - Wholesale customers data.csv`

The dataset contains **440 records and 8 columns**. The notebook excludes `Channel` and `Region` from clustering and uses these six spending features:

- `Fresh`
- `Milk`
- `Grocery`
- `Frozen`
- `Detergents_Paper`
- `Delicassen`

**Important:** Keep the CSV file in the same folder as the notebook, or update the CSV path in the notebook before running it.

## Technologies and Libraries
- Python
- Jupyter Notebook / Google Colab
- NumPy
- Pandas
- Matplotlib
- Seaborn
- Scikit-learn
- SciPy

## Project Workflow

1. **Import libraries and load data** – Load the CSV dataset and required Python packages.
2. **Explore the dataset** – Inspect the first and last rows, dimensions, column names, data types, descriptive statistics, missing values, and duplicate records.
3. **Preprocess the data** – Remove `Channel` and `Region` from the clustering features and standardize the six spending columns using `StandardScaler`.
4. **Choose the number of clusters** – Use the Elbow Method (WCSS/inertia) and Silhouette Scores for values of K from 2 to 10.
5. **Apply K-Means** – Cluster the standardized customer spending data.
6. **Apply hierarchical clustering** – Use agglomerative clustering with Ward linkage and Euclidean distance. Plot full and truncated dendrograms.
7. **Visualize clusters** – Apply PCA to reduce the standardized data to two components and display a scatter plot of the K-Means cluster labels.
8. **Evaluate and profile clusters** – Compare silhouette scores and cluster sizes, then calculate average spending values for each K-Means cluster.

## Algorithms and Methods
- **StandardScaler:** Standardizes the input features so that spending columns on different scales can be compared.
- **Elbow Method:** Plots K-Means inertia (WCSS) for different cluster counts to help identify a suitable K.
- **Silhouette Score:** Measures how well observations fit within their assigned clusters compared with other clusters.
- **K-Means:** Partitions customers into a specified number of clusters.
- **Agglomerative Hierarchical Clustering:** Builds customer groups hierarchically using Ward linkage.
- **PCA:** Projects the standardized features into two dimensions for visualization.

## Results
In the saved notebook outputs:

- The highest tested silhouette score is **0.5483 at K = 3** (the score at K = 2 is 0.5472).
- The K-Means model used for the final comparison has **3 clusters** and a silhouette score of **0.5483**.
- The 3-cluster hierarchical model has a silhouette score of **0.2646**.
- K-Means cluster sizes are **45, 393, and 2** for clusters 0, 1, and 2 respectively.
- Hierarchical cluster sizes are **6, 281, and 153** for clusters 0, 1, and 2 respectively.

The notebook also displays the mean spending in each of the six product categories for every K-Means cluster. These profiles can help interpret the spending patterns represented by the groups.

## How to Run

1. Download or clone this project.
2. Place the notebook and dataset CSV in the same directory.
3. Install the required packages:

   ```bash
   pip install numpy pandas matplotlib seaborn scikit-learn scipy jupyter
   ```

4. Open Jupyter Notebook:

   ```bash
   jupyter notebook
   ```

5. Open `ml_lab9.ipynb` and run all cells from top to bottom.

   Alternatively, upload the notebook and CSV file to Google Colab and run the cells there.

## Output
The notebook generates:
- Dataset inspection and summary outputs
- Standardized feature data
- Elbow Method plot
- Silhouette score table
- Full and truncated hierarchical dendrograms
- PCA scatter plot showing K-Means clusters
- Silhouette score comparison of both clustering algorithms
- Cluster-size comparison
- Average spending profile for each K-Means cluster

## Notes
- The notebook expects the CSV filename shown in the Dataset section.
- The notebook calculates a silhouette-based suggested K and then explicitly uses `K = 3` in the final K-Means clustering section. The saved results show that K = 3 is also the highest-scoring option among the tested values.
- Cluster labels are identifiers, not customer types in a predefined order.

## Author
**Name:** Riya Waghmare  
**Roll No.:** 35  
**Class:** B-B3
