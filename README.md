# Machine Learning-based Land Cover Classification from Sentinel-2 Satellite Data

This project focuses on developing a high-accuracy machine learning model for land cover classification using Sentinel-2 satellite imagery. The primary study area is Thanh Hoa Province, Vietnam, a region with diverse land cover types.

## Introduction
Accurate monitoring and assessment of land cover changes are crucial for sustainable natural resource management and climate change adaptation. Traditional methods like field surveys are resource-intensive and have limitations in continuous monitoring over large spatial extents. The advent of Sentinel-2 satellite imagery, providing high-resolution multispectral data with a short revisit cycle and free access, offers a significant opportunity for automated land cover classification. This project leverages these advancements to build robust classification models.

## Project Objectives
1.  **Develop a Multi-Class Classification Model:** To automatically identify and classify 10 distinct land cover types prevalent in Thanh Hóa Province.
2.  **Optimize ML Algorithms:** To select, fine-tune, and optimize modern machine learning algorithms for enhanced performance and reliability.
3.  **Improve Generalizability:** To employ advanced data preprocessing, feature engineering, and feature selection techniques to ensure model robustness across diverse geographical and ecological conditions.

## Dataset

### Data Source
*   **Satellite Imagery:** Sentinel-2 Level-2A (COPERNICUS/S2_SR_HARMONIZED collection via Google Earth Engine). This product provides surface reflectance data, atmospherically corrected.
*   **Study Area:** Thanh Hóa Province, Vietnam.
*   **Time Period for Map Generation:** Images from 2023 were used for generating the final land cover map of Nghi Sơn town.

### Data Collection & Labeling
1.  **Polygon Definition:** Ranh giới (polygon boundaries) for specific land cover types were manually delineated using Google Earth Pro.
2.  **Labeling:** Each polygon was assigned a label corresponding to its land cover type (e.g., forest, water body, urban).
3.  **KML Export:** Labeled polygons were exported as KML files.
4.  **Point Sampling:** Random points were sampled within these polygons.
5.  **Spectral Data Extraction:** Spectral values for all 12 Sentinel-2 bands (B1-B9, B8A, B11, B12 - B10 was excluded as per `S2_SR_HARMONIZED`) for these points were extracted using the Google Earth Engine Python SDK.
6.  **Dataset Creation:** The final dataset consists of geographic coordinates, spectral band values, and land cover labels, exported as a CSV file.
    *   **Training set size:** 11,400 samples
    *   **Test set size:** 2,850 samples

### Land Cover Classes
The model classifies 10 land cover types:
1.  Residential Land (Khu vực dân cư)
2.  Aquaculture (Vùng nuôi trồng thủy sản)
3.  Open Water (Mặt nước tự nhiên)
4.  Forest (Khu vực rừng)
5.  Cropland (Đất nông nghiệp khác)
6.  Rice Paddies (Vùng trồng lúa)
7.  Shrubland (Vùng cây bụi)
8.  Grassland (Đồng cỏ)
9.  Barren Land (Đất trống)
10. Wetlands (Đất ngập nước)

## Methodology

### EDA

### Feature Engineering
Commonly used spectral indices were calculated and added as features to enhance discrimination between land cover types:
*   **NDVI** (Normalized Difference Vegetation Index)
*   **NDWI** (Normalized Difference Water Index)
*   **NDMI** (Normalized Difference Moisture Index)
*   **NDBI** (Normalized Difference Built-up Index)
*   **BSI** (Bare Soil Index)
*   **SAVI** (Soil-Adjusted Vegetation Index)

### Feature Selection
*   **Initial Pruning:** 
*   **SHAP (SHapley Additive exPlanations)**

### Machine Learning Models
*   **Distance-based:**
    *   Support Vector Machine (SVC)
    *   K-Nearest Neighbors (KNN)
*   **Tree-based:**
    *   Random Forest
    *   XGBoost
*   **Ensemble Methods:**
    *   Voting Classifier
    *   Stacking Ensemble
*   **Deep Learning:**
    *   Multi-Layer Perceptron (MLP)
    *   TabPFN

### Hyperparameter Optimization
*   **RandomizedSearchCV:**
*   **Optuna:** 

### Evaluation Metrics
*   Accuracy
*   Precision
*   Recall
*   F1-Score
*   Confusion Matrix
