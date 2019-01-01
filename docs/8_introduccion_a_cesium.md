 <div class="container">
    <h5>Introducción a Cesium </h5>
    <a href="https://cesiumjs.org/" target="_blank">
            <img width=100 src="https://cesiumjs.org/Cesium/Apps/Sandcastle/images/Cesium_Logo_Color_Overlay.png">
        </a>

    <div class="alert alert-warning">
      <h5>  Recursos Cesium JS</h5>
      <ul>
        <li>
          Web<br>
          <a target="_blank" href="https://cesiumjs.org/">https://cesiumjs.org/</a>
        </li>
        <li>
          API<br>
          <a target="_blank" href="https://cesiumjs.org/refdoc/">https://cesiumjs.org/refdoc/</a>
        </li>
        <li>
          Ejemplos<br>
          <a target="_blank" href="https://cesiumjs.org/Cesium/Build/Apps/Sandcastle/index.html">https://cesiumjs.org/Cesium/Build/Apps/Sandcastle/index.html</a>
        </li>
        <li>
          Definición<br>
          <a target="_blank" href="https://en.wikipedia.org/wiki/Virtual_globe">https://en.wikipedia.org/wiki/Virtual_globe</a>
        </li>
        <li>
          Tutoriales<br>

          <a target="_blank" href="http://cesiumjs.org/tutorials.html">http://cesiumjs.org/tutorials.html</a><br>
          <a target="_blank" href="http://cesiumjs.org/demos.html">http://cesiumjs.org/demos.html</a><br>
          <a target="_blank" href="http://developer.digitalglobe.com/docs/maps-api/integration-examples/maps-apicesium-js/">http://developer.digitalglobe.com/docs/maps-api/integration-examples/maps-apicesium-js/</a><br>
          <a target="_blank" href="http://cesiumjs.org/Cesium/Apps/Sandcastle/index.html">http://cesiumjs.org/Cesium/Apps/Sandcastle/index.html</a><br>

        </li>
        <li>
          Videos<br>
          <a target="_blank" href="https://www.youtube.com/watch?v=ELYsCn-caXY">https://www.youtube.com/watch?v=ELYsCn-caXY</a><br>
          <a target="_blank" href="https://www.youtube.com/watch?v=YZ_2T6dgSw4">https://www.youtube.com/watch?v=YZ_2T6dgSw4</a><br>
          <a target="_blank" href="https://www.youtube.com/watch?v=S745qetDaCc">https://www.youtube.com/watch?v=S745qetDaCc</a><br>
          <a target="_blank" href="https://www.youtube.com/watch?v=lhzYRnNYmwo">https://www.youtube.com/watch?v=lhzYRnNYmwo</a>
        </li>
      </ul>
    </div>

    <div class="soft">
      <h5>Descripción</h5> Cesium JS ees una libreria basada en WebGL, creada por la empresa AGI, que permite trabajar con globos virtuales 3D: Cesium destaca por haber creado de forma abierta
      <ul>
        <li> Formato GLTF</li>
        <li> Especificación 3D Vector-Tiles</li>
      </ul>

      <h5> ¿Cómo empezar?</h5> Cesium no tiene un CDN.
      <p>descargamos Cesium <a target="_blank" href="https://cesiumjs.org/downloads">https://cesiumjs.org/downloads</a></p>
      <p>Descomprimir zip y extraer dentro del directorio web /build/cesium
      <ul>
        <li> Creamos
          <b>Cesium1.html</b> dentro directorio web<br> Ejemplo básico :
          <li>

            <pre><code class="prettyprint">
          &#x3C;html lang="es"&#x3E;
          &#x3C;head&#x3E;
          	&#x3C;title&#x3E;Ejemplo 0 Cesium básico&#x3C;/title&#x3E;
          	&#x3C;meta charset="utf-8" /&#x3E;
          	&#x3C;meta name="viewport" content="width=device-width, initial-scale=1.0"&#x3E;
          	&#x3C;meta name="author" content="autor" /&#x3E;
          	&#x3C;meta name="description" content="descripción página"&#x3E;
          	&#x3C;meta name="robots" content="index,follow"&#x3E;
          	&#x3C;link rel="stylesheet" href="Cesium/Widgets/widgets.css" /&#x3E;
          	&#x3C;script src="Cesium/Cesium.js"&#x3E;&#x3C;/script&#x3E;
          	&#x3C;script src="https://ajax.googleapis.com/ajax/libs/jquery/3.2.1/jquery.min.js"&#x3E;&#x3C;/script&#x3E;
          	&#x3C;style&#x3E;
          		#map {
          			position: absolute;
          			top: 0;
          			left: 0;
          			height: 100%;
          			width: 100%;
          			margin: 0;
          			overflow: hidden;
          			padding: 0;
          		}

          		body {
          			padding: 0;
          			margin: 0;
          			overflow: hidden;
          			height: 100%;
          		}
          	&#x3C;/style&#x3E;

          	&#x3C;script&#x3E;
          		$(document).ready(function() {
          			map = new Cesium.Viewer('map');

          			//add Properties

          			/*
           map.camera.flyTo({
              destination : Cesium.Cartesian3.fromDegrees( 2.1806,41.4003, 15000)
          });

           */
          		});
          	&#x3C;/script&#x3E;
          &#x3C;/head&#x3E;
          &#x3C;body&#x3E;
          &#x3C;div id="map"&#x3E;&#x3C;/div&#x3E;
          &#x3C;/body&#x3E;
          &#x3C;/html&#x3E;

        </code></pre>
          </li>
          <li>
            <h5>Ejemplo 2 Personalizado <b>Cesium2.html</b></h5>
            <pre><code class="prettyprint">
              &#x3C;html lang="es"&#x3E;
               &#x3C;head&#x3E;
                 &#x3C;title&#x3E;Ejemplo 2 Cesium&#x3C;/title&#x3E;
                 &#x3C;meta charset="utf-8" /&#x3E;
                 &#x3C;meta name="viewport" content="width=device-width, initial-scale=1.0"&#x3E;
                 &#x3C;meta name="author" content="autor" /&#x3E;
                 &#x3C;meta name="description" content="descripción página"&#x3E;
                 &#x3C;meta name="robots" content="index,follow"&#x3E;
                 &#x3C;link rel="stylesheet" href="Cesium/Widgets/widgets.css" /&#x3E;
                 &#x3C;script src="Cesium/Cesium.js"&#x3E;&#x3C;/script&#x3E;
                 &#x3C;script src="https://ajax.googleapis.com/ajax/libs/jquery/3.2.1/jquery.min.js"&#x3E;&#x3C;/script&#x3E;
                 &#x3C;style&#x3E;
                   #map {
                     position: absolute;
                     top: 0;
                     left: 0;
                     height: 100%;
                     width: 100%;
                     margin: 0;
                     overflow: hidden;
                     padding: 0;
                     font-family: sans-serif;
                   }
                   html {
                     height: 100%;
                   }
                   body {
                     padding: 0;
                     margin: 0;
                     overflow: hidden;
                     height: 100%;
                   }
                 &#x3C;/style&#x3E;
                 &#x3C;script&#x3E;
                   var map;
                   $(document).ready(function() {
                     map = new Cesium.Viewer('map', {

                       imageryProvider: new Cesium.ArcGisMapServerImageryProvider({
                         url: '//services.arcgisonline.com/ArcGIS/rest/services/World_Imagery/MapServer/',
                       }),

                       timeline: false,
                       navigationHelpButton: true,
                       scene3DOnly: true,
                       fullscreenButton: true,
                       baseLayerPicker: false,
                       homeButton: false,
                       infoBox: true,
                       sceneModePicker: false,
                       animation: false,
                       geocoder: false,
                       sceneMode: Cesium.SceneMode.SCENE3D,

                       terrainProvider: new Cesium.CesiumTerrainProvider({
                         url: 'https://assets.agi.com/stk-terrain/world',
                         requestWaterMask: false,
                         requestVertexNormals: true
                       })

                     });


                     map.camera.flyTo({
                       destination: Cesium.Cartesian3.fromDegrees(2.1806, 41.4003, 15000)
                     });

                   });
                 &#x3C;/script&#x3E;
               &#x3C;/head&#x3E;
               &#x3C;body&#x3E;
               &#x3C;div id="map"&#x3E;&#x3C;/div&#x3E;
               &#x3C;/body&#x3E;
               &#x3C;/html&#x3E;
           </code></pre>
          </li>
          <li>
            <h5>Ejemplo 3 Cesium y MapBox  <b>Cesium3.html</b></h5>

            <pre><code class="prettyprint">
              &#x3C;html lang="es"&#x3E;
