# Automated Terrace Mapping via Deep Learning (ResNet-50)

**Lead Engineer:** Ngoma Wise Crepin  
**Project Focus:** Geoinformatics & Soil Erosion Mitigation in Rwanda  

---

## 1. Project Overview

This repository contains a high-fidelity GeoAI pipeline designed to detect and vectorize radical terraces in Rwanda using high-resolution LiDAR data.

By utilizing a **ResNet-50 backbone within a U-Net architecture**, the system achieves high segmentation accuracy in identifying agricultural structures and converting them into professional-grade **ESRI Shapefiles (.shp)**.

This project contributes to soil erosion mitigation, sustainable land management, and geospatial innovation in Rwanda.

---

## 2. Environment & Prerequisites

To replicate this project, use:

- **Google Colab** (Recommended for GPU access)  
- OR a local machine with GPU support  

### Required Libraries & Versions

- Python 3.9+
- TensorFlow 2.15.0+
- OpenCV 4.8.0
- Rasterio 1.3.8
- GeoPandas 0.13.2
- Scikit-Learn 1.2.2
- Shapely 2.0.1

### Installation Command

Run this in your first notebook cell:

```bash
pip install rasterio geopandas leafmap opengeoai lightly opencv-python-headless
```

---

## 3. Google Drive Alignment (CRITICAL)

For the code to execute successfully, you must mirror the following folder structure exactly within your Google Drive.  

The script is hard-coded to look for these paths.

### Required Folder Structure

```
My Drive/
├── Rwandan Radical Terraces/
│   ├── images/       (Place training images here)
│   ├── masks/        (Place ground truth masks here)
│   └── predictions/  (Model outputs saved here)
└── Lidar data/       (Place raw .tif files here)
```

### Folder Details

**Rwandan Radical Terraces/**
- `/images/` → Training image tiles (PNG)
- `/masks/` → Black & white segmentation labels
- `/predictions/` → Leave empty (model outputs saved here)

**Lidar data/**
- Place raw `.tif` orthophotos here
- Files must be georeferenced for proper vectorization

---

## 4. Data Setup Instructions

### Download the Dataset
Obtain the training tiles (Images & Masks) provided via the project source.

### Upload to Drive
- Upload PNG image tiles into `/images/`
- Upload corresponding masks into `/masks/`

### Custom LiDAR Testing
To test new regions:
- Upload georeferenced `.tif` files into `/Lidar data/`
- Ensure CRS (Coordinate Reference System) is properly defined

---

## 5. Execution Workflow

### Step 1 – Mount Drive
Run the initialization cell to grant the notebook access to your Google Drive.

### Step 2 – Train Model
Execute the training cell.  
The trained model will automatically save as:

```
best_model.h5
```

### Step 3 – Inference
Run the `predict_full_lidar` loop to process raw `.tif` orthophotos.

### Step 4 – Vectorization
The final cell:
- Converts predicted masks into `.shp` files  
- Automatically calculates terrace areas  
- Preserves CRS for GIS compatibility  

---

## 6. Technical Keywords & Definitions

### Projection (CRS)
The mathematical system used to flatten the Earth's surface into a 2D map.  
Essential for accurate terrace measurement and area calculation.

### H5 File Format (.h5)
Hierarchical data format used to store the trained model architecture and weights.

### Image Interpolation
Mathematical resizing technique used when scaling imagery.  
This project uses **Bilinear interpolation** to preserve smooth terrain edges.

### Morphology
A set of image processing operations based on shape analysis.  
Used to bridge small gaps and refine detected terrace structures.

---

## 7. Output Products

- Binary segmentation masks  
- Georeferenced raster outputs  
- ESRI Shapefiles (.shp)  
- Automated terrace area statistics  

All outputs are GIS-ready and compatible with professional GIS software.

---

## 8. Technical Support & Contact

Developed as part of a professional GeoAI initiative supporting Rwandan agricultural resilience.

If you encounter issues running the model, feel free to contact:

**Ngoma Wise Crepin**  
LinkedIn: https://linkedin.com/in/wcrepin  
Email: wisecrepin4@gmail.com  
Phone: +250 786 446 516  

---
