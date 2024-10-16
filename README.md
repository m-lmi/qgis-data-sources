# qgis-data-sources
Collection of WMS, WMTS, WFS, XYZ, REST and more connections to get data for QGIS

# Geospatial Web Services Repository connected with Iceland and Europe

This repository contains a curated collection of public geospatial web services, including **WMS**, **WFS**, **WMTS**, **XYZ** tile servers, **CSW**, **OWS**, and **REST** services. These services are widely used in web mapping applications and geospatial analysis, providing access to various geographic datasets such as satellite imagery, weather data, elevation models, and more.

## Table of Contents
- [Introduction to Web Services](#introduction-to-web-services)
  - [What is WMS?](#what-is-wms)
  - [What is WFS?](#what-is-wfs)
  - [What is WMTS?](#what-is-wmts)
  - [What is XYZ Tile Server?](#what-is-xyz-tile-server)
  - [What is CSW?](#what-is-csw)
  - [What is OWS?](#what-is-ows)
  - [What is REST?](#what-is-rest)
- [Repository Content](#repository-content)
  - [Public Connections](#public-connections)
- [Usage Instructions](#usage-instructions)
- [Contributions](#contributions)
- [License](#license)

---

## Introduction to Web Services

Geospatial web services allow the sharing and retrieval of spatial data across the internet in standard formats, enabling users to interact with maps and spatial data seamlessly in applications like Leaflet, OpenLayers, QGIS, ArcGIS, etc.

### What is WMS?

**Web Map Service (WMS)** is a standard protocol for serving georeferenced map images over the internet. These images are generated on-the-fly based on data stored in a server. WMS provides a way to request maps as rendered images (e.g., PNG, JPEG) with user-specified parameters like layers, styles, and coordinate bounds.

- **How it works**: A WMS request typically asks for a specific geographic area (bounding box) and map layers. The server then renders this data as an image.
- **Example usage**: 
  ```url
  https://example.com/wms?service=WMS&request=GetCapabilties

### What is WFS?

**Web Feature Service (WFS)** allows users to query and retrieve geospatial data in vector format (e.g., GeoJSON, GML). Unlike WMS, which returns rendered images, WFS returns actual geographic features (points, lines, polygons) that can be used for analysis or further processing.

- **How it works**: WFS requests allow users to filter features (e.g., select all points within a region) and retrieve data in a format that can be manipulated on the client-side.
- **Example usage**:
  ```url
  https://example.com/wfs?service=WFS&request=GetCapabilities

### What is WMTS?

**Web Map Tile Service (WMTS)** is a standard for serving map tiles, which are pre-rendered images divided into a grid. This format is optimized for fast display in mapping applications. WMTS is ideal for large datasets (e.g., global satellite imagery) because it allows maps to be loaded quickly by retrieving only the tiles visible on the screen.

- **How it works**: WMTS divides the map into fixed zoom levels and tiles. Each tile is a small image covering a portion of the map, allowing clients to load only the necessary tiles at a given zoom level.
- **Example usage**:
  ```url
  https://example.com/wmts?service=WMTS&request=GetCapabilities

### What is XYZ Tile Server?

**XYZ Tile Servers** are similar to WMTS, but they use a simple URL scheme for serving map tiles. The URL typically contains placeholders for zoom level, tile row, and tile column. XYZ tiles are commonly used in web maps due to their simplicity and wide adoption.

- **How it works**: XYZ tiles are requested with a URL pattern like `/zoom_level/tile_row/tile_column`. The map client computes which tiles are needed based on the zoom level and viewport.
- **Example usage**:
  ```url
  https://example.com/tiles/{z}/{x}/{y}.png

### What is CSW?

**Catalog Service for the Web (CSW)** is a standard for discovering and retrieving metadata records of geospatial datasets and services. CSW provides a way to query catalogs of datasets based on keywords, bounding boxes, or other criteria. It is often used in Spatial Data Infrastructures (SDI) and portals that aggregate geospatial data from various sources.

- **How it works**: CSW allows querying metadata about datasets and services. It supports various query types, including keyword search and spatial searches.
- **Example usage**:
  ```url
  https://example.com/csw?service=CSW&request=GetRecords&query=climate

### What is OWS?

**OGC Web Services (OWS)** is a broader term encompassing a variety of geospatial services defined by the Open Geospatial Consortium (OGC), including WMS, WFS, WMTS, CSW, and others. OWS enables interoperability between geospatial software systems by using standardized service interfaces.

- **How it works**: OWS services provide data in various formats (raster, vector, or metadata) and support operations like querying, rendering, and downloading geospatial data.
- **Example usage**: OWS refers to many different services, and the example usage depends on the type of service (WMS, WFS, etc.).

### What is REST?

**REST (Representational State Transfer)** is an architectural style used for designing networked applications. In the context of geospatial services, REST services provide a way to access geospatial data or perform operations (e.g., querying, filtering) through HTTP requests using simple, human-readable URLs.

- **How it works**: A RESTful service responds to requests for resources (e.g., spatial data) in standard formats such as JSON, GeoJSON, or XML. It supports operations like reading, writing, updating, and deleting geographic data.
- **Example usage**:
  ```url
  https://example.com/rest/api/layer_name?bbox=lon_min,lat_min,lon_max,lat_max&format=geojson

## Repository Content

This repository provides a curated list of public WMS, WFS, WMTS, XYZ tile services, CSW, OWS, and REST APIs, allowing easy access to various geospatial datasets. These services can be used in mapping libraries such as Leaflet, OpenLayers, and GIS software like QGIS or ArcGIS.

### Public Connections

- **WMS Services**: A collection of public Web Map Services (WMS) providing access to layers such as satellite imagery, weather data, elevation models, and more.
- **WFS Services**: A set of Web Feature Services (WFS) providing access to vector data, such as points, lines, and polygons for geospatial analysis.
- **WMTS Services**: A list of Web Map Tile Services (WMTS) optimized for fast map rendering, providing tiled map data.
- **XYZ Tile Servers**: A collection of public XYZ tile servers for easy access to tiled base maps.
- **CSW Services**: Public Catalog Services for the Web (CSW) that allow discovery of geospatial datasets through metadata.
- **OWS**: A collection of OGC Web Services (OWS) providing access to various geospatial datasets.
- **REST APIs**: A list of RESTful geospatial services offering access to spatial data in various formats like GeoJSON.

Each service includes its endpoint and a brief description of the available layers and data.

## Usage Instructions

To use these services in your web or GIS application, follow these steps:

1. **Choose a Service**: Select a service from the list, depending on whether you need raster imagery (WMS/WMTS/XYZ) or vector features (WFS/REST/CSW).

2. **Add to Mapping Application**:
   - In **Leaflet/OpenLayers**, use the appropriate URL to add the service as a layer.
   - In **QGIS**, you can add the service by entering the provided URL in the respective tool for adding web services or by directly downloading the specific XML and importing it into QGIS.

3. **Explore the Data**: Once the service is added, you can explore the map data in your application, use it for analysis, or visualize it in combination with other datasets.

Feel free to contribute to this repository by adding new public connections or updating existing ones.

## Contributions

We welcome contributions! Please feel free to submit pull requests for adding new public geospatial services or fixing any issues with the existing services. Make sure to include a description of the service and any relevant details.

## License

This project is licensed under the **GPU License v3.0**. Please review the LICENSE file for more information.

