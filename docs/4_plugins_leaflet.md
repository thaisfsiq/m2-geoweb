

<img src="http://leafletjs.com/docs/images/logo.png" width="100">     
       

 
### Lealfet Plugins
  > 
* 
 Plugins
  [http://leafletjs.com/plugins.html](http://leafletjs.com/plugins.html)




### Práctica: Buscador de Farmacias
      
 *  Creamos archivo **farmacias.html**
 *  Visualizamos geojson en **/web/datos/farmacias.geojson**
 *  Utilizaremos directaments pluguin GeoJSON AJAX [https://calvinmetcalf.github.io/leaflet-ajax/dist/leaflet.ajax.js](https://calvinmetcalf.github.io/leaflet-ajax/dist/leaflet.ajax.js) 
 *  Descargaremos plugin [https://github.com/stefanocudini/leaflet-search"](leaflet-Search) 
 

```html
    <html lang="es">
    <head>
      <title>Farmacias</title>
      <meta charset="utf-8" />
      <meta name="viewport" content="width=device-width, initial-scale=1.0">
      <meta name="author" content="autor" />
      <meta name="description" content="descripción página">
      <meta name="robots" content="index,follow">
      <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/leaflet/0.7.7/leaflet.css" />
      <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.2.1/jquery.min.js"></script>
      <script>
L_PREFER_CANVAS = true;
      </script>
      <script src="https://cdnjs.cloudflare.com/ajax/libs/leaflet/0.7.7/leaflet.js"></script>
      <script src="https://calvinmetcalf.github.io/leaflet-ajax/dist/leaflet.ajax.js"></script>
    <!--
      <script src="js/leaflet-search.src.js"></script>
      <link rel="stylesheet" href="css/leaflet-search.min.css" />
    -->
      <style>
body {
margin: 0;
padding: 0;
overflow: hidden;
}

#map {
height: 100%;
width: 100%;
}
      </style>
      <script>
var map, osm, esri;
var geojson, farmacias;
var controlCapas;
var controlEscala;
$(document).ready(function() {

map = L.map('map', {
  center: [41.3954, 2.16859],
  zoom: 14
});
esri = L.tileLayer(
  'http://server.arcgisonline.com/ArcGIS/rest/services/World_Imagery/MapServer/tile/{z}/{y}/{x}', {
    maxZoom: 17,
    minZoom: 1,
    attribution: 'Tiles © Esri',
  }).addTo(map);

osm = L.tileLayer('http://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
  maxZoom: 19,
  minZoom: 1,
  attribution: 'OSM'
});

    /*
farmacias = new L.GeoJSON.AJAX('datos/farmacias.geojson', {
  maxZoom: 19,
  minZoom: 14,
  onEachFeature: function(feature, layer) {
    popupContent = "<b>" + feature.properties.NOM + "</b><br>" + feature.properties.CARRCADAST + " " + feature.properties.DOORNUM + "</b>";
    layer.bindPopup(popupContent);
  },
  pointToLayer: function(feature, latlng) {
    return L.circleMarker(latlng, {
      radius: 6,
      fillColor: "#00ff00",
      color: "#ffffff",
      weight: 3,
      opacity: 1,
      fillOpacity: 0.8
    });
  }
}).addTo(map);
    */
var baseMaps = {
  "Orto_esri": esri,
  "Mapa_osm": osm
};
/*
      		var overlayMaps = {
      "locales": locales
      		};
      */
controlCapas = L.control.layers(baseMaps, null);
controlCapas.addTo(map);
controlEscala = L.control.scale();
controlEscala.addTo(map);

    /*

var searchControl = new L.Control.Search({
  layer: farmacias,
  propertyName: 'NOM',
  circleLocation: true
});

map.addControl(searchControl);
    */

});
      </script>
    </head>
    <body>
      <div id="map"></div>
    </body>
    </html>

```  
   Se usa para crear y manipular el mapa. 
   El mapa por defecto tiene dos controles: uno de zoom y uno de atribución.

### Callejero
  > 
 *  Creamos archivo **calles.html**
 *  Descargaremos plugin [https://github.com/MuellerMatthew/L.GeoSearch](GeoSearch) 
 

```html
    <html lang="es">
  <head>
    <title>Calles</title>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="author" content="autor" />
    <meta name="description" content="descripción página">
    <meta name="robots" content="index,follow">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/leaflet/0.7.7/leaflet.css" />
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.2.1/jquery.min.js"></script>
    <script>
      L_PREFER_CANVAS = true;
    </script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/leaflet/0.7.7/leaflet.js"></script>

    <!--

    <script src="js/l.control.geosearch.js"></script>
    <script src="js/l.geosearch.provider.openstreetmap.js"></script>
    <link rel="stylesheet" href="css/l.geosearch.css" />
  -->

    <style>
      body {
margin: 0;
padding: 0;
overflow: hidden;
      }

      #map {
height: 100%;
width: 100%;
      }
    </style>
    <script>
      var map, osm, esri;
      var geojson, farmacias;
      var controlCapas;
      var controlEscala;


      $(document).ready(function() {

map = L.map('map', {
center: [41.3954, 2.16859],
zoom: 14
});


esri = L.tileLayer(
'http://server.arcgisonline.com/ArcGIS/rest/services/World_Imagery/MapServer/tile/{z}/{y}/{x}', {
  maxZoom: 17,
  minZoom: 1,
  attribution: 'Tiles © Esri',
}).addTo(map);

osm = L.tileLayer('http://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
maxZoom: 19,
minZoom: 1,
attribution: 'OSM'
});


var baseMaps = {
"Orto_esri": esri,
"Mapa_osm": osm
};

controlCapas = L.control.layers(baseMaps, null);
controlCapas.addTo(map);

/*
      new L.Control.GeoSearch({
provider: new L.GeoSearch.Provider.OpenStreetMap()
      }).addTo(map);
*/

      });
      </script>
      </head>
      <body>
    <div id="map"></div>
    </body>
    </html>
```
       
### Leaflet + GeoNames

      
 * Crearemos el archivo **geonames.html**

 

```html
    <html>
  <head lang="es">
    <title>GeoNames</title>
    <meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/leaflet/1.3.1/leaflet.css">
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.2.1/jquery.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/leaflet/1.3.1/leaflet.js"></script>
    <style>
      body {
margin: 0;
padding: 0;
overflow: hidden;
      }
      #map {
height: 100%;
width: 100%;
      }
      #ventana {
position: absolute;
top: 100px;
left: 10px;
z-index: 1000;
      }
    </style>
  </head>
  <body>
    <div id="map"></div>
    <script>
    var terremotoPunto = null;
    var map;
    $(document).ready(function() {

 map = L.map("map", {
attributionControl: false,
zoom:8,
center:[42, 2]
});

L.tileLayer('//{s}.tile.stamen.com/toner-lite/{z}/{x}/{y}.png', {
attribution: 'Map tiles by <a href="http://stamen.com">Stamen Design</a>, <a href="http://creativecommons.org/licenses/by/3.0">CC BY 3.0</a> — Map data © <a href="http://openstreetmap.org">OpenStreetMap</a> contributors, <a href="http://creativecommons.org/licenses/by-sa/2.0/">CC-BY-SA</a>',
subdomains: 'abcd',
maxZoom: 17,
minZoom: 2
}).addTo(map);


function peticionTerremotos() {
var peticion = 'http://api.geonames.org/earthquakesJSON?' +
  'north=' + map.getBounds()._northEast.lat + '&' +
  'south=' + map.getBounds()._southWest.lat + '&' +
  'east=' + map.getBounds()._northEast.lng + '&' +
  'west=' + map.getBounds()._southWest.lng + '&' +
  'maxRows=50&' +
  'username=masterupc&';
$.ajax({
    url: peticion,
    method: "GET",
    dataType: "jsonp",
    success: function(respuesta) {
      respuestaTerremotos(respuesta);

    }
  }); //fin ajax

}//fin peticion

function respuestaTerremotos(respuesta) {
if (respuesta == null) {
  return;
} else {

  if (terremotoPunto) {
    map.eachLayer(function(layer) {
      if (layer._radius) {
map.removeLayer(layer);
      }
    });
  }
  var total_terremotos = respuesta.earthquakes;
for (var i = 0; i < total_terremotos.length; i++) {
  var terremoto = total_terremotos[i];
  terremotoPunto = new L.circleMarker([terremoto.lat, terremoto.lng],
    {
      radius: parseInt(terremoto.magnitude * 2),
      fillColor: "#aa0808",
      color: "#ffffff",
      weight: 2,
      opacity: 1,
      fillOpacity: 0.8
    }
  );
  terremotoPunto.bindPopup("Mg:" + terremoto.magnitude);
  terremotoPunto.addTo(map);

}
}
      } //Fin respuesta terremotos


peticionTerremotos() ;

map.on('moveend',function(){
  peticionTerremotos() ;
});

      }); //fin document ready
    </script>
  </body>
  </html>


```


 
