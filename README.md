# Tropopause Detection and Mapping

This Jupyter notebook analyzes atmospheric data using **ERA5 reanalysis files**. It calculates tropopause heights using multiple methods, including classical and **internship-developed methods**: stability, hygropause, and hybrid approaches. The analysis helps visualize global tropopause patterns, vertical profiles, and method comparisons, giving researchers insights into the structure and variability of the tropopause.

---

## Libraries Used
- **netCDF4**: Core library for reading and handling ERA5 NetCDF files.
- **xarray**: For working with multidimensional ERA5 data arrays.
- **numpy**: Numerical operations and array manipulations.
- **matplotlib.pyplot**: 2D visualizations of tropopause data.
- **matplotlib.colors / matplotlib.patches / matplotlib.ticker**: Custom colormaps, legends, and axis formatting.
- **cartopy.crs / cartopy.feature**: Geospatial projections and map features (coastlines, borders).
- **scipy.ndimage**: Gaussian filtering to smooth data.

---

## Tropopause Detection Methods
The notebook implements several tropopause detection methods:

1. **Thermal (WMO) method**: Cold-point/lapse-rate tropopause from ERA5 temperature profiles.
2. **Dynamic (2 PVU) method**: 2-PVU surface as the dynamical tropopause.
3. **Stability-based method**: Uses atmospheric static stability to locate tropopause.
4. **Hygropause-based method**: Identifies tropopause using humidity/moisture profiles.
5. **Hybrid methods**: Combines multiple criteria (stability + hygropause) for robust detection.

Each method calculates tropopause height across all ERA5 grid points and produces visualizations for **single time steps** and **monthly means**.

---

## Internship Notebook
The main Jupyter notebook, `tropopause-detection-mapping.ipynb`, includes:

- Data loading from ERA5 NetCDF files.
- Tropopause calculation using all detection methods.
- Visualization of global tropopause maps, vertical profiles, and method comparisons.
- Notes on challenges, failures, and lessons learned during method development.
- Output generation for both single snapshots and monthly mean analyses.

---

## Setup and Usage

### 1. Install Python libraries
bash:
pip install netCDF4 xarray numpy matplotlib cartopy metpy scipy

## 2. Download ERA5 Data

- **Pressure-level data:** temperature, geopotential, humidity  
- **Complete dataset:** 2-PVU tropopause (optional for comparison)  

See the [Copernicus Climate Data Store (CDS)](https://cds.climate.copernicus.eu/) for instructions.

---

## 3. Prepare Data

Place the downloaded NetCDF files in the `data/` directory and update paths in the notebook if necessary.

---

## 4. Run the Notebook

Open `tropopause-detection-mapping.ipynb` and execute all cells. The notebook will:

- Load ERA5 data via **netCDF4** and `xarray`.  
- Compute tropopause heights using all methods.  
- Generate global maps, vertical profiles, and comparison plots.  
- Optionally calculate monthly means for selected periods.

---

## Comparison of Tropopause Detection Methods

These visualizations allow a **side-by-side comparison** of classical and new methods, highlighting differences and improvements from stability, hygropause, and hybrid approaches.

---

## Vertical Profiles

- Single-location tropopause detection along latitude or longitude.  
- Comparison of tropopause heights for different methods.

---

## Results Confirmed

- Classical and new methods produce consistent results in mid-latitudes.  
- Tropical tropopause is higher than polar tropopause across all methods.  
- Hybrid methods reduce local inconsistencies and smooth extreme values.  
- Monthly mean analyses provide long-term trend insights for selected periods.

---

## References

- ECMWF ERA5 Reanalysis: [https://www.ecmwf.int/en/forecasts/datasets/reanalysis-datasets/era5](https://cds.climate.copernicus.eu/datasets/reanalysis-era5-pressure-levels?tab=download)  
- Classical tropopause definitions: WMO lapse-rate and 2-PVU dynamic tropopause.  
- Internship-developed methods: Stability, hygropause, and hybrid tropopause detection.

---

## Contact

For questions or help with this project, you can contact me at: **mohamedabdioui0@gmail.com**

Best regards,  
Mohammed El Abdioui
