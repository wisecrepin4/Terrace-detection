<div align="right">

Automated Terrace Mapping via Deep Learning (ResNet-50)

Lead Engineer: Ngoma Wise Crepin

Project Focus: Geoinformatics & Soil Erosion Mitigation in Rwanda

1. Project Overview

This repository contains a high-fidelity GeoAI pipeline designed to detect and vectorize radical terraces in Rwanda using high-resolution LiDAR data. By utilizing a ResNet-50 backbone within a U-Net architecture, the system achieves near-perfect accuracy in identifying agricultural structures and converting them into professional-grade ESRI Shapefiles.

2. Environment & Prerequisites

To replicate this project, you must use Google Colab (recommended for GPU access) or a local machine with the following specifications:

Required Libraries & Versions

Python: 3.9+

TensorFlow: 2.15.0+

OpenCV: 4.8.0

Rasterio: 1.3.8

GeoPandas: 0.13.2

Scikit-Learn: 1.2.2

Shapely: 2.0.1

Installation Command

pip install rasterio geopandas leafmap opengeoai lightly opencv-python-headless


3. Google Drive Alignment (CRITICAL)

For the code to execute successfully, you must mirror the following folder structure exactly within your Google Drive. The script is hard-coded to look for these paths.

Root Directory: My Drive/

My Drive/
├── Rwandan Radical Terraces/
│   ├── images/      <-- (Place training images here)
│   ├── masks/       <-- (Place ground truth masks here)
│   └── predictions/ <-- (Model outputs saved here)
└── Lidar data/      <-- (Place raw .tif files here)


4. Data Setup Instructions

Download the Dataset: Obtain the training tiles (Images & Masks) provided via the project source.

Upload to Drive: Upload PNG files to /images/ and /masks/ respectively.

Custom LiDARs: To test new regions, upload georeferenced .tif files into the /Lidar data/ folder.

5. Execution Workflow

Mount Drive: Run the initialization cell to grant access to your Drive.

Train Model: Execute the training cell; the best_model.h5 will save automatically.

Inference: Run the predict_full_lidar loop to process the raw .tif files.

Vectorization: The final cell converts masks into .shp files with automated area calculations.

6. Technical Keywords & Definitions

PROJECTION (CRS): The mathematical system used to flatten
the Earth's surface into a 2D map; essential
for accurate terrace measurement.

H5 FILE FORMAT: A grid-based data format used to store
the weights and architecture of your
trained ResNet-50 model.

IMAGE INTERPOLATION: The math used to resize images; we
use 'Bilinear' to ensure the AI sees
smooth, natural terrain edges.

MORPHOLOGY: A set of image processing operations
that process images based on shapes;
used to bridge gaps in detected terraces.

7. Technical Support & Contact

Developed as part of a professional GeoAI initiative for Rwandan agricultural resilience. In case you find any trouble running this model, you can contact me for technical support.

Lead Engineer: Ngoma Wise Crepin

LinkedIn: linkedin.com/in/wcrepin

Email: wisecrepin4@gmail.com

Phone: +250 786 446 516

</div>
