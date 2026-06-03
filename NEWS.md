AOI 0.3.1.9000 (development version)
=========================

### MAINTENANCE

  * Fixed all `R CMD check` NOTEs:
      - removed the unused `htmlwidgets` import
      - dropped the `VignetteBuilder` field (vignettes are build-ignored)
      - documented package-level help via the `_PACKAGE` sentinel, fixing an invalid Rd alias
      - registered the `zipcodes` dataset as a global variable
      - documented `getFiat()`'s `fip` argument (replacing a stale `bb` entry)
      - converted `LICENSE` to the CRAN MIT stub, with the full text in `LICENSE.md`

AOI 0.3.0 (2023-09)
=========================

### NEW FEATURES

  * Change original OpenStreetMap geocoder to `tidygeocoder` due to new restrictions 
  * Previously, we allowed the following for place based area requests:
       - c(GEO, distance, distance) --> POLYGON
       - c(lat, lng, distance, distance) --> POLYGON
      
  * We now support:
      - c(lat, lng) --> POINT
      - c(lat, lng, distance) --> POLYGON 
  
  * All of these have been moved from aoi_get to aoi_ext which uses:
      - geo
      - xy
      - wh 
      
  * materialize_grid from zonal was moved here and called discritize
  
  * Works with terra not raster objects

AOI 0.2.0 (2021-03)
=========================

### NEW FEATURES

  * `aoi_draw()` - Interactively draw an Area of Interest (AOI) using a `shiny` app.
