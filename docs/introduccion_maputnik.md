### 3.Añadir estilos (ICGC) y capas externas (GeoJSON)

>Podemos trabajar con la libreria JS de Mapbox sin utilizar sus estilos , servicios ni app Tokens

#### OpenICGC

> Presenta estilos y bases Vector Tiles mundiales dónde fusiona datos OSM y del ICGC en un esquema de OpenMapTiles

>[https://openicgc.github.io/](https://openicgc.github.io/)

![alt text](img/openicgc1.png "OpenIcgc")

#### Mapa de carriles bici con estilo Hibrid

* Seleccionaremos el estilo Hibrid de OpenICGC
* Copiaremos el archivo [carriles bici](datos/carrils-bici.geojson) dentro de **geoweb**
* Creamos archivo **mapbox-icgc.html**

```html
<html>
<head>
    <meta charset='utf-8' />
    <title>Carriles bici BCN</title>
    <meta name='viewport' content='initial-scale=1,maximum-scale=1,user-scalable=no' />
    <script src='https://api.tiles.mapbox.com/mapbox-gl-js/v1.6.1/mapbox-gl.js'></script>
    <link href='https://api.tiles.mapbox.com/mapbox-gl-js/v1.6.1/mapbox-gl.css' rel='stylesheet' />
    <style>
        body {
            margin: 0;
            padding: 0;
        }
        #map {
            position: absolute;
            top: 0;
            bottom: 0;
            width: 100%;
            height: 100%
        }
    </style>
    <script>
        function Init() {

            mapboxgl.accessToken = '';
            var map = new mapboxgl.Map({
                container: 'map',
                style: 'https://geoserveis.icgc.cat/contextmaps/hibrid.json',
                center: [2.16859, 41.3954],
                zoom: 13,
                hash: true,
                pitch: 45,
                attributionControl: false
            });
            map.addControl(new mapboxgl.AttributionControl({
                compact: true
            }));
            map.addControl(new mapboxgl.NavigationControl());

            map.on('load', function () {
                map.addSource("carrils-bici", {
                    type: "geojson",
                    data: "datos/carrils-bici.geojson"
                }); //fin map source

                map.addLayer({
                    id: "carrils-bici-layer",
                    type: "line",
                    source: "carrils-bici",
                    layout: {
                        "line-join": "round",
                        "line-cap": "round"
                    },
                    paint: {
                        "line-color": "#FF0000",
                        "line-width": 8
                    }
                }); //fin add layers
            }); //Fin load mapa
        }
    </script>
</head>
<body onload="Init()">
    <div id='map'></div>
</body>
</html>
```

!!! note
    **Probamos**:Cambiar color carriles y estilo de fondo

!!! warning
    ### Práctica Cementrio. **Puntuable!!**

    * Creamos nuevo estilo en Mapbox.com

    * Cargamos capas [datos/constru_cementerio.geojson](datos/constru_cementerio.geojson) y [datos/cementerio.geojson](datos/cementerio.geojson)

    * Añadimos como tileset en MapxBox

    * Integramos el tileset dentro nuestro estilo creado `Menu`  `Add Tileset to Style`

    * Editamos capas

    * Creamos visor ejemplo **mapbox-cementerio.html**


### Extra: Visualizar estilo Mapbox en Leaflet

```html
  <html lang="es">

<head>
    <title>Leaflet y Mapox</title>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="author" content="autor" />
    <meta name="description" content="descripción página">
    <meta name="robots" content="index,follow">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/leaflet/1.3.0/leaflet.css" />
    <script src="https://cdnjs.cloudflare.com/ajax/libs/leaflet/1.3.0/leaflet.js"></script>
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
        var map;
        var capa1;

        function init() {
            map = L.map('map', {
                center: [41.6863, 1.8382],
                zoom: 8,
                attributionControl: false
            });
            // subtituir por vuestra layer
            capa1 = L.tileLayer(
                'https://api.mapbox.com/styles/v1/gismasterm2/cjcumodeg0i4p2rpaihqxx96w/tiles/256/{z}/{x}/{y}?access_token=pk.eyJ1IjoiZ2lzbWFzdGVybTIiLCJhIjoiY2plZHhubTQxMTNoYzMza3Rqa3kxYTdrOCJ9.53B1E6mKD_EQOVb2Y0-SsA', {
                    maxZoom: 19,
                    minZoom: 1,
                    attribution: 'Mapbox'
                });
            capa1.addTo(map);

        }
    </script>
</head>

<body onload="init()">
    <div id="map"></div>
</body>

</html>

```

### Servicio GeoNames y Leaflet
>[Geonames.org](https://www.geonames.org/) es una web que nos ofrece hasta 34 servicios geográficos 
>Nos damos de Alta en GeoNanmes
      
 * Crearemos el archivo **geonames-terremotos.html**

 

```html
 
<html>

<head lang="es">
    <title>GeoNames</title>
    <meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/leaflet/1.4.0/leaflet.css">
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.2.1/jquery.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/leaflet/1.4.0/leaflet.js"></script>
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
        $(document).ready(function () {

            map = L.map("map", {
                attributionControl: false,
                zoom: 8,
                center: [42, 2]
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
                    success: function (respuesta) {
                        respuestaTerremotos(respuesta);

                    }
                }); //fin ajax

            } //fin peticion

            function respuestaTerremotos(respuesta) {
                if (respuesta == null) {
                    return;
                } else {

                    if (terremotoPunto) {
                        map.eachLayer(function (layer) {
                            if (layer._radius) {
                                map.removeLayer(layer);
                            }
                        });
                    }
                    var total_terremotos = respuesta.earthquakes;
                    for (var i = 0; i < total_terremotos.length; i++) {
                        var terremoto = total_terremotos[i];
                        terremotoPunto = new L.circleMarker([terremoto.lat, terremoto.lng], {
                            radius: parseInt(terremoto.magnitude * 2),
                            fillColor: "#aa0808",
                            color: "#ffffff",
                            weight: 2,
                            opacity: 1,
                            fillOpacity: 0.8
                        });
                        terremotoPunto.bindPopup("Mg:" + terremoto.magnitude + "<br>" + terremoto.datetime);
                        terremotoPunto.addTo(map);

                    }
                }
            } //Fin respuesta terremotos


            peticionTerremotos();

            map.on('moveend', function () {
                peticionTerremotos();
            });

        }); //fin document ready
    </script>
</body>

</html>
```