## Handling Rasters in PostGIS  
by Alen Mangafić and Tomaž Žagar, Geodetic Institute of Slovenia  
27 August 2019, Bucharest (FOSS4G Workshop)

### Overview

This tutorial provides a structured walkthrough of raster support in PostGIS. It includes importing, aligning, processing, analyzing, and exporting rasters using SQL, with optional integration of external tools (R, SAGA GIS, GDAL, etc.). The exercises are designed for use in Jupyter and follow a real-world workflow using LiDAR-derived terrain models and imagery. All content is structured in notebooks with SQL and system calls embedded.

### Table of Contents

- `00_Intro.ipynb` – Environment initialization and connection test. Prepares the database and validates PostGIS raster support.  
- `01_Exercise_1.ipynb` – Demonstrates importing rasters into PostGIS with `raster2pgsql`, tiling, indexing, and visualization in QGIS. Includes patching and alignment using `ST_Resample`, `ST_Union`, and `ST_Clip`.  
- `02_Exercise_2.ipynb` – Introduces raster access and analysis with R using `rpostgis`, `raster`, and `rgdal`. Performs NDVI computation and k-means classification, and writes results back to PostGIS. Also includes a SAGA segmentation example via command-line.  
- `03_Exercise_3.ipynb` – Explores raster export options. Covers use of `ST_AsGDALRaster`, `ST_AsTIFF`, and export with `gdal_translate`. Discusses raster constraints and proper use of `AddRasterConstraints` for efficient I/O.  
- `04_Exporting_rasters.ipynb` – Additional examples of raster serialization and export, including direct SQL-based outputs and web-service integration options.  
- `examples_patch.ipynb` – Demonstrates manual pixel alignment and patch updates between two rasters. Focuses on `ST_SameAlignment`, `ST_Resample`, `ST_Union`, and `ST_Clip` workflows with tile-level logic.  
- `examples_union.ipynb` – Shows merging of multiple raster tables using `ST_Union` and common alignment handling. Introduces view-based strategies for memory-efficient mosaicking.  
- `plpgsql_helpers.ipynb` – Contains utility PL/pgSQL functions used across notebooks (e.g., visualization helpers, iteration logic).  
- `sql_magics.ipynb` – Enables use of SQL magic commands (`%%sql`, `%sql`) within Jupyter via IPython-sql, allowing direct SQL queries inside notebooks.
