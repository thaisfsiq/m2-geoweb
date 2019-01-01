<div class="container">
    <h4>Taller GuitHub </h4>
   [https://github.com]
            <img width=100 src="https://assets-cdn.github.com/images/modules/logos_page/GitHub-Logo.png">
       

    <div class="alert alert-warning">
  ##  Recursos GitHub
      > 
        * Web<br>
          <a target="_blank" href="https://github.com/">https://github.com/</a>
        </li>
        * Tutorial<br>
          <a target="_blank" href="https://guides.github.com/activities/hello-world/">https://guides.github.com/activities/hello-world/</a>
        </li>
        * Github Pages<br>
          <a target="_blank" href="https://guides.github.com/features/pages/">https://guides.github.com/features/pages/</a>
        </li>
        * Tutorial<br>
          <a target="_blank" href="http://rogerdudler.github.io/git-guide/index.es.html">http://rogerdudler.github.io/git-guide/index.es.html</a>
        </li>
        * Wikipedia<br>
          <a target="_blank" href="https://es.wikipedia.org/wiki/GitHub">https://es.wikipedia.org/wiki/GitHub</a><br>
        </li>
    </div>


    <div class="soft">
  ## Descripción GitHub es un reporsitorio de código dónde podremos subir nuestros proyectos y también hosting de una pàgina web.<br><br>
  ## Ejemplo crear web site
      > 
        * Requisitos<br> Instalar cliente GIT para windows <a target="_blank" href="https://git-scm.com/download/win">https://git-scm.com/download/win</a>
        </li>
      </ul>
      <h6>Paso 1</h6>
      > 
        * Crear usuario en: <a target="_blank" href="https://github.com/">https://github.com/</a>
        </li>
      </ul>
      <h6>Paso 2</h6>
      > 
        * Crear nuevo proyecto: <mark> Start a project </mark> o <mark> Repositories <i class="fa fa-arrow-right" aria-hidden="true"></i>New Repo </mark></li>
        * Nombre del proyecto: <mark>{nuestro id de usuario}.github.io</mark></li>
        * Público</li>
        * Con README y licencia MIT</li>
      </ul>
      <h6>Paso 3</h6>
      > 
        * Clonamos proyecto en nuestra máquina (mejor dentro espacio web): <mark> Clone or download </mark><i class="fa fa-arrow-right" aria-hidden="true"></i> <mark> Copy to clipboard </mark></li>
        * Ejemplo: <mark>https://github.com/gis-master-m2/gis-master-m2.github.io.git</mark></li>
      </ul>
      <h6>Paso 4</h6>
      > 
        * No situamos en nuestro directorio web, por exemplo <mark>/nginx/html/</mark></li>
        * Boton derecho mouse <mark>Git bash here</mark>
        <pre class="git"><code >
    git clone  https://github.com/gis-master-m2/gis-master-m2.github.io.git
      </code></pre></li>
      </ul>
      <h6>Paso 5</h6>
      > 
        * Copiamos nuestro codigo dentro de <mark>/nginx/html/gis-master-m2.github.io/</mark></li>
        * Boton derecho mouse <mark>Git Gui here</mark></li>
        * <mark>Stage Changed</mark></li>
        * Escribimos dentro Commit Message<mark>"first commit"</mark></li>
        * <mark>Commit</mark></li>
        * <mark>Push</mark></li>
      </ul>

      <h6>Lo mismo pero via consola, sería:</h6>
      > 
        * Copiamos nuestro codigo dentro de <mark>/nginx/html/gis-master-m2.github.io/</mark></li>
        * Boton derecho mouse <mark><b>Git Bash here</b></mark><pre class="git"><code >
	git add .
	git commit -m "first commit"
	git push https://{id-git}:{passwrod}@github.com/gis-master-m2/gis-master-m2.github.io.git
      </code></pre></li>
      </ul>

	  <h6>Para inicializar un repositorio localmente</h6>
	  > 
	   * Boton derecho mouse <mark><b>Git Bash here</b></mark><pre class="git"><code >
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