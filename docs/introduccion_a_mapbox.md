
<img src="https://c1.staticflickr.com/3/2863/33742461420_90c7cd525f_o.png" width="250"> 
       
#### Web
* [https://www.mapbox.com/](https://www.mapbox.com/)

#### Productos
* [https://www.mapbox.com/products/](https://www.mapbox.com/products/)

#### APIs
* [https://www.mapbox.com/api-documentation/](https://www.mapbox.com/api-documentation/)

#### **Página referéncia MapBox GL!!**
* [https://www.mapbox.com/mapbox-gl-js/api/](https://www.mapbox.com/mapbox-gl-js/api/)

#### GitHUB
* [https://github.com/mapbox](https://github.com/mapbox)

#### Tutoriales
* [https://www.mapbox.com/mapbox-gl-js/example/simple-map/](https://www.mapbox.com/mapbox-gl-js/example/simple-map/)
* [https://www.mapbox.com/help/tutorials/](https://www.mapbox.com/help/tutorials/)
* [https://www.mapbox.com/help/studio-manual/](https://www.mapbox.com/help/studio-manual/)
* [https://ovrdc.github.io/gis-tutorials/mapbox/](https://ovrdc.github.io/gis-tutorials/mapbox/)

#### Videos
* [https://www.youtube.com/watch?v=jrnoFU5Wkdo](https://www.youtube.com/watch?v=jrnoFU5Wkdo)
* [https://www.youtube.com/watch?v=Zn3Xx-TSrM8](https://www.youtube.com/watch?v=Zn3Xx-TSrM8)
* [https://www.youtube.com/watch?v=r6Ij_34xTD0](https://www.youtube.com/watch?v=r6Ij_34xTD0)
* [https://www.youtube.com/watch?v=YhynsA9_fPc](https://www.youtube.com/watch?v=YhynsA9_fPc)

  
### Descripción 
> MapxBox es una empresa privada que ofrece una plataforma para la publicacón de mapas. Mapbox destaca por creado de forma abierta
> MBTiles
> Vector Tiles
> MapBox GL

* MapBox Studio es una herramienta para personalizar y publicar estilos de mapa vector
* Maputnik es un editor libre (no de Mapbox) que también sirve para editar estilos de mapas vector
     
###  ¿Cómo empezar?

> Nos damos de alta en [MapBox](https://www.mapbox.com/signup/)

### MapBox Studio

### 1-Creamos nuestor propio estilo

* Entramos en MapBox.com  seleccionamos nuestro avatar `Studio` 

* Dentro de Studio tenemos tres opciones básicas

    * **Styles**: Para crear nuestros estilos pròpios
    * **Tilesets**: Para subir nuestros datos y convertirlos en Vector Tiles y/o integrarlos con nuestros estilos
    * **Dataset**: Para subir capas GeoJson que pueden ser convertidas a Tilesets

* Seleccionamos -->`Styles` --> `New style`

![alt text](img/mapbox1.png "mapbox")

* Seleccionamos un estilo como base y cambiamos colores `Customize`

![alt text](img/mapbox11.png "mapbox")

* Cambiamos nombre del estilo "Bicing"

![alt text](img/mapbox10.png "mapbox")

* Una vez hemos acabado -->`Publish your style` --> `Publish as new`

* Share, develop, and use your style -- Copiamos `Style URL` y `Access token`  

![alt text](img/mapbox12.png "mapbox")

### 2-Visualizar estilo propio con Mapbox Gl JS

MapBox tiene una libreria JavaScript llamada *MapBox GL JS* para visualizar estilos entre otras muchas otras funcionalidades

!!! warning
    <h4>
    Siempre que utilizemos algún estilo de Mapbox studio o algún servicio de Mapbox deberemos añadir nuestro Access Token
    </h4>



!!! tip "mapboxgl.Map"

        Es el constructor principal del mapa [https://docs.mapbox.com/mapbox-gl-js/api/#map](https://docs.mapbox.com/mapbox-gl-js/api/#map)

        ```javascript
            var map = new mapboxgl.Map({
                container: 'map', // container id
                style: 'mapbox://styles/mapbox/streets-v11', // stylesheet location
                center: [-74.5, 40], // starting position [lng, lat]
                zoom: 9 // starting zoom
                });
        ```

Creamos **mapbox-basico.html**

```html
<html>
<head>
    <meta charset='utf-8' />
    <title>Mapbox estilo</title>
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
        //Añadir vuestor token y vuestro estilo
        function init() {
            mapboxgl.accessToken =
                'pk.eyJ1IjoiZ2lzbWFzdGVybTIiLCJhIjoiY2plZHhubTQxMTNoYzMza3Rqa3kxYTdrOCJ9.53B1E6mKD_EQOVb2Y0-SsA';
            var map = new mapboxgl.Map({
                container: 'map',
                style: 'mapbox://styles/gismasterm2/ck4zvjxxs2b8m1cmjumqlru5i',
                center: [2.16859, 41.3954],
                zoom: 13,
                attributionControl: false
            });

        }
    </script>
</head>

<body onload="init()">
    <div id="map"></div>
</body>

</html>  

```

Podemos añadir algunos controles

```html hl_lines="33 34"
 <html>
<head>
    <meta charset='utf-8' />
    <title>Mapbox estilo</title>
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
        //Añadir vuestor token y vuestro estilo
        function init() {
            mapboxgl.accessToken =
                'pk.eyJ1IjoiZ2lzbWFzdGVybTIiLCJhIjoiY2plZHhubTQxMTNoYzMza3Rqa3kxYTdrOCJ9.53B1E6mKD_EQOVb2Y0-SsA';
            var map = new mapboxgl.Map({
                container: 'map',
                style: 'mapbox://styles/gismasterm2/ck4zvjxxs2b8m1cmjumqlru5i',
                center: [2.16859, 41.3954],
                zoom: 13,
                attributionControl: false
            });
            map.addControl(new mapboxgl.AttributionControl({compact: true}));
            map.addControl(new mapboxgl.NavigationControl());
        }
    </script>
</head>

<body onload="init()">
    <div id="map"></div>
</body>

</html>
```



### 3-Añadir una capa nueva propia a un estilo

Nos gustaria que en nuestro estilo estuvieran los carriles bici de Barcelona


[https://opendata-ajuntament.barcelona.cat/data/es/dataset/carril-bici](https://opendata-ajuntament.barcelona.cat/data/es/dataset/carril-bici)


#### Paso 1

* Descargamos en formato **GeoJson** los carriles bicicleta de barcelona en [https://opendata-ajuntament.barcelona.cat/data/es/dataset/carril-bici](https://opendata-ajuntament.barcelona.cat/data/es/dataset/carril-bici)
  

* Utilizamos QGIS para visualizar

     
#### Paso 2 -Añadimos la capa a Mapbox.com 

* Entramos en MapBox.com `Studio` --> `Tilesets` -->`New tileset` Arrastramos **CARRIL_BICI.geojson**

* Añadimos TileSet a nuestro estilo

* `Studio` --> `Styles` -->`Bicing` --> `Layers` --> `Add Layer` -->`Carril_Bici`

![alt text](img/mapbox2.png "mapbox")


* Cambiamos color

* Publicamos

* Visualizamos mapbox-basico.html  ¿Que ha pasado?

 

### 4- Visualizar nuestor propio Tileset como una capa independiente


#### Paso 1

* Descargamos las vias ciclables de Barcelona (vias que no son carriles bici pero se puede ir en bicicleta ) [https://opendata-ajuntament.barcelona.cat/data/es/dataset/bicing](https://opendata-ajuntament.barcelona.cat/data/es/dataset/bicing)

* En formato GeoJson **VIES_CICLABLES.geojson**

#### Paso 2

* Entramos en MapBox.com `Studio` --> `Tilesets` -->`New tileset` Arrastramos **VIES_CICLABLES.geojson**

*Copiamos ID y nombre de la capa

![alt text](img/mapbox22.png "mapbox")

Editamos **mapbox-basico.html** y añadimos

```html hl_lines="37 38 39 40 41 42 43 44 45 46 47 48 49 50 51 52"
<html>
<head>
    <meta charset='utf-8' />
    <title>Mapbox estilo</title>
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
        //Añadir vuestor token y vuestro estilo
        function init() {
            mapboxgl.accessToken =
                'pk.eyJ1IjoiZ2lzbWFzdGVybTIiLCJhIjoiY2plZHhubTQxMTNoYzMza3Rqa3kxYTdrOCJ9.53B1E6mKD_EQOVb2Y0-SsA';
            var map = new mapboxgl.Map({
                container: 'map',
                style: 'mapbox://styles/gismasterm2/ck4zvjxxs2b8m1cmjumqlru5i',
                center: [2.16859, 41.3954],
                zoom: 13,
                attributionControl: false
            });
            map.addControl(new mapboxgl.AttributionControl({compact: true}));
            map.addControl(new mapboxgl.NavigationControl());


            map.on('load', function () {
                map.addSource("viasciclables_source", {
                    type: "vector",
                    url: "mapbox://gismasterm2.25lhjr43" //poner mapbox://vuestro id
                }); //fin map source

                map.addLayer({
                    id: "viasciclables",
                    type: "line",
                    source: "viasciclables_source",
                    'source-layer': "VIES_CICLABLES-2smuz5", //poner vuestro titulo capa
                    paint:{
                        'line-color':"#00ff00"
                    }
                });
            });


        }
    </script>
</head>

<body onload="init()">
    <div id="map"></div>
</body>

</html>

``` 

!!! tip "Probamos cambiar estilo de las vias ciclables"
   
    [https://docs.mapbox.com/mapbox-gl-js/style-spec/#layers-line](https://docs.mapbox.com/mapbox-gl-js/style-spec/#layers-line)


!!! success "¿Subimos el ejemplo al GitHub?"
	
	```bash

		git pull
        git add .
        git commit -m "mapa base mapbox"
        git push

	```       

