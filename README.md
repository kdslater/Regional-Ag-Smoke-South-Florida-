 Project Overview
We aim to leverage the expertise of HAQAST investigators in remote sensing technology to quantify smoke exposure from agricultural burning in South Florida. The repository contains data processing code, analysis scripts, and supplementary materials related to our research paper examining the intersections of environmental exposures, social vulnerability, and health outcomes in South Florida.

Data Sources
1. American Community Survey (ACS)
Demographic and housing data were accessed using the tidycensus R package, which provides a streamlined interface to the U.S. Census Bureau API. We used 5-year ACS estimates to ensure robust data coverage for small geographic units, including census tracts across South Florida.

Data pull specifications:

Variables of interest: e.g., total population, poverty rates, housing characteristics

Geographic level: Census tract

Location: Florida counties located in South Florida

For more details on the specific demographic variables retrieved, refer to the script:
📄 Slater_Ag_Burn_SF_datapull.RMD

More about tidycensus:
https://walker-data.com/tidycensus/

2. NOAA Hazard Mapping System (HMS) Smoke Plumes
Smoke plume data were obtained from the NOAA Hazard Mapping System (HMS), which provides daily shapefiles of satellite-detected smoke plume extents.

Data were accessed directly from the NOAA archive:
https://www.ospo.noaa.gov/products/land/hms.html#data

Key processing steps:

Daily shapefiles were downloaded and read into Python.

Files were filtered by date and region to identify smoke events affecting South Florida.

A plume was counted as affecting a tract if it intersected the census tract centroid.

Processed exposure summaries are available in:
📁 FL_census_tract_HMS_20XX.csv (organized by year)

Each file includes the number of days a plume was detected over each tract.
