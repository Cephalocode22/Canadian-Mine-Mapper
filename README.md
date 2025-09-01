# Canadian-Mine-Mapper
Mapping Canadian mines and metal facilities using open government CKAN datasets, geopandas, and matplotlib.

This project integrates Canada’s open-data CKAN API with geospatial analysis tools to visualize mining and metal processing facilities across the country. Using shapefiles from Natural Resources Canada (900A dataset), the workflow cleans and validates geometry, categorizes facilities by type (smelters, steel mills, shredders, etc.), and groups commodities by metal class (gold, copper, nickel, uranium, etc.). The output is a detailed map overlaying facilities on topographic basemaps with clear color and shape legends. This project highlights how open data and Python geospatial libraries can support materials research, natural resource analysis, and policy decision-making.

# Canadian Mine and Facility Mapper

This project integrates Canada’s open-data CKAN API with geospatial analysis tools to visualize mining and metal processing facilities across the country. It uses shapefiles from Natural Resources Canada’s 900A dataset, applies spatial and attribute-level cleaning, categorizes facility types and commodity groups, and generates a detailed map overlay on a topographic basemap.

## Project Overview

- Connects to the CKAN API to access dataset metadata from the Government of Canada open data portal
- Loads and validates geospatial data from shapefiles
- Filters and standardizes facility categories and commodities
- Plots facilities by shape (facility type) and color (metal group)
- Overlays results on a cartographic basemap with provincial boundaries
- Exports a high-resolution SVG map suitable for publication or presentation

## Data Source

**Dataset**: 900A – Metal Mining Facilities  
**Source**: [open.canada.ca](https://open.canada.ca/data/en/dataset/000183ed-8864-42f0-ae43-c4313a860720)  
**Dataset ID**: `000183ed-8864-42f0-ae43-c4313a860720`  
**Format**: ESRI Shapefile (`.shp`)

**Note**: You must manually download and extract the shapefile and place it into the `data/` directory. For example:

Facility and Metal Categorization

Facilities are categorized by type using the Type_ field and assigned a unique shape:

Smelter: Circle

Shredder: Square

Steel Mill: Triangle

Alloy Facility: Star

Commodities are categorized based on keywords in the CommodityE field and grouped into simplified metal types such as:

Gold, Silver, Copper, Nickel, Zinc, Lead, Uranium, Cobalt, etc.

Both types and metals are used to produce shape-coded and color-coded legends in the final map.

Technologies Used

geopandas for spatial data handling

matplotlib for plotting

contextily for basemaps

requests for CKAN API interaction

pyproj for coordinate transformations

pandas, numpy for tabular data handling

Output Example

The resulting SVG map shows Canadian facilities across all provinces, with visual grouping by facility function and extracted metals. The visualization is suitable for:

Research publications

Cleantech dashboards

Educational materials

Policy analysis in resource management

License

This project is released under the MIT License. See the LICENSE
 file for details.

Author

Colin Tadgell
PhD Materials Engineer | Geospatial Data Analyst
GitHub: Cephalocode22

LinkedIn: colin-tadgell

Future Work

Export interactive maps using Folium or Bokeh

Create web dashboards using Streamlit or Panel

Add filters by commodity, province, or company

Integrate real-time production and emissions data
