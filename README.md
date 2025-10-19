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

 [1] ECMWF. (2024). Reintroducing analysis humidity in the stratosphere. Retrieved
 from
 https://www.ecmwf.int/en/newsletter/183/earth-system-science/
 reintroducing-analysis-humidity-stratosphere
 [2] ECMWF. (2024). IFS Documentation- Cy49r1, Part IV: Physical
 Processes.
 Operational
 from
 implementation
 12
 November
 2024.
 Retrieved
 https://www.ecmwf.int/sites/default/files/elibrary/112024/
 81626-ifs-documentation-cy49r1-part-iv-physical-processes.pdf
 [3] Elmer, N. J., Berndt, E., Jedlovec, G., & Fuell, K. (2019). Limb Correction of Geosta
tionary Infrared Imagery in Clear and Cloudy Regions to Improve Interpretation of RGB
 Composites for Real-Time Applications. Journal of Atmospheric and Oceanic Technology,
 36(8), 1675-1690. DOI: https://doi.org/10.1175/JTECH-D-18-0206.1
 [4] Hoskins, B. J., McIntyre, M. E., & Robertson, A. W. (1985). On the use and significance
 of isentropic potential vorticity maps. Quarterly Journal of the Royal Meteorological
 Society, 111(470), 877-946. DOI: https://doi.org/10.1002/qj.49711147002
 [5] ECMWF. (2024). ERA5: Fifth generation of ECMWF atmospheric reanalyses of
 the global climate. Retrieved from https://www.ecmwf.int/en/forecasts/datasets/
 reanalysis-datasets/era5
 [6] European Centre for Medium-Range Weather Forecasts (ECMWF). (2024). Official web
site. Retrieved from https://www.ecmwf.int
 [7] Santer, B. D., Wehner, M. F., Wigley, T. M. L., Sausen, R., Meehl, G. A., Taylor,
 K. E., ...& Branson, M. (2004). Contributions of anthropogenic and natural forcing to
 recent tropopause height changes. Science, 301(5632), 479-483. DOI: https://doi.org/
 10.1126/science.1084123
 [8] World Meteorological Organization (WMO). (1957). Definition of the tropopause. WMO
 Bulletin, 6(4), 136-137.
 39
Tropopause Detection and Analysis
 DGM &ECMWF&EHTP
 [9] Hoinka, K. P. (1998). Statistics of the global tropopause pressure. Monthly Weather
 Review, 126(12), 3303-3325. DOI: https://doi.org/10.1175/1520-0493(1998)
 126<3303:SOTGTP>2.0.CO;2
 [10] ECMWF. (2023). Hybrid tropopause detection methods in the IFS. ECMWF Technical
 Memorandum No. 987.
 [11] Wang, Z., Bovik, A. C., Sheikh, H. R., & Simoncelli, E. P. (2004). Image quality as
sessment: From error visibility to structural similarity. IEEE Transactions on Image
 Processing, 13(4), 600-612. DOI: https://doi.org/10.1109/TIP.2003.819861
 [12] Gonzalez, R. C., & Woods, R. E. (2018). Digital Image Processing (4th ed.). Pearson
 Education. Chapter 5: Image Restoration and Reconstruction.
 [13] Lewis, J. P. (1995). Fast normalized cross-correlation. Vision Interface, 10(1), 120-123.
 [14] Hore, A., & Ziou, D. (2010). Image quality metrics: PSNR vs. SSIM. In 2010 20th
 International Conference on Pattern Recognition (pp. 2366-2369). IEEE. DOI: https:
 //doi.org/10.1109/ICPR.2010.579
 [15] Theodoridis, S., & Koutroumbas, K. (2008). Pattern Recognition (4th ed.). Academic
 Press. Chapter 7: Feature Generation II.
 [16] Szeliski, R. (2010). Computer Vision: Algorithms and Applications. Springer Science &
 Business Media. Chapter 8: Dense motion estimation.
 [17] Oppenheim, A. V., & Schafer, R. W. (2009). Discrete-Time Signal Processing (3rd ed.).
 Pearson Education. Chapter 7: Filter Design Techniques.
---

## Contact

For questions or help with this project, you can contact me at: **mohamedabdioui0@gmail.com**

Best regards,  
Mohammed El Abdioui
