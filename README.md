# Project: Monsoon Data Interpolation Using AWS Scraped Data in QGIS


## Overview

This project involves processing and visualizing monsoon data using QGIS (Geographic Information System) tools. The data, scraped from AWS (Automatic Weather Station), is used to generate shapefiles, create a boundary, and apply interpolation techniques to create meaningful visualizations.

## Objectives
The primary tasks of the project include:
1. **Generate a shapefile**: Create a point shapefile using the provided monsoon data.
2. **Generate a boundary shapefile**: Create a boundary that encompasses all the points in the point shapefile.
3. **Apply Interpolation Techniques**:
   - **IDW (Inverse Distance Weighting)**: Interpolate the monsoon data over the boundary using the IDW technique.
   - **TIN (Triangulated Irregular Network)**: Interpolate the monsoon data over the boundary using the TIN technique.
4. **Prepare maps**: Visualize the results of the interpolation methods by preparing maps for each technique.

---

## Project Workflow

### 1. Prerequisites
- **QGIS Installation**: Ensure you have QGIS installed (version 3.16 or higher is recommended). You can download it from [here](https://qgis.org/en/site/forusers/download.html).
- **AWS Data**: Have the monsoon data in CSV format, scraped from AWS.
- **Interpolation Plugins**: Install necessary plugins for IDW and TIN interpolation if not already available in QGIS.

### 2. Generating the Point Shapefile
- **Step 1**: Load the scraped AWS data into QGIS by importing the CSV file.
- **Step 2**: Ensure the CSV file contains the following columns:
  - Latitude
  - Longitude
  - Monsoon data (e.g., rainfall, humidity, temperature, etc.)
- **Step 3**: Right-click on the CSV file in QGIS > `Export` > `Save Features As` > Choose "Shapefile" as the format, and save it as a point shapefile.

### 3. Generating the Boundary Shapefile
- **Step 1**: Using the point shapefile, create a convex hull or buffer polygon that covers all the points.
- **Step 2**: Go to `Vector` > `Geoprocessing Tools` > `Convex Hull` or use `Buffer` to generate the boundary polygon that encompasses all points.
- **Step 3**: Save the boundary polygon as a separate shapefile.

### 4. Applying Interpolation Techniques
- **IDW Interpolation**:
  - **Step 1**: Go to `Raster` > `Interpolation` > `IDW` in QGIS.
  - **Step 2**: Select the point shapefile and the monsoon data attribute (e.g., rainfall) as the field for interpolation.
  - **Step 3**: Set the interpolation parameters (e.g., distance coefficient) and run the IDW interpolation.
  - **Step 4**: Save the interpolated surface as a raster layer.

- **TIN Interpolation**:
  - **Step 1**: Go to `Raster` > `Interpolation` > `TIN` in QGIS.
  - **Step 2**: Select the point shapefile and the monsoon data attribute (e.g., rainfall) for TIN interpolation.
  - **Step 3**: Run the TIN interpolation and save the output raster layer.

### 5. Preparing the Maps
- **Step 1**: Style the interpolated layers (IDW and TIN) for better visualization:
  - Right-click on the raster layer > `Properties` > `Symbology` and adjust the color ramps to reflect the intensity of the monsoon data.
- **Step 2**: Add labels, legends, and other map elements using the `Print Layout` tool in QGIS.
- **Step 3**: Export the final maps as images or PDFs for documentation.

---

## Files in the Repository
- `aws_monsoon_data.csv`: The scraped monsoon data in CSV format.
- `monsoon_point_shapefile.shp`: Generated point shapefile from the CSV data.
- `monsoon_boundary_shapefile.shp`: Generated boundary shapefile covering all points.
- `idw_interpolation_map.qgs`: QGIS project file for the IDW interpolation map.
- `tin_interpolation_map.qgs`: QGIS project file for the TIN interpolation map.
- `output_maps/`: Folder containing exported maps of the interpolation results.

---

## Requirements
- QGIS (version 3.16 or higher)
- AWS data in CSV format
- Python (optional for advanced processing or automation)

---

## References
- QGIS Documentation: [https://qgis.org/en/docs/](https://qgis.org/en/docs/)
- IDW Interpolation Guide: [QGIS IDW Guide](https://docs.qgis.org/3.16/en/docs/user_manual/processing_algs/qgis/interpolation.html)
- TIN Interpolation Guide: [QGIS TIN Guide](https://docs.qgis.org/3.16/en/docs/user_manual/processing_algs/qgis/interpolation.html)

---

## License
This project is licensed under the MIT License.
