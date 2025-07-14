# Potentiel vorticity
This notebook analyzes atmospheric data , It calculates brightness temperature differences, zonal means, and potential vorticity to identify tropopause pressure levels. The analysis helps visualize temperature, ozone, and wind patterns across various pressure levels in the atmosphere. All plots represent data for January 1, 2010, at 00:00 UTC, but the time can be modified by using the appropriate ERA5 dataset file. Future enhancements will include plotting monthly mean data for better long-term trend analysis.

Libraries Used:
xarray: For working with multidimensional arrays, especially atmospheric data like temperature, ozone, and winds.

matplotlib.colors: For defining color maps in data visualizations.

numpy: For numerical operations and array manipulations like temperature differences and zonal means.

matplotlib.pyplot: For creating 2D visualizations of the data.

cartopy.crs: For geospatial projections in visualizing data on maps.

cartopy.feature: Adds map features like coastlines and borders to plots.

matplotlib.patches: Used for custom shapes or markers on plots, such as custom legends or regions.

matplotlib.ticker: Formats tick marks on axes, such as latitudes, longitudes, or pressure levels.

scipy.ndimage: Uses gaussian_filter to smooth or blur noisy data.
