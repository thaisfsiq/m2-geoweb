### Visualización con Kepler.gl

Kepler.gl desrrollada por Uber, en u  principio para uso interno, para analizar y visualizar sus propios datos.

Es una aplicación basada en web GL de alto rendimiento y agnóstica de datos para la exploración visual de conjuntos de datos de geolocalización a gran escala. Construido en la parte superior de deck.gl, kepler.gl puede representar millones de puntos que representan miles de viajes y realizar agregaciones espaciales sobre la marcha.

![alt text](img/kepler.png "Kepler GL")


### Ejercicio de visualización con Kepler.gl

!!! tip 
    Queremos ver dónde hay más accidentes

* Descargamos dataset CSV de [OpenData BCN](http://opendata-ajuntament.barcelona.cat/data/ca/dataset/accidents-tipus-gu-bcn)

* Vamos a http://kepler.gl/#/demo 


>  `Añadimos csv`

![alt text](img/step1-kepler.png "add dataset")


> `Add Layer: Type Hexbin`

> `Columns: Latitud Longuitud`

> `Color: Scale Quantize`

> `Hexagon radius 0.1`

> `Coverage 0.75`

![alt text](img/step2-kepler.png "add dataset")

!!!Info 
    Continuamos añadiendo más capas y mapas bases


Exportamos el proyecto y lo subimos a GitHub

### Creamos un embed HTML

```html
<html>

<head>
    <title>Mis mapas
    </title>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="shortcut icon" type="image/x-icon" href="favicon.ico" />
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0-beta.3/css/bootstrap.min.css"
        integrity="sha384-Zug+QiDoJOrZ5t4lssLdxGhVrurbmBWopoEl+M6BdEfwnCJZtKxi1KgxUyJq13dy" crossorigin="anonymous">
    <style>
        html {
            overflow: hidden
        }

        iframe {
            width: 100%;
            height: 600px;
        }
    </style>
</head>

<body>
    <nav class="navbar navbar-light bg-light">
        <h4>Ejemplo visualización accidentes tráfico 2017 </h4>

    </nav>
    <div class="container">

        <iframe src="https://kepler.gl/#/demo?mapUrl=https://gis-master-m2.github.io/geoweb/accidentes-kepler.json">

        </iframe>

    </div>



</body>

</html>

```
