 <div class="container">
    <h5>Introducción a Leaflet </h5>
    <a href="http://leafletjs.com/" target="_blank">
            <img width=100 src="http://leafletjs.com/docs/images/logo.png">
        </a>

    <div class="alert alert-warning">
      <h5>Lealfet Plugins</h5>
  <ul>
<li>
 Plugins<br>
  <a target="_blank" href="http://leafletjs.com/plugins.html">http://leafletjs.com/plugins.html</a>
</li>
</ul>
</div>
        <div class="soft">
            <h5>Buscador de Farmacias</h5>
            <ul>
                <li> Creamos archivos <a>farmacias.html</a></li>
                <li> Visualizamos geojson en /web/datos/farmacias.geojson</li>
                <li> Utilizaremos directaments pluguin GeoJSON AJAX <a target="_blank" href="https://calvinmetcalf.github.io/leaflet-ajax/dist/leaflet.ajax.js">https://calvinmetcalf.github.io/leaflet-ajax/dist/leaflet.ajax.js</a> </li>
                <li> Descargaremos plugin <a target="_blank" href="https://github.com/stefanocudini/leaflet-search">leaflet-Search</a> </li>
            </ul>

            <pre><code class="prettyprint">
              &#x3C;html lang="es"&#x3E;
              &#x3C;head&#x3E;
                &#x3C;title&#x3E;Farmacias&#x3C;/title&#x3E;
                &#x3C;meta charset="utf-8" /&#x3E;
                &#x3C;meta name="viewport" content="width=device-width, initial-scale=1.0"&#x3E;
                &#x3C;meta name="author" content="autor" /&#x3E;
                &#x3C;meta name="description" content="descripción página"&#x3E;
                &#x3C;meta name="robots" content="index,follow"&#x3E;
                &#x3C;link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/leaflet/0.7.7/leaflet.css" /&#x3E;
                &#x3C;script src="https://ajax.googleapis.com/ajax/libs/jquery/3.2.1/jquery.min.js"&#x3E;&#x3C;/script&#x3E;
                &#x3C;script&#x3E;
                  L_PREFER_CANVAS = true;
                &#x3C;/script&#x3E;
                &#x3C;script src="https://cdnjs.cloudflare.com/ajax/libs/leaflet/0.7.7/leaflet.js"&#x3E;&#x3C;/script&#x3E;
                &#x3C;script src="https://calvinmetcalf.github.io/leaflet-ajax/dist/leaflet.ajax.js"&#x3E;&#x3C;/script&#x3E;
              &#x3C;!--
                &#x3C;script src="js/leaflet-search.src.js"&#x3E;&#x3C;/script&#x3E;
                &#x3C;link rel="stylesheet" href="css/leaflet-search.min.css" /&#x3E;
              --&#x3E;
                &#x3C;style&#x3E;
                  body {
                    margin: 0;
                    padding: 0;
                    overflow: hidden;
                  }

                  #map {
                    height: 100%;
                    width: 100%;
                  }
                &#x3C;/style&#x3E;
                &#x3C;script&#x3E;
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
                        popupContent = "&#x3C;b&#x3E;" + feature.properties.NOM + "&#x3C;/b&#x3E;&#x3C;br&#x3E;" + feature.properties.CARRCADAST + " " + feature.properties.DOORNUM + "&#x3C;/b&#x3E;";
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
                &#x3C;/script&#x3E;
              &#x3C;/head&#x3E;
              &#x3C;body&#x3E;
                &#x3C;div id="map"&#x3E;&#x3C;/div&#x3E;
              &#x3C;/body&#x3E;
              &#x3C;/html&#x3E;

             </code></pre>
             Se usa para crear y manipular el mapa. <br>
             El mapa por defecto tiene dos controles: uno de zoom y uno de atribución.<br>

  <br><h5>Callejero</h5>
  <ul>
      <li> Creamos archivo <a>calles.html</a></li>
      <li> Descargaremos plugin <a target="_blank" href="https://github.com/MuellerMatthew/L.GeoSearch">GeoSearch</a> </li>
  </ul>

            <pre><code class="prettyprint">
              &#x3C;html lang="es"&#x3E;
  &#x3C;head&#x3E;
    &#x3C;title&#x3E;Calles&#x3C;/title&#x3E;
    &#x3C;meta charset="utf-8" /&#x3E;
    &#x3C;meta name="viewport" content="width=device-width, initial-scale=1.0"&#x3E;
    &#x3C;meta name="author" content="autor" /&#x3E;
    &#x3C;meta name="description" content="descripción página"&#x3E;
    &#x3C;meta name="robots" content="index,follow"&#x3E;
    &#x3C;link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/leaflet/0.7.7/leaflet.css" /&#x3E;
    &#x3C;script src="https://ajax.googleapis.com/ajax/libs/jquery/3.2.1/jquery.min.js"&#x3E;&#x3C;/script&#x3E;
    &#x3C;script&#x3E;
      L_PREFER_CANVAS = true;
    &#x3C;/script&#x3E;
    &#x3C;script src="https://cdnjs.cloudflare.com/ajax/libs/leaflet/0.7.7/leaflet.js"&#x3E;&#x3C;/script&#x3E;

    &#x3C;!--

    &#x3C;script src="js/l.control.geosearch.js"&#x3E;&#x3C;/script&#x3E;
    &#x3C;script src="js/l.geosearch.provider.openstreetmap.js"&#x3E;&#x3C;/script&#x3E;
    &#x3C;link rel="stylesheet" href="css/l.geosearch.css" /&#x3E;
  --&#x3E;

    &#x3C;style&#x3E;
      body {
        margin: 0;
        padding: 0;
        overflow: hidden;
      }

      #map {
        height: 100%;
        width: 100%;
      }
    &#x3C;/style&#x3E;
    &#x3C;script&#x3E;
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
      &#x3C;/script&#x3E;
      &#x3C;/head&#x3E;
      &#x3C;body&#x3E;
    &#x3C;div id="map"&#x3E;&#x3C;/div&#x3E;
    &#x3C;/body&#x3E;
    &#x3C;/html&#x3E;
        </code></pre>
        <div class="footnote">
            <h5>Leaflet + GeoNames</h5>
        </div>
            <ul>
                <li>Crearemos el archivo <b>geonames.html</b></li>

            </ul>

            <pre><code class="prettyprint">
              &#x3C;html&#x3E;
  &#x3C;head lang="es"&#x3E;
    &#x3C;title&#x3E;GeoNames&#x3C;/title&#x3E;
    &#x3C;meta http-equiv="Content-Type" content="text/html; charset=UTF-8"&#x3E;
    &#x3C;meta name="viewport" content="width=device-width, initial-scale=1"&#x3E;
    &#x3C;link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/leaflet/1.3.1/leaflet.css"&#x3E;
    &#x3C;script src="https://ajax.googleapis.com/ajax/libs/jquery/3.2.1/jquery.min.js"&#x3E;&#x3C;/script&#x3E;
    &#x3C;script src="https://cdnjs.cloudflare.com/ajax/libs/leaflet/1.3.1/leaflet.js"&#x3E;&#x3C;/script&#x3E;
    &#x3C;style&#x3E;
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
    &#x3C;/style&#x3E;
  &#x3C;/head&#x3E;
  &#x3C;body&#x3E;
    &#x3C;div id="map"&#x3E;&#x3C;/div&#x3E;
    &#x3C;script&#x3E;
    var terremotoPunto = null;
    var map;
    $(document).ready(function() {

         map = L.map("map", {
          attributionControl: false,
          zoom:8,
          center:[42, 2]
        });

        L.tileLayer('//{s}.tile.stamen.com/toner-lite/{z}/{x}/{y}.png', {
          attribution: 'Map tiles by &#x3C;a href="http://stamen.com"&#x3E;Stamen Design&#x3C;/a&#x3E;, &#x3C;a href="http://creativecommons.org/licenses/by/3.0"&#x3E;CC BY 3.0&#x3C;/a&#x3E; — Map data © &#x3C;a href="http://openstreetmap.org"&#x3E;OpenStreetMap&#x3C;/a&#x3E; contributors, &#x3C;a href="http://creativecommons.org/licenses/by-sa/2.0/"&#x3E;CC-BY-SA&#x3C;/a&#x3E;',
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
                    for (var i = 0; i &#x3C; total_terremotos.length; i++) {
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
    &#x3C;/script&#x3E;
  &#x3C;/body&#x3E;
  &#x3C;/html&#x3E;


        </code></pre>


            <!--end container -->
        </div>