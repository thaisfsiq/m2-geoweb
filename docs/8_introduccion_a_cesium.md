
## Introducción a Cesium 
   [https://cesiumjs.org]
<img src="https://cesiumjs.org/Cesium/Apps/Sandcastle/images/Cesium_Logo_Color_Overlay" width="100"> 
       

 
### Recursos Cesium JS

* 
Web
[https://cesiumjs.org/](https://cesiumjs.org/)

* 
API
[https://cesiumjs.org/refdoc/](https://cesiumjs.org/refdoc/)

* 
Ejemplos
[https://cesiumjs.org/Cesium/Build/Apps/Sandcastle/index.html](https://cesiumjs.org/Cesium/Build/Apps/Sandcastle/index.html)

* 
Definición
[https://en.wikipedia.org/wiki/Virtual_globe](https://en.wikipedia.org/wiki/Virtual_globe)

* 
Tutoriales

[http://cesiumjs.org/tutorials.html](http://cesiumjs.org/tutorials.html)
[http://cesiumjs.org/demos.html](http://cesiumjs.org/demos.html)
[http://developer.digitalglobe.com/docs/maps-api/integration-examples/maps-apicesium-js/](http://developer.digitalglobe.com/docs/maps-api/integration-examples/maps-apicesium-js/)
[http://cesiumjs.org/Cesium/Apps/Sandcastle/index.html](http://cesiumjs.org/Cesium/Apps/Sandcastle/index.html)


* 
Videos
[https://www.youtube.com/watch?v=ELYsCn-caXY](https://www.youtube.com/watch?v=ELYsCn-caXY)
[https://www.youtube.com/watch?v=YZ_2T6dgSw4](https://www.youtube.com/watch?v=YZ_2T6dgSw4)
[https://www.youtube.com/watch?v=S745qetDaCc](https://www.youtube.com/watch?v=S745qetDaCc)
[https://www.youtube.com/watch?v=lhzYRnNYmwo](https://www.youtube.com/watch?v=lhzYRnNYmwo)

     
    

    
### Descripción Cesium JS ees una libreria basada en WebGL, creada por la empresa AGI, que permite trabajar con globos virtuales 3D: Cesium destaca por haber creado de forma abierta

*  Formato GLTF
*  Especificación 3D Vector-Tiles
     

###  ¿Cómo empezar? Cesium no tiene un CDN.
      <p>descargamos Cesium [https://cesiumjs.org/downloads](https://cesiumjs.org/downloads)</p>
      <p>Descomprimir zip y extraer dentro del directorio web /build/cesium

*  Creamos
**Cesium1.html** dentro directorio web Ejemplo básico :
* 

```html
<html lang="es">
<head>
	<title>Ejemplo 0 Cesium básico</title>
	<meta charset="utf-8" />
	<meta name="viewport" content="width=device-width, initial-scale=1.0">
	<meta name="author" content="autor" />
	<meta name="description" content="descripción página">
	<meta name="robots" content="index,follow">
	<link rel="stylesheet" href="Cesium/Widgets/widgets.css" />
	<script src="Cesium/Cesium.js"></script>
	<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.2.1/jquery.min.js"></script>
	<style>
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
	</style>

	<script>
		$(document).ready(function() {
map = new Cesium.Viewer('map');

//add Properties

/*
 map.camera.flyTo({
    destination : Cesium.Cartesian3.fromDegrees( 2.1806,41.4003, 15000)
});

 */
		});
	</script>
</head>
<body>
<div id="map"></div>
</body>
</html>

```

* 
### Ejemplo 2 Personalizado **Cesium2.html**
```html
    <html lang="es">
     <head>
       <title>Ejemplo 2 Cesium</title>
       <meta charset="utf-8" />
       <meta name="viewport" content="width=device-width, initial-scale=1.0">
       <meta name="author" content="autor" />
       <meta name="description" content="descripción página">
       <meta name="robots" content="index,follow">
       <link rel="stylesheet" href="Cesium/Widgets/widgets.css" />
       <script src="Cesium/Cesium.js"></script>
       <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.2.1/jquery.min.js"></script>
       <style>
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
       </style>
       <script>
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
       </script>
     </head>
     <body>
     <div id="map"></div>
     </body>
     </html>
``` 

* 
### Ejemplo 3 Cesium y MapBox  **Cesium3.html**

```html
    <html lang="es">
<head>
  <title>Ejemplo 3 Cesium</title>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="author" content="autor" />
  <meta name="description" content="descripción página">
  <meta name="robots" content="index,follow">
  <link rel="stylesheet" href="Cesium/Widgets/widgets.css" />
  <script src="Cesium/Cesium.js"></script>
  <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.2.1/jquery.min.js"></script>
  <style>
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
  </style>
  <script>
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
  </script>
  </head>
  <body>
  <div id="map"></div>
  </body>
  </html>

```


* 
### Ejemplo 4 Layers  **Cesium4.html**
  <p>Capas Raster: imageryLayers.addImageryProvider</p>
```html
  <html lang="es">

  <head>
    <title>Ejemplo 4 Layers</title>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="author" content="autor" />
    <meta name="description" content="descripción página">
    <meta name="robots" content="index,follow">
    <link rel="stylesheet" href="Cesium/Widgets/widgets.css" />
    <script src="Cesium/Cesium.js"></script>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.2.1/jquery.min.js"></script>
    <style>
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
    </style>
    <script>
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
    </script>

  </head>

  <body>
    <!--
    <div id="capas">
      <ul>
<li>Capas</li>
<li>
<input type="checkbox" value="ortoICGC" class="chk_capes"> ortoICGC
</li>
<li>
<input type="checkbox" value="topoICGC" class="chk_capes"> topoICGC
</li>
<li>
<input type="checkbox" value="topo2ICGC" class="chk_capes"> topo2ICGC
</li>
<li>
<input type="checkbox" value="orto46" class="chk_capes"> orto46
</li>
      
    </div>
  -->
    <div id="map"></div>
  </body>

  </html>
 ``` 

### Ejemplo 5 Vectores  **Cesium5.html**
  <p>Capas Vector: dataSources</p>
```html
    <html lang="es">
    <head>
    	<title>Ejemplo 4 Cesium</title>
    	<meta charset="utf-8" />
    	<meta name="viewport" content="width=device-width, initial-scale=1.0">
    	<meta name="author" content="autor" />
    	<meta name="description" content="descripción página">
    	<meta name="robots" content="index,follow">
    	<link rel="stylesheet" href="Cesium/Widgets/widgets.css" />
    	<script src="Cesium/Cesium.js"></script>
    	<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.2.1/jquery.min.js"></script>
    	<style>
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
    	</style>

    	<script>
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
    	</script>

    </head>
    <body>
    <div id="map"></div>
    </body>
    </html>

```
  * 
  ### Ejemplo 6  **Clonamos 100 cims dentro del directorio web**
    <pre class="git"><code>
    git clone https://github.com/geostarters/100cims.git
   ```  
  
 
    