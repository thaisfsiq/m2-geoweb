<div class="container">
    <h4>Taller GuitHub </h4>
    <a href="https://github.com/" target="_blank">
            <img width=100 src="https://assets-cdn.github.com/images/modules/logos_page/GitHub-Logo.png">
        </a>

    <div class="alert alert-warning">
      <h5> Recursos GitHub</h5>
      <ul>
        <li>Web<br>
          <a target="_blank" href="https://github.com/">https://github.com/</a>
        </li>
        <li>Tutorial<br>
          <a target="_blank" href="https://guides.github.com/activities/hello-world/">https://guides.github.com/activities/hello-world/</a>
        </li>
        <li>Github Pages<br>
          <a target="_blank" href="https://guides.github.com/features/pages/">https://guides.github.com/features/pages/</a>
        </li>
        <li>Tutorial<br>
          <a target="_blank" href="http://rogerdudler.github.io/git-guide/index.es.html">http://rogerdudler.github.io/git-guide/index.es.html</a>
        </li>
        <li>Wikipedia<br>
          <a target="_blank" href="https://es.wikipedia.org/wiki/GitHub">https://es.wikipedia.org/wiki/GitHub</a><br>
        </li>
    </div>


    <div class="soft">
      <h5>Descripción</h5> GitHub es un reporsitorio de código dónde podremos subir nuestros proyectos y también hosting de una pàgina web.<br><br>
      <h5>Ejemplo crear web site</h5>
      <ul>
        <li>Requisitos<br> Instalar cliente GIT para windows <a target="_blank" href="https://git-scm.com/download/win">https://git-scm.com/download/win</a>
        </li>
      </ul>
      <h6>Paso 1</h6>
      <ul>
        <li>Crear usuario en: <a target="_blank" href="https://github.com/">https://github.com/</a>
        </li>
      </ul>
      <h6>Paso 2</h6>
      <ul>
        <li>Crear nuevo proyecto: <mark> Start a project </mark> o <mark> Repositories <i class="fa fa-arrow-right" aria-hidden="true"></i>New Repo </mark></li>
        <li>Nombre del proyecto: <mark>{nuestro id de usuario}.github.io</mark></li>
        <li>Público</li>
        <li>Con README y licencia MIT</li>
      </ul>
      <h6>Paso 3</h6>
      <ul>
        <li>Clonamos proyecto en nuestra máquina (mejor dentro espacio web): <mark> Clone or download </mark><i class="fa fa-arrow-right" aria-hidden="true"></i> <mark> Copy to clipboard </mark></li>
        <li>Ejemplo: <mark>https://github.com/gis-master-m2/gis-master-m2.github.io.git</mark></li>
      </ul>
      <h6>Paso 4</h6>
      <ul>
        <li>No situamos en nuestro directorio web, por exemplo <mark>/nginx/html/</mark></li>
        <li>Boton derecho mouse <mark>Git bash here</mark>
        <pre class="git"><code >
    git clone  https://github.com/gis-master-m2/gis-master-m2.github.io.git
      </code></pre></li>
      </ul>
      <h6>Paso 5</h6>
      <ul>
        <li>Copiamos nuestro codigo dentro de <mark>/nginx/html/gis-master-m2.github.io/</mark></li>
        <li>Boton derecho mouse <mark>Git Gui here</mark></li>
        <li><mark>Stage Changed</mark></li>
        <li>Escribimos dentro Commit Message<mark>"first commit"</mark></li>
        <li><mark>Commit</mark></li>
        <li><mark>Push</mark></li>
      </ul>

      <h6>Lo mismo pero via consola, sería:</h6>
      <ul>
        <li>Copiamos nuestro codigo dentro de <mark>/nginx/html/gis-master-m2.github.io/</mark></li>
        <li>Boton derecho mouse <mark><b>Git Bash here</b></mark><pre class="git"><code >
	git add .
	git commit -m "first commit"
	git push https://{id-git}:{passwrod}@github.com/gis-master-m2/gis-master-m2.github.io.git
      </code></pre></li>
      </ul>

	  <h6>Para inicializar un repositorio localmente</h6>
	  <ul>
	   <li>Boton derecho mouse <mark><b>Git Bash here</b></mark><pre class="git"><code >
	mkdir mirepositori
	cd mirepositorio
	git init
	touch README
	git add README
	git commit -m 'first commit'
	git remote add origin https://{id-git}:{passwrod}@github.com/gis-master-m2/mirepositorio.git
	git push -u origin master
		</li>		  
	  </ul>
	  
	  
    </div>
  </div>