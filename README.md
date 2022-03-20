# Mapping_Earthquakes

   ![0 09889000_1594303909_earthquake](https://user-images.githubusercontent.com/89308251/142531397-65170d28-48de-4c22-8f18-5028ffc43818.jpg)


## Challenge Overview

### Purpose:

  The purpose of this analysis is to use JavaScript's Leaflet library along with the Mapbox API to create visualizations of GeoJSON earthquake data from the [U.S. Geological Survey](https://www.usgs.gov/natural-hazards/earthquake-hazards/earthquakes). The user will be able to select from 3 different map styles, street view, satellite view, and dark view. The user will also be able to toggle earthquakes in the past 7 days, tectonic plate lines, and major earthquake (magnitude greater than 4.5) locations.

## Resources
- Software:
   - Visual Studio Code 1.61.2
   - HTML/CSS
   - JavaScript
     - [Leaflet library](https://leafletjs.com/examples/quick-start/)
     - [D3.js library](https://d3js.org/)
   - [Mapbox API](https://docs.mapbox.com/help/glossary/static-tiles-api/)

- Data sources: 
   - GeoJSON data
     - [Earthquakes Past 7 Days](https://earthquake.usgs.gov/earthquakes/feed/v1.0/summary/all_week.geojson)
     - [Earthquakes with a magnitude greater than 4.5](https://earthquake.usgs.gov/earthquakes/feed/v1.0/summary/4.5_week.geojson) 
     - [Tectonic Plate](https://raw.githubusercontent.com/fraxen/tectonicplates/master/GeoJSON/PB2002_boundaries.json)

## Results 

- **The interactive features**

  - Earthquakes with tectonic plates

    ![EQ_with_TectonicPlates](https://user-images.githubusercontent.com/89308251/142570276-08c1eb1b-b7d1-4363-9713-c4b649ec3fa8.png)


  - Major Earthquakes with tectonic plates

    ![MajorEQ_with_TectonicPlates](https://user-images.githubusercontent.com/89308251/142570285-e4da0d74-f443-4e0c-976c-30fd13db28ac.png)



  - [Mapbox Styles](https://docs.mapbox.com/api/maps/styles/)

     - Streets Style: 

        ```
        let streets = L.tileLayer('https://api.mapbox.com/styles/v1/mapbox/streets-v11/tiles/{z}/{x}/{y}?access_token={accessToken}', {
          attribution: 'Map data &copy; <a href="https://www.openstreetmap.org/">OpenStreetMap</a> contributors, <a href="https://creativecommons.org/licenses/by-sa/2.0/">CC-BY-SA</a>, Imagery (c) <a href="https://www.mapbox.com/">Mapbox</a>',
          maxZoom: 18,
          accessToken: API_KEY
        });
        ```

        ![1 streets_style](https://user-images.githubusercontent.com/89308251/142570080-f1282138-a398-4161-a1eb-003f9b9bc234.png)


     - Satellite Streets Style: 

        ```
        let satelliteStreets = L.tileLayer('https://api.mapbox.com/styles/v1/mapbox/satellite-streets-v11/tiles/{z}/{x}/{y}?access_token={accessToken}', {
          attribution: 'Map data &copy; <a href="https://www.openstreetmap.org/">OpenStreetMap</a> contributors, <a href="https://creativecommons.org/licenses/by-sa/2.0/">CC-BY-SA</a>, Imagery (c) <a href="https://www.mapbox.com/">Mapbox</a>',
          maxZoom: 18,
          accessToken: API_KEY
        });
        ```

        ![2 satellite_style](https://user-images.githubusercontent.com/89308251/142570112-3475cf57-c58b-43ec-a795-91f75ea884f4.png)


     - Dark Style:

        ```
        let dark = L.tileLayer('https://api.mapbox.com/styles/v1/mapbox/dark-v10/tiles/{z}/{x}/{y}?access_token={accessToken}', {
          attribution: 'Map data &copy; <a href="https://www.openstreetmap.org/">OpenStreetMap</a> contributors, <a href="https://creativecommons.org/licenses/by-sa/2.0/">CC-BY-SA</a>, Imagery (c) <a href="https://www.mapbox.com/">Mapbox</a>',
          maxZoom: 18,
          accessToken: API_KEY
        });
        ```

        ![3 dark_style](https://user-images.githubusercontent.com/89308251/142570131-39f396a5-9b02-4ff7-bb2e-58e7da7633fd.png)


## Summary

- **This earthquakes map** was built with earthquake data from around the world which came from the last seven days of earthquake GeoJSON data. 
- **On the map,** 
   - The magnitude and the location of each earthquake will be shown in a popup marker. 
   - The diameter of the markers for each earthquake will reflect the magnitude of the earthquakes in their size and color. 
   - Earthquakes with higher magnitudes will appear larger and darker in color with a legend providing the context for the map data. 
   - Finally, to illustrate the relationship between the location and frequency of seismic activity and tectonic plates, I added fault lines in the map.
