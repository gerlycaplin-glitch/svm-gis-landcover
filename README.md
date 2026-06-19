Spatial Machine Learning for Land Cover Classification using SVM
Project Overview
This project applies a Support Vector Machine (SVM) model to classify land cover types in a rural area of Indonesia using Sentinel-1 SAR backscatter data (VV/VH) extracted via Google Earth Engine. The pipeline covers the full workflow from data extraction to model evaluation, achieving an overall classification accuracy of 77.27%.
Tech Stack

Python — core programming language
Scikit-Learn — SVM modeling & hyperparameter tuning (GridSearchCV)
Pandas / NumPy — data preprocessing & feature engineering
Google Earth Engine (GEE) — satellite data extraction (Sentinel-1 SAR)
Matplotlib / Seaborn — visualization (confusion matrix, prediction map)

Repository Structure
├── main_pipeline.ipynb        # Main Jupyter Notebook (full pipeline)
├── data/
│   └── sample_points.csv      # Cleaned sample points with land cover labels
├── outputs/
│   ├── confusion_matrix.png   # Model evaluation visualization
│   └── prediction_map.png     # Final land cover prediction map
└── README.md
Key Insights

The model achieved 77.27% overall accuracy, with the strongest performance on the Hutan (Forest) and Sawah (Paddy Field) classes, which have the most distinct VV/VH backscatter signatures.
The main source of misclassification was overlap between Pemukiman (Settlement) and Lahan Terbuka (Open Land), since both classes can produce similar backscatter intensity when vegetation cover is sparse.
Feature engineering — particularly the VV/VH ratio and normalized difference — improved class separability beyond using raw backscatter values alone.
Hyperparameter tuning via GridSearchCV identified the RBF kernel as consistently outperforming the linear kernel, confirming non-linear separability among land cover classes in the SAR feature space.

How to Run

Clone this repository
Install dependencies: pip install earthengine-api pandas numpy scikit-learn matplotlib seaborn
Authenticate Google Earth Engine: ee.Authenticate()
Open main_pipeline.ipynb and run all cells sequentially

Author
Geraldine — IPB University, Land Resource Management

Background in geospatial analysis (ArcGIS, QGIS, GEE) and data analytics.
