# MUSA-6950-Final-Project
# 🚌 AI-Driven Analysis of Trolley Service Gaps in Miami

This project analyzes public transportation service gaps in Miami using AI-assisted spatial techniques. It identifies areas underserved by trolley routes, clusters gap hotspots, and prioritizes neighborhoods based on population and landmark inaccessibility. A Random Forest model is also trained to predict trolley coverage based on geospatial location.

---

## 📌 Project Motivation

Miami’s urban vibrancy relies heavily on accessible public infrastructure, especially public transit. This project was motivated by the need to understand:

- Where trolley service fails to cover important community landmarks.
- Which neighborhoods are underserved in both service and population terms.
- How AI models can support spatial coverage prediction.

---

## 📂 Data Sources

- **Miami Trolley Routes** – Official route shapefiles (`GeoJSON`)
- **Landmarks** – Points of interest including parks, malls, and museums (`GeoJSON` + `CSV`)
- **Neighborhood Boundaries** – Miami neighborhood shapefile (`GeoJSON`)
- **Census Tracts** – Population data by tract (`Shapefile`)
- **NAIP Imagery** – RGB composite from aerial imagery (used in earlier exploratory stages)

---

## 📈 Key Methods & Workflow

1. **Trolley Coverage Analysis**  
   - Buffer (300m) created around trolley lines  
   - Landmarks classified as `Covered` or `Uncovered`

2. **Clustering Underserved Landmarks**  
   - DBSCAN used to group uncovered landmarks  
   - Cluster centroids suggested for future service extension

3. **Neighborhood-Level Analysis**  
   - Spatial join with neighborhood shapefile  
   - Ranking neighborhoods by number of uncovered landmarks

4. **Population Prioritization**  
   - Integrated census tract population estimates  
   - Weighted prioritization by both landmark count and population

5. **Machine Learning: Coverage Prediction**  
   - Sampled ~10,000 random points across Miami  
   - Labeled based on intersection with trolley buffers  
   - Trained Random Forest model to predict coverage using only (x, y) coordinates  
   - Evaluated model prediction vs actual coverage by neighborhood

---

## 🧠 AI Models Used

| Model            | Purpose                                      |
|------------------|----------------------------------------------|
| **DBSCAN**        | Spatial clustering of uncovered landmarks    |
| **Random Forest** | Binary classifier for coverage prediction    |

---

## 📊 Key Findings

- Several high-density neighborhoods lack adequate trolley access.
- Park landmarks are frequently underserved in peripheral areas.
- Population-weighted analysis helps prioritize extension strategies.
- Machine learning can reasonably approximate buffer-based service zones using only spatial coordinates.

---

## 🗺️ Sample Visualizations

- **Uncovered Landmarks Clustered with Centroids**  
- **Neighborhoods Ranked by Service Gap Severity**  
- **Random Forest Coverage Prediction Map**  
- **Actual vs Predicted Coverage by Neighborhood**

---

## 🚀 Future Directions

- Improve model accuracy using engineered spatial features (e.g., proximity to main roads).
- Incorporate real-time transit data (e.g., GTFS feed).
- Explore equity-focused metrics (e.g., income-weighted gap analysis).
- Expand analysis to other city services (e.g., green space, libraries).
