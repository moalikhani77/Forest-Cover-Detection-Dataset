# 🌲 Forest Cover Detection Dataset (ALOS-2, Sentinel-1, Sentinel-2)
Pixel-level, fully co-registered forest/non-forest dataset generated from synthetic aperture radar (SAR) and optical remote sensing imagery over the **Hyrcanian Green Belt in northern Iran**.

---

## 📍 Study Area
The dataset covers the **Hyrcanian Forests** across the provinces of:

- **Gilan**
- **Mazandaran**
- **Golestan**




###
- All files are **GeoTIFF (.tif)**
- Image size: **256 × 256 px**
- Spatial resolution: **25 m**
- CRS: **EPSG:4326**
- Each sensor contains **650 patches**, including labels

---

## 🛰️ Data Sources and Preprocessing (GEE)

All satellite imagery and the forest cover map were acquired and preprocessed using **Google Earth Engine (GEE)**.  
For temporal consistency, only imagery from **the year 2020** was used, corresponding to the **JRC Global Forest Cover 2020 map**.
### **ALOS-2 (L-band SAR)**
- Global annual mosaic by **JAXA**
- Preprocessed by provider (radiometric corrections, orthorectification)

### **Sentinel-1 (C-band SAR, GRD)**
Includes GEE preprocessing:
- Radiometric calibration  
- dB conversion  
- Orbit correction  
- Thermal noise removal  
- Terrain correction  
- **+ additional circular median filter (30 m)** for speckle reduction

### **Sentinel-2 (Optical Multispectral, Level-2A)**
- Surface Reflectance  
- Cloud masking  
- Removal of aerosol, cirrus, vapor bands  
- Annual mean composite generation  

---

## 🌲 Label Generation
- Binary forest mask created from **JRC Global Forest Cover 2020**  
- Values:
  - **1 = Forest**
  - **0 = Non-Forest**
- All imagery + mask:
  - **Resampled to 25 m**
  - **Cropped to identical extent**
  - **Perfectly co-registered**

---

## 🧩 Patch Extraction
Each patch:
- **256 × 256 px**
- Covers **6.4 × 6.4 km**
- Exported as **GeoTIFF**
- Co-registered across:
  - ALOS-2  
  - Sentinel-1  
  - Sentinel-2  
  - Forest mask  

Total:
- **650 patches per sensor**
- **650 label masks**
- All exported with **CRS EPSG:4326**

---

## 📘 Applications
This dataset is suitable for:
- Pixel-level forest segmentation  
- Land cover mapping  
- SAR-optical fusion studies  
- Lightweight CNN benchmarking  
- Remote sensing deep learning experiments  

---



## 🙌 Acknowledgments
This dataset was generated using:
- **Google Earth Engine**
- **JAXA ALOS-2 PALSAR-2 mosaic**
- **Copernicus Sentinel-1 / Sentinel-2**
- **JRC Global Forest Cover 2020**

      
