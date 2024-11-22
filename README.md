# Nearmap DSM Viewer

This project is a web-based application that allows users to fetch and render Digital Surface Model (DSM) data from Nearmap's API using OpenLayers. The application integrates with Nearmap's `staticmap` API to retrieve GeoTIFF files, which are then displayed as raster layers on the map.

---

## Features

- **Interactive Map**: Uses OpenLayers to display a map with OpenStreetMap (OSM) as the base layer.
- **DSM Data Retrieval**: Fetches DSM GeoTIFF files from Nearmap's API based on user-selected locations.
- **Custom Projection Rendering**: Displays DSM data as a static image overlay using OpenLayers' `ImageStatic` source.
- **Dynamic Extent Handling**: Automatically adjusts the map's projection and extent to align with the DSM data.

---

## Prerequisites

1. A valid **Nearmap API Key**.
2. A modern browser (Chrome, Firefox, Edge) with JavaScript enabled.

---

## Installation

1. Clone or download the repository:
   ```bash
   git clone https://github.com/your-repo/nearmap-dsm-viewer.git
   cd nearmap-dsm-viewer
Open the index.html file in a browser.

No additional server setup is required as the project is self-contained in a single HTML file.

Usage
Open the application in your browser.
Enter your Nearmap API Key in the input field at the top left.
Click anywhere on the map to select a location.
Enter a radius (in meters) for the area you want to fetch DSM data for.
Click Render DSM to fetch and display the DSM data as a raster overlay on the map.
Files
index.html: Contains the main application code and layout.
main.js: Implements the map logic and API integration (inline in the HTML).
styles.css: Basic styles for the map and controls (inline in the HTML).
API Details
DSM Coverage API
Used to fetch metadata about available surveys and obtain a transactionToken.

Endpoint: https://api.nearmap.com/staticmap/v2/coverage.json
Parameters:
point: Latitude and longitude of the selected location (e.g., -122.4194,37.7749).
radius: Radius in meters for the area of interest.
resources: Resource type to fetch (DetailDsm).
DSM GeoTIFF API
Used to fetch the GeoTIFF file for a specific survey.

Endpoint: https://api.nearmap.com/staticmap/v2/surveys/{surveyId}/DetailDsm.tif
Parameters:
transactionToken: Token obtained from the Coverage API.
point: Latitude and longitude of the selected location.
radius: Radius in meters for the area of interest.
size: Dimensions of the requested GeoTIFF (e.g., 1024x1024).
Libraries Used
OpenLayers: For rendering the map and integrating custom projections.
Proj4.js: For custom projection support.
Nearmap API: For fetching DSM data.
Known Issues
GeoTIFF Rendering:
The application relies on the ImageStatic source for rendering. Ensure the extent and projection align with the GeoTIFF dimensions.
Browser Restrictions:
Ensure CORS policies are correctly handled when accessing Nearmap's API.
Future Enhancements
Add support for multiple raster data formats.
Integrate better visualization tools for GeoTIFF data.
Add a backend to cache API requests for performance optimization.
License
This project is licensed under the MIT License. See the LICENSE file for details.

Acknowledgments
Nearmap for providing the DSM API.
OpenLayers for the mapping framework.
Proj4.js for handling projections.
vbnet
Copy code