&#x3C;head&#x3E;
  &#x3C;title&#x3E;Ejemplo 3 Cesium&#x3C;/title&#x3E;
  &#x3C;meta charset="utf-8" /&#x3E;
  &#x3C;meta name="viewport" content="width=device-width, initial-scale=1.0"&#x3E;
  &#x3C;meta name="author" content="autor" /&#x3E;
  &#x3C;meta name="description" content="descripción página"&#x3E;
  &#x3C;meta name="robots" content="index,follow"&#x3E;
  &#x3C;link rel="stylesheet" href="Cesium/Widgets/widgets.css" /&#x3E;
  &#x3C;script src="Cesium/Cesium.js"&#x3E;&#x3C;/script&#x3E;
  &#x3C;script src="https://ajax.googleapis.com/ajax/libs/jquery/3.2.1/jquery.min.js"&#x3E;&#x3C;/script&#x3E;
  &#x3C;style&#x3E;
    #map {
      position: absolute;
      top: 0;
      left: 0;
      height: 100%;
      width: 100%;
      margin: 0;
      overflow: hidden;
      padding: 0;
      font-family: sans-serif;
    }

    html {
      height: 100%;
    }

    body {
      padding: 0;
      margin: 0;
      overflow: hidden;
      height: 100%;
    }
  &#x3C;/style&#x3E;
  &#x3C;script&#x3E;
    var map;
    $(document).ready(function() {
      map = new Cesium.Viewer('map', {

              				imageryProvider: new Cesium.UrlTemplateImageryProvider({
              					url: 'https://api.mapbox.com/styles/v1/gismasterm2/cjdaf9xjd90eo2spdfzlmr2vb/tiles/256/{z}/{x}/{y}@2x?access_token=pk.eyJ1IjoiZ2lzbWFzdGVybTIiLCJhIjoiY2pjamdzbHZlMjg5YjMzbzBvMjRpazc3eSJ9.6L0nrPLbjWxZCMdBit-z8g'
              				}),


        /*
                      imageryProvider:new Cesium.MapboxImageryProvider({
                      mapId: 'mapbox.satellite',
                      accessToken: 'pk.eyJ1IjoiZ2lzbWFzdGVybTIiLCJhIjoiY2pjamdzbHZlMjg5YjMzbzBvMjRpazc3eSJ9.6L0nrPLbjWxZCMdBit-z8g'
                    }),
                    */


        timeline: false,
        navigationHelpButton: true,
        scene3DOnly: true,
        fullscreenButton: true,
        baseLayerPicker: false,
        homeButton: false,
        infoBox: true,
        sceneModePicker: false,
        animation: false,
        geocoder: false,
        sceneMode: Cesium.SceneMode.SCENE3D,
        terrainProvider: new Cesium.CesiumTerrainProvider({
          url: 'https://assets.agi.com/stk-terrain/world',
          requestWaterMask: false,
          requestVertexNormals: true
        })

      });

      map.camera.flyTo({
        destination: Cesium.Cartesian3.fromDegrees(2.1806, 41.4003, 15000)
      });

      /*

			var overlay= map.imageryLayers;

			var mapBoxTileset=overlay.addImageryProvider(new Cesium.MapboxImageryProvider({
			mapId: 'mapbox.mapbox-traffic-v1',
			accessToken: 'pk.eyJ1IjoiZ2lzbWFzdGVybTIiLCJhIjoiY2pjamdzbHZlMjg5YjMzbzBvMjRpazc3eSJ9.6L0nrPLbjWxZCMdBit-z8g'
		}));
		mapBoxTileset.alpha = 0.5;
                          */


    });
  &#x3C;/script&#x3E;
  &#x3C;/head&#x3E;
  &#x3C;body&#x3E;
  &#x3C;div id="map"&#x3E;&#x3C;/div&#x3E;
  &#x3C;/body&#x3E;
  &#x3C;/html&#x3E;

        </code></pre>

          </li>
          <li>
            <h5>Ejemplo 4 Layers  <b>Cesium4.html</b></h5>
            <p>Capas Raster: imageryLayers.addImageryProvider</p>
            <pre><code class="prettyprint">
            &#x3C;html lang="es"&#x3E;

            &#x3C;head&#x3E;
              &#x3C;title&#x3E;Ejemplo 4 Layers&#x3C;/title&#x3E;
              &#x3C;meta charset="utf-8" /&#x3E;
              &#x3C;meta name="viewport" content="width=device-width, initial-scale=1.0"&#x3E;
              &#x3C;meta name="author" content="autor" /&#x3E;
              &#x3C;meta name="description" content="descripción página"&#x3E;
              &#x3C;meta name="robots" content="index,follow"&#x3E;
              &#x3C;link rel="stylesheet" href="Cesium/Widgets/widgets.css" /&#x3E;
              &#x3C;script src="Cesium/Cesium.js"&#x3E;&#x3C;/script&#x3E;
              &#x3C;script src="https://ajax.googleapis.com/ajax/libs/jquery/3.2.1/jquery.min.js"&#x3E;&#x3C;/script&#x3E;
              &#x3C;style&#x3E;
                #map {
                  position: absolute;
                  top: 0;
                  left: 0;
                  height: 100%;
                  width: 100%;
                  margin: 0;
                  overflow: hidden;
                  padding: 0;
                  font-family: sans-serif;
                }

                html {
                  height: 100%;
                }

                body {
                  padding: 0;
                  margin: 0;
                  overflow: hidden;
                  height: 100%;
                }

                #capas {
                  position: absolute;
                  top: 10px;
                  left: 10px;
                  z-index: 1000;
                  width: auto;
                  height: auto;

                  background-color: white;
                }

                li {
                  list-style-type: none;
                }

                ul {
                  padding: 10px !important
                }
              &#x3C;/style&#x3E;
              &#x3C;script&#x3E;
                var map;
                $(document).ready(function() {
                  map = new Cesium.Viewer('map', {

                    imageryProvider: new Cesium.UrlTemplateImageryProvider({
                      url: 'https://api.mapbox.com/styles/v1/gismasterm2/cjdaf9xjd90eo2spdfzlmr2vb/tiles/256/{z}/{x}/{y}@2x?access_token=pk.eyJ1IjoiZ2lzbWFzdGVybTIiLCJhIjoiY2pjamdzbHZlMjg5YjMzbzBvMjRpazc3eSJ9.6L0nrPLbjWxZCMdBit-z8g'
                    }),


                    timeline: false,
                    navigationHelpButton: true,
                    scene3DOnly: true,
                    fullscreenButton: true,
                    baseLayerPicker: false,
                    homeButton: false,
                    infoBox: true,
                    sceneModePicker: false,
                    animation: false,
                    geocoder: false,
                    sceneMode: Cesium.SceneMode.SCENE3D,
                    terrainProvider: new Cesium.CesiumTerrainProvider({
                      url: 'https://assets.agi.com/stk-terrain/world',
                      requestWaterMask: false,
                      requestVertexNormals: true
                    })

                  });

                  map.camera.flyTo({
                    destination: Cesium.Cartesian3.fromDegrees(2.1806, 41.4003, 15000)
                  });


            /*Pas01
                  var overlay = map.imageryLayers;

                  var ortoICGC = overlay.addImageryProvider(new Cesium.createOpenStreetMapImageryProvider({
                    url: 'https://geoserveis.icgc.cat/icc_mapesmultibase/noutm/wmts/orto/GRID3857/',
                    fileExtension: 'jpeg',
                    maximumLevel: 19,
                    credit: 'Institut Cartogràfic i Geològic de Catalunya'
                  }));
                  ortoICGC.show = false;

                  var topoICGC = overlay.addImageryProvider(new Cesium.createOpenStreetMapImageryProvider({
                    url: 'https://geoserveis.icgc.cat/icc_mapesmultibase/noutm/wmts/topo/GRID3857/',
                    fileExtension: 'jpeg',
                    maximumLevel: 19,
                    credit: 'Institut Cartogràfic i Geològic de Catalunya'
                  }));
                  topoICGC.show = false;

                  var topo2ICGC = overlay.addImageryProvider(new Cesium.createOpenStreetMapImageryProvider({
                    url: 'https://tilemaps.icgc.cat/mapfactory/wmts/topo_suau/CAT3857/',
                    fileExtension: 'png',
                    maximumLevel: 19,
                    credit: 'Institut Cartogràfic i Geològic de Catalunya'
                  }));
                  topo2ICGC.show = false;

                  var orto46 = overlay.addImageryProvider(new Cesium.createOpenStreetMapImageryProvider({
                    url: 'https://tilemaps.icgc.cat/mapfactory/wmts/orto46/CAT3857/',
                    fileExtension: 'png',
                    maximumLevel: 17,
                    credit: 'Institut Cartogràfic i Geològic de Catalunya'
                  }));
                  orto46.show = false;
            */

            /*Paso2
                  $('.chk_capes').on('click', function() {
                    var layer = $(this).val();
                    var estado = $(this).prop('checked');

                    if (layer == 'ortoICGC') {
                      ortoICGC.show = estado;
                    } else if (layer == 'topoICGC') {
                      topoICGC.show = estado;

                    } else if (layer == 'topo2ICGC') {
                    topo2ICGC.show = estado;

                    } else if (layer == 'orto46') {
                      orto46.show = estado;
                    }

                  }); //fin onclick
            */


                }); //Fin ready
              &#x3C;/script&#x3E;

            &#x3C;/head&#x3E;

            &#x3C;body&#x3E;
              &#x3C;!--
              &#x3C;div id="capas"&#x3E;
                &#x3C;ul&#x3E;
                  &#x3C;li&#x3E;Capas&#x3C;/li&#x3E;
                  &#x3C;li&#x3E;
                    &#x3C;input type="checkbox" value="ortoICGC" class="chk_capes"&#x3E; ortoICGC
                  &#x3C;/li&#x3E;
                  &#x3C;li&#x3E;
                    &#x3C;input type="checkbox" value="topoICGC" class="chk_capes"&#x3E; topoICGC
                  &#x3C;/li&#x3E;
                  &#x3C;li&#x3E;
                    &#x3C;input type="checkbox" value="topo2ICGC" class="chk_capes"&#x3E; topo2ICGC
                  &#x3C;/li&#x3E;
                  &#x3C;li&#x3E;
                    &#x3C;input type="checkbox" value="orto46" class="chk_capes"&#x3E; orto46
                  &#x3C;/li&#x3E;
                &#x3C;/ul&#x3E;
              &#x3C;/div&#x3E;
            --&#x3E;
              &#x3C;div id="map"&#x3E;&#x3C;/div&#x3E;
            &#x3C;/body&#x3E;

            &#x3C;/html&#x3E;
  </code></pre>

            <h5>Ejemplo 5 Vectores  <b>Cesium5.html</b></h5>
            <p>Capas Vector: dataSources</p>
            <pre><code class="prettyprint">
              &#x3C;html lang="es"&#x3E;
              &#x3C;head&#x3E;
              	&#x3C;title&#x3E;Ejemplo 4 Cesium&#x3C;/title&#x3E;
              	&#x3C;meta charset="utf-8" /&#x3E;
              	&#x3C;meta name="viewport" content="width=device-width, initial-scale=1.0"&#x3E;
              	&#x3C;meta name="author" content="autor" /&#x3E;
              	&#x3C;meta name="description" content="descripción página"&#x3E;
              	&#x3C;meta name="robots" content="index,follow"&#x3E;
              	&#x3C;link rel="stylesheet" href="Cesium/Widgets/widgets.css" /&#x3E;
              	&#x3C;script src="Cesium/Cesium.js"&#x3E;&#x3C;/script&#x3E;
              	&#x3C;script src="https://ajax.googleapis.com/ajax/libs/jquery/3.2.1/jquery.min.js"&#x3E;&#x3C;/script&#x3E;
              	&#x3C;style&#x3E;
              		#map {
              			position: absolute;
              			top: 0;
              			left: 0;
              			height: 100%;
              			width: 100%;
              			margin: 0;
              			overflow: hidden;
              			padding: 0;
              			font-family: sans-serif;
              		}

              		html {
              			height: 100%;
              		}

              		body {
              			padding: 0;
              			margin: 0;
              			overflow: hidden;
              			height: 100%;
              		}
              	&#x3C;/style&#x3E;

              	&#x3C;script&#x3E;
              		var map, capas, GPX_lyr;

              		$(document).ready(function() {

              			map = new Cesium.Viewer('map', {

              				imageryProvider: new Cesium.ArcGisMapServerImageryProvider({
              					url: '//services.arcgisonline.com/ArcGIS/rest/services/World_Imagery/MapServer/',

              				}),

              				timeline: false,
              				navigationHelpButton: true,
              				scene3DOnly: true,
              				fullscreenButton: true,
              				baseLayerPicker: false,
              				homeButton: false,
              				infoBox: true,
              				sceneModePicker: false,
              				animation: false,
              				geocoder: false,
              				shadows: false,
              				terrainShadows: Cesium.ShadowMode.ENABLED,
              				sceneMode: Cesium.SceneMode.SCENE3D,
              				terrainProvider: new Cesium.CesiumTerrainProvider({
              					url: 'https://assets.agi.com/stk-terrain/world',
              					requestWaterMask: false,
              					requestVertexNormals: true
              				})

              			});
              			GPX_lyr = Cesium.GeoJsonDataSource.load('datos/ruta.geojson', {
              				stroke: Cesium.Color.RED,
              				strokeWidth: 3,
              				clampToGround:true
              			});

              			GPX_lyr.then(function(dataSource) {
              				map.dataSources.add(dataSource);
              				map.flyTo(dataSource);
              			});



              		});
              	&#x3C;/script&#x3E;

              &#x3C;/head&#x3E;
              &#x3C;body&#x3E;
              &#x3C;div id="map"&#x3E;&#x3C;/div&#x3E;
              &#x3C;/body&#x3E;
              &#x3C;/html&#x3E;

        </code></pre>
            <li>
              <h5>Ejemplo 6  <b>Clonamos 100 cims dentro del directorio web</b></h5>
              <pre class="git"><code>
    git clone https://github.com/geostarters/100cims.git
      </code></pre>
            </li>
            <!--end container -->
    </div>