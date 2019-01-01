
  ### Taller GuitHub 
   [https://github.com]
<img src="https://assets-cdn.github.com/images/modules/logos_page/GitHub-Logo" width="100"> 
       

 
###  Recursos GitHub

* Web
[https://github.com/](https://github.com/)

* Tutorial
[https://guides.github.com/activities/hello-world/](https://guides.github.com/activities/hello-world/)

* Github Pages
[https://guides.github.com/features/pages/](https://guides.github.com/features/pages/)

* Tutorial
[http://rogerdudler.github.io/git-guide/index.es.html](http://rogerdudler.github.io/git-guide/index.es.html)

* Wikipedia
[https://es.wikipedia.org/wiki/GitHub](https://es.wikipedia.org/wiki/GitHub)

    


    
### Descripción GitHub es un reporsitorio de código dónde podremos subir nuestros proyectos y también hosting de una pàgina web.
### Ejemplo crear web site

* Requisitos Instalar cliente GIT para windows [https://git-scm.com/download/win](https://git-scm.com/download/win)

     
    ### Paso 1

* Crear usuario en: [https://github.com/](https://github.com/)

     
    ### Paso 2

* Crear nuevo proyecto: ** Start a project ** o ** Repositories <i class="fa fa-arrow-right" aria-hidden="true"></i>New Repo **
* Nombre del proyecto: **{nuestro id de usuario}.github.io**
* Público
* Con README y licencia MIT
     
    ### Paso 3

* Clonamos proyecto en nuestra máquina (mejor dentro espacio web): ** Clone or download **<i class="fa fa-arrow-right" aria-hidden="true"></i> ** Copy to clipboard **
* Ejemplo: **https://github.com/gis-master-m2/gis-master-m2.github.io.git**
     
    ### Paso 4

* No situamos en nuestro directorio web, por exemplo **/nginx/html/**
* Boton derecho mouse **Git bash here**
``` 
    git clone  https://github.com/gis-master-m2/gis-master-m2.github.io.git
   ```  
     
    ### Paso 5

* Copiamos nuestro codigo dentro de **/nginx/html/gis-master-m2.github.io/**
* Boton derecho mouse **Git Gui here**
* **Stage Changed**
* Escribimos dentro Commit Message**"first commit"**
* **Commit**
* **Push**
     

    ### Lo mismo pero via consola, sería:

* Copiamos nuestro codigo dentro de **/nginx/html/gis-master-m2.github.io/**
* Boton derecho mouse ****Git Bash here****
		``` 
	git add .
	git commit -m "first commit"
	git push https://{id-git}:{passwrod}@github.com/gis-master-m2/gis-master-m2.github.io.git
   ```  
     

	### Para inicializar un repositorio localmente
	  > 
	   * Boton derecho mouse ****Git Bash here****
	   
	```  
	mkdir mirepositori
	cd mirepositorio
	git init
	touch README
	git add README
	git commit -m 'first commit'
	git remote add origin https://{id-git}:{passwrod}@github.com/gis-master-m2/mirepositorio.git
	git push -u origin master
	  
	 
	  
	  
    
  