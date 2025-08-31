

This repository analyzes ERA5 atmospheric data to detect and map the tropopause using multiple methods, including classical and **internship-developed methods**: stability, hygropause, and hybrid approaches. The analysis includes global maps, vertical profiles, and method comparisons.

---

## Repository Structure

Tropopause/
├─ tropopause-detection-mapping.ipynb # Main notebook
├─ data/ # ERA5 NetCDF input files
├─ outputs/ # Generated plots and results
├─ utils/ # Optional helper scripts
└─ README.md # Documentation

yaml
Copy code

---

## Setup and Usage

### 1. Install Python libraries

pip install netCDF4 xarray numpy matplotlib cartopy metpy scipy
### 2. Download ERA5 data
Pressure-level data: temperature, geopotential, humidity

Complete dataset: 2-PVU tropopause (optional for comparison)

See the Copernicus Climate Data Store (CDS) for instructions.

### 3. Prepare Data
Place the downloaded NetCDF files in the data/ directory and update paths in the notebook if necessary.

### 4. Run the Notebook
Open tropopause-detection-mapping.ipynb and execute all cells. The notebook will:

Load ERA5 data via netCDF4 and xarray.

Compute tropopause heights using all methods: thermal (WMO), dynamic (2 PVU), stability, hygropause, and hybrid.

Generate global maps, vertical profiles, and comparison plots.

Optionally calculate monthly means for selected periods.

Comparison of Tropopause Detection Methods
Method	Example Plot
Thermal (WMO)	
Dynamic (2 PVU)	
Stability	
Hygropause	
Hybrid	

These plots allow a side-by-side comparison of classical and new methods, highlighting differences and improvements from stability, hygropause, and hybrid approaches.

### Results Confirmed
Classical and new methods produce consistent results in mid-latitudes.

Tropical tropopause is higher than polar tropopause across all methods.

Hybrid methods reduce local inconsistencies and smooth extreme values.

Monthly mean analyses provide long-term trend insights for selected periods.

### References
ECMWF ERA5 Reanalysis: https://www.ecmwf.int/en/forecasts/datasets/reanalysis-datasets/era5

Classical tropopause definitions: WMO lapse-rate and 2-PVU dynamic tropopause.

Internship-developed methods: Stability, hygropause, and hybrid tropopause detection.

Best regards,
Mohammed El Abdioui
